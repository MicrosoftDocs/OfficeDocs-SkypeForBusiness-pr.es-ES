---
title: Tabla MonitoredUserSiteLink
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
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: La tabla MonitoredUserSiteLink es una tabla auxiliar. Cada registro representa un vínculo entre dos sitios de usuario.
ms.openlocfilehash: 88b4d385f3c96dc93a519274c584e1f99584982f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806360"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="42a5c-104">Tabla MonitoredUserSiteLink</span><span class="sxs-lookup"><span data-stu-id="42a5c-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="42a5c-p102">La tabla MonitoredUserSiteLink es una tabla auxiliar. Cada registro representa un vínculo entre dos sitios de usuario.</span><span class="sxs-lookup"><span data-stu-id="42a5c-p102">The MonitoredUserSiteLink table is a supporting table. Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="42a5c-107">**Columna**</span><span class="sxs-lookup"><span data-stu-id="42a5c-107">**Column**</span></span>|<span data-ttu-id="42a5c-108">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="42a5c-108">**Data Type**</span></span>|<span data-ttu-id="42a5c-109">**Clave/índice**</span><span class="sxs-lookup"><span data-stu-id="42a5c-109">**Key/Index**</span></span>|<span data-ttu-id="42a5c-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="42a5c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="42a5c-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="42a5c-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="42a5c-112">entero</span><span class="sxs-lookup"><span data-stu-id="42a5c-112">int</span></span>  <br/> |<span data-ttu-id="42a5c-113">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="42a5c-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="42a5c-114">Se hace referencia desde la [tabla UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="42a5c-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="42a5c-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="42a5c-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="42a5c-116">entero</span><span class="sxs-lookup"><span data-stu-id="42a5c-116">int</span></span>  <br/> |<span data-ttu-id="42a5c-117">Principal, Externa</span><span class="sxs-lookup"><span data-stu-id="42a5c-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="42a5c-118">Referencia de la [tabla UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="42a5c-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

