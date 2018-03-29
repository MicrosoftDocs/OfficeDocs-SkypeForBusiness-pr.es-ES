---
title: Tabla UserSite
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: La tabla UserSite es un auxiliar. Cada registro representa un sitio de usuario definido en la configuración de red.
ms.openlocfilehash: effc2404a91bf122dc9be9ad371372e8355b230f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="usersite-table"></a><span data-ttu-id="1e0e4-104">Tabla UserSite</span><span class="sxs-lookup"><span data-stu-id="1e0e4-104">UserSite table</span></span>
 
<span data-ttu-id="1e0e4-105">La tabla UserSite es un auxiliar.</span><span class="sxs-lookup"><span data-stu-id="1e0e4-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="1e0e4-106">Cada registro representa un sitio de usuario definido en la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="1e0e4-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="1e0e4-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="1e0e4-107">**Column**</span></span>|<span data-ttu-id="1e0e4-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="1e0e4-108">**Data Type**</span></span>|<span data-ttu-id="1e0e4-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="1e0e4-109">**Key/Index**</span></span>|<span data-ttu-id="1e0e4-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="1e0e4-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1e0e4-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="1e0e4-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="1e0e4-112">int</span><span class="sxs-lookup"><span data-stu-id="1e0e4-112">int</span></span>  <br/> |<span data-ttu-id="1e0e4-113">Primary</span><span class="sxs-lookup"><span data-stu-id="1e0e4-113">Primary</span></span>  <br/> |<span data-ttu-id="1e0e4-114">Número único que identifica el sitio del usuario.</span><span class="sxs-lookup"><span data-stu-id="1e0e4-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="1e0e4-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="1e0e4-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="1e0e4-116">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="1e0e4-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="1e0e4-117">Único</span><span class="sxs-lookup"><span data-stu-id="1e0e4-117">Unique</span></span>  <br/> |<span data-ttu-id="1e0e4-118">Nombre del sitio del usuario.</span><span class="sxs-lookup"><span data-stu-id="1e0e4-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="1e0e4-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="1e0e4-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="1e0e4-120">int</span><span class="sxs-lookup"><span data-stu-id="1e0e4-120">int</span></span>  <br/> |<span data-ttu-id="1e0e4-121">Externa</span><span class="sxs-lookup"><span data-stu-id="1e0e4-121">Foreign</span></span>  <br/> |<span data-ttu-id="1e0e4-122">Referencia de [tabla de la región](region.md).</span><span class="sxs-lookup"><span data-stu-id="1e0e4-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

