---
title: 'Lync Server 2013: prueba de la publicación y suscripción de presencia de usuario'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing user presence publishing and subscribing
ms:assetid: 27694c71-8e63-4aa4-b49f-fa06ccb81949
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743832(v=OCS.15)
ms:contentKeyID: 63969587
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b76cd47ccfe35cecf7b7e9182aeadccc37436bc5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-user-presence-publishing-and-subscribing-in-lync-server-2013"></a>Prueba de publicación de presencia de usuario y suscripción en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet test-CsPresence. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPresence&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

Test-CsPresence se usa para determinar si un par de usuarios de prueba pueden iniciar sesión en Lync Server y, a continuación, intercambiar información de presencia. Para esto, el cmdlet primero inicia la sesión de ambos usuarios en el sistema. Si los dos inicios de sesión se realizan correctamente, el primer usuario de prueba solicita recibir información de presencia del segundo usuario. El segundo usuario publica esta información y Test-CsPresence comprueba que esta se transmita correctamente al primer usuario. Después del intercambio de información de presencia, los dos usuarios de prueba se desconectan de Lync Server.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet test-CsPresence se puede ejecutar usando un par de cuentas de prueba preconfiguradas (consulte Setting up test accounts for Running Lync Server test) o las cuentas de dos usuarios que están habilitados para Lync Server. Para ejecutar esta comprobación mediante cuentas de prueba, solo tiene que especificar el FQDN del grupo de Lync Server que se está probando. Por ejemplo:

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com"

Para ejecutar esta comprobación con las cuentas de usuario reales, debe crear dos objetos de credenciales de Windows PowerShell (objetos que contienen el nombre de cuenta y la contraseña) para cada cuenta. A continuación, debe incluir dichos objetos de credenciales y las direcciones SIP de las dos cuentas cuando llame a test-CsPresence:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -PublisherSipAddress "sip:kenmyer@litwareinc.com" -PublisherCredential $credential1 -SubscriberSipAddress "sip:davidlongmire@litwareinc.com" -SubscriberCredential $credential2

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsPresence](https://docs.microsoft.com/powershell/module/skype/Test-CsPresence) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si los usuarios especificados pueden intercambiar información de presencia, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: correcto

Latencia: 00:00:06.3280315

Error

Diagnóstico

Si los dos usuarios no pueden intercambiar información de presencia, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnóstico:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:00

Error: 404, no encontrado

Diagnosis: ErrorCode = 4005, Source = ATL-CS-001.litwareinc.com

Razón = URI de destino no habilitado para SIP o no

haber.

Microsoft. RTC. Signaling. DiagnosticHeader

Por ejemplo, la salida anterior indica que se produjo un error en la prueba porque al menos una de las dos cuentas de usuario no es válida: la cuenta no existe o no se ha habilitado para Lync Server. Puede comprobar que las cuentas existen y determinar si están habilitadas para Lync Server ejecutando un comando similar al siguiente:

    "sip:kenmyer@litwareinc.com", "sip:davidlongmire@litwareinc.com" | Get-CsUser | Select-Object SipAddress, Enabled

Si test-CsPresence produce un error, es posible que desee volver a ejecutar la prueba, pero esta vez incluya el parámetro verbose:

    Test-CsPresence -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Cuando se incluye el parámetro verbose, test-CsPresence devolverá una cuenta paso a paso de cada acción que se intentó realizar cuando se comprobó la capacidad del usuario especificado para iniciar sesión en Lync Server. Por ejemplo:

Aciertos de solicitud de registro contra desconocido

La actividad "Register" se completó en "0,0345791" segundos.

Se inició la actividad ' SelfSubscribeActivity '.

Actividad ' SelfSubscribeActivity ' completada en ' 0,0041174 ' en segundos.

Se inició la actividad ' SubscribePresence '.

Actividad ' SubscribePresence ' completada en ' 0,0038764 ' en segundos.

Se inició la actividad ' PublishPresence '.

No se recibe una notificación de presencia de excepción en 25 segundos. se produjo ruing flujo de trabajo Microsoft. RTC. SyntheticTransactions. workflows. STPresenceWorkflow Execution.

El hecho de que la notificación de presencia no se haya recibido en 25 segundos podría indicar que hay problemas de red que impiden que se intercambie la información.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que test-CsPresence podría fallar:

  - Ha especificado una cuenta de usuario incorrecta. Puede comprobar si existe una cuenta de usuario mediante la ejecución de un comando similar al siguiente:
    
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

