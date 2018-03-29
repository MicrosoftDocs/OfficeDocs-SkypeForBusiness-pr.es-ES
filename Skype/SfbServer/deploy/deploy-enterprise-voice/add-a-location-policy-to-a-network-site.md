---
title: Agregar una directiva de ubicación a un sitio de red en Skype Empresarial Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Asignar directivas de ubicación de E9-1-1 a los sitios de la red de Skype para Telefonía IP empresarial de Business Server.
ms.openlocfilehash: bf2b8675ebaa14e98f8a362b3a0714037000de95
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server-2015"></a><span data-ttu-id="d765a-103">Agregar una directiva de ubicación a un sitio de red en Skype Empresarial Server 2015</span><span class="sxs-lookup"><span data-stu-id="d765a-103">Add a location policy to a network site in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d765a-104">Asignar directivas de ubicación de E9-1-1 a los sitios de la red de Skype para Telefonía IP empresarial de Business Server.</span><span class="sxs-lookup"><span data-stu-id="d765a-104">Assign E9-1-1 location policies to network sites in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="d765a-105">Los ejemplos siguientes muestran cómo agregar la directiva de ubicación de **Redmond** definida en [las políticas de ubicación de crear en Skype para Business Server 2015](create-location-policies.md) a un sitio de red existente y cómo crear un nuevo sitio de red que utiliza la ubicación de **Redmond** Directiva.</span><span class="sxs-lookup"><span data-stu-id="d765a-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Skype for Business Server 2015](create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>
  
<span data-ttu-id="d765a-106">Para obtener más información acerca de cómo trabajar con sitios de red, consulte la documentación de Shell de administración de Lync Server para los siguientes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="d765a-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>
  
- <span data-ttu-id="d765a-107">**Nueva CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="d765a-107">**New-CsNetworkSite**</span></span>
    
- <span data-ttu-id="d765a-108">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="d765a-108">**Get-CsNetworkSite**</span></span>
    
- <span data-ttu-id="d765a-109">**Conjunto de CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="d765a-109">**Set-CsNetworkSite**</span></span>
    
- <span data-ttu-id="d765a-110">**Quitar CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="d765a-110">**Remove-CsNetworkSite**</span></span>
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="d765a-111">Para asignar una directiva de ubicación a un sitio de red existente</span><span class="sxs-lookup"><span data-stu-id="d765a-111">To assign a location policy to an existing network site</span></span>

1. <span data-ttu-id="d765a-112">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="d765a-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d765a-113">Ejecute los siguientes cmdlets para modificar un sitio de red existente.</span><span class="sxs-lookup"><span data-stu-id="d765a-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="d765a-114">Asigne la directiva de ubicación con la etiqueta **Redmond** a un sitio de red existente denominado **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="d765a-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
  ```
  Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"

  ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="d765a-115">Para asignar una directiva de ubicación a un nuevo sitio de red</span><span class="sxs-lookup"><span data-stu-id="d765a-115">To assign a location policy to a new network site</span></span>

1. <span data-ttu-id="d765a-116">Inicie el Shell de administración de Skype Empresarial Server: haga clic en **Inicio**, **Todos los programas**, **Skype Empresarial Server 2015** y, después, en **Shell de administración de Skype Empresarial Server**.</span><span class="sxs-lookup"><span data-stu-id="d765a-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d765a-117">Ejecute el siguiente cmdlet para crear un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="d765a-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="d765a-118">Cree el sitio de red en la región de red y asígnele la directiva de ubicación con la etiqueta **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="d765a-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
   ```
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


