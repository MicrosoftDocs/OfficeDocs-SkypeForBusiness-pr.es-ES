---
title: 'Lync Server 2013: probar la capacidad de un usuario para iniciar sesión en Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the ability of a user to log on to Lync Server
ms:assetid: d9cd0f9b-6ef2-4050-a4ca-263c5afa93ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743841(v=OCS.15)
ms:contentKeyID: 63969655
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fb1d0af8a5191c7e0af1ffe3319c426c116b586
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745470"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-ability-of-a-user-to-log-on-to-lync-server-2013"></a>Probar la capacidad de un usuario para iniciar sesión en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsRegistration. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsRegistration&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet test-CsRegistration le permite comprobar que los usuarios de su organización pueden iniciar sesión en Lync Server. Al ejecutar test-CsRegistration, el cmdlet intenta iniciar sesión en Lync Server en un usuario de prueba y, a continuación, si se realiza correctamente, desconecta ese usuario de prueba del sistema. Todo esto sucede sin ninguna interacción por el usuario y sin afectar a ningún usuario real. Por ejemplo, supongamos que el sip:kenmyer@litwareinc.com de la cuenta de prueba corresponde a un usuario real que tiene una cuenta real de Lync Server. En ese caso, la prueba se realizará sin interrupciones en real Ken Myer. Cuando la cuenta de prueba Ken Myer cierra la sesión en el sistema, Ken Myer permanecerá en la sesión.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet test-CsRegistration se puede ejecutar mediante una cuenta de prueba preconfigurada (consulte Configurar cuentas de prueba para ejecutar pruebas de Lync Server) o la cuenta de cualquier usuario que esté habilitado para Lync Server. Para ejecutar esta comprobación mediante una cuenta de prueba, solo tiene que especificar el FQDN del grupo de registradores de Lync Server que se está probando. Por ejemplo:

    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"

Para ejecutar esta comprobación mediante una cuenta de usuario real, primero debe crear un objeto de credenciales de Windows PowerShell que contenga el nombre de la cuenta y la contraseña. Después debes incluir ese objeto de credenciales y la dirección SIP asignada a la cuenta al llamar a test-CsRegistration:

    $credential = Get-Credential "litwareinc\kenmyer"
    Test-CsRegistration -TargetFqdn "atl-cs-001.litwareinc.com"-UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsRegistration](https://docs.microsoft.com/powershell/module/skype/Test-CsRegistration) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si el usuario especificado puede iniciar sesión en y, a continuación, cerrar sesión en Lync Server, recibirá una salida similar a la siguiente con la propiedad result marcada como **correcta:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: éxito

Latencia: 00:00:06.8630376

:

Diagnóstico

Si el usuario especificado no puede iniciar sesión ni cerrar la sesión, el resultado se mostrará como error y la información adicional se registrará en las propiedades de diagnóstico y errores:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:00

Error: 404, no se encontró

Diagnosis: ErrorCode = 1003, Source = ATL-CS-001. litwareinc. com, razón = el usuario sí

no existe

Microsoft. RTC. Signaling. DiagnosticHeader

Por ejemplo, la salida anterior indica que se produjo un error en la prueba porque no se encontró el usuario especificado. Puede determinar si una dirección SIP es válida (y si el usuario asignado a esa dirección SIP está habilitado para Lync Server) ejecutando este comando:

    Get-CsUser "sip:kenmyer@litwareinc.com"

Si prueba-CsRegistration da error, es posible que desee volver a ejecutar la prueba, esta vez incluido el parámetro detallado:

    Test-CsRegistration -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Cuando se incluye el parámetro detallado, test-CsRegistration devolverá una cuenta paso a paso de cada acción que se probó cuando se comprobó la capacidad del usuario especificado para iniciar sesión en Lync Server. Por ejemplo:

VERBOse: actividad ' Register ' iniciada.

Enviando solicitud de registro:

FQDN de destino = atl-cs-011.litwareinc.com

Dirección SIP del usuario = sip:kenmyer@litwareinc.com

Registrar puerto = 5061.

El tipo de autenticación "de confianza" está seleccionado.

Excepción ' el punto de conexión no se puede registrar. Vea el código de error de motivo específico ' durante el flujo de trabajo Microsoft. RTC. SyntheticTransactions. Workflow. STRegistrerWorkflow Execution.

Pila de llamadas de excepción: en Microsoft. RTC. SipAsyncResult'1. ThrowIfFailed ()

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que test-CsRegistration podría fallar:

  - Ha especificado una cuenta de usuario incorrecta. Puede comprobar que una cuenta de usuario existe ejecutando un comando similar a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server. Para comprobar que una cuenta de usuario está habilitada para Lync Server, ejecute un comando similar al siguiente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.

  - Ha especificado un grupo de registradores incorrecto. Puede devolver los FQDN de sus grupos de registradores con este comando:
    
        Get-CsService -Registrar | Select-Object PoolFqdn

  - El grupo de registradores no está disponible en este momento. Intente hacer ping al grupo para ver si responde:
    
        ping atl-cs-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

