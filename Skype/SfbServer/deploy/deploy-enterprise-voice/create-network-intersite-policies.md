---
title: Crear directivas entre sitios de red en Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Cree directivas entre sitios de red, que se usan en Telefonía IP empresarial control de admisión de llamadas en Skype Empresarial Server.
ms.openlocfilehash: 69609da75fdfa87309743920eace59892a440f2b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822480"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a><span data-ttu-id="4ba91-103">Crear directivas entre sitios de red en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="4ba91-103">Create network intersite policies in Skype for Business Server</span></span>
 
<span data-ttu-id="4ba91-104">Cree directivas entre sitios de red, que se usan en Telefonía IP empresarial control de admisión de llamadas en Skype Empresarial Server.</span><span class="sxs-lookup"><span data-stu-id="4ba91-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="4ba91-105">Una directiva entre sitios de red define las limitaciones de ancho de banda entre sitios que tienen vínculos WAN directos entre ellos.</span><span class="sxs-lookup"><span data-stu-id="4ba91-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4ba91-106">Solo se requiere una  directiva entre sitios de red si hay un vínculo cruzado directo entre dos sitios de red.</span><span class="sxs-lookup"><span data-stu-id="4ba91-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="4ba91-107">En la topología de ejemplo de la región de Norteamérica, hay un vínculo directo entre los sitios de Reno y Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="4ba91-107">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="4ba91-108">Estos dos sitios requieren una directiva entre sitios que aplique un perfil de directiva de ancho de banda adecuado.</span><span class="sxs-lookup"><span data-stu-id="4ba91-108">These two sites require an inter-site policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="4ba91-109">En el siguiente ejemplo se aplica el perfil 20Mb_Link.</span><span class="sxs-lookup"><span data-stu-id="4ba91-109">The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="4ba91-110">Para crear una directiva entre sitios de red</span><span class="sxs-lookup"><span data-stu-id="4ba91-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="4ba91-111">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="4ba91-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="4ba91-112">Ejecute el cmdlet New-CsNetworkInterSitePolicy para crear directivas entre sitios de red y aplicar un perfil de directiva de ancho de banda adecuado para dos sitios que tienen un vínculo cruzado directo.</span><span class="sxs-lookup"><span data-stu-id="4ba91-112">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link.</span></span> <span data-ttu-id="4ba91-113">Por ejemplo, ejecute:</span><span class="sxs-lookup"><span data-stu-id="4ba91-113">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="4ba91-114">Repita el paso 2 según sea necesario para crear directivas entre sitios de red para todos los pares de sitios de red que tengan un vínculo cruzado directo.</span><span class="sxs-lookup"><span data-stu-id="4ba91-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4ba91-115">Ver también</span><span class="sxs-lookup"><span data-stu-id="4ba91-115">See also</span></span>

[<span data-ttu-id="4ba91-116">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="4ba91-116">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="4ba91-117">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="4ba91-117">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="4ba91-118">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="4ba91-118">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="4ba91-119">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="4ba91-119">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
