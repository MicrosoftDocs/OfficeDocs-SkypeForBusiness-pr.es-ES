---
title: 'Lync Server 2013: ver información sobre la configuración de notificaciones de inserción'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing information about push notification settings
ms:assetid: be5c6b01-4294-4d17-9772-fed40201e8a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721868(v=OCS.15)
ms:contentKeyID: 49733801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58602a2fed6faa03c7dd573b95345a0ee57aa607
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523547"
---
# <a name="viewing-information-about-push-notification-settings-in-lync-server-2013"></a>Ver información sobre la configuración de notificaciones de inserción en Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Las notificaciones de inserción, en la forma de distintivos, iconos o alertas, se pueden enviar a un dispositivo móvil aunque la aplicación móvil se encuentre inactiva. Las notificaciones de inserción notifican a un usuario eventos como correo de voz o invitaciones de mensajería instantánea nuevas o perdidas. Puede ver la configuración de notificaciones de inserción de información para dispositivos móviles mediante el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013.

<div>

## <a name="to-view-push-notification-information-from-lync-server-control-panel"></a>Para ver la información de notificaciones de inserción desde el panel de control de Lync Server

1.  Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en el botón de navegación **Configuración de notificaciones de inserción**.

4.  En la página **configuración de notificaciones de inserción** , haga clic en el sitio que desea ver, haga clic en el menú **Editar** y, a continuación, haga clic en **Mostrar detalles**.

</div>

<div>

## <a name="viewing-push-notification-information-by-using-windows-powershell-cmdlets"></a>Ver la información de notificaciones de inserción mediante cmdlets de Windows PowerShell

Puede ver las opciones de configuración de notificaciones de inserción con Windows PowerShell y el cmdlet **Get-CsPushNotificationConfiguration** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server 2010 mediante PowerShell remoto" en [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-push-notification-configuration-information"></a>Para ver información sobre la configuración de las notificaciones de inserción:

  - Para ver información sobre todas las opciones de configuración de notificaciones de inserción, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:
    
        Get-CsPushNotificationConfiguration
    
    Devolverá información similar a la siguiente:
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

</div>

Para más información, consulte el tema de Ayuda del cmdlet [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration).

</div>

<div>

## <a name="see-also"></a>Consulte también


[Configuración de notificaciones de inserción en Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

