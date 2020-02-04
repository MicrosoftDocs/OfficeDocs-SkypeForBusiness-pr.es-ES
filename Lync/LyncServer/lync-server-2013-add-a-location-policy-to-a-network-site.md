---
title: 'Lync Server 2013: agregar una directiva de ubicación a un sitio de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add a location policy to a network site
ms:assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425936(v=OCS.15)
ms:contentKeyID: 48183980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd5e0247ccdff82737c2ed7ed830b0a99b7da1f6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="add-a-location-policy-to-a-network-site-in-lync-server-2013"></a><span data-ttu-id="a3ed5-102">Agregar una directiva de ubicación a un sitio de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3ed5-102">Add a location policy to a network site in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3ed5-103">_**Última modificación del tema:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="a3ed5-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="a3ed5-104">En los siguientes ejemplos se muestra cómo agregar la Directiva de ubicación de **Redmond** definida en [crear directivas de ubicación en Lync Server 2013](lync-server-2013-create-location-policies.md) a un sitio de red existente y cómo crear un nuevo sitio de red que usa la Directiva de ubicación de **Redmond** .</span><span class="sxs-lookup"><span data-stu-id="a3ed5-104">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Lync Server 2013](lync-server-2013-create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>

<span data-ttu-id="a3ed5-105">Para obtener más información sobre cómo trabajar con sitios de red, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="a3ed5-105">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="a3ed5-106">**New-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="a3ed5-106">**New-CsNetworkSite**</span></span>

  - <span data-ttu-id="a3ed5-107">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="a3ed5-107">**Get-CsNetworkSite**</span></span>

  - <span data-ttu-id="a3ed5-108">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="a3ed5-108">**Set-CsNetworkSite**</span></span>

  - <span data-ttu-id="a3ed5-109">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="a3ed5-109">**Remove-CsNetworkSite**</span></span>

<div>

## <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="a3ed5-110">Para asignar una directiva de ubicación a un sitio de red existente</span><span class="sxs-lookup"><span data-stu-id="a3ed5-110">To assign a location policy to an existing network site</span></span>

1.  <span data-ttu-id="a3ed5-111">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a3ed5-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a3ed5-112">Ejecute los siguientes cmdlets para modificar un sitio de red existente.</span><span class="sxs-lookup"><span data-stu-id="a3ed5-112">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="a3ed5-113">Asigne la directiva de ubicación con la etiqueta **Redmond** a un sitio de red existente denominado **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="a3ed5-113">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
        Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

<div>

## <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="a3ed5-114">Para asignar una directiva de ubicación a un nuevo sitio de red</span><span class="sxs-lookup"><span data-stu-id="a3ed5-114">To assign a location policy to a new network site</span></span>

1.  <span data-ttu-id="a3ed5-115">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a3ed5-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="a3ed5-116">Ejecute el siguiente cmdlet para crear un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="a3ed5-116">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="a3ed5-117">Cree el sitio de red en la región de red y asígnele la directiva de ubicación con la etiqueta **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="a3ed5-117">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
        New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

</div>

</div>

<span> </span>

</div>

</div>

</div>

