---
title: 'Lync Server 2013: configurar regiones de red para CAC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f0b79ade468300928edded9830219ba06b11b4f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147043"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a><span data-ttu-id="6c751-102">Configurar regiones de red para CAC en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6c751-102">Configure network regions for CAC in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6c751-103">_**Última modificación del tema:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="6c751-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="6c751-104">Si ya ha creado regiones de red para E9-1-1 o para el desvío de medios, puede modificar las regiones de red existentes mediante la adición de parámetros específicos de control de admisión de llamadas con el cmdlet Set-<STRONG>Set-CsNetworkRegion</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="6c751-104">If you have already created network regions for E9-1-1 or media bypass, you can modify the existing network regions by adding settings specific to call admission control (CAC) by using the <STRONG>Set-CsNetworkRegion</STRONG> cmdlet.</span></span> <span data-ttu-id="6c751-105">Para ver un ejemplo sobre cómo modificar una región de red, vea <A href="lync-server-2013-create-or-modify-a-network-region.md">crear o modificar una región de red en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6c751-105">For an example of how to modify a network region, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="6c751-106">*Las regiones de red* son los concentradores de red o redes troncales que se usan en la configuración del control de admisión de llamadas, de E9-1-1 y del desvío de medios.</span><span class="sxs-lookup"><span data-stu-id="6c751-106">*Network regions* are the network hubs or backbones that are used in configuring CAC, E9-1-1, and media bypass.</span></span> <span data-ttu-id="6c751-107">Siga estos procedimientos para crear regiones de red que se correspondan con las regiones de red del ejemplo de topología de red para controlar la admisión de llamadas.</span><span class="sxs-lookup"><span data-stu-id="6c751-107">Use the following procedure to create network regions that align to network regions in the example network topology for CAC.</span></span> <span data-ttu-id="6c751-108">Para ver la topología de red de ejemplo, consulte [ejemplo: recopilación de los requisitos para el control de admisión de llamadas en Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) en la documentación referente a la planeación.</span><span class="sxs-lookup"><span data-stu-id="6c751-108">To view the example network topology, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="6c751-109">La topología de red de ejemplo para el control de admisión de llamadas tiene tres regiones: Norteamérica, EMEA y APAC.</span><span class="sxs-lookup"><span data-stu-id="6c751-109">The example network topology for CAC has three regions: North America, EMEA, and APAC.</span></span> <span data-ttu-id="6c751-110">Cada región tiene un sitio central especificado.</span><span class="sxs-lookup"><span data-stu-id="6c751-110">Each region has a specified central site.</span></span> <span data-ttu-id="6c751-111">Para la región de Norteamérica, el sitio central designado se denomina CHICAGO.</span><span class="sxs-lookup"><span data-stu-id="6c751-111">For the North America region, the designated central site is named CHICAGO.</span></span> <span data-ttu-id="6c751-112">En el procedimiento siguiente se muestra un ejemplo de cómo puede usar el cmdlet  **New-CsNetworkRegion** para crear la región de Norteamérica.</span><span class="sxs-lookup"><span data-stu-id="6c751-112">The following procedure shows an example of how you can use the **New-CsNetworkRegion** cmdlet to create the North America region.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6c751-113">En el siguiente procedimiento, el shell de administración de Lync Server se usa para crear una región de red.</span><span class="sxs-lookup"><span data-stu-id="6c751-113">In the following procedure, Lync Server Management Shell is used to create a network region.</span></span> <span data-ttu-id="6c751-114">Para obtener información detallada sobre cómo usar el panel de control de Lync Server para crear una región de red, vea <A href="lync-server-2013-create-or-modify-a-network-region.md">crear o modificar una región de red en Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="6c751-114">For details about using Lync Server Control Panel to create a network region, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a><span data-ttu-id="6c751-115">Para crear una región de red para el control de admisión de llamadas</span><span class="sxs-lookup"><span data-stu-id="6c751-115">To create a network region for call admission control</span></span>

1.  <span data-ttu-id="6c751-116">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="6c751-116">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="6c751-117">Para cada región que necesite crear, ejecute el cmdlet **New-CsNetworkRegion**.</span><span class="sxs-lookup"><span data-stu-id="6c751-117">For each region that you need to create, run the **New-CsNetworkRegion** cmdlet.</span></span> <span data-ttu-id="6c751-118">Por ejemplo, para crear la región de Norteamérica, ejecute:</span><span class="sxs-lookup"><span data-stu-id="6c751-118">For example, to create the North America region, run:</span></span>
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  <span data-ttu-id="6c751-119">Repita el segundo paso para crear regiones de red de EMEA y APAC.</span><span class="sxs-lookup"><span data-stu-id="6c751-119">Repeat step 2 to create the network regions, EMEA and APAC.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

