---
title: Crear directivas de red entre sitios en Skype empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Cree directivas de red entre sitios, que usan el control de admisión de llamadas de telefonía de empresa en Skype empresarial Server.
ms.openlocfilehash: ac03057de5b6e25e2b9de812f0d53ae02811d456
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233485"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a><span data-ttu-id="e068a-103">Crear directivas de red entre sitios en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="e068a-103">Create network intersite policies in Skype for Business Server</span></span>
 
<span data-ttu-id="e068a-104">Cree directivas de red entre sitios, que usan el control de admisión de llamadas de telefonía de empresa en Skype empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="e068a-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="e068a-105">Una directiva entre sitios de red define las limitaciones de ancho de banda entre sitios que tienen vínculos WAN entre ellos.</span><span class="sxs-lookup"><span data-stu-id="e068a-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e068a-106">Una directiva de red entre sitios *solo* es necesaria si hay un vínculo cruzado directo entre dos sitios de red.</span><span class="sxs-lookup"><span data-stu-id="e068a-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="e068a-p101">En la topología de ejemplo de la región de Norteamérica, hay un vínculo directo entre los sitios de Reno y Albuquerque. Estos dos sitios requieren una directiva entre sitios que aplique un perfil de directiva de ancho de banda adecuado. En el siguiente ejemplo se aplica el perfil 20Mb_Link.</span><span class="sxs-lookup"><span data-stu-id="e068a-p101">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites. These two sites require an inter-site policy that applies an appropriate bandwidth policy profile. The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="e068a-110">Para crear una directiva entre sitios de red</span><span class="sxs-lookup"><span data-stu-id="e068a-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="e068a-111">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="e068a-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="e068a-p102">Ejecute el cmdlet New-CsNetworkInterSitePolicy para crear directivas entre sitios de red y aplicar un perfil de directiva de ancho de banda adecuado para dos sitios que tienen un vínculo cruzado directo. Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="e068a-p102">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link. For example, run:</span></span>
    
   ```
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="e068a-114">Repita el paso 2 según sea necesario para crear directivas entre sitios de red para todos los pares de sitios de red que tengan un vínculo cruzado directo.</span><span class="sxs-lookup"><span data-stu-id="e068a-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="e068a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="e068a-115">See also</span></span>

[<span data-ttu-id="e068a-116">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="e068a-116">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="e068a-117">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="e068a-117">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="e068a-118">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="e068a-118">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="e068a-119">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="e068a-119">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
