---
title: Tabla UserSite
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: La tabla UserSite es una tabla compatible. Cada registro representa un sitio de usuario definido en la configuración de red.
ms.openlocfilehash: 88df08875ea3254ee355a96aa3b12d3ee7f5ccaf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799920"
---
# <a name="usersite-table"></a><span data-ttu-id="6befa-104">Tabla UserSite</span><span class="sxs-lookup"><span data-stu-id="6befa-104">UserSite table</span></span>
 
<span data-ttu-id="6befa-105">La tabla UserSite es una tabla compatible.</span><span class="sxs-lookup"><span data-stu-id="6befa-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="6befa-106">Cada registro representa un sitio de usuario definido en la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="6befa-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="6befa-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="6befa-107">**Column**</span></span>|<span data-ttu-id="6befa-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6befa-108">**Data Type**</span></span>|<span data-ttu-id="6befa-109">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="6befa-109">**Key/Index**</span></span>|<span data-ttu-id="6befa-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="6befa-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6befa-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="6befa-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="6befa-112">entero</span><span class="sxs-lookup"><span data-stu-id="6befa-112">int</span></span>  <br/> |<span data-ttu-id="6befa-113">Principal</span><span class="sxs-lookup"><span data-stu-id="6befa-113">Primary</span></span>  <br/> |<span data-ttu-id="6befa-114">Número único que identifica el sitio de usuario.</span><span class="sxs-lookup"><span data-stu-id="6befa-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="6befa-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="6befa-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="6befa-116">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="6befa-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="6befa-117">Única</span><span class="sxs-lookup"><span data-stu-id="6befa-117">Unique</span></span>  <br/> |<span data-ttu-id="6befa-118">Nombre del sitio de usuario.</span><span class="sxs-lookup"><span data-stu-id="6befa-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="6befa-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="6befa-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="6befa-120">entero</span><span class="sxs-lookup"><span data-stu-id="6befa-120">int</span></span>  <br/> |<span data-ttu-id="6befa-121">Externo</span><span class="sxs-lookup"><span data-stu-id="6befa-121">Foreign</span></span>  <br/> |<span data-ttu-id="6befa-122">Referencia de la [tabla Región](region.md).</span><span class="sxs-lookup"><span data-stu-id="6befa-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

