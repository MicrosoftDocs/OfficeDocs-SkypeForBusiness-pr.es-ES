---
title: Tabla MonitoredUserSiteLink
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: La tabla MonitoredUserSiteLink es un auxiliar. Cada registro representa un vínculo entre dos sitios de usuario.
ms.openlocfilehash: 7b9b2ddab3bff48105a24f586816666b15c0b9b6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="dd545-104">Tabla MonitoredUserSiteLink</span><span class="sxs-lookup"><span data-stu-id="dd545-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="dd545-105">La tabla MonitoredUserSiteLink es un auxiliar.</span><span class="sxs-lookup"><span data-stu-id="dd545-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="dd545-106">Cada registro representa un vínculo entre dos sitios de usuario.</span><span class="sxs-lookup"><span data-stu-id="dd545-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="dd545-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="dd545-107">**Column**</span></span>|<span data-ttu-id="dd545-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="dd545-108">**Data Type**</span></span>|<span data-ttu-id="dd545-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="dd545-109">**Key/Index**</span></span>|<span data-ttu-id="dd545-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="dd545-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dd545-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="dd545-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="dd545-112">int</span><span class="sxs-lookup"><span data-stu-id="dd545-112">int</span></span>  <br/> |<span data-ttu-id="dd545-113">Principal, externa</span><span class="sxs-lookup"><span data-stu-id="dd545-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="dd545-114">Referencia de la [tabla UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="dd545-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="dd545-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="dd545-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="dd545-116">int</span><span class="sxs-lookup"><span data-stu-id="dd545-116">int</span></span>  <br/> |<span data-ttu-id="dd545-117">Principal, externa</span><span class="sxs-lookup"><span data-stu-id="dd545-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="dd545-118">Referencia de la [tabla UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="dd545-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

