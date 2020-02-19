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
ms.openlocfilehash: 8e2d08cdd1db5607b8565cd6b1cf0317b9db26de
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-location-policy-in-lync-server-2013"></a>Directiva de ubicación de pruebas en Lync Server 2013

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
<td><p>Programación de comprobación</p></td>
<td><p>Diario</p></td>
</tr>
<tr class="even">
<td><p>Herramienta de prueba</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permisos necesarios</p></td>
<td><p>Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</p>
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsLocationPolicy. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLocationPolicy&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet test-CsLocationPolicy comprueba que una directiva de ubicación está asignada a un usuario. La Directiva de ubicación se usa para aplicar la configuración relacionada con la funcionalidad de E9-1-1 y la ubicación del cliente. La Directiva de ubicación determina si un usuario está habilitado para E9-1-1 y, si la respuesta es "sí", cuál es el comportamiento de una llamada de emergencia. Por ejemplo, puede usar la Directiva de ubicación para definir el número que constituye una llamada de emergencia (911 en Estados Unidos), si se debe notificar automáticamente a la seguridad corporativa y cómo se debe enrutar la llamada.

Puede probar directivas de ubicación en usuarios o subredes. Si ejecuta la prueba en una subred (mediante la especificación de un valor para el parámetro Subnet), el cmdlet intentará resolver la directiva de ubicación para esa subred. Si no se asigna ninguna directiva de ubicación a la subred, se recuperará la directiva de ubicación para el usuario configurado. Si la Directiva de subred se recupera correctamente, el resultado incluirá un valor de LocationPolicyTagID que empieza con subnet-TagID. Si no se encontró una directiva de ubicación para la subred, LocationPolicyTagID comenzará con el Id. de etiqueta del usuario.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet test-CsLocationPolicy se puede ejecutar con una cuenta de prueba preconfigurada (consulte la configuración de las cuentas de prueba para ejecutar pruebas de Lync Server) o en la cuenta de cualquier usuario que esté habilitado para Lync Server. Para ejecutar esta comprobación con una cuenta de prueba, solo tiene que especificar el FQDN del grupo de Lync Server que se está probando. Por ejemplo:

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"

Para ejecutar esta comprobación con una cuenta de usuario real, primero debe crear un objeto de credenciales de Windows PowerShell que contenga el nombre y la contraseña de la cuenta. A continuación, debe incluir ese objeto Credentials y la dirección SIP asignada a la cuenta al llamar a test-CsLocationPolicy:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Test-CsLocationPolicy) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si el usuario especificado tiene una directiva de ubicación válida, recibirá un resultado similar al siguiente, con la propiedad result marcada como **correcta:**

EnhancedEmergencyServicesEnabled: true

LocationPolicyTagID: usuario-TagID

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: correcto

Latencia: 00:00:06.8630376

Error

Diagnóstico

Si no se encuentra una directiva de ubicación válida para el usuario especificado, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnóstico:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:00

Error: 404, no encontrado

Diagnosis: ErrorCode = 4005, Source = ATL-CS-001.litwareinc.com

Razón = URI de destino no habilitado para SIP o no

haber.

Microsoft. RTC. Signaling. DiagnosticHeader

La salida anterior indica que se produjo un error en la prueba porque el usuario especificado no es válido: la cuenta no existe o el usuario no se ha habilitado para Lync Server. Puede comprobar la validez de una cuenta y determinar si la cuenta se ha habilitado para nm-OCS-14-3rd mediante la ejecución de un comando similar al siguiente:

    Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object SipAddress, Enabled

Si test-CsLocationPolicy produce un error, es posible que desee volver a ejecutar la prueba, pero esta vez incluya el parámetro verbose:

    Test-CsLocationPolicy -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Cuando se incluye el parámetro verbose, test-CsLocationPolicy devolverá una cuenta paso a paso de cada acción que intentó realizar la comprobación de la Directiva de ubicación. Por ejemplo, este resultado indica que Lync Server no pudo iniciar sesión en el usuario de prueba, probablemente debido a que se ha proporcionado una contraseña no válida:

Enviando solicitud de registro:

FQDN de destino = atl-cs-011.litwareinc.com

Dirección SIP del usuario = sip:kenmyer@litwareinc.com

Puerto del registrador = 5061

El tipo de autenticación "IWA" está seleccionado.

Aciertos de registro en SIP/ATL-CS-001. litwareinc. com

La actividad "Register" se completó en "0,0601795" segundos.

Excepción: "se denegó el inicio de sesión. Compruebe que se usan las credenciales correctas y que la cuenta está activa. se produjo durante el flujo de trabajo.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que test-CsLocationPolicy podría fallar:

  - Ha especificado una cuenta de usuario que no es válida. Puede comprobar si existe una cuenta de usuario mediante la ejecución de un comando similar al siguiente:
    
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

