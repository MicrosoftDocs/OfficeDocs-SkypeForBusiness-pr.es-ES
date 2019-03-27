---
title: Vista VoIPDetails
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: La vista VoIPDetails almacena información acerca de las sesiones de punto a punto, donde al menos un usuario es un usuario de VoIP. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 940c3874d5ce8eb8a4d2261de56b8988b6d3a4c9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875556"
---
# <a name="voipdetails-view"></a><span data-ttu-id="3027b-104">Vista VoIPDetails</span><span class="sxs-lookup"><span data-stu-id="3027b-104">VoIPDetails view</span></span>
 
<span data-ttu-id="3027b-105">La vista VoIPDetails almacena información acerca de las sesiones de punto a punto, donde al menos un usuario es un usuario de VoIP.</span><span class="sxs-lookup"><span data-stu-id="3027b-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="3027b-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3027b-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3027b-107">La vista VoIPDetails contiene todos los de las columnas de la [SessionDetails view](sessiondetails-0.md) además las columnas enumeradas a continuación.</span><span class="sxs-lookup"><span data-stu-id="3027b-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="3027b-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="3027b-108">**Column**</span></span>|<span data-ttu-id="3027b-109">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="3027b-109">**Data Type**</span></span>|<span data-ttu-id="3027b-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="3027b-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3027b-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="3027b-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="3027b-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="3027b-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="3027b-113">URI de teléfono del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="3027b-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="3027b-114">**ToPhone**</span><span class="sxs-lookup"><span data-stu-id="3027b-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="3027b-115">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="3027b-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="3027b-116">URI de teléfono del usuario que ha iniciado la sesión.</span><span class="sxs-lookup"><span data-stu-id="3027b-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="3027b-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="3027b-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="3027b-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="3027b-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="3027b-119">URI del usuario que ha desconectado la sesión.</span><span class="sxs-lookup"><span data-stu-id="3027b-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="3027b-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="3027b-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="3027b-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3027b-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3027b-122">Tipo de URI del usuario que ha desconectado la sesión.</span><span class="sxs-lookup"><span data-stu-id="3027b-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="3027b-123">Consulte la [tabla UriTypes](uritypes.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="3027b-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="3027b-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="3027b-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="3027b-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3027b-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3027b-126">Inquilino del usuario que ha desconectado la sesión.</span><span class="sxs-lookup"><span data-stu-id="3027b-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="3027b-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="3027b-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="3027b-128">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="3027b-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="3027b-129">URI de teléfono del usuario que ha desconectado la sesión.</span><span class="sxs-lookup"><span data-stu-id="3027b-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="3027b-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="3027b-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="3027b-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3027b-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3027b-132">Servidor de mediación usado por el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="3027b-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="3027b-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="3027b-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="3027b-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3027b-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3027b-135">Servidor de mediación usado por el usuario que ha iniciado la sesión.</span><span class="sxs-lookup"><span data-stu-id="3027b-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="3027b-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="3027b-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="3027b-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3027b-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3027b-138">Puerta de enlace usada por el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="3027b-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="3027b-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="3027b-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="3027b-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3027b-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="3027b-141">Puerta de enlace usada por el usuario que ha iniciado la sesión.</span><span class="sxs-lookup"><span data-stu-id="3027b-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

