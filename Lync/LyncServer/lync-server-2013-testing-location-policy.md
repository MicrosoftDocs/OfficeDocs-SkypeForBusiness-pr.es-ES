---
title: 'Lync Server 2013: Directiva de ubicación de pruebas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing location policy
ms:assetid: 23d06fd3-31ee-4480-ba1e-d179a55b8b14
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690127(v=OCS.15)
ms:contentKeyID: 63969591
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2a954405cb8dbba842250e0545ac8661d4f3795c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745780"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-location-policy-in-lync-server-2013"></a>Probar la Directiva de ubicación en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-06-05_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Programación de verificación</p></td>
<td><p>Cada día</p></td>
</tr>
<tr class="even">
<td><p>Herramienta de prueba</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permisos necesarios</p></td>
<td><p>Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</p>
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsLocationPolicy. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet test-CsLocationPolicy verifica que se asigne una directiva de ubicación a un usuario. La Directiva de ubicación se usa para aplicar la configuración relacionada con la funcionalidad de E9-1-1 y la ubicación del cliente. La Directiva de ubicación determina si un usuario está habilitado para E9-1-1 y, si la respuesta es "sí", cuál es el comportamiento de una llamada de emergencia. Por ejemplo, puede usar la política de ubicación para definir qué número constituye una llamada de emergencia (911 en los Estados Unidos), si se debe notificar automáticamente la seguridad corporativa y cómo se debe dirigir la llamada.

Puede probar las directivas de ubicación en los usuarios o en las subredes de la red. Si ejecuta la prueba en una subred (especificando un valor para el parámetro de subred), el cmdlet intentará resolver la Directiva de ubicación de esa subred. Si no se asigna ninguna directiva de ubicación a la subred, se recuperará la Directiva de ubicación del usuario configurado. Si la Directiva de subred se recupera correctamente, la salida incluirá un valor LocationPolicyTagID que comienza con subnet-TagID. Si no se encontró una directiva de ubicación para la subred, el LocationPolicyTagID comenzará con el usuario-TagID.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet test-CsLocationPolicy se puede ejecutar mediante una cuenta de prueba preconfigurada (consulte Configurar cuentas de prueba para ejecutar pruebas de Lync Server) o la cuenta de cualquier usuario que esté habilitado para Lync Server. Para ejecutar esta comprobación mediante una cuenta de prueba, solo tiene que especificar el FQDN del grupo de servidores de Lync que se está probando. Por ejemplo:

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

Para ejecutar esta comprobación mediante una cuenta de usuario real, primero debe crear un objeto de credenciales de Windows PowerShell que contenga el nombre de la cuenta y la contraseña. Después debes incluir ese objeto de credenciales y la dirección SIP asignada a la cuenta al llamar a test-CsLocationPolicy:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si el usuario especificado tiene una directiva de ubicación válida, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta:**

EnhancedEmergencyServicesEnabled: verdadero

LocationPolicyTagID: usuario-TagID

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: éxito

Latencia: 00:00:06.8630376

:

Diagnóstico

Si no se puede encontrar una directiva de ubicación válida para el usuario especificado, el resultado se mostrará como error y la información adicional se registrará en las propiedades de diagnóstico y errores:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:00

Error: 404, no se encontró

Diagnosis: ErrorCode = 4005, Source = ATL-CS-001.litwareinc.com,

Motivo = URI de destino no habilitado para SIP o no

condiciones.

Microsoft. RTC. Signaling. DiagnosticHeader

El resultado anterior indica que se produjo un error en la prueba porque el usuario especificado no es válido: la cuenta no existe o el usuario no se ha habilitado para Lync Server. Puede comprobar la validez de una cuenta y determinar si la cuenta se ha habilitado para nm-OCS-14-3rd ejecutando un comando similar a este:

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

Si prueba-CsLocationPolicy da error, es posible que desee volver a ejecutar la prueba, esta vez incluido el parámetro detallado:

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Cuando se incluye el parámetro detallado, test-CsLocationPolicy devolverá una cuenta paso a paso de cada acción que intentó realizar al comprobar la Directiva de ubicación. Por ejemplo, este resultado indica que Lync Server no pudo iniciar sesión en el usuario de prueba, probablemente porque se proporcionó una contraseña no válida:

Enviando solicitud de registro:

FQDN de destino = atl-cs-011.litwareinc.com

Dirección SIP del usuario = sip:kenmyer@litwareinc.com

Registrar puerto = 5061

El tipo de autenticación ' IWA ' está seleccionado.

Registro de visitas contra SIP/ATL-CS-001. litwareinc. com

Actividad ' Register ' completada en ' 0,0601795 ' s.

Excepción ' se denegó el inicio de sesión. Compruebe que se están usando las credenciales correctas y que la cuenta está activa. durante el flujo de trabajo.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que test-CsLocationPolicy podría fallar:

  - Ha especificado una cuenta de usuario que no es válida. Puede comprobar que una cuenta de usuario existe ejecutando un comando similar a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server. Para comprobar que una cuenta de usuario está habilitada para Lync Server, ejecute un comando similar al siguiente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

