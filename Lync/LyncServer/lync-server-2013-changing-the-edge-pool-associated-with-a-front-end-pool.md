---
title: 'Lync Server 2013: Cambio del grupo de servidores perimetrales asociado al grupo de servidores front-end'
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
ms.openlocfilehash: 736ed552a51182102310f4e10eb28472b251eb22
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changing-the-edge-pool-associated-with-a-front-end-pool-in-lync-server-2013"></a><span data-ttu-id="dabd7-102">Cambio del grupo de servidores perimetrales asociado al grupo de servidores front-end Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dabd7-102">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dabd7-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="dabd7-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="dabd7-104">Si un grupo de servidores perimetrales deja de funcionar pero el grupo de servidores front-end en el mismo sitio aún se está ejecutando, tendrá que configurar el grupo de servidores front-end para que use un grupo de límites en un sitio diferente hasta que se restaure el grupo perimetral con error.</span><span class="sxs-lookup"><span data-stu-id="dabd7-104">If an Edge pool goes down but the Front End pool at the same site is still running, you will need to set the Front End pool to use an Edge pool at a different site until the failed Edge pool is restored.</span></span>

<div>

## <a name="changing-the-edge-pool-associated-with-a-front-end-pool"></a><span data-ttu-id="dabd7-105">Cambiar el grupo perimetral asociado a un grupo de servidores front-end</span><span class="sxs-lookup"><span data-stu-id="dabd7-105">Changing the Edge Pool Associated with a Front End Pool</span></span>

1.  <span data-ttu-id="dabd7-106">En el generador de topología, vaya al nombre del grupo de servidores front-end que necesita cambiar.</span><span class="sxs-lookup"><span data-stu-id="dabd7-106">In Topology Builder, navigate to the name of the Front End pool you need to change.</span></span>

2.  <span data-ttu-id="dabd7-107">Haga clic con el botón secundario en el grupo y luego haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="dabd7-107">Right-click the pool, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="dabd7-108">En la sección **asociaciones** , en **asociar grupo perimetral (para componentes multimedia)**, use el cuadro desplegable para seleccionar el grupo perimetral al que desea asociar este grupo de servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="dabd7-108">In the **Associations** section, under **Associate Edge Pool (for media components)**, use the drop down box to select the Edge pool you want to associate this Front End pool with.</span></span>

4.  <span data-ttu-id="dabd7-109">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="dabd7-109">Click **OK**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dabd7-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="dabd7-110">See Also</span></span>


[<span data-ttu-id="dabd7-111">Recuperación ante desastres del servidor perimetral en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dabd7-111">Edge Server disaster recovery in Lync Server 2013</span></span>](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

