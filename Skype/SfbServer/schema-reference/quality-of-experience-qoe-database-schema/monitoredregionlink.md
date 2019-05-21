---
title: Tabla MonitoredRegionLink
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: La tabla MonitoredRegionLink es una tabla de soporte. Cada registro representa un vínculo entre dos países o regiones.
ms.openlocfilehash: fdace97e0a7c9685f59471074cca64ede4fcc63d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294876"
---
# <a name="monitoredregionlink-table"></a><span data-ttu-id="f6b4e-104">Tabla MonitoredRegionLink</span><span class="sxs-lookup"><span data-stu-id="f6b4e-104">MonitoredRegionLink table</span></span>
 
<span data-ttu-id="f6b4e-105">La tabla MonitoredRegionLink es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="f6b4e-105">The MonitoredRegionLink table is a supporting table.</span></span> <span data-ttu-id="f6b4e-106">Cada registro representa un vínculo entre dos países o regiones.</span><span class="sxs-lookup"><span data-stu-id="f6b4e-106">Each record represents one link between two countries/regions.</span></span>
  
|<span data-ttu-id="f6b4e-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="f6b4e-107">**Column**</span></span>|<span data-ttu-id="f6b4e-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f6b4e-108">**Data Type**</span></span>|<span data-ttu-id="f6b4e-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="f6b4e-109">**Key/Index**</span></span>|<span data-ttu-id="f6b4e-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="f6b4e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f6b4e-111">**Region1Key**</span><span class="sxs-lookup"><span data-stu-id="f6b4e-111">**Region1Key**</span></span> <br/> |<span data-ttu-id="f6b4e-112">int</span><span class="sxs-lookup"><span data-stu-id="f6b4e-112">int</span></span>  <br/> |<span data-ttu-id="f6b4e-113">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="f6b4e-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="f6b4e-114">Se hace referencia a ella desde la [tabla region](region.md).</span><span class="sxs-lookup"><span data-stu-id="f6b4e-114">Referenced from the [Region table](region.md).</span></span>  <br/> |
|<span data-ttu-id="f6b4e-115">**Region2Key**</span><span class="sxs-lookup"><span data-stu-id="f6b4e-115">**Region2Key**</span></span> <br/> |<span data-ttu-id="f6b4e-116">int</span><span class="sxs-lookup"><span data-stu-id="f6b4e-116">int</span></span>  <br/> |<span data-ttu-id="f6b4e-117">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="f6b4e-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="f6b4e-118">Se hace referencia a ella desde la [tabla region](region.md).</span><span class="sxs-lookup"><span data-stu-id="f6b4e-118">Referenced from the [Region table](region.md).</span></span>  <br/> |
   

