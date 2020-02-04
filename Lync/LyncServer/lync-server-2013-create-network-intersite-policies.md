---
title: 'Lync Server 2013: crear directivas de sitios intersitios de red'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network intersite policies
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412844(v=OCS.15)
ms:contentKeyID: 48185148
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 655cde30a3d798d57520c57e3882b2162010888c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740330"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-intersite-policies-in-lync-server-2013"></a><span data-ttu-id="b0b1c-102">Crear directivas de intersitios de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0b1c-102">Create network intersite policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0b1c-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="b0b1c-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="b0b1c-104">Una *Directiva de red entre sitios* define limitaciones de ancho de banda entre los sitios que tienen vínculos WAN directos entre ellos.</span><span class="sxs-lookup"><span data-stu-id="b0b1c-104">A *network intersite policy* defines bandwidth limitations between sites that have direct WAN links between them.</span></span>

<span data-ttu-id="b0b1c-105">Para obtener más información, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="b0b1c-105">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="b0b1c-106">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="b0b1c-106">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="b0b1c-107">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="b0b1c-107">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="b0b1c-108">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="b0b1c-108">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="b0b1c-109">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="b0b1c-109">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b0b1c-110">Una directiva de red entre sitios <EM>solo</EM> es necesaria si hay un vínculo cruzado directo entre dos sitios de red.</span><span class="sxs-lookup"><span data-stu-id="b0b1c-110">A network intersite policy is required <EM>only</EM> if there is a direct cross link between two network sites.</span></span>



</div>

<span data-ttu-id="b0b1c-111">En la topología de ejemplo de la región de Norteamérica, hay un vínculo directo entre los sitios de Reno y Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="b0b1c-111">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="b0b1c-112">Estos dos sitios requieren una directiva entre sitios que aplique un perfil de directiva de ancho de banda adecuado.</span><span class="sxs-lookup"><span data-stu-id="b0b1c-112">These two sites require an intersite policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="b0b1c-113">En el siguiente ejemplo se aplica\_el perfil de vínculo de 20 MB.</span><span class="sxs-lookup"><span data-stu-id="b0b1c-113">The following example applies the 20Mb\_Link profile.</span></span>

<div>

## <a name="to-create-a-network-intersite-policy"></a><span data-ttu-id="b0b1c-114">Para crear una directiva de intersitios de red</span><span class="sxs-lookup"><span data-stu-id="b0b1c-114">To create a network intersite policy</span></span>

1.  <span data-ttu-id="b0b1c-115">Inicie el shell de administración de Lync Server: haga clic en **Inicio**, seleccione **todos los programas**, **Microsoft Lync Server 2013**y, a continuación, haga clic en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b0b1c-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b0b1c-116">Ejecute el cmdlet New-CsNetworkInterSitePolicy para crear directivas entre sitios de red y aplicar un perfil de directiva de ancho de banda adecuado para dos sitios que tengan un vínculo cruzado directo.</span><span class="sxs-lookup"><span data-stu-id="b0b1c-116">Run the New-CsNetworkInterSitePolicy cmdlet to create network intersite policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link.</span></span> <span data-ttu-id="b0b1c-117">Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b0b1c-117">For example, run:</span></span>
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  <span data-ttu-id="b0b1c-118">Repita el paso 2 según sea necesario para crear directivas de intersitios de red para todas las parejas de sitios de red con vínculos cruzados directos.</span><span class="sxs-lookup"><span data-stu-id="b0b1c-118">Repeat step 2 as needed to create network intersite policies for all network sites pairs that have a direct cross link.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

