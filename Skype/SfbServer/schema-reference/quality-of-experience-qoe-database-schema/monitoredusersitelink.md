---
title: Tabla MonitoredUserSiteLink
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: En la tabla MonitoredUserSiteLink es una tabla de apoyo. Cada registro representa un vínculo entre dos sitios de usuario.
ms.openlocfilehash: 8022286289d4acd5fab8ea821c72897d9500597b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874262"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="dcb65-104">Tabla MonitoredUserSiteLink</span><span class="sxs-lookup"><span data-stu-id="dcb65-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="dcb65-105">En la tabla MonitoredUserSiteLink es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="dcb65-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="dcb65-106">Cada registro representa un vínculo entre dos sitios de usuario.</span><span class="sxs-lookup"><span data-stu-id="dcb65-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="dcb65-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="dcb65-107">**Column**</span></span>|<span data-ttu-id="dcb65-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="dcb65-108">**Data Type**</span></span>|<span data-ttu-id="dcb65-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="dcb65-109">**Key/Index**</span></span>|<span data-ttu-id="dcb65-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="dcb65-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dcb65-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="dcb65-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="dcb65-112">int</span><span class="sxs-lookup"><span data-stu-id="dcb65-112">int</span></span>  <br/> |<span data-ttu-id="dcb65-113">Principal, externa</span><span class="sxs-lookup"><span data-stu-id="dcb65-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="dcb65-114">Referencia de la [tabla UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="dcb65-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="dcb65-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="dcb65-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="dcb65-116">int</span><span class="sxs-lookup"><span data-stu-id="dcb65-116">int</span></span>  <br/> |<span data-ttu-id="dcb65-117">Principal, externa</span><span class="sxs-lookup"><span data-stu-id="dcb65-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="dcb65-118">Referencia de la [tabla UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="dcb65-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

