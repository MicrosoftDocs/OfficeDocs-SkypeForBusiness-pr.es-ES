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
ms.openlocfilehash: fb0e2db6eeff584c4d1ab08bdd293113f1394e4a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724830"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-new-connections-to-lync-server-2013-for-server-maintenance"></a><span data-ttu-id="813f3-102">Impedir nuevas conexiones a Lync Server 2013 para el mantenimiento del servidor</span><span class="sxs-lookup"><span data-stu-id="813f3-102">Prevent new connections to Lync Server 2013 for server maintenance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="813f3-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="813f3-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="813f3-104">Lync Server le permite poner fuera de conexión un servidor (por ejemplo, para aplicar actualizaciones de software o hardware) sin ninguna pérdida de servicio para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="813f3-104">Lync Server enables you to take a server offline (for example, to apply software or hardware upgrades) without any loss of service to users.</span></span>

<span data-ttu-id="813f3-105">Cuando especifica la opción de evitar nuevas conexiones o llamadas a un servidor de un grupo, deja de tomarse cualquier conexión y llamada nuevas tan pronto como implemente esta opción.</span><span class="sxs-lookup"><span data-stu-id="813f3-105">When you specify the option to prevent new connections or calls to a server in a pool, it stops taking any new connections and calls as soon as you implement this option.</span></span> <span data-ttu-id="813f3-106">Estas nuevas conexiones y llamadas se enrutan a través de otros servidores del grupo.</span><span class="sxs-lookup"><span data-stu-id="813f3-106">These new connections and calls are routed through other servers in the pool.</span></span> <span data-ttu-id="813f3-107">Un servidor que impide nuevas conexiones permite que las sesiones de las conexiones existentes continúen hasta que se desordenan de forma natural.</span><span class="sxs-lookup"><span data-stu-id="813f3-107">A server that is preventing new connections allows its sessions on existing connections to continue until they naturally end.</span></span> <span data-ttu-id="813f3-108">Cuando haya finalizado todas las sesiones existentes, el servidor estará listo para desconectarse.</span><span class="sxs-lookup"><span data-stu-id="813f3-108">When all existing sessions have ended, the server is ready to be taken offline.</span></span>

<span data-ttu-id="813f3-109">Cuando impide nuevas conexiones a un servidor front-end, algunas características y servicios de Lync Server dependen del equilibrio de carga de DNS para asegurarse de que funciona correctamente.</span><span class="sxs-lookup"><span data-stu-id="813f3-109">When you prevent new connections to a Front End Server, some Lync Server features and services rely on DNS load balancing to ensure that it functions properly.</span></span> <span data-ttu-id="813f3-110">Si no usa el equilibrio de carga de DNS en el grupo, es posible que las conexiones a través de estos servicios no se redirijan a otros servidores durante el período en el que el servidor está impidiendo las conexiones nuevas y, por lo tanto, cuando el servidor se desconecta, algunas sesiones y llamadas pueden ser interrupción.</span><span class="sxs-lookup"><span data-stu-id="813f3-110">If you are not using DNS load balancing on the pool, connections through these services may not be re-routed to other servers during the period that the server is preventing new connections, and thus when the server is taken offline some sessions and calls may be interrupted.</span></span> <span data-ttu-id="813f3-111">Las características que dependen del equilibrio de carga de DNS para asegurarse de que esta opción funciona correctamente son las siguientes:</span><span class="sxs-lookup"><span data-stu-id="813f3-111">The features that rely on DNS load balancing to ensure that this option operates properly are as follows:</span></span>

  - <span data-ttu-id="813f3-112">Operador</span><span class="sxs-lookup"><span data-stu-id="813f3-112">Attendant</span></span>

  - <span data-ttu-id="813f3-113">Aplicación de anuncio de conferencia</span><span class="sxs-lookup"><span data-stu-id="813f3-113">Conferencing Announcement application</span></span>

  - <span data-ttu-id="813f3-114">Aplicación de grupo de respuesta</span><span class="sxs-lookup"><span data-stu-id="813f3-114">Response Group application</span></span>

  - <span data-ttu-id="813f3-115">Aplicación de anuncio</span><span class="sxs-lookup"><span data-stu-id="813f3-115">Announcement application</span></span>

  - <span data-ttu-id="813f3-116">Aplicación de estacionamiento de llamadas</span><span class="sxs-lookup"><span data-stu-id="813f3-116">Call Park application</span></span>

<span data-ttu-id="813f3-117">Para obtener más información sobre el equilibrio de carga de DNS, consulte [equilibrio de carga de DNS en Lync Server 2013](lync-server-2013-dns-load-balancing.md) en la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="813f3-117">For details about DNS load balancing, see [DNS load balancing in Lync Server 2013](lync-server-2013-dns-load-balancing.md) in the Planning documentation.</span></span>

<span data-ttu-id="813f3-118">Además de impedir nuevas conexiones para todos los servicios en un servidor que ejecuta Lync Server, también puede impedir nuevas conexiones para servicios individuales de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="813f3-118">In addition to preventing new connections for all services on a server running Lync Server, you can also prevent new connections for individual Lync Server services.</span></span> <span data-ttu-id="813f3-119">Por ejemplo, este método es útil en una situación en la que necesita aplicar una actualización de Lync Server que no requiera que se cierre todo el servidor.</span><span class="sxs-lookup"><span data-stu-id="813f3-119">For example, this method is useful in a situation where you need to apply a Lync Server update that does not require the whole server to be shut down.</span></span> <span data-ttu-id="813f3-120">Tenga en cuenta que cuando impide las conexiones para un servicio, debe seleccionar un servicio tal como está agrupado y se muestra en la lista de servicios de Windows.</span><span class="sxs-lookup"><span data-stu-id="813f3-120">Note that when you prevent connections for one service, you must select a service as it is grouped and displayed in the Windows list of services.</span></span> <span data-ttu-id="813f3-121">Por ejemplo, el servicio front-end de Lync Server y el agente de recopilación de datos para la supervisión son servicios independientes de Lync Server, pero en la lista de servicios de Windows se consolidan y se muestran como el servicio front-end de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="813f3-121">For example, the Lync Server Front-End service and the data collection agent for Monitoring are separate Lync Server services, but in the Windows services list they are consolidated and shown as the Lync Server Front End service.</span></span> <span data-ttu-id="813f3-122">Puede evitar nuevas conexiones para el servicio front-end de Lync Server, pero no puede evitar nuevas conexiones por separado en estos dos servicios de Lync Server subyacentes.</span><span class="sxs-lookup"><span data-stu-id="813f3-122">You can prevent new connections for the Lync Server Front End service, but you cannot prevent new connections for these two individual underlying Lync Server services separately.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="813f3-123">Al configurar un servidor para evitar nuevas conexiones y reiniciar el servidor, de forma predeterminada, el servidor comenzará a aceptar inmediatamente nuevas conexiones después de que se inicie.</span><span class="sxs-lookup"><span data-stu-id="813f3-123">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="813f3-124">Para evitar esto, configure el servidor para que solo PAUSE y reanude de forma manual, antes de reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="813f3-124">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>



</div>

<div>

## <a name="to-prevent-new-connections-to-lync-server"></a><span data-ttu-id="813f3-125">Para evitar nuevas conexiones a Lync Server:</span><span class="sxs-lookup"><span data-stu-id="813f3-125">To prevent new connections to Lync Server:</span></span>

1.  <span data-ttu-id="813f3-126">Inicie sesión en el equipo local como miembro del grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="813f3-126">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="813f3-127">Abra la consola del complemento Servicios: haga clic en **Inicio**, seleccione **todos los programas**, seleccione **herramientas administrativas**y, a continuación, haga clic en **servicios**.</span><span class="sxs-lookup"><span data-stu-id="813f3-127">Open the Services snap-in console: Click **Start**, point to **All Programs**, point to **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="813f3-128">En la lista, haga doble clic en el servicio de Windows de Lync Server en el que desea evitar nuevas conexiones.</span><span class="sxs-lookup"><span data-stu-id="813f3-128">In the list, double-click the Lync Server Windows service to which you want to prevent new connections.</span></span>

4.  <span data-ttu-id="813f3-129">En el cuadro de diálogo Propiedades, en **Estado del servicio: iniciado**, haga clic en **pausar**.</span><span class="sxs-lookup"><span data-stu-id="813f3-129">In the Properties dialog box, under **Service status: Started**, click **Pause**.</span></span>

5.  <span data-ttu-id="813f3-130">De forma opcional, pero recomendado, junto a **tipo de inicio**, haga clic en **manual**.</span><span class="sxs-lookup"><span data-stu-id="813f3-130">Optionally, but recommended, next to **Startup type**, click **Manual**.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="813f3-131">Al configurar un servidor para evitar nuevas conexiones y reiniciar el servidor, de forma predeterminada, el servidor comenzará a aceptar inmediatamente nuevas conexiones después de que se inicie.</span><span class="sxs-lookup"><span data-stu-id="813f3-131">When you set a server to prevent new connections, and then restart the server, by default the server will immediately begin accepting new connections after it starts.</span></span> <span data-ttu-id="813f3-132">Para evitar esto, configure el servidor para que solo PAUSE y reanude de forma manual, antes de reiniciar el servidor.</span><span class="sxs-lookup"><span data-stu-id="813f3-132">To prevent this, set the server to only pause and resume manually, before you restart the server.</span></span>

    
    </div>

6.  <span data-ttu-id="813f3-133">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="813f3-133">When you are finished, click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

