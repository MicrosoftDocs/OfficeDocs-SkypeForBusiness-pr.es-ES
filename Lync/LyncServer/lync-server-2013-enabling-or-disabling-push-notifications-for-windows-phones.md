---
title: 'Lync Server 2013: habilitar o deshabilitar las notificaciones push para Windows Phone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling push notifications for Windows Phones
ms:assetid: a34f0c5c-4228-40e3-9d93-bc0b5df4895d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688162(v=OCS.15)
ms:contentKeyID: 49733767
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1b4c8f1f86fa1456230ad4695de0f5b8c56d406
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735640"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-push-notifications-for-windows-phones-in-lync-server-2013"></a><span data-ttu-id="cfc33-102">Habilitar o deshabilitar las notificaciones push para teléfonos Windows en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfc33-102">Enabling or disabling push notifications for Windows Phones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cfc33-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="cfc33-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="cfc33-104">Las notificaciones push, en forma de insignias, iconos o alertas, se pueden enviar a un Windows Phone incluso cuando la aplicación móvil no está activa.</span><span class="sxs-lookup"><span data-stu-id="cfc33-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a Windows Phone even when the mobile application is inactive.</span></span> <span data-ttu-id="cfc33-105">Las notificaciones push notifican a un usuario de eventos como una invitación o un correo de voz nuevos o perdidos.</span><span class="sxs-lookup"><span data-stu-id="cfc33-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="cfc33-106">Puede habilitar o deshabilitar las notificaciones push para dispositivos Windows Phone mediante el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cfc33-106">You can enable or disable push notifications for Windows Phone devices by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-enable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a><span data-ttu-id="cfc33-107">Para habilitar las notificaciones push para Windows Phone mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="cfc33-107">To enable push notifications for Windows Phone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="cfc33-108">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="cfc33-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cfc33-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cfc33-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cfc33-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cfc33-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cfc33-111">En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, haga clic en el botón de navegación de **configuración de notificaciones push** .</span><span class="sxs-lookup"><span data-stu-id="cfc33-111">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="cfc33-112">En la página **configuración de notificaciones push** , haga clic en el sitio que desea editar, haga clic en el menú **Editar** y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="cfc33-112">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="cfc33-113">Haga clic en la casilla de verificación **habilitar notificaciones de inserción de Microsoft** .</span><span class="sxs-lookup"><span data-stu-id="cfc33-113">Click the **Enable Microsoft push notifications** checkbox.</span></span>

6.  <span data-ttu-id="cfc33-114">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="cfc33-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a><span data-ttu-id="cfc33-115">Para deshabilitar las notificaciones push para Windows Phone mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="cfc33-115">To disable push notifications for Windows Phone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="cfc33-116">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="cfc33-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cfc33-117">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cfc33-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cfc33-118">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cfc33-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cfc33-119">En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, haga clic en el botón de navegación de **configuración de notificaciones push** .</span><span class="sxs-lookup"><span data-stu-id="cfc33-119">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="cfc33-120">En la página **configuración de notificaciones push** , haga clic en el sitio que desea editar, haga clic en el menú **Editar** y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="cfc33-120">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="cfc33-121">Desactive la casilla **habilitar notificaciones de inserción de Microsoft** .</span><span class="sxs-lookup"><span data-stu-id="cfc33-121">Clear the **Enable Microsoft push notifications** checkbox.</span></span>

6.  <span data-ttu-id="cfc33-122">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="cfc33-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-for-windows-phone-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="cfc33-123">Habilitar o deshabilitar las notificaciones push para Windows Phone mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cfc33-123">Enabling or Disabling Push Notifications for Windows Phone by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="cfc33-124">Puede habilitar o deshabilitar las notificaciones push para Windows Phone mediante el cmdlet **set-CsPushNotificationConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="cfc33-124">You can enable or disable push notifications for Windows Phone by using the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="cfc33-125">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cfc33-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="cfc33-126">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="cfc33-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-push-notifications-for-windows-phone"></a><span data-ttu-id="cfc33-127">Para habilitar las notificaciones push para Windows Phone</span><span class="sxs-lookup"><span data-stu-id="cfc33-127">To enable push notifications for Windows Phone</span></span>

  - <span data-ttu-id="cfc33-128">Para habilitar las notificaciones de inserción para Windows Phone, establezca el valor de la propiedad EnableMicrosoftPushNotificationService en true ($True).</span><span class="sxs-lookup"><span data-stu-id="cfc33-128">To enable push notifications for Windows Phone set the value of the EnableMicrosoftPushNotificationService property to True ($True).</span></span> <span data-ttu-id="cfc33-129">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cfc33-129">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone"></a><span data-ttu-id="cfc33-130">Para deshabilitar las notificaciones push para Windows Phone</span><span class="sxs-lookup"><span data-stu-id="cfc33-130">To disable push notifications for Windows Phone</span></span>

  - <span data-ttu-id="cfc33-131">Para deshabilitar las notificaciones de inserción para Windows Phone, establezca el valor de la propiedad EnableMicrosoftPushNotificationService en false ($False).</span><span class="sxs-lookup"><span data-stu-id="cfc33-131">To disable push notifications for Windows Phone set the value of the EnableMicrosoftPushNotificationService property to False ($False).</span></span> <span data-ttu-id="cfc33-132">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="cfc33-132">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $False

</div>

<span data-ttu-id="cfc33-133">Para obtener más información, consulte el tema de ayuda para el cmdlet [set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="cfc33-133">For more information, see the help topic for the [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cfc33-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="cfc33-134">See Also</span></span>


[<span data-ttu-id="cfc33-135">Configurar las notificaciones de inserción en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cfc33-135">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

