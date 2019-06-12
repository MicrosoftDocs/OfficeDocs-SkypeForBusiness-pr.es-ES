---
title: 'Lync Server 2013: validación de conferencias de audio o vídeo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Validating audio/video conferences
ms:assetid: 6c8c422a-d501-42cb-820b-b002f9b2250b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720915(v=OCS.15)
ms:contentKeyID: 63969615
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0e608f0c765c4dd552645320ec947c7e8a54ac4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850157"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validating-audiovideo-conferences-in-lync-server-2013"></a>Validación de conferencias de audio o vídeo en Lync Server 2013

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
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Programación de verificación</p></td>
<td><p>Cada día</p></td>
</tr>
<tr class="odd">
<td><p>Herramienta de prueba</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="even">
<td><p>Permisos necesarios</p></td>
<td><p>Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</p>
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsAVConference. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsAVConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet test-CsAVConference comprueba si dos usuarios de prueba pueden participar en una conferencia de audio o vídeo (A/V). Cuando se ejecuta el cmdlet, los dos usuarios inician sesión en el sistema. Una vez que se hayan conectado correctamente, el primer usuario crea una conferencia a/V y, a continuación, espera a que el segundo usuario se una a la Conferencia. Después de un breve intercambio de datos, se elimina la Conferencia y se desconectan las dos pruebas de los usuarios.

Tenga en cuenta que prueba-CsAVConference no realiza una conferencia A/V real entre los dos usuarios de prueba. En su lugar, el cmdlet verifica que los dos usuarios pueden hacer todas las conexiones necesarias para llevar a cabo una conferencia.

Puede encontrar más ejemplos de este comando en [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference).

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet test-CsAVConference se puede ejecutar con un par de cuentas de prueba preconfiguradas (consulte Configurar cuentas de prueba para ejecutar pruebas de Lync Server) o las cuentas de dos usuarios que están habilitados para Lync Server. Para ejecutar esta comprobación mediante cuentas de prueba, solo tiene que especificar el FQDN del grupo de servidores de Lync que se está probando. Por ejemplo:

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com"

Para ejecutar esta comprobación con las cuentas de usuario reales, debe crear dos objetos de credenciales de Windows PowerShell (objetos que contengan el nombre y la contraseña de la cuenta) de cada cuenta. Después, debe incluir esos objetos de credenciales y las direcciones SIP de las dos cuentas cuando llaman a test-CsAVConference:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si los usuarios especificados pueden completar correctamente una conferencia A/V, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: éxito

Latencia: 00:00:02.6841765

:

Diagnóstico

Si los usuarios no pueden completar la Conferencia, el resultado se mostrará como error y la información adicional se registrará en las propiedades de diagnóstico y errores:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:00

Error: 404, no se encontró

Diagnosis: ErrorCode = 4005, Source = ATL-CS-001.litwareinc.com,

Motivo = URI de destino no habilitado para SIP o no

condiciones.

Microsoft. RTC. Signaling. DiagnosticHeader

Por ejemplo, la salida anterior indica que la prueba no se realizó correctamente porque al menos una de las dos cuentas de usuario no era válida, ya sea porque la cuenta no existe o porque la cuenta no se ha habilitado para Lync Server. Puede comprobar la existencia de las dos cuentas de prueba y si se han habilitado para Lync Server ejecutando un comando similar al siguiente:

    "sip:kenmyer@litwareinc.com","sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, enabled

Si prueba-CsAVConference da error, es posible que desee volver a ejecutar la prueba, esta vez incluido el parámetro detallado:

    Test-CsAVConference -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Cuando se incluye el parámetro detallado, test-CsAVConference devolverá una cuenta paso a paso de cada acción que se probó cuando se comprobó la capacidad de los usuarios especificados para participar en una conferencia antivirus. Por ejemplo, supongamos que la prueba falla y recibe el siguiente diagnóstico:

ErrorCode = 1008, Source = accessproxy. litwareinc. com, causa = no se puede resolver el registro SRV de DNS

Si vuelve a ejecutar la prueba con el parámetro verbose, la información devuelta incluirá una salida similar a la siguiente:

VERBOse: actividad ' Register ' iniciada.

Enviando solicitud de registro:

FQDN de destino = atl-cs-001.litwareinc.com

Dirección SIP del usuario = sip:davidlongmire@litwareinc.com

Registrar puerto = 5061.

El tipo de autenticación "de confianza" está seleccionado.

Actividad ' Register ' iniciada.

Enviando solicitud de registro:

FQDN de destino = atl-cs-001.litwareinc.com

Dirección SIP del usuario = sip:kenmyer@litwareinc.com

Registrar puerto = 5061.

El tipo de autenticación "de confianza" está seleccionado.

Excepción ' el punto de conexión no se pudo registrar. Consulte ErrorCode por razones específicas. ' durante el flujo de trabajo

La última línea de la salida indica que el usuario sip:kenmyer@litwareinc.com no se pudo registrar con Lync Server. Eso significa que debe comprobar que la dirección SIP sip:kenmyer@litwareinc.com es válida y que el usuario asociado está habilitado para Lync Server.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que test-CsAVConference podría fallar:

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

