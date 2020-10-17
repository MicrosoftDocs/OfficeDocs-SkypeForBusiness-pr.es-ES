---
title: 'Lync Server 2013: realizar una llamada de punto a punto de RTC'
description: 'Lync Server 2013: realizar una llamada de punto a punto de RTC.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing PSTN peer to peer call
ms:assetid: 7e128eef-9ada-49b4-940f-97d7d13f1e4a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690131(v=OCS.15)
ms:contentKeyID: 63969622
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bf8726c46374e3a799b986e071566d0ae1de138
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552686"
---
# <a name="testing-pstn-peer-to-peer-call-in-lync-server-2013"></a>Probar la llamada RTC de punto a punto en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsPstnPeerToPeerCall. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsPstnPeerToPeerCall&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet Test-CsPstnPeerToPeerCall comprueba la capacidad de un par de usuarios de realizar una llamada punto a punto a través de la puerta de enlace de la red telefónica conmutada (RTC). Cuando se llama a test-CsPstnPeerToPeerCall, el cmdlet intenta primero iniciar sesión en dos usuarios de prueba en Lync Server. Suponiendo que los inicios de sesión se realizan correctamente, el cmdlet tendrá un intento del usuario 1 de llamar al usuario 2 a través de la puerta de enlace RTC. Test-CsPstnPeerToPeerCall hará esta llamada con el plan de marcado, la Directiva de voz y otras opciones de configuración y directivas asignadas al usuario de prueba. Si la prueba se realiza como planeada, el cmdlet comprobará que el usuario 2 pudo responder a la llamada y, a continuación, cierra sesión ambas cuentas de prueba desde el sistema.

Test-CsPstnPeerToPeerCall realiza una llamada de teléfono real, una que comprueba que se puede realizar una conexión y que también transmite códigos DTMF a través de la red para determinar si se pueden enviar medios a través de la conexión. La llamada la responde el propio cmdlet, y no es necesaria una finalización manual de la llamada. (Es decir, nadie debe contestar y, a continuación, colgar el teléfono al que se llamó).

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet Test-CsPstnPeerToPeerCall puede ejecutarse con un par de cuentas de prueba preconfiguradas (consulte Configurar cuentas de prueba para ejecutar pruebas de Lync Server) o las cuentas de dos usuarios que están habilitados para Lync Server. Para ejecutar esta comprobación mediante cuentas de prueba, solo tiene que especificar el FQDN del grupo de Lync Server que se está probando. Por ejemplo:

`Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com"`

Para ejecutar esta comprobación con las cuentas de usuario reales, debe crear dos objetos de credenciales de Windows PowerShell (objetos que contienen el nombre de cuenta y la contraseña) para cada cuenta. A continuación, debe incluir dichos objetos de credenciales y las direcciones SIP de las dos cuentas cuando llame a test-CsPstnPeerToPeerCall:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsPstnPeerToPeerCall](https://docs.microsoft.com/powershell/module/skype/Test-CsPstnPeerToPeerCall) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si los usuarios especificados pueden completar una llamada punto a punto, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: correcto

Latencia: 00:00:06.8630376

Error

Diagnóstico

Si los usuarios especificados no pueden completar una llamada punto a punto, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnosis:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:0182361

Error: 403, prohibido

Diagnosis: ErrorCode = 12001, Source = ATL-CS-001.litwareinc.com

Razón = la Directiva de usuario no contiene uso de ruta telefónica

La salida anterior indica que la prueba produjo un error porque la Directiva de voz asignada a al menos uno de los usuarios especificados no incluye un uso de teléfono. (Los usos de teléfono unen las directivas de voz a las rutas de voz. Sin una directiva de voz y una ruta de voz correspondiente, no se pueden realizar llamadas a través de la RTC.)

Si Test-CsPstnPeerToPeerCall da error, es posible que desee volver a ejecutar la prueba, pero esta vez incluya el parámetro verbose:

    Test-CsPstnPeerToPeerCall -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Cuando se incluye el parámetro verbose, Test-CsPstnPeerToPeerCall devolverá una cuenta paso a paso por cada acción que se intentó realizar cuando se comprobó la capacidad del usuario especificado para iniciar sesión en Lync Server. Por ejemplo, este resultado indica que hay problemas de red que impiden la conexión con la RTC:

Establecimiento de una llamada de audio en vídeo a ' SIP: + 12065551219@litwareinc. com; User = Phone '.

Se ha recibido una respuesta de excepción de 404 (no se encontró) desde la red y se ha producido un error en la operación.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que Test-CsPstnPeerToPeerCall podría producir un error:

  - Ha especificado una cuenta de usuario que no es válida. Puede comprobar si existe una cuenta de usuario mediante la ejecución de un comando similar al siguiente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server. Para comprobar que una cuenta de usuario está habilitada para Lync Server, ejecute un comando similar al siguiente:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object Enabled
    
    Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.

  - La Directiva de voz asignada al usuario especificado no tiene un uso de RTC válido. Puede determinar la Directiva de voz que se asigna a un usuario mediante un comando similar a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com" | Select-Object VoicePolicy
    
    A continuación, puede determinar los usos de RTC (si los hay) asignados a esa Directiva mediante un comando similar al siguiente, que recupera información sobre la Directiva de voz por usuario RedmondVoicePolicy:
    
        Get-CsVoicePolicy -Identity "RedmondVoicePolicy"

</div>

</div>

<span> </span>

</div>

</div>

</div>

