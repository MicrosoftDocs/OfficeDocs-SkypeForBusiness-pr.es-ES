---
title: 'Lync Server 2013: habilitar o deshabilitar las notificaciones de inserción para iPhone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling push notifications for iPhones
ms:assetid: 8bbf531a-807f-4a8f-814a-94bfed8f97ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688122(v=OCS.15)
ms:contentKeyID: 49733719
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28820bacf3208d8918e18e3bbb9904f762cfdd21
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207884"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-push-notifications-for-iphones-in-lync-server-2013"></a><span data-ttu-id="1380b-102">Habilitar o deshabilitar las notificaciones de inserción para iPhone en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1380b-102">Enabling or disabling push notifications for iPhones in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1380b-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="1380b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="1380b-104">Las notificaciones de inserción, en forma de identificadores, iconos o alertas, se pueden enviar a un iPhone incluso cuando la aplicación móvil está inactiva.</span><span class="sxs-lookup"><span data-stu-id="1380b-104">Push notifications, in the form of badges, icons, or alerts, can be sent to an iPhone even when the mobile application is inactive.</span></span> <span data-ttu-id="1380b-105">Las notificaciones de inserción notifican a un usuario eventos como una invitación de mensajería instantánea nueva o perdida, o el correo de voz.</span><span class="sxs-lookup"><span data-stu-id="1380b-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="1380b-106">Puede habilitar o deshabilitar las notificaciones de inserción para iPhone mediante el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1380b-106">You can enable or disable push notifications for iPhone by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-enable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a><span data-ttu-id="1380b-107">Para habilitar las notificaciones de inserción para iPhone mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="1380b-107">To enable push notifications for iPhone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="1380b-108">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="1380b-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1380b-109">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1380b-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1380b-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1380b-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1380b-111">En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en el botón de navegación **Configuración de notificaciones de inserción**.</span><span class="sxs-lookup"><span data-stu-id="1380b-111">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="1380b-112">En la página **configuración de notificaciones de inserción** , haga clic en el sitio que desee editar, haga clic en el menú **Editar** y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="1380b-112">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="1380b-113">Haga clic en la casilla **Habilitar notificaciones de inserción de Apple**.</span><span class="sxs-lookup"><span data-stu-id="1380b-113">Click the **Enable Apple push notifications** checkbox.</span></span>

6.  <span data-ttu-id="1380b-114">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="1380b-114">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a><span data-ttu-id="1380b-115">Para deshabilitar las notificaciones de inserción para iPhone mediante el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="1380b-115">To disable push notifications for iPhone by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="1380b-116">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="1380b-116">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1380b-117">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1380b-117">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1380b-118">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1380b-118">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1380b-119">En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en el botón de navegación **Configuración de notificaciones de inserción**.</span><span class="sxs-lookup"><span data-stu-id="1380b-119">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="1380b-120">En la página **configuración de notificaciones de inserción** , haga clic en el sitio que desee editar, haga clic en el menú **Editar** y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="1380b-120">On the **Push Notification Configuration** page, click the site you want to edit, click the **Edit** menu, and then click **Show details**.</span></span>

5.  <span data-ttu-id="1380b-121">Desactive la casilla **Habilitar notificaciones de inserción de Apple**.</span><span class="sxs-lookup"><span data-stu-id="1380b-121">Clear the **Enable Apple push notifications** checkbox.</span></span>

6.  <span data-ttu-id="1380b-122">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="1380b-122">Click **Commit**.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-to-iphone-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1380b-123">Habilitación o deshabilitación de notificaciones de inserción en iPhone mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1380b-123">Enabling or Disabling Push Notifications to iPhone by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1380b-124">Se pueden habilitar o deshabilitar las notificaciones de inserción para Apple iPhone con el cmdlet **set-CsPushNotificationConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="1380b-124">Push notifications to Apple iPhone can be enabled or disabled by using the **Set-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="1380b-125">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1380b-125">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1380b-126">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="1380b-126">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-push-notifications-for-iphone"></a><span data-ttu-id="1380b-127">Para habilitar las notificaciones de inserción para iPhone</span><span class="sxs-lookup"><span data-stu-id="1380b-127">To enable push notifications for iPhone</span></span>

  - <span data-ttu-id="1380b-128">Para habilitar las notificaciones de inserción para iPhone, establezca el valor de la propiedad EnableApplePushNotificationService en true ($True).</span><span class="sxs-lookup"><span data-stu-id="1380b-128">To enable push notifications for iPhone set the value of the EnableApplePushNotificationService property to True ($True).</span></span> <span data-ttu-id="1380b-129">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1380b-129">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone"></a><span data-ttu-id="1380b-130">Para deshabilitar las notificaciones de inserción para iPhone</span><span class="sxs-lookup"><span data-stu-id="1380b-130">To disable push notifications for iPhone</span></span>

  - <span data-ttu-id="1380b-131">Para deshabilitar las notificaciones de inserción para iPhone, establezca el valor de la propiedad EnableApplePushNotificationService en false ($False).</span><span class="sxs-lookup"><span data-stu-id="1380b-131">To disable push notifications for iPhone set the value of the EnableApplePushNotificationService property to False ($False).</span></span> <span data-ttu-id="1380b-132">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="1380b-132">For example:</span></span>
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False

</div>

<span data-ttu-id="1380b-133">Si desea obtener más información, consulte el tema de ayuda del cmdlet [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration).</span><span class="sxs-lookup"><span data-stu-id="1380b-133">For more information, see the help topic for the [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1380b-134">Consulta también</span><span class="sxs-lookup"><span data-stu-id="1380b-134">See Also</span></span>


[<span data-ttu-id="1380b-135">Configuración de notificaciones de inserción en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1380b-135">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

