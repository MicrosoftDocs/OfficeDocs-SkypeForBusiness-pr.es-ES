---
title: 'Lync Server 2013: probar las notificaciones de inserción en teléfonos inteligentes'
description: 'Lync Server 2013: probar las notificaciones de inserción en los teléfonos inteligentes.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test push notifications to smart phones
ms:assetid: 8f5ca7d1-1ccb-4cb0-b417-730559e79b6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767948(v=OCS.15)
ms:contentKeyID: 63969626
ms.date: 03/15/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b92ef444a5331c9a673fd2db506631554e96eea
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550846"
---
# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a>Probar las notificaciones de inserción con teléfonos inteligentes en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2017-03-15_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Programación de comprobación</p></td>
<td><p>Mensualmente</p></td>
</tr>
<tr class="even">
<td><p>Herramienta de prueba</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permisos necesarios</p></td>
<td><p>Cuando se ejecuta de forma local mediante el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</p>
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol RBAC que tenga permiso para ejecutar el cmdlet Test-CsMcxPushNotification. Para ver una lista de todos los roles RBAC que pueden usar este cmdlet, ejecute el siguiente comando desde el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El servicio de notificaciones de inserción (servicio de notificaciones de inserción de Apple y servicio de notificaciones de inserción de Microsoft) puede enviar notificaciones sobre eventos como nuevos mensajes instantáneos o correo de voz nuevo a dispositivos móviles, como iPhone y Windows Phone, incluso si el cliente de Lync en estos dispositivos está actualmente suspendido o en ejecución en segundo plano. El servicio de notificaciones de inserción es un servicio basado en la nube que se ejecuta en servidores de Microsoft. Para aprovechar las notificaciones de inserción, debe ser capaz de conectarse y autenticarse con el centro de notificaciones de inserción. El cmdlet Test-CsMcxPushNotification permite a los administradores comprobar que las solicitudes de notificación de inserción se pueden enrutar a través del servidor perimetral hacia el centro de notificaciones de inserción.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

Para probar el servicio de notificaciones de inserción, llame al cmdlet Test-CsMcxPushNotification. Asegúrese de especificar el nombre de dominio completo del servidor perimetral:

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

Para obtener más información, consulte el tema de ayuda del cmdlet [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar si se ha realizado correctamente o erróneo

Si Test-CsMcxPushNotification tiene éxito, el cmdlet devolverá el resultado de la prueba:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: correcto

Latencia: 00:00:00

Error

Diagnóstico

Si Test-CsMcxPushNotification no puede conectarse al centro de notificaciones de inserción, el cmdlet no devolverá normalmente un resultado de prueba de error. En su lugar, el comando producirá un error por completo. Por ejemplo:

Test-CsMcxPushNotification: se recibió una respuesta 504 (tiempo de espera del servidor) desde la red y se produjo un error en la operación. Vea los detalles de la excepción para obtener más información.

En la línea: 1 carácter: 27

\+Test-CsMcxPushNotification \< \< \< \< AccessEdgeFqdn lyncedge.mydomain.com

\+ CategoryInfo: OperationStopped: (:) \[ Test-CsMcxPushNotification \] , FailureResponseException

\+ FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. RTC. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Motivos por los que se ha producido un error en la prueba

Si se produce un error en el servicio de notificaciones de inserción que normalmente indica problemas de comunicación con el servidor perimetral o problemas de comunicación con el centro de enrutamiento de notificaciones de inserción. Si surgen problemas al ejecutar test-CsMcxPushNotification, lo primero que debe hacer es comprobar que el servidor perimetral funciona correctamente. Una forma de hacerlo es usar el cmdlet Test-CsAVEdgeConnectivity:

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Esta comprobación comprueba que un usuario especificado puede conectarse al servidor perimetral.

Si el servidor perimetral parece funcionar correctamente, esto suele significar que no puede conectarse al centro de notificaciones de inserción. A su vez, eso suele significar que no ha configurado correctamente el URI del centro de activación o que no tiene un registro SRV de DNS que señale a esta dirección URL. Puede comprobar que el URI está establecido en el valor correcto (sip:push@push.lync.com) ejecutando este comando:

    Get-CsMcxConfiguration

Si la propiedad PushNotificationProxyUri se establece en un valor distinto de sip:push@push.lync.com, puede corregir el problema mediante el cmdlet Set-McxConfiguration. Por ejemplo, este comando establece correctamente el URI en toda la organización:

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

Para obtener más información, consulte el tema de ayuda del cmdlet [set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) .

Si el URI está configurado correctamente, el siguiente paso debe ser comprobar que tiene un registro SRV de DNS que se resuelve en el dominio SIP y el servidor perimetral. Para obtener más información acerca de cómo configurar estos registros, consulte el tema de ayuda sobre los requisitos de DNS para la movilidad. Tenga en cuenta que el siguiente mensaje de error suele indicar un problema con los registros DNS:

Se ha recibido una respuesta 504 (tiempo de espera del servidor) de la red y se ha producido un error en la operación. Vea los detalles de la excepción para obtener más información.

También es posible que se produzca un error en Test-CsMcxConfiguration con este mensaje de error:

Test-CsMcxPushNotification: se rechazó la solicitud de notificación de inserción.

En la línea: 1 carácter: 27

\+ Test-CsMcxPushNotification \<\<\<\<

\+ CategoryInfo: OperationStopped: (:) \[ Test-CsMcxPushNotification \] , SyntheticTransactionException

\+ FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. RTC. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet

El mensaje "se rechazó la solicitud de notificación de inserción" suele producirse si ha habilitado el filtrado de URL y está bloqueando los prefijos http: y https:. Puede determinar qué prefijos se están bloqueando mediante un comando similar al siguiente:

```PowerShell 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

Si http: o https: aparecen en los resultados, debe quitarlos de la lista de prefijos bloqueados para que funcionen las notificaciones de inserción. Esto se puede hacer con comandos similares a los siguientes:

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

Para obtener más información, consulte el tema de ayuda del cmdlet [set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration).

</div>

</div>

<span> </span>

</div>

</div>

</div>

