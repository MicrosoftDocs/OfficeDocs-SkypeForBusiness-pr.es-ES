---
title: 'Lync Server 2013: realizar una llamada de punto a punto de RTC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing PSTN peer to peer call
ms:assetid: 7e128eef-9ada-49b4-940f-97d7d13f1e4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690131(v=OCS.15)
ms:contentKeyID: 63969622
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 51b74697c7d6d5a037537bb036494d89264c4e75
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a>Probar la llamada RTC de par a par en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsPstnPeerToPeerCall. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet test-CsPstnPeerToPeerCall comprueba la capacidad de un par de usuarios de realizar una llamada de punto a punto a través de la puerta de enlace de la red telefónica conmutada (RTC). Al llamar a test-CsPstnPeerToPeerCall, el cmdlet primero intenta iniciar sesión en dos usuarios de prueba en Lync Server. Suponiendo que los inicios de sesión se realicen correctamente, el cmdlet tendrá el intento de usuario 1 de llamar al usuario 2 a través de la puerta de enlace RTC. Prueba-CsPstnPeerToPeerCall realizará esta llamada con el plan de marcado, la Directiva de voz y otras opciones de configuración y directivas asignadas al usuario de prueba. Si la prueba se reproduce como planeada, el cmdlet comprobará que el usuario 2 pudo contestar la llamada y, a continuación, cerrará la sesión con ambas cuentas de prueba del sistema.

Prueba-CsPstnPeerToPeerCall realiza una llamada real, una que comprueba que se puede realizar una conexión y que también transmite códigos de DTMF a través de la red para determinar si los medios se pueden enviar a través de la conexión. La llamada es respondida por el propio cmdlet, y no es necesaria la finalización manual de la llamada. (Es decir, nadie debe responder y, a continuación, colgar el teléfono al que se llamó).

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet test-CsPstnPeerToPeerCall se puede ejecutar con un par de cuentas de prueba preconfiguradas (consulte Configurar cuentas de prueba para ejecutar pruebas de Lync Server) o las cuentas de dos usuarios que están habilitados para Lync Server. Para ejecutar esta comprobación mediante cuentas de prueba, solo tiene que especificar el FQDN del grupo de servidores de Lync que se está probando. Por ejemplo:

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

Para ejecutar esta comprobación con las cuentas de usuario reales, debe crear dos objetos de credenciales de Windows PowerShell (objetos que contengan el nombre y la contraseña de la cuenta) de cada cuenta. Después, debe incluir esos objetos de credenciales y las direcciones SIP de las dos cuentas cuando llame a test-CsPstnPeerToPeerCall:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si los usuarios especificados pueden completar una llamada de punto a punto, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: éxito

Latencia: 00:00:06.8630376

:

Diagnóstico

Si los usuarios especificados no pueden completar una llamada de punto a punto, el resultado se mostrará como error y la información adicional se registrará en las propiedades de diagnóstico y errores:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:0182361

Error: 403, prohibido

Diagnosis: ErrorCode = 12001, Source = ATL-CS-001.litwareinc.com,

Motivo = la Directiva de usuario no contiene uso de la ruta telefónica

El resultado anterior indica que no se pudo realizar la prueba porque la Directiva de voz asignada a al menos uno de los usuarios especificados no incluye un uso de teléfono. (Las directivas de voz se asocian con las directivas de voz. Sin una directiva de voz y una ruta de voz correspondiente, no puede hacer llamadas a través de la RTC.)

Si prueba-CsPstnPeerToPeerCall da error, es posible que desee volver a ejecutar la prueba, esta vez incluido el parámetro detallado:

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Cuando se incluye el parámetro detallado, test-CsPstnPeerToPeerCall devolverá una cuenta paso a paso de cada acción que se probó cuando se comprobó la capacidad del usuario especificado para iniciar sesión en Lync Server. Por ejemplo, esta salida indica que hay problemas de red que impiden una conexión con la RTC:

Establecer videollamadas de audio a ' SIP: +12065551219@litwareinc.com; User = Phone '.

Se ha recibido una respuesta ' una 404 (no se encontró) de la red y se produjo un error en la operación.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que test-CsPstnPeerToPeerCall podría fallar:

  - Ha especificado una cuenta de usuario que no es válida. Puede comprobar que una cuenta de usuario existe ejecutando un comando similar a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server. Para comprobar que una cuenta de usuario está habilitada para Lync Server, ejecute un comando similar al siguiente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.

  - La Directiva de voz asignada al usuario especificado no tiene un uso de RTC válido. Puede determinar la Directiva de voz asignada a un usuario mediante un comando similar a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    Y, después, puede determinar los usos de RTC (si los hay) que se asignan a esa Directiva mediante un comando similar al siguiente, que recupera información sobre la Directiva de voz por usuario RedmondVoicePolicy:
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

