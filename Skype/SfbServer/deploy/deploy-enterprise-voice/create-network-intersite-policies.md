---
title: Crear directivas entre sitios de red en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Crear red directivas entre sitios, que son utilizadas por el control de admisión de llamadas de Telefonía IP empresarial en Skype para Business Server.
ms.openlocfilehash: 73eee49022f039bf1bd36d1a06176fa94f3ef3f7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="create-network-intersite-policies-in-skype-for-business-server-2015"></a><span data-ttu-id="a3de6-103">Crear directivas entre sitios de red en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="a3de6-103">Create network intersite policies in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a3de6-104">Crear red directivas entre sitios, que son utilizadas por el control de admisión de llamadas de Telefonía IP empresarial en Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="a3de6-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="a3de6-105">Una directiva de red entre sitios define las limitaciones de ancho de banda entre sitios que tienen vínculos WAN directas entre ellos.</span><span class="sxs-lookup"><span data-stu-id="a3de6-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a3de6-106">Una directiva de red entre sitios es necesaria *sólo* si hay un vínculo cruzado directo entre dos sitios de red.</span><span class="sxs-lookup"><span data-stu-id="a3de6-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="a3de6-p101">En la topología de ejemplo de la región de Norteamérica, hay un vínculo directo entre los sitios de Reno y Albuquerque. Estos dos sitios requieren una directiva entre sitios que aplique un perfil de directiva de ancho de banda adecuado. En el siguiente ejemplo se aplica el perfil 20Mb_Link.</span><span class="sxs-lookup"><span data-stu-id="a3de6-p101">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites. These two sites require an inter-site policy that applies an appropriate bandwidth policy profile. The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="a3de6-110">Para crear una directiva entre sitios de red</span><span class="sxs-lookup"><span data-stu-id="a3de6-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="a3de6-111">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="a3de6-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="a3de6-p102">Ejecute el cmdlet New-CsNetworkInterSitePolicy para crear directivas entre sitios de red y aplicar un perfil de directiva de ancho de banda adecuado para dos sitios que tienen un vínculo cruzado directo. Por ejemplo, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a3de6-p102">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link. For example, run:</span></span>
    
   ```
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="a3de6-114">Repita el paso 2 según sea necesario para crear directivas entre sitios de red para todos los pares de sitios de red que tengan un vínculo cruzado directo.</span><span class="sxs-lookup"><span data-stu-id="a3de6-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a3de6-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3de6-115">See also</span></span>

#### 

[<span data-ttu-id="a3de6-116">Nueva CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="a3de6-116">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="a3de6-117">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="a3de6-117">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="a3de6-118">Conjunto de CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="a3de6-118">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="a3de6-119">Quitar CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="a3de6-119">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)

