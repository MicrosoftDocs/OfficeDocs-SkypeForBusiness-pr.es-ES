---
title: 'Lync Server 2013: configurar la omisión de medios para omitir siempre el servidor de mediación'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass to always bypass the Mediation Server
ms:assetid: 370c4f54-e520-4d77-96a3-84c5e84a9996
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425846(v=OCS.15)
ms:contentKeyID: 48183819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 376ce5c00b4d326f283d1fde204d6c1bd17dd1de
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038302"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013-to-always-bypass-the-mediation-server"></a><span data-ttu-id="2c6a8-102">Configurar la omisión de medios en Lync Server 2013 para omitir siempre el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="2c6a8-102">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c6a8-103">_**Última modificación del tema:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="2c6a8-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2c6a8-104">En este tema se presupone que ya ha configurado el desvío de medios para las conexiones de enlace troncal con un par (una puerta de enlace de red telefónica conmutada [RTC], un sistema PBX IP o un controlador de borde de sesión [SBC] en un proveedor de servicios de telefonía por Internet [ITSP]) para un sitio o servicio específico en el que desea que los medios omitan el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="2c6a8-104">This topic assumes that you have already configured media bypass for any trunk connections to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP)) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="2c6a8-105">No puede configurar los medios para que omitan siempre el servidor de mediación al tiempo que también habilita el control de admisión de llamadas.</span><span class="sxs-lookup"><span data-stu-id="2c6a8-105">You cannot configure media to always bypass the Mediation Server while also enabling call admission control.</span></span> <span data-ttu-id="2c6a8-106">Estas opciones son incompatibles y, por lo tanto, son configuraciones mutuamente excluyentes en la interfaz de usuario del panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2c6a8-106">These settings are incompatible and are therefore mutually exclusive settings in the Lync Server Control Panel user interface.</span></span>



</div>

<span data-ttu-id="2c6a8-107">Además de habilitar el desvío de medios para conexiones de enlace troncal individuales asociadas a un par en el servidor de mediación, debe configurar también opciones globales para el desvío de medios.</span><span class="sxs-lookup"><span data-stu-id="2c6a8-107">In addition to enabling media bypass for individual trunk connections associated with a peer to the Mediation Server, you must also configure global settings for media bypass.</span></span> <span data-ttu-id="2c6a8-108">Si usa los pasos de este tema para establecer la configuración global de la omisión de medios, se supone que tiene buena conectividad entre los puntos de conexión de Lync y cualquier elemento del mismo nivel para el que haya configurado el desvío de medios en la conexión troncal.</span><span class="sxs-lookup"><span data-stu-id="2c6a8-108">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you have good connectivity between Lync endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>

<span data-ttu-id="2c6a8-109">Si no tiene buena conectividad entre los puntos de conexión de Lync Server y todos los elementos del mismo nivel que el servidor de mediación cuyas conexiones de tronco respectivas están habilitadas para la omisión de medios, debe configurar la configuración de omisión de medios globales para usar la información de sitio y región cuando usar la omisión de medios.</span><span class="sxs-lookup"><span data-stu-id="2c6a8-109">If you do not have good connectivity between Lync Server endpoints and all peers to the Mediation Server whose respective trunk connections have been enabled for media bypass, you must configure global media bypass settings to use site and region information when employing media bypass.</span></span> <span data-ttu-id="2c6a8-110">Con esto se permite un control más preciso para determinar cuándo los medios omiten el servidor de mediación.</span><span class="sxs-lookup"><span data-stu-id="2c6a8-110">This allows for more control in determining when media bypasses the Mediation Server.</span></span> <span data-ttu-id="2c6a8-111">Para ello, siga los pasos descritos en [configurar la configuración global de omisión de medios en Lync server 2013 para usar la información de sitio y región](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) y [asociar una subred a un sitio de red en Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="2c6a8-111">To do this, use the steps in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md) and [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md) instead.</span></span>

<div>

## <a name="to-enable-media-bypass-globally-to-always-bypass-the-mediation-server"></a><span data-ttu-id="2c6a8-112">Para habilitar globalmente el desvío de medios para que omita siempre el servidor de mediación</span><span class="sxs-lookup"><span data-stu-id="2c6a8-112">To Enable Media Bypass Globally to Always Bypass the Mediation Server</span></span>

1.  <span data-ttu-id="2c6a8-113">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2c6a8-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2c6a8-114">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2c6a8-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="2c6a8-115">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="2c6a8-115">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="2c6a8-116">Haga doble clic en la configuración **Global** de la lista.</span><span class="sxs-lookup"><span data-stu-id="2c6a8-116">Double-click the **Global** configuration in the list.</span></span>

4.  <span data-ttu-id="2c6a8-117">En la página **Editar configuración global**, seleccione la casilla **Habilitar desvío de medios**.</span><span class="sxs-lookup"><span data-stu-id="2c6a8-117">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="2c6a8-118">Haga clic en **Desviar siempre**.</span><span class="sxs-lookup"><span data-stu-id="2c6a8-118">Click **Always bypass**.</span></span>

6.  <span data-ttu-id="2c6a8-119">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="2c6a8-119">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2c6a8-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="2c6a8-120">See Also</span></span>


[<span data-ttu-id="2c6a8-121">Configurar la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c6a8-121">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="2c6a8-122">Opciones de omisión de medios globales en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c6a8-122">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
[<span data-ttu-id="2c6a8-123">Omisión de medios y servidor de mediación en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c6a8-123">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  


[<span data-ttu-id="2c6a8-124">Planeación de la omisión de medios en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c6a8-124">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

