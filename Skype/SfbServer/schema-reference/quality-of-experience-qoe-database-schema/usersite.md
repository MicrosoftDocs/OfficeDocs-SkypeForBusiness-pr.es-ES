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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: La tabla UserSite es una tabla de soporte. Cada registro representa un sitio de usuario definido en la configuración de red.
ms.openlocfilehash: e1d6c4ddc3a756f2e5df0713d6abe1cb7b61295f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805008"
---
# <a name="usersite-table"></a><span data-ttu-id="07944-104">Tabla UserSite</span><span class="sxs-lookup"><span data-stu-id="07944-104">UserSite table</span></span>
 
<span data-ttu-id="07944-105">La tabla UserSite es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="07944-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="07944-106">Cada registro representa un sitio de usuario definido en la configuración de red.</span><span class="sxs-lookup"><span data-stu-id="07944-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="07944-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="07944-107">**Column**</span></span>|<span data-ttu-id="07944-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="07944-108">**Data Type**</span></span>|<span data-ttu-id="07944-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="07944-109">**Key/Index**</span></span>|<span data-ttu-id="07944-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="07944-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="07944-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="07944-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="07944-112">int</span><span class="sxs-lookup"><span data-stu-id="07944-112">int</span></span>  <br/> |<span data-ttu-id="07944-113">Primary</span><span class="sxs-lookup"><span data-stu-id="07944-113">Primary</span></span>  <br/> |<span data-ttu-id="07944-114">Número único que identifica el sitio del usuario.</span><span class="sxs-lookup"><span data-stu-id="07944-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="07944-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="07944-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="07944-116">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="07944-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="07944-117">Solo</span><span class="sxs-lookup"><span data-stu-id="07944-117">Unique</span></span>  <br/> |<span data-ttu-id="07944-118">Nombre del sitio del usuario.</span><span class="sxs-lookup"><span data-stu-id="07944-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="07944-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="07944-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="07944-120">int</span><span class="sxs-lookup"><span data-stu-id="07944-120">int</span></span>  <br/> |<span data-ttu-id="07944-121">Extranjero</span><span class="sxs-lookup"><span data-stu-id="07944-121">Foreign</span></span>  <br/> |<span data-ttu-id="07944-122">[Tabla de regiones](region.md)a la que se hace referencia.</span><span class="sxs-lookup"><span data-stu-id="07944-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

