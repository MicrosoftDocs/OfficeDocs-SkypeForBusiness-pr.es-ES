---
title: Agregar una directiva de ubicación a un sitio de red en Skype empresarial Server
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Asignar directivas de ubicación E9-1-1 a los sitios de red en la telefonía IP empresarial de Skype empresarial.
ms.openlocfilehash: 4a74b1ee44d1e2f34a51d7859235e10649d0e2ee
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233870"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a><span data-ttu-id="6003c-103">Agregar una directiva de ubicación a un sitio de red en Skype empresarial Server</span><span class="sxs-lookup"><span data-stu-id="6003c-103">Add a location policy to a network site in Skype for Business Server</span></span>
 
<span data-ttu-id="6003c-104">Asignar directivas de ubicación E9-1-1 a los sitios de red en la telefonía IP empresarial de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="6003c-104">Assign E9-1-1 location policies to network sites in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="6003c-105">En los siguientes ejemplos se muestra cómo agregar la Directiva de ubicación de **Redmond** definida en [crear directivas de ubicación en Skype empresarial Server](create-location-policies.md) a un sitio de red existente y cómo crear un nuevo sitio de red que use la Directiva de ubicación de **Redmond** .</span><span class="sxs-lookup"><span data-stu-id="6003c-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Skype for Business Server](create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>
  
<span data-ttu-id="6003c-106">Para obtener más información sobre cómo trabajar con sitios de red, consulte la documentación del shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="6003c-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>
  
- <span data-ttu-id="6003c-107">**New-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="6003c-107">**New-CsNetworkSite**</span></span>
    
- <span data-ttu-id="6003c-108">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="6003c-108">**Get-CsNetworkSite**</span></span>
    
- <span data-ttu-id="6003c-109">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="6003c-109">**Set-CsNetworkSite**</span></span>
    
- <span data-ttu-id="6003c-110">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="6003c-110">**Remove-CsNetworkSite**</span></span>
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="6003c-111">Para asignar una directiva de ubicación a un sitio de red existente</span><span class="sxs-lookup"><span data-stu-id="6003c-111">To assign a location policy to an existing network site</span></span>

1. <span data-ttu-id="6003c-112">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="6003c-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="6003c-113">Ejecute los siguientes cmdlets para modificar un sitio de red existente.</span><span class="sxs-lookup"><span data-stu-id="6003c-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="6003c-114">Asigne la directiva de ubicación con la etiqueta **Redmond** a un sitio de red existente denominado **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="6003c-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
   ```
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="6003c-115">Para asignar una directiva de ubicación a un nuevo sitio de red</span><span class="sxs-lookup"><span data-stu-id="6003c-115">To assign a location policy to a new network site</span></span>

1. <span data-ttu-id="6003c-116">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="6003c-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="6003c-117">Ejecute el siguiente cmdlet para crear un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="6003c-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="6003c-118">Cree el sitio de red en la región de red y asígnele la directiva de ubicación con la etiqueta **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="6003c-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
   ```
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


