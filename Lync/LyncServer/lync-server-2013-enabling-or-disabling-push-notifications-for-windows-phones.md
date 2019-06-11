---
title: 'Lync Server 2013: habilitar o deshabilitar las notificaciones push para Windows Phone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling or disabling push notifications for Windows Phones
ms:assetid: a34f0c5c-4228-40e3-9d93-bc0b5df4895d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688162(v=OCS.15)
ms:contentKeyID: 49733767
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b25594948f1d88caaca3dd07ca035b20f9f00079
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-push-notifications-for-windows-phones-in-lync-server-2013"></a>Habilitar o deshabilitar las notificaciones push para teléfonos Windows en Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificación del tema:** 2013-02-23_

Las notificaciones push, en forma de insignias, iconos o alertas, se pueden enviar a un Windows Phone incluso cuando la aplicación móvil no está activa. Las notificaciones push notifican a un usuario de eventos como una invitación o un correo de voz nuevos o perdidos. Puede habilitar o deshabilitar las notificaciones push para dispositivos Windows Phone mediante el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013.

<div>

## <a name="to-enable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a>Para habilitar las notificaciones push para Windows Phone mediante el panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, haga clic en el botón de navegación de **configuración de notificaciones push** .

4.  En la página **configuración de notificaciones push** , haga clic en el sitio que desea editar, haga clic en el menú **Editar** y, a continuación, haga clic en **Mostrar detalles**.

5.  Haga clic en la casilla de verificación **habilitar notificaciones de inserción de Microsoft** .

6.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a>Para deshabilitar las notificaciones push para Windows Phone mediante el panel de control de Lync Server

1.  Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.

2.  Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server. Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, haga clic en el botón de navegación de **configuración de notificaciones push** .

4.  En la página **configuración de notificaciones push** , haga clic en el sitio que desea editar, haga clic en el menú **Editar** y, a continuación, haga clic en **Mostrar detalles**.

5.  Desactive la casilla **habilitar notificaciones de inserción de Microsoft** .

6.  Haga clic en **Confirmar**.

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-for-windows-phone-by-using-windows-powershell-cmdlets"></a>Habilitar o deshabilitar las notificaciones push para Windows Phone mediante cmdlets de Windows PowerShell

Puede habilitar o deshabilitar las notificaciones push para Windows Phone mediante el cmdlet **set-CsPushNotificationConfiguration** . Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell. Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.

<div>

## <a name="to-enable-push-notifications-for-windows-phone"></a>Para habilitar las notificaciones push para Windows Phone

  - Para habilitar las notificaciones de inserción para Windows Phone, establezca el valor de la propiedad EnableMicrosoftPushNotificationService en true ($True). Por ejemplo:
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone"></a>Para deshabilitar las notificaciones push para Windows Phone

  - Para deshabilitar las notificaciones de inserción para Windows Phone, establezca el valor de la propiedad EnableMicrosoftPushNotificationService en false ($False). Por ejemplo:
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $False

</div>

Para obtener más información, consulte el tema de ayuda para el cmdlet [set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) .

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

