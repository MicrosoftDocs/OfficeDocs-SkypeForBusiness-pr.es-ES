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
ms.openlocfilehash: 8855abbb92accbae66048905869f20958e128019
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-ucwa-conferencing-in-lync-server-2013"></a>Probar conferencias de UCWA en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsUcwaConference</strong> . Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsUcwaConference&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet **Test-CsUcwaConference** comprueba que un par de usuarios de prueba puedan programar, unirse y realizar una conferencia en línea mediante la API Web de comunicaciones unificadas (UCWA). Para ello, el cmdlet usa el servicio de vale Web de Lync Server para autenticar los dos usuarios de prueba y registrarlos con Lync Server. A continuación, el cmdlet inicia una conferencia usando las credenciales de organizador e invita al participante a incorporarse a la reunión. Una vez que se ha unido la reunión, el cmdlet **Test-CsUcwaConference** comprueba que los usuarios pueden hacer cosas como mensajes instantáneos de Exchange y realizar grupos de servidores y, a continuación, desconectar la Conferencia y anular el registro de los dos usuarios de prueba. La Conferencia programada también se eliminará cuando finalice la prueba.

El cmdlet **Test-CsUcwaConference** también se puede usar para determinar si los usuarios anónimos pueden unirse a conferencias en línea.

Tenga en cuenta que el cmdlet **Test-CsUcwaConference** no debe ejecutarse en un grupo de servidores de Microsoft Lync Server 2010 a menos que se haya instalado UCWA en ese grupo. Si no se ha instalado UCWA, se producirá un error en la llamada al cmdlet **Test-CsUcwaConference** .

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

El comando que se muestra en el Ejemplo 1 comprueba que un par de usuarios de prueba pueden participar en una conferencia UCWA en el grupo atl-cs-001.litwareinc.com. Tenga en cuenta que este comando dará error si no ha predefinido un par de usuarios de prueba de configuración de seguimiento de estado en atl-cs-001.litwareinc.com.

    Test-CsUcwaConference -TargetFqdn "atl-cs-001.litwareinc.com"

Los comandos que se muestran en el ejemplo 2 prueban la capacidad de un par\\de usuarios (\\litwareinc Pilar y litwareinc kenmyer) para participar en una conferencia de UCWA. Para ello, el primer comando del ejemplo usa el cmdlet Get-Credential para crear un objeto de credencial de interfaz de línea de comandos de Windows PowerShell que contiene el nombre y la contraseña del usuario Pilar Ackerman. (Como el nombre de inicio de\\sesión, litwareinc pilar, se incluyó como parámetro, el cuadro de diálogo solicitud de credenciales de Windows PowerShell solo requiere que el administrador escriba la contraseña de la cuenta Pilar Ackerman). A continuación, el objeto de credenciales resultante se almacena en una variable llamada $cred 1. El segundo comando realiza la misma acción pero, esta vez, devuelve un objeto de credenciales de la cuenta de Ken Myer.

Con los dos objetos de credenciales a mano, el tercer comando del ejemplo determina si los dos usuarios pueden participar en una conferencia de UCWA. Para ejecutar esta tarea, se llama al cmdlet **Test-CsUcwaConference** , junto con los siguientes parámetros: TargetFqdn (el FQDN del grupo de registrador); OrganizerSipAddress (la dirección SIP del organizador de la reunión); OrganizerCredential (el objeto de Windows PowerShell que contiene las credenciales para este mismo usuario); ParticipantSipAddress (la dirección SIP del otro usuario de prueba); y ParticipantCredential (el objeto de la interfaz de línea de comandos de Windows PowerShell que contiene las credenciales del otro usuario).

    $cred1 = Get-Credential "litwareinc\pilar"
    $cred2 = Get-Credential "litwareinc\kenmyer"
    Test-CsUcwaConference -TargetFqdn atl-cs-001.litwareinc.com -OrganizerSipAddress "sip:pilar@litwareinc.com" -OrganizerCredential $cred1 -ParticipantSipAddress "sip:kenmyer@litwareinc.com" -ParticipantCredential $cred2

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si la Conferencia está configurada correctamente, recibirá una salida similar a la siguiente, con la propiedad result marcada como **correcta:**

FQDN de destino: atl-cs-001.litwareinc.com

URI de destino: https://LyncTest-SE. LyncTest. SelfHost. Corp.

Microsoft.com:443/CertProv/CertProvisiongService.svc

Resultado: correcto

Latencia: 00:00:14.9862716

Mensaje de error:

Diagnóstico

Si los usuarios especificados no pueden usar la Conferencia, el resultado se mostrará como **error**y la información adicional se registrará en las propiedades error y diagnóstico:

ADVERTENCIA: no se pudo leer el número de puerto del registrador para el certificado completo

nombre de dominio (FQDN). Se usará el número de puerto del registrador predeterminado. Excepción

System. InvalidOperationException: no se encontró ningún clúster que coincida en la topología.

Veamos

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

Test-CsUcwaConference: no hay ningún usuario de prueba asignado para

\[LyncTest.SelfHost.Corp.Microsoft.com\]. Compruebe la configuración del usuario de prueba.

En la línea: 1 carácter: 1

\+Test-CsUcwaConference-TargetFqdn "LyncTest.SelfHost.Corp.Microsoft.com"

\+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

\+CategoryInfo: ResourceUnavailable: (:) \[Test-CsUcwaConference\]

, InvalidOperationException

\+FullyQualifiedErrorId: NotFoundTestUsers, Microsoft. RTC. Management. sintetizador

eticTransactions.TestUcwaConferenceCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que **Test-CsUcwaConference** podría fallar:

  - Se ha suministrado un valor de parámetro incorrecto. Si se usa, los parámetros opcionales deben configurarse correctamente o se producirá un error en la prueba. Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.

  - La capacidad de realizar una conferencia depende de la Directiva de conferencia asignada al usuario que organizó la Conferencia (en el caso del cmdlet **Test-CsUcwaConference** , que es el "remitente"). Si el organizador no puede incluir actividades colaborativas en su reunión (por ejemplo, si su Directiva de conferencia tiene la propiedad EnableDataCollaboration establecida en false), se producirá un error en el cmdlet **Test-CsUcwaConference** .

  - Este comando producirá un error si el servidor perimetral está mal configurado o no se ha implementado todavía.

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

