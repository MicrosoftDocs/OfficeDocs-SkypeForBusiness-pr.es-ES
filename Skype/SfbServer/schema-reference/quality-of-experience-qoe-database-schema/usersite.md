---
title: Tabla UserSite
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: En la tabla UserSite es una tabla de apoyo. Cada registro representa un sitio de usuario definido en la opción de configuración de red.
ms.openlocfilehash: a52f5cd9aa7059e2b545dec3bcc7ccb86191347a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212049"
---
# <a name="usersite-table"></a><span data-ttu-id="6070b-104">Tabla UserSite</span><span class="sxs-lookup"><span data-stu-id="6070b-104">UserSite table</span></span>
 
<span data-ttu-id="6070b-105">En la tabla UserSite es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="6070b-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="6070b-106">Cada registro representa un sitio de usuario definido en la opción de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="6070b-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="6070b-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="6070b-107">**Column**</span></span>|<span data-ttu-id="6070b-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6070b-108">**Data Type**</span></span>|<span data-ttu-id="6070b-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="6070b-109">**Key/Index**</span></span>|<span data-ttu-id="6070b-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="6070b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6070b-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="6070b-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="6070b-112">int</span><span class="sxs-lookup"><span data-stu-id="6070b-112">int</span></span>  <br/> |<span data-ttu-id="6070b-113">Primary</span><span class="sxs-lookup"><span data-stu-id="6070b-113">Primary</span></span>  <br/> |<span data-ttu-id="6070b-114">Número único que identifica el sitio del usuario.</span><span class="sxs-lookup"><span data-stu-id="6070b-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="6070b-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="6070b-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="6070b-116">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="6070b-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="6070b-117">Único</span><span class="sxs-lookup"><span data-stu-id="6070b-117">Unique</span></span>  <br/> |<span data-ttu-id="6070b-118">Nombre del sitio de usuario.</span><span class="sxs-lookup"><span data-stu-id="6070b-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="6070b-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="6070b-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="6070b-120">int</span><span class="sxs-lookup"><span data-stu-id="6070b-120">int</span></span>  <br/> |<span data-ttu-id="6070b-121">Externa</span><span class="sxs-lookup"><span data-stu-id="6070b-121">Foreign</span></span>  <br/> |<span data-ttu-id="6070b-122">Referencia de la [tabla de región](region.md).</span><span class="sxs-lookup"><span data-stu-id="6070b-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

