---
title: Agregar una directiva de ubicación a un sitio de red en Skype Empresarial Server
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Asigne directivas de ubicación E9-1-1 a sitios de red en Skype Empresarial Server Telefonía IP empresarial.
ms.openlocfilehash: 887c2fcab63acd5d143ba80f6be6976e8fe2b39f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804280"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a><span data-ttu-id="dc501-103">Agregar una directiva de ubicación a un sitio de red en Skype Empresarial Server</span><span class="sxs-lookup"><span data-stu-id="dc501-103">Add a location policy to a network site in Skype for Business Server</span></span>
 
<span data-ttu-id="dc501-104">Asigne directivas de ubicación E9-1-1 a sitios de red en Skype Empresarial Server Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="dc501-104">Assign E9-1-1 location policies to network sites in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="dc501-105">Los ejemplos siguientes muestran cómo agregar la directiva de ubicación **de Redmond** definida en Crear directivas de ubicación en Skype Empresarial [Server](create-location-policies.md) a un sitio de red existente y cómo crear un nuevo sitio de red que use la directiva de ubicación **redmond.**</span><span class="sxs-lookup"><span data-stu-id="dc501-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Skype for Business Server](create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>
  
<span data-ttu-id="dc501-106">Para obtener más información sobre cómo trabajar con sitios de red, consulte la documentación del Shell de administración de Lync Server para los cmdlets siguientes:</span><span class="sxs-lookup"><span data-stu-id="dc501-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>
  
- <span data-ttu-id="dc501-107">**New-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="dc501-107">**New-CsNetworkSite**</span></span>
    
- <span data-ttu-id="dc501-108">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="dc501-108">**Get-CsNetworkSite**</span></span>
    
- <span data-ttu-id="dc501-109">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="dc501-109">**Set-CsNetworkSite**</span></span>
    
- <span data-ttu-id="dc501-110">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="dc501-110">**Remove-CsNetworkSite**</span></span>
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="dc501-111">Para asignar una directiva de ubicación a un sitio de red existente</span><span class="sxs-lookup"><span data-stu-id="dc501-111">To assign a location policy to an existing network site</span></span>

1. <span data-ttu-id="dc501-112">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="dc501-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="dc501-113">Ejecute los siguientes cmdlets para modificar un sitio de red existente.</span><span class="sxs-lookup"><span data-stu-id="dc501-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="dc501-114">Asigne la **directiva de ubicación etiquetada redmond** a un sitio de red existente denominado **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="dc501-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="dc501-115">Para asignar una directiva de ubicación a un nuevo sitio de red</span><span class="sxs-lookup"><span data-stu-id="dc501-115">To assign a location policy to a new network site</span></span>

1. <span data-ttu-id="dc501-116">Inicie el Shell de administración de Skype Empresarial Server: Haga clic en **Inicio,** en Todos los **programas,** **en Skype Empresarial 2015** y, a continuación, en Shell de administración de Skype Empresarial **Server.**</span><span class="sxs-lookup"><span data-stu-id="dc501-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="dc501-117">Ejecute el siguiente cmdlet para crear un sitio de red.</span><span class="sxs-lookup"><span data-stu-id="dc501-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="dc501-118">Cree el sitio de red en la región de red y asígnele la directiva de ubicación con la etiqueta **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="dc501-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


