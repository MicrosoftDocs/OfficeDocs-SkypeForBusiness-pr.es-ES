---
title: 'Lync Server 2013: probar el programador web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing the Web scheduler
ms:assetid: 58e34058-1afa-42e3-9096-c4ea1954c237
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn727304(v=OCS.15)
ms:contentKeyID: 63969603
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8bc3d93e1e4a08575119031471863dad817f3e80
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-the-web-scheduler-in-lync-server-2013"></a>Probar el programador web en Lync Server 2013

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
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet <strong>Test-CsWebScheduler</strong> . Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsWebScheduler&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El cmdlet **Test-CsWebScheduler** permite determinar si un usuario específico puede programar una reunión con el programador web. El programador web permite a los usuarios que no ejecutan Outlook programar reuniones en línea. Entre otras cosas, esta nueva característica (que incorpora la funcionalidad que se encuentra en la herramienta de programador web incluida en el kit de recursos de Microsoft Lync Server 2010) permite a los usuarios:

  - Programar una nueva reunión en línea.

  - Enumerar todas las reuniones que él o ella ha programado.

  - Ver o modificar una reunión existente.

  - Eliminar una reunión existente.

  - Enviar una invitación por correo electrónico a los participantes en la reunión mediante un servidor de correo SMTP configurado previamente.

  - Unirse a una llamada de conferencia existente.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

En el siguiente ejemplo se comprueba el programador web del grupo atl-cs-001.litwareinc.com. Este comando funcionará solo si los usuarios de prueba están definidos para el grupo atl-cs-001.litwareinc.com. Si lo tienen, el comando determinará si el primer usuario de prueba puede programar una reunión en línea mediante el programador web.

Si no se definen los usuarios de prueba, se producirá un error en el comando porque no sabrá en qué usuario se inicia sesión. Si no ha definido usuarios de prueba para un grupo de servidores, debe incluir el parámetro UserSipAddress y las credenciales del usuario que el comando debe usar al intentar iniciar sesión.

    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com"

Los comandos que se muestran en el siguiente ejemplo prueban la capacidad de un usuario\\específico (litwareinc kenmeyer) para programar una reunión en línea mediante el programador web. Para ello, el primer comando del ejemplo usa el cmdlet **Get-Credential** para crear un objeto de credencial de interfaz de línea de comandos de Windows PowerShell que contiene el nombre y la contraseña del usuario Ken Meyer. (Como el nombre de inicio\\de sesión litwareinc kenmeyer se incluye como un parámetro, el cuadro de diálogo solicitud de credenciales de Windows PowerShell solo requiere que el administrador escriba la contraseña de la cuenta Ken Meyer). El objeto Credential resultante se almacena en una variable llamada $cred 1.

A continuación, el segundo comando comprueba si este usuario puede iniciar sesión en el grupo atl-cs-001.litwareinc.com y programar una reunión en línea. Para ejecutar esta tarea, se llama al cmdlet **Test-CsWebScheduler** , junto con tres parámetros: TargetFqdn (el FQDN del grupo de registrador); UserCredential (el objeto de Windows PowerShell que contiene las credenciales de usuario de Pilar Ackerman); y UserSipAddress (la dirección SIP que corresponde a las credenciales de usuario suministradas).

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsWebScheduler -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si el programador web está configurado correctamente, recibirá un resultado similar al siguiente, con la propiedad result marcada como **correcta**:

FQDN de destino: atl-cs-001.litwareinc.com

URI de destino: https://atl-cs-001.litwareinc.com.

litwareinc.com:443/Scheduler

Resultado: correcto

Latencia: 00:00:00

Mensaje de error:

Diagnóstico

Si el programador web no está configurado correctamente, el resultado se mostrará como **error**y la información adicional se registrará en las propiedades error y diagnosis:

ADVERTENCIA: no se pudo leer el número de puerto del registrador para el certificado completo

nombre de dominio (FQDN). Se usará el número de puerto del registrador predeterminado. Excepción

System. InvalidOperationException: no se encontró ningún clúster que coincida en la topología.

Veamos

Microsoft. RTC. Management. SyntheticTransactions. SipSyntheticTransaction. TryRetri

eveRegistrarPortFromTopology (Int32& registrarPortNumber)

FQDN de destino: atl-cs-001.litwareinc.com

URI de destino:

Resultado: error

Latencia: 00:00:00

Mensaje de error: no se encontró ningún clúster que coincida en la topología.

Diagnóstico

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Estas son algunas de las razones comunes por las que **Test-CsWebScheduler** podría fallar:

  - Se ha suministrado un valor de parámetro incorrecto. Si se usa, los parámetros opcionales deben configurarse correctamente o se producirá un error en la prueba. Vuelva a ejecutar el comando sin los parámetros opcionales y vea si se realiza correctamente.

  - Este comando producirá un error si el programador web está mal configurado o no se ha implementado todavía.

</div>

<div>

## <a name="see-also"></a>Vea también


[Set-CsWebServer](https://docs.microsoft.com/powershell/module/skype/Set-CsWebServer)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

