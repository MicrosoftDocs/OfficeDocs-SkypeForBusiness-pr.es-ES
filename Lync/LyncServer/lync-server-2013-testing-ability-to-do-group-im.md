---
title: 'Lync Server 2013: capacidad de pruebas para realizar conversaciones grupales'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing ability to do group IM
ms:assetid: ca5545bc-51ac-490f-b96b-917bb742ad04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743839(v=OCS.15)
ms:contentKeyID: 63969652
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c371db385b29f68aa8cc9280a901d095c43f2ac2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ability-to-do-group-im-in-lync-server-2013"></a>Capacidad de pruebas para realizar una conversación grupal en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsGroupIM. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsGroupIM&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet test-CsGroupIM verifica que los usuarios de su organización puedan realizar sesiones grupales de mensajería instantánea. Al ejecutar test-CsGroupIM, el cmdlet intenta iniciar sesión en un par de usuarios de prueba para Lync Server. Si se realiza correctamente, test-CsGroupIM crea una nueva conferencia con el primer usuario de prueba y, a continuación, invita al segundo usuario a unirse a la Conferencia. Después de un intercambio de mensajes, ambos usuarios se desconectan del sistema. Tenga en cuenta que todo esto se produce sin la intervención del usuario y sin afectar a los usuarios reales. Por ejemplo, supongamos que el sip:kenmyer@litwareinc.com de la cuenta de prueba corresponde a un usuario real que tiene una cuenta real de Lync Server. En ese caso, la prueba se realizará sin interrupciones en real Ken Myer. Por ejemplo, incluso cuando la cuenta de prueba Ken Myer cierra la sesión desde el sistema, Ken Myer la persona permanecerá conectada. Del mismo modo, los verdaderos Ken Myer no recibirán una invitación para unirse a la Conferencia. La invitación se enviará a la cuenta de prueba y la aceptará.

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El cmdlet test-CsGroupIM se puede ejecutar con un par de cuentas de prueba preconfiguradas (consulte Configurar cuentas de prueba para ejecutar pruebas de Lync Server) o las cuentas de dos usuarios que están habilitados para Lync Server. Para ejecutar esta comprobación mediante cuentas de prueba, solo tiene que especificar el FQDN del grupo de servidores de Lync que se está probando. Por ejemplo:

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com"

Para ejecutar esta comprobación con las cuentas de usuario reales, debe crear dos objetos de credenciales del shell de administración de Lync Server (objetos que contengan el nombre y la contraseña de la cuenta) de cada cuenta. Después, debe incluir esos objetos de credenciales y las direcciones SIP de las dos cuentas cuando llame a test-CsGroupIM:

    $credential1 = Get-Credential "litwareinc\kenmyer"
    $credential2 = Get-Credential "litwareinc\davidlongmire"
    Test-CsGroupIm -TargetFqdn "atl-cs-001.litwareinc.com" -SenderSipAddress "sip:kenmyer@litwareinc.com" -SenderCredential $credential1 -ReceiverSipAddress "sip:davidlongmire@litwareinc.com" -ReceiverCredential $credential2

Para obtener más información, consulte la documentación de ayuda del cmdlet [Test-CsGroupIM](https://docs.microsoft.com/powershell/module/skype/Test-CsGroupIM) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si los dos usuarios pueden completar una sesión de mensajería instantánea grupal, recibirá un resultado similar a este con la propiedad resultado marcada como **correcto:**

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: éxito

Latencia: 00:00:06.3812203

:

Diagnóstico

Si los dos usuarios no pueden completar la sesión de mensajería instantánea, el resultado se mostrará como error y la información adicional se registrará en las propiedades de error y diagnóstico:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: error

Latencia: 00:00:00

Error: 404, no se encontró

Diagnosis: ErrorCode = 4005, Source = ATL-CS-001.litwareinc.com,

Motivo = URI de destino no habilitado para SIP o no

condiciones.

Microsoft. RTC. Signaling. DiagnosticHeader

El resultado anterior indica que la prueba no se realizó correctamente porque al menos una de las cuentas de prueba no era válida, ya sea porque la cuenta no existe o porque el usuario no se ha habilitado para Lync Server. Puede comprobar si la cuenta existe y si la cuenta ha sido habilitada para nm-OCS-14-3rd ejecutando un comando similar a este:

    "Ken Myer", "David Longmire" | Get-CsUser | Select-Object SipAddress, Enabled

Si prueba-CsGroupIM da error, es posible que desee volver a ejecutar la prueba, esta vez incluido el parámetro detallado:

    Test-CsGroupIM -TargetFqdn "atl-cs-001.litwareinc.com" -Verbose

Cuando se incluye el parámetro detallado, test-CsGroupIM devolverá una cuenta paso a paso de cada acción que se probó cuando se comprobó la capacidad de los usuarios especificados para participar en una sesión de mensajería instantánea grupal. Por ejemplo, si se produce un error en la prueba y se dice que una o varias de las cuentas de usuario no son válidas, puede volver a ejecutar la prueba con el parámetro detallado y determinar qué cuenta de usuario no es válida:

Enviando solicitud de registro:

 FQDN de destino = atl-cs-001.litwareinc.com

 Dirección SIP del usuario = sip:kenmyer@litwareinc.com

 Registrar puerto = 5061

El tipo de autenticación ' IWA ' está seleccionado.

Excepción ' se denegó el inicio de sesión. Compruebe que se están usando las credenciales correctas y que la cuenta está activa.

Como puede ver, en este ejemplo, el usuario que tiene la dirección SIP sip:kenmyer@litwareinc.com no pudo iniciar sesión.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que test-CsGroupIM podría fallar:

  - Ha especificado una cuenta de usuario incorrecta. Puede comprobar que una cuenta de usuario existe ejecutando un comando similar a este:
    
        Get-CsUser "sip:kenmyer@litwareinc.com"

  - La cuenta de usuario es válida, pero la cuenta no está habilitada actualmente para Lync Server. Para comprobar que una cuenta de usuario se ha habilitado para Lync Server, ejecute un comando similar al siguiente:
    
    Get-CsUser "sip:kenmyer@litwareinc.com" | Seleccionar-objeto habilitado
    
    Si la propiedad Enabled se establece en false, significa que el usuario no está habilitado actualmente para Lync Server.

  - Es posible que el servicio de mensajería instantánea no esté disponible. Con Lync Server, puede configurar el sistema para que la mensajería instantánea no esté disponible si no se puede obtener acceso a la base de datos de archivado. Puede comprobar que al ejecutar un comando similar al siguiente:
    
        Get-CsArchivingConfiguration -Identity "atl-cs-001.litwareinc.com" | Select-Object BlockOnArchiveFailure
    
    Si BlockOnArchiveFailure se establece en true, debe determinar si la base de datos de archivado está disponible o no. Puede devolver las ubicaciones de las bases de datos de archivado con el siguiente comando:
    
        Get-CsService -ArchivingDatabase

  - Es posible que el servidor de archivado no esté disponible. Puede recuperar el FQDN de los servidores de archivado con este comando:
    
        Get-CsService -ArchivingServer
    
    Después, puede hacer ping al servidor apropiado para comprobar que está disponible. Por ejemplo:
    
        ping atl-archiving-001.litwareinc.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

