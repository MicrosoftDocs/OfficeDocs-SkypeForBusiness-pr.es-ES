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

# <a name="viewing-information-about-push-notification-settings-in-lync-server-2013"></a><span data-ttu-id="37d0a-102">Ver información sobre la configuración de notificaciones de inserción en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37d0a-102">Viewing information about push notification settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37d0a-103">_**Última modificación del tema:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="37d0a-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="37d0a-104">Las notificaciones push, en forma de insignias, iconos o alertas, se pueden enviar a un dispositivo móvil incluso cuando la aplicación móvil no está activa.</span><span class="sxs-lookup"><span data-stu-id="37d0a-104">Push notifications, in the form of badges, icons, or alerts, can be sent to a mobile device even when the mobile application is inactive.</span></span> <span data-ttu-id="37d0a-105">Las notificaciones push notifican a un usuario de eventos como una invitación o un correo de voz nuevos o perdidos.</span><span class="sxs-lookup"><span data-stu-id="37d0a-105">Push notifications notify a user of events such as a new or missed IM invitation and voice mail.</span></span> <span data-ttu-id="37d0a-106">Puede ver la configuración de notificaciones de inserción de información para dispositivos móviles usando el panel de control de Lync Server 2013 o el shell de administración de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="37d0a-106">You can view information push notifications settings for mobile devices by using either Lync Server 2013 Control Panel or Lync Server 2013 Management Shell.</span></span>

<div>

## <a name="to-view-push-notification-information-from-lync-server-control-panel"></a><span data-ttu-id="37d0a-107">Para ver la información de notificaciones Push en el panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="37d0a-107">To view push notification information from Lync Server Control Panel</span></span>

1.  <span data-ttu-id="37d0a-108">Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.</span><span class="sxs-lookup"><span data-stu-id="37d0a-108">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="37d0a-109">Abra una ventana del explorador y, a continuación, escriba la dirección URL del administrador para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="37d0a-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="37d0a-110">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [abrir las herramientas administrativas 2013 de Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="37d0a-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="37d0a-111">En la barra de navegación izquierda, haga clic en **clientes**y, a continuación, haga clic en el botón de navegación de **configuración de notificaciones push** .</span><span class="sxs-lookup"><span data-stu-id="37d0a-111">In the left navigation bar, click **Clients**, and then click the **Push Notification Configuration** navigation button.</span></span>

4.  <span data-ttu-id="37d0a-112">En la página **configuración de notificaciones push** , haga clic en el sitio que desea ver, haga clic en el menú **Editar** y, a continuación, haga clic en **Mostrar detalles**.</span><span class="sxs-lookup"><span data-stu-id="37d0a-112">On the **Push Notification Configuration** page, click the site you want to view, click the **Edit** menu, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-push-notification-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="37d0a-113">Ver la información de notificaciones de inserción mediante cmdlets de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="37d0a-113">Viewing Push Notification Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="37d0a-114">Puede ver la configuración de las notificaciones push mediante Windows PowerShell y el cmdlet **Get-CsPushNotificationConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="37d0a-114">You can view push notification configuration settings by using Windows PowerShell and the **Get-CsPushNotificationConfiguration** cmdlet.</span></span> <span data-ttu-id="37d0a-115">Puede ejecutar este cmdlet desde el shell de administración de Lync Server 2013 o desde una sesión remota de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="37d0a-115">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="37d0a-116">Para obtener más información sobre cómo usar Windows PowerShell remoto para conectarse a Lync Server, consulte el artículo del blog de Lync Server de Windows PowerShell "Inicio rápido: administrar Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 mediante PowerShell remoto" en.</span><span class="sxs-lookup"><span data-stu-id="37d0a-116">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-push-notification-configuration-information"></a><span data-ttu-id="37d0a-117">Para ver la información de configuración de notificaciones push</span><span class="sxs-lookup"><span data-stu-id="37d0a-117">To view push notification configuration information</span></span>

  - <span data-ttu-id="37d0a-118">Para ver información sobre todas las opciones de configuración de notificaciones de inserción, escriba el siguiente comando en el shell de administración de Lync Server y, a continuación, presione ENTRAR:</span><span class="sxs-lookup"><span data-stu-id="37d0a-118">To view information about all your push notification configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsPushNotificationConfiguration
    
    <span data-ttu-id="37d0a-119">Devolverá información similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="37d0a-119">That will return information similar to this:</span></span>
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

</div>

<span data-ttu-id="37d0a-120">Para obtener más información, consulte el tema de ayuda para el cmdlet [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="37d0a-120">For more information, see the help topic for the [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="37d0a-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="37d0a-121">See Also</span></span>


[<span data-ttu-id="37d0a-122">Configurar las notificaciones de inserción en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37d0a-122">Configuring for push notifications in Lync Server 2013</span></span>](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

