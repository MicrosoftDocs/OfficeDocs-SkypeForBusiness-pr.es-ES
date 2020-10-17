---
title: 'Lync Server 2013: conmutación por error del grupo de servidores perimetrales usado para la Federación de Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ed4849aff6dd65de524a99ac8fc6f886d7c4db5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48530927"
---
# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a><span data-ttu-id="1e658-102">Conmutación por error del grupo de servidores perimetrales usado para la Federación de Lync Server en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e658-102">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e658-103">_**Última modificación del tema:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="1e658-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="1e658-104">Si el grupo de servidores perimetrales en el que se ha configurado la Federación de Lync Server está inactivo, debe cambiar la Federación para usar un grupo perimetral diferente para que la Federación funcione.</span><span class="sxs-lookup"><span data-stu-id="1e658-104">If the Edge pool where you have Lync Server federation configured goes down, you must change federation to use a different Edge pool for federation to work.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a><span data-ttu-id="1e658-105">Conmutación por error del grupo de servidores perimetrales usado para la Federación de Lync Server</span><span class="sxs-lookup"><span data-stu-id="1e658-105">Failing Over the Edge Pool Used for Lync Server Federation</span></span>

1.  <span data-ttu-id="1e658-p101">En un servidor front-end, abra el Generador de topologías. Expanda **Grupos de servidores perimetrales** y después haga clic con el botón secundario en el servidor perimetral o en el grupo de servidores perimetrales que está configurado actualmente para la federación. Seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="1e658-p101">On a Front End server, open Topology Builder. Expand **Edge pools**, then right click the Edge server or Edge server pool that is currently configured for Federation. Select **Edit properties**.</span></span>

2.  <span data-ttu-id="1e658-p102">En **Editar propiedades**, en la pestaña **General**, desactive **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**. Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1e658-p102">In **Edit Properties** under **General**, clear **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>

3.  <span data-ttu-id="1e658-111">Expanda grupos de servidores **perimetrales**y haga clic con el botón secundario en el servidor perimetral o en el grupo de servidores perimetrales que ahora desea usar para la Federación.</span><span class="sxs-lookup"><span data-stu-id="1e658-111">Expand **Edge pools**, then right click the Edge server or Edge server pool that you now want to use for Federation.</span></span> <span data-ttu-id="1e658-112">Seleccione **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="1e658-112">Select **Edit properties**.</span></span>

4.  <span data-ttu-id="1e658-p104">En **Editar propiedades**, en **General**, seleccione **Habilitar la federación para este grupo de servidores perimetrales (puerto 5061)**. Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="1e658-p104">In **Edit Properties** under **General**, select **Enable federation for this Edge pool (Port 5061)**. Click **OK**.</span></span>

5.  <span data-ttu-id="1e658-p105">Haga clic en **Acción**, y seleccione sucesivamente **Topología** y **Publicar**. Cuando el sistema se lo solicite, en **Publicar la topología**, haga clic en **Siguiente**. Cuando haya acabado la publicación, haga clic en **Finalizar**.</span><span class="sxs-lookup"><span data-stu-id="1e658-p105">Click **Action**, select **Topology**, select **Publish**. When prompted on **Publish the topology**, click **Next**. When the Publish is finished, click **Finish**.</span></span>

6.  <span data-ttu-id="1e658-p106">En el servidor perimetral, abra el asistente para la implementación de Lync Server. Haga clic en **Instalar o actualizar el sistema Lync Server** y después haga clic en **Instalar o eliminar componentes de Lync Server**. Haga clic en **Ejecutar de nuevo**.</span><span class="sxs-lookup"><span data-stu-id="1e658-p106">On the Edge server, open the Lync Server Deployment wizard. Click **Install or Update Lync Server System**, then click **Setup or Remove Lync Server Components**. Click **Run Again**.</span></span>

7.  <span data-ttu-id="1e658-p107">En Instalar componentes de Lync Server, haga clic en **Siguiente**. En la pantalla de resumen aparecerán las acciones tal como se ejecutan. Cuando haya acabado la implementación, haga clic en **Ver registro** para ver los archivos de registro disponibles. Haga clic en **Finalizar** para completar la implementación.</span><span class="sxs-lookup"><span data-stu-id="1e658-p107">At Setup Lync Server components, click **Next**. The summary screen will show actions as they are executed. Once the deployment is done, click **View Log** to view available log files. Click **Finish** to complete the deployment.</span></span>
    
    <span data-ttu-id="1e658-125">Si el sitio que contiene el grupo de servidores perimetrales con error contiene servidores front-end que aún se están ejecutando, debe actualizar el servicio de conferencia web y el servicio de conferencia A/V en estos grupos de servidores front-end para usar un grupo de servidores perimetrales en un sitio remoto que todavía se esté ejecutando.</span><span class="sxs-lookup"><span data-stu-id="1e658-125">If the site containing the failed Edge pool contains Front End Servers that are still running, you must update the Web Conferencing Service and A/V Conferencing Service on these Front End pools to use an Edge pool in a remote site that is still running.</span></span> <span data-ttu-id="1e658-126">Para obtener más información, consulte [cambiar el grupo de servidores perimetrales asociado a un grupo de servidores front-end en Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span><span class="sxs-lookup"><span data-stu-id="1e658-126">For more information, see [Changing the Edge pool associated with a Front End pool in Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1e658-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1e658-127">See Also</span></span>


[<span data-ttu-id="1e658-128">Conmutación por error del grupo de servidores perimetrales usado para la Federación XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e658-128">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[<span data-ttu-id="1e658-129">Conmutación por recuperación del grupo de servidores perimetrales usado para la Federación de Lync Server o la Federación XMPP en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e658-129">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[<span data-ttu-id="1e658-130">Recuperación ante desastres del servidor perimetral en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e658-130">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

