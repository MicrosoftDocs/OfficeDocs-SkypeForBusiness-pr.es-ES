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
ms.openlocfilehash: 075deabdbc57bd809fce4bf3e4635309f367d69c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-information-about-push-notification-settings-in-lync-server-2013"></a><span data-ttu-id="2d78f-102">Ver información sobre la configuración de notificaciones de inserción en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d78f-102">Viewing information about push notification settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d78f-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="2d78f-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="2d78f-104">Las notificaciones de inserción, en la forma de distintivos, iconos o alertas, se pueden enviar a un dispositivo móvil aunque la aplicación móvil se encuentre inactiva.</span><span class="sxs-lookup"><span data-stu-id="2d78f-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the mobile application is inactive.</span></span> <span data-ttu-id="2d78f-105">Las notificaciones de inserción notifican a un usuario eventos como correo de voz o invitaciones de mensajería instantánea nuevas o perdidas.</span><span class="sxs-lookup"><span data-stu-id="2d78f-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="2d78f-106">Puede ver la configuración de notificaciones de inserción de información para dispositivos móviles mediante el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2d78f-106">You can view information push notifications settings for mobile devices by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-view-push-notification-information-from-lync-server-control-panel"></a><span data-ttu-id="2d78f-107">Para ver la información de notificaciones de inserción desde el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="2d78f-107">To view push notification information from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="2d78f-108">Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.</span><span class="sxs-lookup"><span data-stu-id="2d78f-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2d78f-109">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2d78f-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2d78f-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2d78f-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2d78f-111">En la barra de navegación izquierda, haga clic en **Clientes** y, a continuación, en el botón de navegación **Configuración de notificaciones de inserción**.</span><span class="sxs-lookup"><span data-stu-id="2d78f-111">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="2d78f-112">En la página **configuración de notificaciones de inserción** , haga clic en el sitio que desea ver, haga clic en el menú **Editar** y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="2d78f-112">On the **Push Notification Configuration** page, click the site you want to view, click the **Edit** menu, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-push-notification-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2d78f-113">Ver la información de notificaciones de inserción mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d78f-113">Viewing Push Notification Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2d78f-114">Puede ver las opciones de configuración de notificaciones de inserción con Windows PowerShell y el cmdlet **Get-CsPushNotificationConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="2d78f-114">You can view push notification configuration settings by using Windows PowerShell and the **Get-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="2d78f-115">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d78f-115">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2d78f-116">Para obtener información detallada sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server Windows PowerShell "Inicio rápido: administración de Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="2d78f-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-push-notification-configuration-information"></a><span data-ttu-id="2d78f-117">Para ver información sobre la configuración de las notificaciones de inserción:</span><span class="sxs-lookup"><span data-stu-id="2d78f-117">To view push notification configuration information</span></span>

  - <span data-ttu-id="2d78f-118">Para ver información sobre todas las opciones de configuración de notificaciones de inserción, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="2d78f-118">To view information about all your push notification configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsPushNotificationConfiguration
    
    <span data-ttu-id="2d78f-119">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="2d78f-119">That will return information similar to this:</span></span>
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

</div>

<span data-ttu-id="2d78f-120">Para más información, consulte el tema de Ayuda del cmdlet [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration).</span><span class="sxs-lookup"><span data-stu-id="2d78f-120">For more information, see the help topic for the [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2d78f-121">Consulta también</span><span class="sxs-lookup"><span data-stu-id="2d78f-121">See Also</span></span>


[<span data-ttu-id="2d78f-122">Configuración de notificaciones de inserción en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d78f-122">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

