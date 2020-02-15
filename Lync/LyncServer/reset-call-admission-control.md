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
ms.openlocfilehash: 1c51eed6e5164316c2785ff5d560291afe58015c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-call-admission-control"></a><span data-ttu-id="b436f-102">Restablecer el control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="b436f-102">Reset call admission control</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b436f-103">_**Última modificación del tema:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="b436f-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="b436f-104">Si un grupo de servidores front-end 2010 de Lync Server hospeda el controlador de admisión de llamadas (CAC), debe mover el hospedaje de CAC a un grupo de servidores de Lync Server 2013 para poder quitar el grupo de servidores front-end de Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="b436f-104">If a Lync Server 2010 Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Lync Server 2013 pool before you can remove the Lync Server 2010 Front End pool.</span></span>

<div>

## <a name="to-reset-cac"></a><span data-ttu-id="b436f-105">Para restablecer el CAC</span><span class="sxs-lookup"><span data-stu-id="b436f-105">To reset CAC</span></span>

1.  <span data-ttu-id="b436f-106">Abra el Generador de topologías.</span><span class="sxs-lookup"><span data-stu-id="b436f-106">Open Topology Builder.</span></span>

2.  <span data-ttu-id="b436f-107">Haga clic con el botón secundario en el nodo del sitio y luego haga clic en **Editar propiedades**.</span><span class="sxs-lookup"><span data-stu-id="b436f-107">Right-click the site node, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="b436f-108">En el parámetro **Control de admisión de llamadas**, asegúrese de que **Habilitar control de admisión de llamadas** esté activado.</span><span class="sxs-lookup"><span data-stu-id="b436f-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span>

4.  <span data-ttu-id="b436f-109">En **grupo de servidores front-end para ejecutar el control de admisión de llamadas (CAC)**, seleccione el grupo de servidores de Lync Server 2013 que va a hospedar CAC y, a continuación, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b436f-109">Under **Front End pool to run call admission control (CAC)**, select the Lync Server 2013 pool that is to host CAC, and then click **OK**.</span></span>

5.  <span data-ttu-id="b436f-110">Publique la topología.</span><span class="sxs-lookup"><span data-stu-id="b436f-110">Publish the topology.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

