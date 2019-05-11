---
title: Tabla UserSite
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: En la tabla UserSite es una tabla de apoyo. Cada registro representa un sitio de usuario definido en la opción de configuración de red.
ms.openlocfilehash: 519cedc35c03fd9bcb5479ea3cecf75ec617917c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906956"
---
# <a name="usersite-table"></a><span data-ttu-id="368db-104">Tabla UserSite</span><span class="sxs-lookup"><span data-stu-id="368db-104">UserSite table</span></span>
 
<span data-ttu-id="368db-105">En la tabla UserSite es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="368db-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="368db-106">Cada registro representa un sitio de usuario definido en la opción de configuración de red.</span><span class="sxs-lookup"><span data-stu-id="368db-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="368db-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="368db-107">**Column**</span></span>|<span data-ttu-id="368db-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="368db-108">**Data Type**</span></span>|<span data-ttu-id="368db-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="368db-109">**Key/Index**</span></span>|<span data-ttu-id="368db-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="368db-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="368db-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="368db-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="368db-112">int</span><span class="sxs-lookup"><span data-stu-id="368db-112">int</span></span>  <br/> |<span data-ttu-id="368db-113">Primary</span><span class="sxs-lookup"><span data-stu-id="368db-113">Primary</span></span>  <br/> |<span data-ttu-id="368db-114">Número único que identifica el sitio del usuario.</span><span class="sxs-lookup"><span data-stu-id="368db-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="368db-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="368db-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="368db-116">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="368db-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="368db-117">Único</span><span class="sxs-lookup"><span data-stu-id="368db-117">Unique</span></span>  <br/> |<span data-ttu-id="368db-118">Nombre del sitio de usuario.</span><span class="sxs-lookup"><span data-stu-id="368db-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="368db-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="368db-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="368db-120">int</span><span class="sxs-lookup"><span data-stu-id="368db-120">int</span></span>  <br/> |<span data-ttu-id="368db-121">Externa</span><span class="sxs-lookup"><span data-stu-id="368db-121">Foreign</span></span>  <br/> |<span data-ttu-id="368db-122">Referencia de la [tabla de región](region.md).</span><span class="sxs-lookup"><span data-stu-id="368db-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

