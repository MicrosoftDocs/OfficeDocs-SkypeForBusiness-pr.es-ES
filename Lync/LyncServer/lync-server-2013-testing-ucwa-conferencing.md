---
title: 'Lync Server 2013: probar conferencias de UCWA'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing UCWA conferencing
ms:assetid: 62b3866a-0759-4b1f-99ec-5a68d6a74f00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727306(v=OCS.15)
ms:contentKeyID: 63969610
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9496b2a860f0a8272d6eb98df6a2c897aa245ec9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745400"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a>Prueba de conferencias de UCWA en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2014-11-03_


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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsUcwaConference</strong> . Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet **Test-CsUcwaConference** verifica que un par de usuarios de prueba puedan programar, unirse y, a continuación, realizar una conferencia en línea con la API Web de comunicaciones unificadas (UCWA). Para ello, el cmdlet usa el servicio de vale Web de Lync Server para autenticar los dos usuarios de prueba y registrarlos con Lync Server. A continuación, el cmdlet inicia una conferencia con las credenciales del organizador e invita al participante a unirse a la reunión. Una vez que se ha unido la reunión, el cmdlet **Test-CsUcwaConference** verifica que los usuarios puedan realizar acciones como mensajes instantáneos de Exchange y realizar grupos, desconectar la Conferencia y anular el registro de los dos usuarios de prueba. La Conferencia programada también se eliminará al finalizar la prueba.

El cmdlet **Test-CsUcwaConference** también se puede usar para determinar si los usuarios anónimos pueden unirse a conferencias en línea.

Tenga en cuenta que el cmdlet **Test-CsUcwaConference** no se debe ejecutar en un grupo de servidores de Microsoft Lync Server 2010 a menos que se haya instalado UCWA en ese grupo. Si UCWA no se ha instalado, se producirá un error en la llamada al cmdlet **Test-CsUcwaConference** .

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El comando que se muestra en el ejemplo 1 comprueba que un par de usuarios de prueba pueden participar en una conferencia de UCWA en el grupo atl-cs-001.litwareinc.com. Tenga en cuenta que este comando producirá un error si no ha predefinido un par de usuarios de prueba de la configuración de supervisión de estado para atl-cs-001.litwareinc.com.

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

Los comandos que se muestran en el ejemplo 2 prueban la capacidad de un par\\de usuarios (\\litwareinc Pilar y litwareinc kenmyer) para participar en una conferencia de UCWA. Para ello, el primer comando del ejemplo usa el cmdlet Get-Credential para crear un objeto de credencial de interfaz de línea de comandos de Windows PowerShell que contiene el nombre y la contraseña del usuario Pilar Ackerman. (Como el nombre de inicio de\\sesión, litwareinc pilar, se incluyó como parámetro, el cuadro de diálogo solicitud de credenciales de Windows PowerShell solo requiere que el administrador escriba la contraseña de la cuenta de Pilar Ackerman). El objeto de credenciales resultante se almacena en una variable llamada $cred 1. El segundo comando hace lo mismo, pero esta vez devuelve un objeto de credenciales para la cuenta Ken Myer.

Con los dos objetos de credenciales a mano, el tercer comando del ejemplo determina si los dos usuarios pueden participar en una conferencia de UCWA. Para ejecutar esta tarea, se llama al cmdlet **Test-CsUcwaConference** , junto con los siguientes parámetros: TargetFqdn (el FQDN del grupo de servidores de registrar); OrganizerSipAddress (la dirección SIP del organizador de la reunión); OrganizerCredential (el objeto de Windows PowerShell que contiene las credenciales de este mismo usuario); ParticipantSipAddress (la dirección SIP del otro usuario de prueba); y ParticipantCredential (el objeto de la interfaz de línea de comandos de Windows PowerShell que contiene las credenciales del otro usuario).

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si la Conferencia está configurada correctamente, recibirá un resultado similar a este, con la propiedad result marcada como **correcta:**

FQDN de destino: atl-cs-001.litwareinc.com

URI de destino: https://LyncTest-SE. LyncTest. SelfHost. Corp.

Microsoft.com:443/CertProv/CertProvisiongService.svc

Resultado: éxito

Latencia: 00:00:14.9862716

Mensaje de error:

Diagnóstico

Si los usuarios especificados no pueden usar la Conferencia, el resultado se mostrará como **error**y la información adicional se registrará en las propiedades de diagnóstico y errores:

ADVERTENCIA: no se pudo leer el número de puerto del registrador para el nombre completo

nombre de dominio (FQDN). Usando el número de puerto predeterminado del registrador. Excepción

System. InvalidOperationException: no se encontró ningún clúster coincidente en la topología.

en

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Prueba-CsUcwaConference: no hay ningún usuario de prueba asignado para

\[LyncTest.SelfHost.Corp.Microsoft.com\]. Comprobar la configuración del usuario de prueba.

En la línea: 1 carácter: 1

\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo: ResourceUnavailable: (:) \[Prueba-CsUcwaConference\]

, InvalidOperationException

\+FullyQualifiedErrorId: NotFoundTestUsers, Microsoft. RTC. Management. sintetizador

eticTransactions.TestUcwaConferenceCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que **Test-CsUcwaConference** podría fallar:

  - Se proporcionó un valor de parámetro incorrecto. Si se usa, los parámetros opcionales deben estar configurados correctamente o se producirá un error en la prueba. Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.

  - La capacidad de llevar a cabo una conferencia depende de la Directiva de conferencia que se haya asignado al usuario que organizó la Conferencia (en el caso del cmdlet **Test-CsUcwaConference** , que es el "remitente"). Si el organizador no puede incluir actividades de colaboración en su reunión (por ejemplo, si su Directiva de conferencia tiene la propiedad EnableDataCollaboration establecida en falso), el cmdlet **Test-CsUcwaConference** se producirá un error.

  - Este comando fallará si el servidor perimetral está mal configurado o aún no se ha implementado.

</div>

<div>

## <a name="see-also"></a>Vea también


[Test-CsASConference](https://docs.microsoft.com/powershell/module/skype/Test-CsASConference)  
[Test-CsDataConference](https://docs.microsoft.com/powershell/module/skype/Test-CsDataConference)  
[Test-CsAVConference](https://docs.microsoft.com/powershell/module/skype/Test-CsAVConference)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

