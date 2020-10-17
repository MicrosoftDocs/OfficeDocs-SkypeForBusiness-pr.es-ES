---
title: 'Lync Server 2013: cambiar el grupo de servidores perimetrales asociado a un grupo de servidores front-end'
description: 'Lync Server 2013: cambiar el grupo de servidores perimetrales asociado a un grupo de servidores front-end.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changing the Edge pool associated with a Front End pool
ms:assetid: 369468c7-2c0b-48cc-bbc3-825dad7b85aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688023(v=OCS.15)
ms:contentKeyID: 49733613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab22ba35420341e291d51a1ff012459840e63a56
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543576"
---
# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="0d078-103">Cambiar el grupo de servidores perimetrales asociado a un grupo de servidores front-end en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d078-103">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d078-104">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="0d078-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="0d078-105">Si se produce un error en un grupo perimetral pero el grupo de front-end del mismo sitio sigue en ejecución, deberá establecer el grupo de servidores front-end para que use un grupo perimetral de otro sitio hasta que se restablezca el grupo perimetral en el que se ha producido el error.</span><span class="sxs-lookup"><span data-stu-id="0d078-105">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="0d078-106">Cambio del grupo perimetral asociado a un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="0d078-106">Changing the Edge Pool Associated with a Front End Pool</span></span>

1.  <span data-ttu-id="0d078-107">En el Generador de topologías, navegue hasta el nombre del grupo de servidores front-end que desea cambiar.</span><span class="sxs-lookup"><span data-stu-id="0d078-107">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="0d078-108">Haga clic con el botón secundario en el grupo y, a continuación, haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="0d078-108">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="0d078-109">En la sección **Asociaciones**, en **Asociar grupo perimetral (para componentes multimedia)**, use el cuadro desplegable para seleccionar el grupo perimetral al que desea asociar este grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="0d078-109">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="0d078-110">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0d078-110">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0d078-111">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0d078-111">See Also</span></span>


[<span data-ttu-id="0d078-112">Recuperación ante desastres del servidor perimetral en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d078-112">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

