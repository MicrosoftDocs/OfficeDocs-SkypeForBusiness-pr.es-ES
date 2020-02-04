---
title: Restablecer el control de admisión de llamadas
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Reset call admission control
ms:assetid: 5873f56c-f3d6-4d73-beea-c9f37d5077f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688064(v=OCS.15)
ms:contentKeyID: 49733658
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6956b1a871a4a0a5c7e758d2890a58989f5ac8a2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-call-admission-control"></a><span data-ttu-id="05ac4-102">Restablecer el control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="05ac4-102">Reset call admission control</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05ac4-103">_**Última modificación del tema:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="05ac4-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="05ac4-104">Si un grupo de aplicaciones para el usuario de Lync Server 2010 hospeda control de admisión de llamadas (CAC), debe mover el alojamiento de hospedaje de CAC a un grupo de servidores de Lync 2013 antes de poder quitar el grupo de aplicaciones para usuario de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="05ac4-104">If a Lync Server 2010 Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Lync Server 2013 pool before you can remove the Lync Server 2010 Front End pool.</span></span>

<div>

## <a name="to-reset-cac"></a><span data-ttu-id="05ac4-105">Para restablecer CAC</span><span class="sxs-lookup"><span data-stu-id="05ac4-105">To reset CAC</span></span>

1.  <span data-ttu-id="05ac4-106">Abra el generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="05ac4-106">Open Topology Builder.</span></span>

2.  <span data-ttu-id="05ac4-107">Haga clic con el botón secundario en el nodo del sitio y haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="05ac4-107">Right-click the site node, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="05ac4-108">En **configuración de control de admisión de llamadas**, asegúrese de que **Habilitar control de admisión de llamadas** está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="05ac4-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span>

4.  <span data-ttu-id="05ac4-109">En **grupo de servidores front-end para ejecutar el controlador de admisión de llamadas (CAC)**, seleccione el grupo de 2013 de Lync Server que hospedará CAC y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="05ac4-109">Under **Front End pool to run call admission control (CAC)**, select the Lync Server 2013 pool that is to host CAC, and then click **OK**.</span></span>

5.  <span data-ttu-id="05ac4-110">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="05ac4-110">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

