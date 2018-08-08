---
title: Agregar una directiva de ubicación a un sitio de red en Skype para Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Asignar directivas de ubicación de E9-1-1 a los sitios de red de Skype para Business Server Enterprise Voice.
ms.openlocfilehash: 862b6d91371199fe3f9380acf7e2898539153f28
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2018
ms.locfileid: "20979828"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a><span data-ttu-id="14bb4-103">Agregar una directiva de ubicación a un sitio de red en Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="14bb4-103">Add a location policy to a network site in Skype for Business Server</span></span>
 
<span data-ttu-id="14bb4-104">Asignar directivas de ubicación de E9-1-1 a los sitios de red de Skype para Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="14bb4-104">Assign E9-1-1 location policies to network sites in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="14bb4-105">Los siguientes ejemplos muestran cómo agregar la directiva de ubicación de **Redmond** definida en [las directivas de ubicación de crear de Skype para Business Server](create-location-policies.md) a un sitio de red existente y cómo crear un nuevo sitio de red que usa la directiva de ubicación de **Redmond** .</span><span class="sxs-lookup"><span data-stu-id="14bb4-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Skype for Business Server](create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>
  
<span data-ttu-id="14bb4-106">Para obtener información detallada sobre cómo trabajar con sitios de red, consulte la documentación del Shell de administración de Lync Server para los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="14bb4-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>
  
- <span data-ttu-id="14bb4-107">**New-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="14bb4-107">**New-CsNetworkSite**</span></span>
    
- <span data-ttu-id="14bb4-108">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="14bb4-108">**Get-CsNetworkSite**</span></span>
    
- <span data-ttu-id="14bb4-109">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="14bb4-109">**Set-CsNetworkSite**</span></span>
    
- <span data-ttu-id="14bb4-110">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="14bb4-110">**Remove-CsNetworkSite**</span></span>
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="14bb4-111">Para asignar una directiva de ubicación a un sitio de red existente</span><span class="sxs-lookup"><span data-stu-id="14bb4-111">To assign a location policy to an existing network site</span></span>

1. <span data-ttu-id="14bb4-112">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="14bb4-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="14bb4-113">Ejecute los siguientes cmdlets para modificar un sitio de red existente.</span><span class="sxs-lookup"><span data-stu-id="14bb4-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="14bb4-114">Asigne la directiva de ubicación con la etiqueta **Redmond** a un sitio de red existente denominado **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="14bb4-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
  ```
  Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
  ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="14bb4-115">Para asignar una directiva de ubicación a un nuevo sitio de red</span><span class="sxs-lookup"><span data-stu-id="14bb4-115">To assign a location policy to a new network site</span></span>

1. <span data-ttu-id="14bb4-116">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="14bb4-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="14bb4-117">Ejecute el siguiente cmdlet para crear un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="14bb4-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="14bb4-118">Cree el sitio de red en la región de red y asígnele la directiva de ubicación con la etiqueta **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="14bb4-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
   ```
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


