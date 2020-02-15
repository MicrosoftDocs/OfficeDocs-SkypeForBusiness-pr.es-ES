---
title: 'Lync Server 2013: crear vínculos de región de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network region links
ms:assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413047(v=OCS.15)
ms:contentKeyID: 48185873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ef56e2b71e1692b4343515613dec37b2a30621b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007109"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-region-links-in-lync-server-2013"></a><span data-ttu-id="9b44f-102">Crear vínculos de región de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b44f-102">Create network region links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b44f-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="9b44f-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="9b44f-p101">Las regiones de una red se vinculan mediante conexiones de red WAN físicas. Un *vínculo de región de red* crea un vínculo entre dos regiones configuradas para el control de admisión de llamadas y establece los límites de ancho de banda en el tráfico de audio y vídeo entre estas regiones.</span><span class="sxs-lookup"><span data-stu-id="9b44f-p101">Regions within a network are linked through physical WAN connectivity. A *network region link* creates a link between two regions configured for call admission control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>

<span data-ttu-id="9b44f-106">Para obtener información detallada sobre cómo trabajar con vínculos de región de red, vea la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="9b44f-106">For details about working with network region links, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="9b44f-107">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="9b44f-107">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)

  - [<span data-ttu-id="9b44f-108">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="9b44f-108">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [<span data-ttu-id="9b44f-109">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="9b44f-109">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)

  - [<span data-ttu-id="9b44f-110">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="9b44f-110">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)

<span data-ttu-id="9b44f-111">La topología de ejemplo tiene un vínculo entre las regiones de Norteamérica y APAC, y uno entre las regiones de EMEA y APAC.</span><span class="sxs-lookup"><span data-stu-id="9b44f-111">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="9b44f-112">Cada uno de estos vínculos de región está restringido por el ancho de banda de WAN, tal como se describe en la tabla de información de ancho de banda de vínculos de región en la sección [ejemplo: recopilación de los requisitos para el control de admisión de llamadas en Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) de la documentación de planeación.</span><span class="sxs-lookup"><span data-stu-id="9b44f-112">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in the [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) section of the Planning documentation.</span></span>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-management-shell"></a><span data-ttu-id="9b44f-113">Para crear vínculos de región de red mediante el Shell de administración de Communications Server</span><span class="sxs-lookup"><span data-stu-id="9b44f-113">To create network region links by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="9b44f-114">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9b44f-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="9b44f-p103">Ejecute el cmdlet New-CsNetworkRegionLink para crear vínculos de región de red y aplicar los correspondientes perfiles de directiva de ancho de banda. Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9b44f-p103">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles. For example, run:</span></span>
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
      ```
    
      ```powershell
        New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
      ```

</div>

<div>

## <a name="to-create-network-region-links-by-using-lync-server-control-panel"></a><span data-ttu-id="9b44f-117">Para crear vínculos de región de red mediante el Panel de control de Lync Server</span><span class="sxs-lookup"><span data-stu-id="9b44f-117">To create network region links by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9b44f-118">Abra una ventana del explorador y, a continuación, escriba la URL de administración para abrir el panel de control de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9b44f-118">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9b44f-119">Para obtener más información sobre los diferentes métodos que puede usar para iniciar el panel de control de Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9b44f-119">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="9b44f-120">En la barra de navegación izquierda, haga clic en **Configuración de red**.</span><span class="sxs-lookup"><span data-stu-id="9b44f-120">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="9b44f-121">Haga clic en el botón de navegación **Vínculo de región**.</span><span class="sxs-lookup"><span data-stu-id="9b44f-121">Click the **Region Link** navigation button.</span></span>

4.  <span data-ttu-id="9b44f-122">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="9b44f-122">Click **New**.</span></span>

5.  <span data-ttu-id="9b44f-123">En la página **Nuevo vínculo de región**, haga clic en **Nombre** y asigne un nombre al vínculo de región de red.</span><span class="sxs-lookup"><span data-stu-id="9b44f-123">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>

6.  <span data-ttu-id="9b44f-124">Haga clic en **región \#de red 1**y, a continuación, haga clic en la región de red en la lista \#que desea vincular a la región de red 2.</span><span class="sxs-lookup"><span data-stu-id="9b44f-124">Click **Network Region \#1**, and then click the network region in the list that you want to link to Network Region \#2.</span></span>

7.  <span data-ttu-id="9b44f-125">Haga clic en **región \#de red 2**y, a continuación, haga clic en una región de red en la lista \#que desea vincular a la región de red 1.</span><span class="sxs-lookup"><span data-stu-id="9b44f-125">Click **Network Region \#2**, and then click a network region in the list that you want to link to Network Region \#1.</span></span>

8.  <span data-ttu-id="9b44f-126">También puede hacer clic en **Directiva de ancho de banda** y seleccionar el perfil de directiva de ancho de banda que desea aplicar al vínculo de región de red.</span><span class="sxs-lookup"><span data-stu-id="9b44f-126">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="9b44f-127">Aplique una directiva de ancho de banda únicamente si el vínculo de región de red tiene restricciones de ancho de banda y desea usar control de admisión de llamadas para controlar el tráfico de medios en ese vínculo.</span><span class="sxs-lookup"><span data-stu-id="9b44f-127">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span>

    
    </div>

9.  <span data-ttu-id="9b44f-128">Haga clic en **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="9b44f-128">Click **Commit**.</span></span>

10. <span data-ttu-id="9b44f-129">Para terminar de crear vínculos de región de red para la topología, repita los pasos del 4 al 9 con parámetros para otras regiones.</span><span class="sxs-lookup"><span data-stu-id="9b44f-129">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>
