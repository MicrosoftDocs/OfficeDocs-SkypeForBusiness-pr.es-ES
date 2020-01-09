---
title: 'Lync Server 2013: probar las notificaciones de inserción en teléfonos inteligentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test push notifications to smart phones
ms:assetid: 8f5ca7d1-1ccb-4cb0-b417-730559e79b6e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767948(v=OCS.15)
ms:contentKeyID: 63969626
ms.date: 03/15/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 653becc1cc22abc8b3c04e0ab3d2a2d1260a98d9
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-push-notifications-to-smart-phones-in-lync-server-2013"></a>Probar las notificaciones Push a Smart Phone en Lync Server 2013

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
<td><p>Programación de verificación</p></td>
<td><p>Cada mes</p></td>
</tr>
<tr class="even">
<td><p>Herramienta de prueba</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Permisos necesarios</p></td>
<td><p>Al ejecutarse de forma local con el shell de administración de Lync Server, los usuarios deben ser miembros del grupo de seguridad RTCUniversalServerAdmins.</p>
<p>Cuando se ejecuta con una instancia remota de Windows PowerShell, a los usuarios se les debe asignar un rol de RBAC que tenga permiso para ejecutar el cmdlet test-CsMcxPushNotification. Para ver una lista de todos los roles de RBAC que pueden usar este cmdlet, ejecute el siguiente comando en el símbolo del sistema de Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsMcxPushNotification&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Descripción

El servicio de notificaciones push (servicio de notificaciones push de Apple y servicio de notificaciones push de Microsoft) puede enviar notificaciones sobre eventos como nuevos mensajes instantáneos o un nuevo correo de voz a dispositivos móviles como iPhone y Windows Phone, incluso si el cliente de Lync en estos dispositivos está suspendido o se está ejecutando en segundo plano. El servicio de notificaciones push es un servicio basado en la nube que se ejecuta en servidores de Microsoft. Para aprovechar las notificaciones push, debe poder conectarse a la conexión de notificaciones Push y autenticarla en él. El cmdlet test-CsMcxPushNotification permite a los administradores comprobar que las solicitudes de notificaciones push se pueden enrutar a través del servidor perimetral al centro de notificaciones Push.

</div>

<div>

## <a name="running-the-test"></a>Ejecutar la prueba

Para probar el servicio de notificaciones push, llame al cmdlet test-CsMcxPushNotification. Asegúrese de especificar el nombre de dominio completo del servidor perimetral:

    Test-CsMcxPushNotification -AccessEdgeFqdn "atl-edge-001.litwareinc.com"

Para obtener más información, vea el tema de ayuda para el cmdlet [Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Determinar el éxito o el fracaso

Si prueba-CsMcxPushNotification se ejecuta correctamente, el cmdlet devolverá el resultado de la prueba correctamente:

TargetFqdn: atl-cs-001.litwareinc.com

Resultado: éxito

Latencia: 00:00:00

:

Diagnóstico

Si prueba-CsMcxPushNotification no puede conectarse al centro de notificaciones push, el cmdlet normalmente no devolverá un resultado de prueba de error. En su lugar, el comando fallará por completo. Por ejemplo:

Prueba-CsMcxPushNotification: se recibió una respuesta de 504 (tiempo de espera del servidor) desde la red y se produjo un error en la operación. Para obtener más información, consulta los detalles de la excepción.

En la línea: 1 carácter: 27

\+Prueba-CsMcxPushNotification \< \< \< \< -AccessEdgeFqdn lyncedge.mydomain.com

\+CategoryInfo: OperationStopped: (:) \[Prueba-CsMcxPushNotification\], FailureResponseException

\+FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. RTC. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Razones por las que se ha producido un error en la prueba

Si se produce un error en el servicio de notificaciones Push que normalmente indica problemas de comunicación con el servidor perimetral o problemas de comunicación con el centro de enrutamiento de notificaciones de inserción. Si experimenta problemas al ejecutar test-CsMcxPushNotification, lo primero que debe hacer es comprobar que el servidor perimetral funciona correctamente. Una forma de hacerlo es usar el cmdlet test-CsAVEdgeConnectivity:

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsAVEdgeConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Esta comprobación comprueba que un usuario especificado puede conectarse al servidor perimetral.

Si el servidor perimetral parece funcionar correctamente, eso a menudo significa que no puede conectarse al centro de notificaciones Push. A su vez, eso significa que no ha configurado el URI de Clearinghouse correctamente o que no tiene un registro SRV de DNS que apunte a esta dirección URL. Puede comprobar que el URI está configurado con el valor correcto (sip:push@push.lync.com) ejecutando este comando:

    Get-CsMcxConfiguration

Si la propiedad PushNotificationProxyUri se establece en un valor distinto de sip:push@push.lync.com, puede corregir ese problema mediante el cmdlet Set-McxConfiguration. Por ejemplo, este comando establece correctamente el URI en toda la organización:

    Get-CsMcxConfiguration | Set-CsMcxConfiguration -PushNotificationProxyUri "sip:push@push.lync.com"

Para obtener más información, consulte el tema de ayuda para el cmdlet [set-CsMcxConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsMcxConfiguration) .

Si el URI está configurado correctamente, el siguiente paso debe ser comprobar que tiene un registro SRV de DNS que se resuelve en el dominio SIP y en el servidor perimetral. Para obtener más información sobre cómo configurar estos registros, vea el tema de ayuda sobre los requisitos de DNS para la movilidad. Tenga en cuenta que el siguiente mensaje de error suele indicar un problema con los registros DNS:

Se ha recibido una respuesta 504 (tiempo de espera del servidor) de la red y se ha producido un error en la operación. Para obtener más información, consulta los detalles de la excepción.

También es posible que la prueba-CsMcxConfiguration falle con este mensaje de error:

Prueba-CsMcxPushNotification: se rechazó la solicitud de notificaciones Push.

En la línea: 1 carácter: 27

\+Prueba-CsMcxPushNotification\<\<\<\<

\+CategoryInfo: OperationStopped: (:) \[Prueba-CsMcxPushNotification\], SyntheticTransactionException

\+FullyQualifiedErrorId: WorkflowNotCompleted, Microsoft. RTC. Management. SyntheticTransactions. TestMcxPushNotificationCmdlet

El mensaje "se rechazó la solicitud de notificación de inserción" suele ocurrir si ha habilitado el filtrado de URL y está bloqueando los prefijos http: y https:. Puede determinar qué prefijos se están bloqueando mediante un comando similar al siguiente:

```PowerShell 
 (Get-CsImFilterConfiguration -Identity Global).Prefixes
```

Si http: o https: aparecen en los resultados, debe eliminarlos de la lista de prefijos bloqueados para que las notificaciones de inserción funcionen. Esto se puede hacer con comandos similares a estos:

    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="http:"}
    Set-CsImFilterConfiguration -Identity site:Redmond -Prefixes @{remove="https:"}

Para obtener más información, consulte el tema de ayuda para el cmdlet [set-CsImFilterConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsImFilterConfiguration).

</div>

</div>

<span> </span>

</div>

</div>

</div>

