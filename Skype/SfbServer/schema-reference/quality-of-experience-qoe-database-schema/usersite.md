---
title: Tabla UserSite
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: La tabla UserSite es una tabla de soporte. Cada registro representa un sitio de usuario definido en la configuración de red.
ms.openlocfilehash: 21f60afdb1690024f85dc74e11f856642413e6a8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294575"
---
# <a name="usersite-table"></a><span data-ttu-id="b7d52-104">Tabla UserSite</span><span class="sxs-lookup"><span data-stu-id="b7d52-104">UserSite table</span></span>
 
<span data-ttu-id="b7d52-105">La tabla UserSite es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="b7d52-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="b7d52-106">Cada registro representa un sitio de usuario definido en la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="b7d52-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="b7d52-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="b7d52-107">**Column**</span></span>|<span data-ttu-id="b7d52-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="b7d52-108">**Data Type**</span></span>|<span data-ttu-id="b7d52-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="b7d52-109">**Key/Index**</span></span>|<span data-ttu-id="b7d52-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="b7d52-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b7d52-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="b7d52-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="b7d52-112">int</span><span class="sxs-lookup"><span data-stu-id="b7d52-112">int</span></span>  <br/> |<span data-ttu-id="b7d52-113">Primary</span><span class="sxs-lookup"><span data-stu-id="b7d52-113">Primary</span></span>  <br/> |<span data-ttu-id="b7d52-114">Número único que identifica el sitio del usuario.</span><span class="sxs-lookup"><span data-stu-id="b7d52-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="b7d52-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="b7d52-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="b7d52-116">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="b7d52-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="b7d52-117">Solo</span><span class="sxs-lookup"><span data-stu-id="b7d52-117">Unique</span></span>  <br/> |<span data-ttu-id="b7d52-118">Nombre del sitio del usuario.</span><span class="sxs-lookup"><span data-stu-id="b7d52-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="b7d52-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="b7d52-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="b7d52-120">int</span><span class="sxs-lookup"><span data-stu-id="b7d52-120">int</span></span>  <br/> |<span data-ttu-id="b7d52-121">Extranjero</span><span class="sxs-lookup"><span data-stu-id="b7d52-121">Foreign</span></span>  <br/> |<span data-ttu-id="b7d52-122">[Tabla de regiones](region.md)a la que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="b7d52-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

