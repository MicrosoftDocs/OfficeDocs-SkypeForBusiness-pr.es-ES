---
title: Conmutación por recuperación para el grupo de servidores perimetrales que se usa para la federación Lync Server o la federación XMPP
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98fec3082c172cc9e31d931d1c64ef3eaeccd04b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756164"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="800fe-102">Conmutación por recuperación para el grupo de servidores perimetrales que se usa para la federación Lync Server o la federación XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="800fe-102">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="800fe-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="800fe-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="800fe-104">Después de que se haya vuelto a conectar un grupo perimetral que usó para hospedar la Federación, use este procedimiento para recuperar la ruta de Federación de Lync Server y/o la ruta de Federación XMPP para usar de nuevo este grupo de bordes restaurado.</span><span class="sxs-lookup"><span data-stu-id="800fe-104">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Lync Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a><span data-ttu-id="800fe-105">Conmutación por error de la Federación a un grupo perimetral restaurado</span><span class="sxs-lookup"><span data-stu-id="800fe-105">Failing Back Federation to a Restored Edge Pool</span></span>

1.  <span data-ttu-id="800fe-106">En el grupo Edge que ya está disponible de nuevo, inicie los servicios de Edge.</span><span class="sxs-lookup"><span data-stu-id="800fe-106">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="800fe-107">Si desea recuperar la conmutación por error de la ruta de Federación de Lync Server para usar el servidor perimetral restaurado, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="800fe-107">If you want to fail back the Lync Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="800fe-108">En un servidor front-end, abra Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="800fe-108">On a Front End server, open Topology Builder.</span></span> <span data-ttu-id="800fe-109">Expanda **agrupaciones perimetrales**y haga clic con el botón secundario en el servidor perimetral o en el grupo de servidores perimetrales actualmente configurados para la Federación.</span><span class="sxs-lookup"><span data-stu-id="800fe-109">Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation.</span></span> <span data-ttu-id="800fe-110">Seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="800fe-110">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="800fe-111">En **Editar propiedades** , en **General**, desactive **Habilitar Federación para este grupo perimetral (puerto 5061)**.</span><span class="sxs-lookup"><span data-stu-id="800fe-111">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="800fe-112">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="800fe-112">Click **OK**.</span></span>
    
      - <span data-ttu-id="800fe-113">Expanda **agrupaciones perimetrales**y, a continuación, haga clic con el botón secundario en el servidor perimetral original o en el grupo de servidores perimetrales que desea usar de nuevo para la Federación.</span><span class="sxs-lookup"><span data-stu-id="800fe-113">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation.</span></span> <span data-ttu-id="800fe-114">Seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="800fe-114">Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="800fe-115">En **propiedades de edición** , en **General**, seleccione **Habilitar Federación para este grupo perimetral (puerto 5061)**.</span><span class="sxs-lookup"><span data-stu-id="800fe-115">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**.</span></span> <span data-ttu-id="800fe-116">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="800fe-116">Click **OK**.</span></span>
    
      - <span data-ttu-id="800fe-117">Haga clic en **acción**, seleccione **topología**, seleccione **publicar**.</span><span class="sxs-lookup"><span data-stu-id="800fe-117">Click **Action**, select **Topology**, select **Publish**.</span></span> <span data-ttu-id="800fe-118">Cuando se le solicite al **publicar la topología**, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="800fe-118">When prompted on **Publish the topology**, click **Next**.</span></span> <span data-ttu-id="800fe-119">Una vez finalizada la publicación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="800fe-119">When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="800fe-120">En el servidor perimetral, abra el Asistente para la implementación de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="800fe-120">On the Edge server, open the Lync Server Deployment wizard.</span></span> <span data-ttu-id="800fe-121">Haga clic en **instalar o actualizar el sistema Lync Server**y, a continuación, haga clic en **configurar o quitar los componentes de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="800fe-121">Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**.</span></span> <span data-ttu-id="800fe-122">**Vuelva a**hacer clic en ejecutar.</span><span class="sxs-lookup"><span data-stu-id="800fe-122">Click **Run Again**.</span></span>
    
      - <span data-ttu-id="800fe-123">En instalación de los componentes de Lync Server, haga clic en **siguiente**.</span><span class="sxs-lookup"><span data-stu-id="800fe-123">At Setup Lync Server components, click **Next**.</span></span> <span data-ttu-id="800fe-124">La pantalla resumen mostrará las acciones a medida que se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="800fe-124">The summary screen will show actions as they are executed.</span></span> <span data-ttu-id="800fe-125">Una vez que haya finalizado la implementación, haga clic en **Ver registro** para ver los archivos de registro disponibles.</span><span class="sxs-lookup"><span data-stu-id="800fe-125">Once the deployment is done, click **View Log** to view available log files.</span></span> <span data-ttu-id="800fe-126">Haga clic en **Finalizar** para completar la implementación.</span><span class="sxs-lookup"><span data-stu-id="800fe-126">Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="800fe-127">Si desea recuperar la conmutación por recuperación de la ruta de Federación de XMPP para usar el servidor perimetral restaurado, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="800fe-127">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="800fe-128">Ejecute el siguiente cmdlet para redirigir la ruta de Federación de XMPP al conjunto de servidores perimetrales que ahora hospedan la Federación XMPP (en este ejemplo, EdgeServer1):</span><span class="sxs-lookup"><span data-stu-id="800fe-128">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="800fe-129">En este ejemplo, Sitio1 es el sitio que contiene el grupo Edge que ahora hospedará la ruta de Federación XMPP y EdgeServer1.contoso.com es el FQDN de un servidor perimetral en ese grupo.</span><span class="sxs-lookup"><span data-stu-id="800fe-129">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="800fe-130">Si todavía no tiene un registro SRV de DNS para la Federación de XMPP, que se resuelve en el grupo Edge que ahora hospedará la Federación XMPP, debe agregarlo, como en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="800fe-130">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example.</span></span> <span data-ttu-id="800fe-131">Este registro SRV debe tener un valor de puerto de 5269.</span><span class="sxs-lookup"><span data-stu-id="800fe-131">This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="800fe-132">En el servidor DNS externo, cambie el registro A de DNS para la Federación XMPP para que apunte a EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="800fe-132">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="800fe-133">Verifique que el grupo de servidores perimetrales que ahora hospeda la Federación XMPP tenga el puerto 5269 abierto externamente.</span><span class="sxs-lookup"><span data-stu-id="800fe-133">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="800fe-134">Si las agrupaciones front-end permanecieron ejecutándose en el sitio que contiene el grupo perimetral que falló y se han restaurado, debe actualizar el servicio de conferencias web y el servicio de conferencia A/V en estos grupos de aplicaciones para el usuario de nuevo para usar los grupos perimetrales en su sitio local.</span><span class="sxs-lookup"><span data-stu-id="800fe-134">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span> <span data-ttu-id="800fe-135">Para obtener más información, vea [cambiar el grupo perimetral asociado a un grupo de servidores front-end en Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="800fe-135">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

5.  <span data-ttu-id="800fe-136">Si el grupo de servidores front-end en el mismo sitio que el grupo perimetral con errores también ha fallado, ahora puede usar Invoke-CsPoolFailback para recuperar el repositorio front-end.</span><span class="sxs-lookup"><span data-stu-id="800fe-136">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="800fe-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="800fe-137">See Also</span></span>


[<span data-ttu-id="800fe-138">Conmutación por error para el grupo de servidores perimetrales usado para la federación Lync Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="800fe-138">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[<span data-ttu-id="800fe-139">Conmutación por error para el grupo de servidores perimetrales para la federación XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="800fe-139">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[<span data-ttu-id="800fe-140">Recuperación ante desastres del servidor perimetral en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="800fe-140">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

