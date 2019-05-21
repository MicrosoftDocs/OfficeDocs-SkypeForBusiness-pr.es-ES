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
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: La tabla MonitoredUserSiteLink es una tabla de soporte. Cada registro representa un vínculo entre dos sitios de usuario.
ms.openlocfilehash: 789c1a721e1a8c204ff6e214f419de77d1b7f7bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294855"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="b3427-104">Tabla MonitoredUserSiteLink</span><span class="sxs-lookup"><span data-stu-id="b3427-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="b3427-105">La tabla MonitoredUserSiteLink es una tabla de soporte.</span><span class="sxs-lookup"><span data-stu-id="b3427-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="b3427-106">Cada registro representa un vínculo entre dos sitios de usuario.</span><span class="sxs-lookup"><span data-stu-id="b3427-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="b3427-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="b3427-107">**Column**</span></span>|<span data-ttu-id="b3427-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="b3427-108">**Data Type**</span></span>|<span data-ttu-id="b3427-109">**Clave o índice**</span><span class="sxs-lookup"><span data-stu-id="b3427-109">**Key/Index**</span></span>|<span data-ttu-id="b3427-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="b3427-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b3427-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="b3427-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="b3427-112">int</span><span class="sxs-lookup"><span data-stu-id="b3427-112">int</span></span>  <br/> |<span data-ttu-id="b3427-113">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="b3427-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="b3427-114">Se hace referencia a ella desde la [tabla UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="b3427-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="b3427-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="b3427-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="b3427-116">int</span><span class="sxs-lookup"><span data-stu-id="b3427-116">int</span></span>  <br/> |<span data-ttu-id="b3427-117">Principal, extranjero</span><span class="sxs-lookup"><span data-stu-id="b3427-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="b3427-118">Referencia de la [tabla UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="b3427-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

