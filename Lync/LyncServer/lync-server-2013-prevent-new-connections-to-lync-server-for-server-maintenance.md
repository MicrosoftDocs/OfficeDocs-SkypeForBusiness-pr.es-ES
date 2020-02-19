---
title: Impedir nuevas conexiones a Lync Server para el mantenimiento del servidor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prevent new connections to Lync Server for server maintenance
ms:assetid: 22b27adf-a590-43bd-9306-a5789ae108d7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520964(v=OCS.15)
ms:contentKeyID: 48183625
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06516c3d47a9ec5e491a5a16098dfae334ff4f4e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a><span data-ttu-id="6564d-102">Impedir nuevas conexiones a Lync Server 2013 para el mantenimiento del servidor</span><span class="sxs-lookup"><span data-stu-id="6564d-102">Prevent new connections to Lync Server 2013 for server maintenance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6564d-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="6564d-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="6564d-104">Lync Server permite desconectar un servidor (por ejemplo, para aplicar actualizaciones de software o hardware) sin que los usuarios pierdan el servicio.</span><span class="sxs-lookup"><span data-stu-id="6564d-104">Lync Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="6564d-p101">Si especifica la opción para prevenir nuevas conexiones o llamadas al servidor en un grupo de servidores, dicho grupo deja de atender nuevas conexiones o llamadas en el momento en que se implementa la opción. Dichas nuevas conexiones y llamadas se redirigen a los otros servidores del grupo. Un servidor que no permite las nuevas conexiones permite que continúen las sesiones de conexiones existentes hasta su final natural. Cuando terminan todas las sesiones iniciadas, el servidor está listo para ser desconectado.</span><span class="sxs-lookup"><span data-stu-id="6564d-p101">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option. These new connections and calls are routed through other servers in the pool. A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end. When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="6564d-109">Cuando evita nuevas conexiones a un servidor front-end, algunas características y servicios de Lync Server se basan en el equilibrio de carga de DNS para asegurarse de que funcionan correctamente.</span><span class="sxs-lookup"><span data-stu-id="6564d-109">When you prevent new connections to a Front End Server, some Lync Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="6564d-110">Si no usa el equilibrador de carga de DNS en el grupo de servidores, puede que las conexiones a través de dichos servicios no se redirijan a otros servidores durante el período en que el servidor no admite nuevas conexiones, por lo cual es posible que cuando el servidor se desconecte se vean interrumpidas algunas sesiones y llamadas.</span><span class="sxs-lookup"><span data-stu-id="6564d-110">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="6564d-111">Las características que dependen del equilibrador de carga de DNS para garantizar que esta opción funciona correctamente son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="6564d-111">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="6564d-112">Auxiliar</span><span class="sxs-lookup"><span data-stu-id="6564d-112">Attendant</span></span>

  - <span data-ttu-id="6564d-113">Aplicación de anuncio de conferencia</span><span class="sxs-lookup"><span data-stu-id="6564d-113">Conferencing Announcement application</span></span>

  - <span data-ttu-id="6564d-114">Aplicación de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="6564d-114">Response Group application</span></span>

  - <span data-ttu-id="6564d-115">Aplicación de anuncio</span><span class="sxs-lookup"><span data-stu-id="6564d-115">Announcement application</span></span>

  - <span data-ttu-id="6564d-116">Aplicación Estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="6564d-116">Call Park application</span></span>

<span data-ttu-id="6564d-117">Para obtener más información sobre el equilibrio de carga de DNS, vea [equilibrio de carga de DNS en Lync Server 2013](lync-server-2013-dns-load-balancing.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="6564d-117">For details about DNS load balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<span data-ttu-id="6564d-118">Además de impedir nuevas conexiones para todos los servicios en un servidor que ejecuta Lync Server, también puede evitar nuevas conexiones para servicios individuales de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6564d-118">In addition to preventing new connections for all services on a server running Lync Server, you can also prevent new connections for individual Lync Server services.</span></span> <span data-ttu-id="6564d-119">Por ejemplo, este método es útil en una situación en la que se debe aplicar una actualización de Lync Server que no requiera que se cierre todo el servidor.</span><span class="sxs-lookup"><span data-stu-id="6564d-119">For example, this method is useful in a situation where you need to apply a Lync Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="6564d-120">Tenga en cuenta que cuando deje de admitir conexiones para un servicio, es necesario seleccionar un servicio según está agrupado y según se muestra en la lista de servicios de Windows.</span><span class="sxs-lookup"><span data-stu-id="6564d-120">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="6564d-121">Por ejemplo, el servicio front-end de Lync Server y el agente de recopilación de datos para la supervisión son servicios independientes de Lync Server, pero en la lista de servicios de Windows se consolidan y se muestran como el servicio front-end de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6564d-121">For example, the Lync Server Front-End service and the data collection agent for Monitoring are separate Lync Server services, but in the Windows services list they are consolidated and shown as the Lync Server Front End service.</span></span> <span data-ttu-id="6564d-122">Puede evitar nuevas conexiones para el servicio front-end de Lync Server, pero no puede evitar nuevas conexiones para estos dos servicios de Lync Server subyacentes por separado.</span><span class="sxs-lookup"><span data-stu-id="6564d-122">You can prevent new connections for the Lync Server Front End service, but you cannot prevent new connections for these two individual underlying Lync Server services separately.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="6564d-p104">Cuando se establece un servidor para impedir nuevas conexiones y después se reinicia el servidor, el servidor empezará de forma predeterminada y de inmediato a aceptar nuevas comunicaciones tras reiniciarse. Para evitar esto, establezca que el servidor solo pueda pausarse y reanudarse manualmente antes de reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="6564d-p104">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a><span data-ttu-id="6564d-125">Para evitar nuevas conexiones a Lync Server:</span><span class="sxs-lookup"><span data-stu-id="6564d-125">To prevent new connections to Lync Server:</span></span>

1.  <span data-ttu-id="6564d-126">Inicie sesión en el equipo local como miembro del grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="6564d-126">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="6564d-127">Abra la consola del complemento Servicios: haga clic en **Inicio**, seleccione **todos los programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **servicios**.</span><span class="sxs-lookup"><span data-stu-id="6564d-127">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="6564d-128">En la lista, haga doble clic en el servicio de Windows Lync Server en el que desea impedir que se realicen nuevas conexiones.</span><span class="sxs-lookup"><span data-stu-id="6564d-128">In the list, double-click the Lync Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="6564d-129">En el cuadro de diálogo Propiedades, en **Estado del servicio: Iniciado**, haga clic en **Pausar**.</span><span class="sxs-lookup"><span data-stu-id="6564d-129">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="6564d-130">Como alternativa, y recomendación, junto a **Tipo de inicio**, haga clic en **Manual**.</span><span class="sxs-lookup"><span data-stu-id="6564d-130">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="6564d-p105">Cuando se establece un servidor para impedir nuevas conexiones y después se reinicia el servidor, el servidor empezará de forma predeterminada y de inmediato a aceptar nuevas comunicaciones tras reiniciarse. Para evitar esto, establezca que el servidor solo pueda pausarse y reanudarse manualmente antes de reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="6564d-p105">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts. To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

    
    </div>

6.  <span data-ttu-id="6564d-133">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6564d-133">When you are finished, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

