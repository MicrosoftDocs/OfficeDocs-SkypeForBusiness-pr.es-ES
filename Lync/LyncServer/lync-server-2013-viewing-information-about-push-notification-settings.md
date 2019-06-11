---
title: 'Lync Server 2013: ver información sobre la configuración de notificaciones de inserción'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing information about push notification settings
ms:assetid: be5c6b01-4294-4d17-9772-fed40201e8a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721868(v=OCS.15)
ms:contentKeyID: 49733801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da9279d09ab3b344514a472f3fb0f38e7071aabd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850083"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-information-about-push-notification-settings-in-lync-server-2013"></a>Ver información sobre la configuración de notificaciones de inserción en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Las notificaciones push, en forma de insignias, iconos o alertas, se pueden enviar a un dispositivo móvil incluso cuando la aplicación móvil no está activa. Las notificaciones push notifican a un usuario de eventos como una invitación o un correo de voz nuevos o perdidos. Puede ver la configuración de notificaciones de inserción de información para dispositivos móviles usando el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013.

<div>

## <a name="to-view-push-notification-information-from-lync-server-control-panel"></a>Para ver la información de notificaciones Push en el panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, haga clic en el botón de navegación de **configuración de notificaciones push** .

4.  En la página **configuración de notificaciones push** , haga clic en el sitio que desea ver, haga clic en el menú **Editar** y, a continuación, haga clic en **Mostrar detalles**.

</div>

<div>

## <a name="viewing-push-notification-information-by-using-windows-powershell-cmdlets"></a>Ver la información de notificaciones de inserción mediante cmdlets de Windows PowerShell

Puede ver la configuración de las notificaciones push mediante Windows PowerShell y el cmdlet **Get-CsPushNotificationConfiguration** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-view-push-notification-configuration-information"></a>Para ver la información de configuración de notificaciones push

  - Para ver información sobre todas las opciones de configuración de notificaciones de inserción, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
        Get-CsPushNotificationConfiguration
    
    Devolverá información similar a la siguiente:
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

</div>

Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration) .

</div>

<div>

## <a name="see-also"></a>Vea también


[Configurar las notificaciones de inserción en Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

