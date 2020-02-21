---
title: 'Lync Server 2013: crear directivas entre sitios de red'
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
ms.openlocfilehash: ae7024aa0a9f5c5734762ed0accb6e1dc723f2b9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205606"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-network-intersite-policies-in-lync-server-2013"></a><span data-ttu-id="b9bfa-102">Crear directivas entre sitios de red en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9bfa-102">Create network intersite policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9bfa-103">_**Última modificación del tema:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="b9bfa-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="b9bfa-104">Una *directiva entre sitios de red* define las limitaciones de ancho de banda entre sitios que tienen vínculos WAN entre ellos.</span><span class="sxs-lookup"><span data-stu-id="b9bfa-104">A *network intersite policy* defines bandwidth limitations between sites that have direct WAN links between them.</span></span>

<span data-ttu-id="b9bfa-105">Para obtener más información, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="b9bfa-105">For details, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="b9bfa-106">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="b9bfa-106">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="b9bfa-107">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="b9bfa-107">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="b9bfa-108">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="b9bfa-108">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [<span data-ttu-id="b9bfa-109">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="b9bfa-109">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b9bfa-110">Una directiva entre sitios de red <EM>solo</EM> se necesita si hay un vínculo cruzado directo entre dos sitios de red.</span><span class="sxs-lookup"><span data-stu-id="b9bfa-110">A network intersite policy is required <EM>only</EM> if there is a direct cross link between two network sites.</span></span>



</div>

<span data-ttu-id="b9bfa-111">En la topología de ejemplo de la región de Norteamérica, hay un vínculo directo entre los sitios de Reno y Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="b9bfa-111">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="b9bfa-112">Estos dos sitios requieren una directiva entre sitios que aplique un perfil de directiva de ancho de banda adecuado.</span><span class="sxs-lookup"><span data-stu-id="b9bfa-112">These two sites require an intersite policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="b9bfa-113">En el siguiente ejemplo, se\_aplica el perfil de vínculo de 20 MB.</span><span class="sxs-lookup"><span data-stu-id="b9bfa-113">The following example applies the 20Mb\_Link profile.</span></span>

<div>

## <a name="to-create-a-network-intersite-policy"></a><span data-ttu-id="b9bfa-114">Para crear una directiva entre sitios de red</span><span class="sxs-lookup"><span data-stu-id="b9bfa-114">To create a network intersite policy</span></span>

1.  <span data-ttu-id="b9bfa-115">Inicie el Shell de administración de Lync Server: haga clic en **Inicio**, **Todos los programas**, **Microsoft Lync Server 2013** y después en **Shell de administración de Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b9bfa-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b9bfa-p102">Ejecute el cmdlet New-CsNetworkInterSitePolicy para crear directivas entre sitios de red y aplicar un perfil de directiva de ancho de banda adecuado para dos sitios que tienen un vínculo cruzado directo. Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="b9bfa-p102">Run the New-CsNetworkInterSitePolicy cmdlet to create network intersite policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link. For example, run:</span></span>
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  <span data-ttu-id="b9bfa-118">Repita el paso 2 según sea necesario para crear directivas entre sitios de red para todos los pares de sitios de red que tengan un vínculo cruzado directo.</span><span class="sxs-lookup"><span data-stu-id="b9bfa-118">Repeat step 2 as needed to create network intersite policies for all network sites pairs that have a direct cross link.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

