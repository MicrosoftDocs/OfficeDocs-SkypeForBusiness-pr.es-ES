---
title: 'Lync Server 2013: realizar una llamada de audio o vídeo de par a par'
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
ms.openlocfilehash: e319ace4ee4cc6613ac5ed29659ac14c5853d7b5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745640"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-peer-to-peer-audiovideo-call-in-lync-server-2013"></a>Prueba de las videollamadas de par a par en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsP2PAV. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsP2PAV&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

Prueba-CsP2PAV se usa para determinar si un par de usuarios de prueba pueden participar en una conversación A/V de punto a punto. Para probar este escenario, el cmdlet se inicia al iniciar sesión en los dos usuarios en Lync Server. Suponiendo que los dos inicios de sesión se realicen correctamente, el primero invita al segundo usuario a unirse a una llamada de A/V. El segundo usuario acepta la llamada, se prueba la conexión entre los dos usuarios y, a continuación, finaliza la llamada y se cerrará la sesión de los usuarios de prueba en el sistema.

Test-CsP2PAV realmente no realiza una llamada A/V. La información multimedia no se cambia entre los usuarios de prueba. En su lugar, el cmdlet simplemente comprueba que se pueden realizar las conexiones apropiadas y que los dos usuarios pueden realizar dicha llamada.

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsP2PAV](https://docs.microsoft.com/powershell/module/skype/Test-CsP2PAV) .

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet test-CsP2PAV se puede ejecutar con un par de cuentas de prueba preconfiguradas (consulte Configurar cuentas de prueba para ejecutar pruebas de Lync Server) o las cuentas de dos usuarios que están habilitados para Lync Server. Para ejecutar esta comprobación mediante cuentas de prueba, solo tiene que especificar el FQDN del grupo de servidores de Lync que se está probando. Por ejemplo:

    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com"

Para ejecutar esta comprobación con las cuentas de usuario reales, debe crear dos objetos de credenciales de Lync Server (objetos que contengan el nombre y la contraseña de la cuenta) de cada cuenta. Después, debe incluir esos objetos de credenciales y las direcciones SIP de las dos cuentas cuando llame a test-CsP2PAV:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsP2PAV -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si los dos usuarios de prueba pueden completar una llamada de punto a punto a/V, recibirá un resultado similar a este con la propiedad resultado marcada como **correcto:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: éxito

Latencia: 00:00:06.8630376

:

Diagnóstico

Si los usuarios de prueba no pueden completar la llamada, el resultado se mostrará como error y la información adicional se registrará en las propiedades de diagnóstico y errores:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:00

Error: 480, no disponible temporalmente

Diagnosis: ErrorCode = 15030, Source = ATL-CS-001. litwareinc. com, causa = error

para enrutar a Exchange Server

Microsoft. RTC. Signaling. DiagnosticHeader

Por ejemplo, la salida anterior indica que se produjo un error en la prueba porque no se pudo establecer contacto con el servidor de Microsoft Exchange. Este mensaje de error suele indicar un problema con la configuración de la mensajería unificada de Exchange.

Si prueba-CsP2PAV da error, es posible que desee volver a ejecutar la prueba, esta vez incluido el parámetro detallado:

Prueba-CsP2PAV-TargetFqdn "atl-cs-001.litwareinc.com": detallado

Cuando se incluye el parámetro detallado, test-CsP2PAV devolverá una cuenta paso a paso de cada acción que ha probado, ya que el usuario especificado puede iniciar sesión en Lync Server. Por ejemplo, supongamos que la prueba falló con el siguiente diagnóstico:

ErrorCode = 6003, Source = ATL-CS-001. litwareinc. com, causa = no se admiten las solicitudes de cuadro de diálogo.

Si vuelve a ejecutar test-CsP2PAV e incluye el parámetro verbose, obtendrá un resultado similar a este:

VERBOse: actividad ' Register ' iniciada.

Enviando solicitud de registro:

FQDN de destino = atl-cs-011.litwareinc.com

Dirección SIP del usuario = sip:kenmyer@litwareinc.com

Registrar puerto = 5062.

El tipo de autenticación ' IWA ' está seleccionado.

Excepción ' el punto de conexión no se pudo registrar. Consulte ErrorCode por razones específicas. ' durante el flujo de trabajo, Microsoft. RTC. SyntheticTransactions. workflows. STP2PAVWorkflow Execution.

Aunque es posible que no sea evidente de inmediato, si examina la salida detenidamente verá que se especificó un puerto de registro incorrecto (puerto 5062). A su vez, esto causaba un error en la prueba.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que test-CsP2PAV podría fallar:

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

