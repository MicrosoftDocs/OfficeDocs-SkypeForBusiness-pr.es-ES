---
title: Tabla MonitoredUserSiteLink
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: En la tabla MonitoredUserSiteLink es una tabla de apoyo. Cada registro representa un vínculo entre dos sitios de usuario.
ms.openlocfilehash: 18f0931feb46e69db76c93225ccc11398b4d6daf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920015"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="8d1c9-104">Tabla MonitoredUserSiteLink</span><span class="sxs-lookup"><span data-stu-id="8d1c9-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="8d1c9-105">En la tabla MonitoredUserSiteLink es una tabla de apoyo.</span><span class="sxs-lookup"><span data-stu-id="8d1c9-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="8d1c9-106">Cada registro representa un vínculo entre dos sitios de usuario.</span><span class="sxs-lookup"><span data-stu-id="8d1c9-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="8d1c9-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="8d1c9-107">**Column**</span></span>|<span data-ttu-id="8d1c9-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="8d1c9-108">**Data Type**</span></span>|<span data-ttu-id="8d1c9-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="8d1c9-109">**Key/Index**</span></span>|<span data-ttu-id="8d1c9-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="8d1c9-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8d1c9-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="8d1c9-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="8d1c9-112">int</span><span class="sxs-lookup"><span data-stu-id="8d1c9-112">int</span></span>  <br/> |<span data-ttu-id="8d1c9-113">Principal, externa</span><span class="sxs-lookup"><span data-stu-id="8d1c9-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="8d1c9-114">Referencia de la [tabla UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="8d1c9-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="8d1c9-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="8d1c9-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="8d1c9-116">int</span><span class="sxs-lookup"><span data-stu-id="8d1c9-116">int</span></span>  <br/> |<span data-ttu-id="8d1c9-117">Principal, externa</span><span class="sxs-lookup"><span data-stu-id="8d1c9-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="8d1c9-118">Referencia de la [tabla UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="8d1c9-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

