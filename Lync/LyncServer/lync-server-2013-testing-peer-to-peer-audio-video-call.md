---
title: 'Lync Server 2013: prueba de una llamada de audio o vídeo punto a punto'
description: 'Lync Server 2013: prueba de la llamada de audio o vídeo punto a punto.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing peer to peer audio/video call
ms:assetid: 95eb3693-b866-4652-bc45-9b75fdb40b49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743835(v=OCS.15)
ms:contentKeyID: 63969627
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03bab69d926a99c091a510ce64b78dbf505d4cbc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556296"
---
# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a>Probar la llamada de audio y vídeo de punto a punto en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsP2PAV. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

Test-CsP2PAV se usa para determinar si un par de usuarios de prueba pueden participar en una conversación A/V de punto a punto. Para probar este escenario, el cmdlet se inicia al iniciar sesión en los dos usuarios en Lync Server. Suponiendo que los dos inicios de sesión se hayan realizado correctamente, el primer usuario invita al segundo usuario a unirse a una llamada de A/V. El segundo usuario acepta la llamada, se prueba la conexión entre los dos usuarios y, a continuación, finaliza la llamada y se cierra la sesión de los usuarios de prueba desde el sistema.

Test-CsP2PAV no realiza realmente una llamada A/V. La información multimedia no se intercambiará entre los usuarios de prueba. En su lugar, el cmdlet simplemente comprueba que se pueden realizar las conexiones adecuadas y que los dos usuarios pueden realizar dicha llamada.

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) .

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet Test-CsP2PAV puede ejecutarse con un par de cuentas de prueba preconfiguradas (consulte Configurar cuentas de prueba para ejecutar pruebas de Lync Server) o las cuentas de dos usuarios que están habilitados para Lync Server. Para ejecutar esta comprobación mediante cuentas de prueba, solo tiene que especificar el FQDN del grupo de Lync Server que se está probando. Por ejemplo:

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

Para ejecutar esta comprobación con las cuentas de usuario reales, debe crear dos objetos de credenciales de Lync Server (objetos que contienen el nombre de cuenta y la contraseña) para cada cuenta. A continuación, debe incluir dichos objetos de credenciales y las direcciones SIP de las dos cuentas cuando llame a test-CsP2PAV:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si los dos usuarios de prueba pueden completar una llamada a/V de punto a punto, recibirá un resultado similar al siguiente con la propiedad result marcada como **correcta:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: correcto

Latencia: 00:00:06.8630376

Error

Diagnóstico

Si los usuarios de prueba no pueden completar la llamada, el resultado se mostrará como error y la información adicional se registrará en las propiedades error y diagnosis:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:00

Error: 480, temporalmente no disponible

Diagnosis: ErrorCode = 15030, Source = ATL-CS-001. litwareinc. com, Reason = failed

para enrutar a Exchange Server

Microsoft. RTC. Signaling. DiagnosticHeader

Por ejemplo, la salida anterior indica que se produjo un error en la prueba porque no se pudo establecer contacto con el servidor de Microsoft Exchange. Este mensaje de error suele indicar un problema con la configuración de la mensajería unificada de Exchange.

Si Test-CsP2PAV da error, es posible que desee volver a ejecutar la prueba, pero esta vez incluya el parámetro verbose:

Test-CsP2PAV-TargetFqdn "atl-cs-001.litwareinc.com": detallado

Cuando se incluye el parámetro verbose, Test-CsP2PAV devolverá una cuenta paso a paso por cada acción que se intentó, ya que se comprobó la capacidad del usuario especificado para iniciar sesión en Lync Server. Por ejemplo, supongamos que la prueba ha fallado con el siguiente diagnóstico:

ErrorCode = 6003, Source = ATL-CS-001. litwareinc. com, causa = no se admite fuera de la solicitud de cuadro de diálogo

Si vuelve a ejecutar Test-CsP2PAV e incluye el parámetro verbose, obtendrá un resultado similar al siguiente:

VERBOse: Activity "Register" (registro) iniciada.

Enviando solicitud de registro:

FQDN de destino = atl-cs-011.litwareinc.com

Dirección SIP del usuario = sip:kenmyer@litwareinc.com

Puerto del registrador = 5062.

El tipo de autenticación "IWA" está seleccionado.

Una excepción ' el punto de conexión no se pudo registrar. Consulte ErrorCode por motivos específicos. ' se produjeron durante la ejecución del flujo de trabajo Microsoft. RTC. SyntheticTransactions. workflows. STP2PAVWorkflow.

Aunque es posible que no sea obvio inmediatamente, si examina el resultado con cuidado, verá que se ha especificado un puerto registrado incorrecto (puerto 5062). A su vez, esto provocaba un error en la prueba.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que Test-CsP2PAV podría producir un error:

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

