---
title: Tabla MonitoredUserSiteLink
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
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: La tabla MonitoredUserSiteLink es una tabla de soporte. Cada registro representa un vínculo entre dos sitios de usuario.
ms.openlocfilehash: 2cf229947da143fb01b3009020cfa432a4b558a0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807798"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="e679f-104">Tabla MonitoredUserSiteLink</span><span class="sxs-lookup"><span data-stu-id="e679f-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="e679f-105">La tabla MonitoredUserSiteLink es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="e679f-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="e679f-106">Cada registro representa un vínculo entre dos sitios de usuario.</span><span class="sxs-lookup"><span data-stu-id="e679f-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="e679f-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="e679f-107">**Column**</span></span>|<span data-ttu-id="e679f-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="e679f-108">**Data Type**</span></span>|<span data-ttu-id="e679f-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="e679f-109">**Key/Index**</span></span>|<span data-ttu-id="e679f-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="e679f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e679f-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="e679f-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="e679f-112">int</span><span class="sxs-lookup"><span data-stu-id="e679f-112">int</span></span>  <br/> |<span data-ttu-id="e679f-113">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="e679f-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e679f-114">Se hace referencia a ella desde la [tabla UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="e679f-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="e679f-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="e679f-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="e679f-116">int</span><span class="sxs-lookup"><span data-stu-id="e679f-116">int</span></span>  <br/> |<span data-ttu-id="e679f-117">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="e679f-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="e679f-118">Referencia de la [tabla UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="e679f-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

