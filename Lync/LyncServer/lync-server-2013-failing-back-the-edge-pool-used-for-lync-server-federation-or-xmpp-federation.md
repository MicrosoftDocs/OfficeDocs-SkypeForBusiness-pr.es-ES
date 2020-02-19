---
title: Conmutación por recuperación del grupo de servidores perimetrales usado para la Federación de Lync Server o la Federación XMPP
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
ms.openlocfilehash: 9001b3fd901888622aaf13922eb59c37e51e9936
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="65b35-102">Conmutación por recuperación del grupo de servidores perimetrales usado para la Federación de Lync Server o la Federación XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65b35-102">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65b35-103">_**Última modificación del tema:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="65b35-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="65b35-104">Después de volver a poner en línea un grupo de servidores perimetrales erróneo que hospedaba la federación, siga este procedimiento para conmutar por recuperación la ruta de la federación de Lync Server y/o la ruta de la federación XMPP para volver a usar este grupo de servidores perimetrales.</span><span class="sxs-lookup"><span data-stu-id="65b35-104">After a failed Edge pool that used to host federation has been brought back online, use this procedure to fail back the Lync Server federation route and/or the XMPP federation route to again use this restored Edge pool.</span></span>

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a><span data-ttu-id="65b35-105">Conmutar por recuperación una federación en un grupo de servidores perimetrales restaurado</span><span class="sxs-lookup"><span data-stu-id="65b35-105">Failing Back Federation to a Restored Edge Pool</span></span>

1.  <span data-ttu-id="65b35-106">En el grupo de servidores perimetrales que vuelve a estar disponible, inicie los servicios perimetrales.</span><span class="sxs-lookup"><span data-stu-id="65b35-106">On the Edge pool that is now available again, start the Edge Services.</span></span>

2.  <span data-ttu-id="65b35-107">Si quiere conmutar por recuperación la ruta de la federación de Lync Server para usar el servidor perimetral restaurado, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="65b35-107">If you want to fail back the Lync Server federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="65b35-p101">En un servidor front-end, abra el Generador de topologías. Expanda **Grupos de servidores perimetrales** y después haga clic con el botón secundario en el servidor perimetral o en el grupo de servidores perimetrales que está configurado actualmente para la federación. Seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="65b35-p101">On a Front End server, open Topology Builder. Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="65b35-p102">En **Editar propiedades**, en la pestaña **General**, desactive **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**. Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="65b35-p102">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="65b35-p103">Expanda **Grupos de servidores perimetrales**, después haga clic con el botón secundario en el servidor perimetral original o en el grupo de servidores perimetrales que quiere volver a usar para la federación. Seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="65b35-p103">Expand **Edge pools**, then right click the original Edge server or Edge server pool that you again want to use for Federation. Select **Edit properties**.</span></span>
    
      - <span data-ttu-id="65b35-p104">En **Editar propiedades**, en **General**, seleccione **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**. Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="65b35-p104">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>
    
      - <span data-ttu-id="65b35-p105">Haga clic en **Acción**, y seleccione sucesivamente **Topología** y **Publicar**. Cuando el sistema se lo solicite, en **Publicar la topología**, haga clic en **Siguiente**. Cuando haya acabado la publicación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="65b35-p105">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>
    
      - <span data-ttu-id="65b35-p106">En el servidor perimetral, abra el asistente para la implementación de Lync Server. Haga clic en **Instalar o actualizar el sistema Lync Server** y después haga clic en **Instalar o eliminar componentes de Lync Server**. Haga clic en **Ejecutar de nuevo**.</span><span class="sxs-lookup"><span data-stu-id="65b35-p106">On the Edge server, open the Lync Server Deployment wizard. Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**. Click **Run Again**.</span></span>
    
      - <span data-ttu-id="65b35-p107">En Instalar componentes de Lync Server, haga clic en **Siguiente**. En la pantalla de resumen aparecerán las acciones tal como se ejecutan. Cuando haya acabado la implementación, haga clic en **Ver registro** para ver los archivos de registro disponibles. Haga clic en **Finalizar** para completar la implementación.</span><span class="sxs-lookup"><span data-stu-id="65b35-p107">At Setup Lync Server components, click **Next**. The summary screen will show actions as they are executed. Once the deployment is done, click **View Log** to view available log files. Click **Finish** to complete the deployment.</span></span>

3.  <span data-ttu-id="65b35-127">Si quiere conmutar por recuperación la ruta de la federación XMPP para usar el servidor perimetral restaurado, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="65b35-127">If you want to fail back the XMPP federation route to use the restored Edge Server, do the following:</span></span>
    
      - <span data-ttu-id="65b35-128">Ejecute el cmdlet siguiente para volver a apuntar la ruta de la federación XMPP al grupo de servidores perimetrales que ahora hospedarán la federación XMPP (en este ejemplo, EdgeServer1):</span><span class="sxs-lookup"><span data-stu-id="65b35-128">Run the following cmdlet to repoint the XMPP federation route to the Edge pool which will now host XMPP federation (in this example, EdgeServer1):</span></span>
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        <span data-ttu-id="65b35-129">En este ejemplo, Site1 es el sitio que contiene el grupo de servidores perimetrales que ahora contendrá la ruta de la federación XMPP y EdgeServer1.contoso.com es el FQDN de un servidor perimetral de ese grupo de servidores.</span><span class="sxs-lookup"><span data-stu-id="65b35-129">In this example, Site1 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer1.contoso.com is the FQDN of an Edge Server in that pool.</span></span>
    
      - <span data-ttu-id="65b35-p108">Si todavía no tiene un registro DNS SRV para la federación XMPP que se resuelva en el grupo de servidores perimetrales que ahora hospedará la federación XMPP, agréguelo, como en el ejemplo siguiente. Este registro SRV debe tener un valor de puerto de 5269.</span><span class="sxs-lookup"><span data-stu-id="65b35-p108">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
        
            _xmpp-server._tcp.contoso.com
    
      - <span data-ttu-id="65b35-132">En el servidor DNS externo, cambie el registro DNS A para la federación XMPP para que apunte a EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="65b35-132">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>
    
      - <span data-ttu-id="65b35-133">Compruebe que el grupo de servidores perimetrales que ahora hospedará la federación XMPP tiene el puerto 5269 abierto externamente.</span><span class="sxs-lookup"><span data-stu-id="65b35-133">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

4.  <span data-ttu-id="65b35-134">Si los grupos de servidores front-end siguieron ejecutándose en el sitio que contiene el grupo de servidores perimetrales que tuvo el error y que se ha restaurado, actualice el servicio de conferencia web y el servicio de conferencia A/V en estos grupos de servidores front-end para que vuelvan a usar los grupos de servidores perimetrales en su sitio local.</span><span class="sxs-lookup"><span data-stu-id="65b35-134">If the Front End pools remained running in the site containing the Edge pool that failed and has been restored, you should update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to again use the Edge pools at their local site.</span></span> <span data-ttu-id="65b35-135">Para obtener más información, consulte [cambiar el grupo de servidores perimetrales asociado a un grupo de servidores front-end en Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="65b35-135">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

5.  <span data-ttu-id="65b35-136">Si el grupo de servidores front-end del mismo sitio que el grupo de servidores perimetrales también tuvo errores, ahora puede usar Invoke–CsPoolFailback para conmutar por recuperación el grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="65b35-136">If the Front End pool at the same site as the failed Edge pool also failed, you can now use Invoke–CsPoolFailback to fail back the Front End pool.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="65b35-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="65b35-137">See Also</span></span>


[<span data-ttu-id="65b35-138">Conmutación por error del grupo de servidores perimetrales usado para la Federación de Lync Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65b35-138">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[<span data-ttu-id="65b35-139">Conmutación por error del grupo de servidores perimetrales usado para la Federación XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65b35-139">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[<span data-ttu-id="65b35-140">Recuperación ante desastres del servidor perimetral en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65b35-140">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

