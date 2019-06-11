---
title: 'Lync Server 2013: habilitar la supervisión'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling monitoring
ms:assetid: 244df419-d0a8-4b1d-aedd-a92114172ab6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687994(v=OCS.15)
ms:contentKeyID: 49733584
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2b13028390328e93a9e90636962dedea8ea8ec9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34835257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-monitoring-in-lync-server-2013"></a><span data-ttu-id="7ec86-102">Habilitar la supervisión en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ec86-102">Enabling monitoring in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ec86-103">_**Última modificación del tema:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="7ec86-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="7ec86-104">Aunque los agentes unificados de recopilación de datos se instalan y activan automáticamente en cada servidor front-end, eso no significa que comience a recopilar datos de supervisión de forma automática en el momento de finalizar la instalación de Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ec86-104">Although the unified data collection agents are automatically installed and activated on each Front End server, that does not mean that you will automatically begin to collect monitoring data the moment you finish installing Microsoft Lync Server 2013.</span></span> <span data-ttu-id="7ec86-105">En su lugar, debe hacer dos cosas: debe asociar los servidores front-end o las agrupaciones front-end con una base de datos de supervisión, y debe habilitar la supervisión de la grabación de detalles de llamadas (CDR) o la calidad de la experiencia (QoE) en el ámbito global o en el ámbito del sitio.</span><span class="sxs-lookup"><span data-stu-id="7ec86-105">Instead, you must do two things: you must associate your Front End servers/Front End pools with a monitoring database, and you must enable call detail recording (CDR) and/or Quality of Experience (QoE) monitoring at the global scope and/or the site scope.</span></span>

<span data-ttu-id="7ec86-106">Para obtener instrucciones paso a paso sobre la Asociación de servidores front-end o grupos de aplicaciones para el usuario con una base de datos de supervisión, consulte el tema sobre cómo [asociar una tienda de supervisión con un grupo de servidores front-end en Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) en la guía de implementación.</span><span class="sxs-lookup"><span data-stu-id="7ec86-106">For step-by-step instructions on associating Front End servers or Front End pools with a monitoring database, see the topic [Associating a monitoring store with a Front End pool in Lync Server 2013](lync-server-2013-associating-a-monitoring-store-with-a-front-end-pool.md) in the Deployment guide.</span></span> <span data-ttu-id="7ec86-107">Después de que se hayan realizado estas asociaciones y después de que se haya publicado la nueva topología de Lync Server, aún no podrá recopilar datos de supervisión.</span><span class="sxs-lookup"><span data-stu-id="7ec86-107">After these associations have been made, and after your new Lync Server topology has been published, you will still not be able to collect monitoring data.</span></span> <span data-ttu-id="7ec86-108">Esto se debe a que, de forma predeterminada, la recopilación de datos de CDR y QoE está deshabilitada al instalar Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ec86-108">That's because, by default, both CDR and QoE data collection is disabled when you install Lync Server 2013.</span></span>

<span data-ttu-id="7ec86-109">Para comenzar la recopilación de datos, deberá habilitar la supervisión de CDR y/o QoE.</span><span class="sxs-lookup"><span data-stu-id="7ec86-109">In order to begin data collection you will need to enable CDR and/or QoE monitoring.</span></span> <span data-ttu-id="7ec86-110">(Tenga en cuenta que no tiene que habilitar la supervisión de CDR y QoE; si lo prefiere, puede habilitar un tipo de supervisión y dejar el otro tipo deshabilitado). Para habilitar la supervisión de CDR en el ámbito global, ejecute el siguiente comando desde el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="7ec86-110">(Note that you do not have to enable both CDR and QoE monitoring; if you prefer, you can enable one type of monitoring while leaving the other type disabled.) To enable CDR monitoring at the global scope run the following command from within the Lync Server Management Shell:</span></span>

    Set-CsCdrConfiguration -Identity "global" -EnableCDR $True

<span data-ttu-id="7ec86-111">Como alternativa, puede habilitar la supervisión de CDR desde el panel de control de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ec86-111">Alternatively, you can enable CDR monitoring from within the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="7ec86-112">En el panel de control de Lync Server, complete el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="7ec86-112">From within the Lync Server Control Panel, complete the following procedure:</span></span>

1.  <span data-ttu-id="7ec86-113">Haga clic en **Supervisión**.</span><span class="sxs-lookup"><span data-stu-id="7ec86-113">Click **Monitoring**.</span></span>

2.  <span data-ttu-id="7ec86-114">En la pestaña **Registro detallado de llamadas**, haga doble clic en la configuración **Global**.</span><span class="sxs-lookup"><span data-stu-id="7ec86-114">On the **Call Detail Recording** tab, double-click the **Global** setting.</span></span>

3.  <span data-ttu-id="7ec86-115">En el panel **Editar configuración del registro detallado de llamadas (CDR)**, seleccione **Habilitar supervisión de CDR** y haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="7ec86-115">In the **Edit Call Detail Recording (CDR) Setting** pane, select **Enable monitoring of CDRs** and then click **Commit**.</span></span>

<span data-ttu-id="7ec86-116">Para habilitar la supervisión de QoE en el ámbito global, ejecute este comando desde el shell de administración de Lync Server:</span><span class="sxs-lookup"><span data-stu-id="7ec86-116">To enable QoE monitoring at the global scope, run this command from within the Lync Server Management Shell:</span></span>

    Set-CsQoEConfiguration -Identity "global" -EnableQoE $True

<span data-ttu-id="7ec86-117">Si lo prefiere, también puede habilitar la supervisión de QoE desde el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7ec86-117">If you prefer, you can also enable QoE monitoring from within the Lync Server Control Panel.</span></span> <span data-ttu-id="7ec86-118">Desde allí, lleve a cabo el procedimiento siguiente:</span><span class="sxs-lookup"><span data-stu-id="7ec86-118">From within the Control Panel, complete the following procedure:</span></span>

1.  <span data-ttu-id="7ec86-119">Haga clic en **Supervisión**.</span><span class="sxs-lookup"><span data-stu-id="7ec86-119">Click **Monitoring**.</span></span>

2.  <span data-ttu-id="7ec86-120">En la pestaña **Datos de calidad de la experiencia**, haga doble clic en la configuración **Global**.</span><span class="sxs-lookup"><span data-stu-id="7ec86-120">On the **Quality of Experience Data** tab, double-click the **Global** setting.</span></span>

3.  <span data-ttu-id="7ec86-121">En el panel **Editar configuración de calidad de la experiencia (QoE)**, seleccione **Habilitar supervisión de datos de QoE** y haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="7ec86-121">In the **Edit Quality of Experience (QoE) Setting** pane, select **Enable monitoring of QoE data** and then click **Commit**.</span></span>

<span data-ttu-id="7ec86-122">Tal como hemos visto, los ejemplos anteriores muestran cómo habilitar la supervisión de forma global; es decir, permiten habilitar la supervisión de CDR y QoE en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="7ec86-122">As noted, the preceding examples enable monitoring at the global scope; that is, they enable CDR and QoE monitoring throughout your organization.</span></span> <span data-ttu-id="7ec86-123">De forma alternativa, puede separar las opciones de configuración de CDR y QoE en el sitio para habilitar o deshabilitar la supervisión en cada sitio.</span><span class="sxs-lookup"><span data-stu-id="7ec86-123">Alternatively, you can create separate CDR and QoE configuration settings at the site scope, and then selectively enable or disable monitoring for each site.</span></span> <span data-ttu-id="7ec86-124">Por ejemplo, puede habilitar la supervisión de CDR para el sitio de Redmont y deshabilitarla para el sitio de Dublín.</span><span class="sxs-lookup"><span data-stu-id="7ec86-124">For example, you could enable CDR monitoring for your Redmond site, yet disable CDR monitoring for your Dublin site.</span></span> <span data-ttu-id="7ec86-125">Para obtener más información sobre cómo administrar las opciones de configuración de supervisión, consulte el tema de la guía de implementación configuración de la [grabación de detalles de llamadas y configuración de la calidad de la experiencia en Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).</span><span class="sxs-lookup"><span data-stu-id="7ec86-125">For more information on managing your monitoring configuration settings, see the Deployment guide topic [Configuring call detail recording and Quality of Experience settings in Lync Server 2013](lync-server-2013-configuring-call-detail-recording-and-quality-of-experience-settings.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

