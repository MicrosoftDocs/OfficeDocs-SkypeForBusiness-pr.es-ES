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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212708"
---
# <a name="voipdetails-view"></a><span data-ttu-id="d26ed-104">Vista VoIPDetails</span><span class="sxs-lookup"><span data-stu-id="d26ed-104">VoIPDetails view</span></span>
 
<span data-ttu-id="d26ed-105">La vista VoIPDetails almacena información acerca de las sesiones de punto a punto, donde al menos un usuario es un usuario de VoIP.</span><span class="sxs-lookup"><span data-stu-id="d26ed-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="d26ed-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d26ed-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d26ed-107">La vista VoIPDetails contiene todos los de las columnas de la [SessionDetails view](sessiondetails-0.md) además las columnas enumeradas a continuación.</span><span class="sxs-lookup"><span data-stu-id="d26ed-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="d26ed-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d26ed-108">**Column**</span></span>|<span data-ttu-id="d26ed-109">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="d26ed-109">**Data Type**</span></span>|<span data-ttu-id="d26ed-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="d26ed-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d26ed-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="d26ed-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="d26ed-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="d26ed-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="d26ed-113">URI de teléfono del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="d26ed-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="d26ed-114">**ToPhone**</span><span class="sxs-lookup"><span data-stu-id="d26ed-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="d26ed-115">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="d26ed-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="d26ed-116">URI de teléfono del usuario que ha iniciado la sesión.</span><span class="sxs-lookup"><span data-stu-id="d26ed-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="d26ed-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="d26ed-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="d26ed-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="d26ed-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="d26ed-119">URI del usuario que ha desconectado la sesión.</span><span class="sxs-lookup"><span data-stu-id="d26ed-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="d26ed-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="d26ed-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="d26ed-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d26ed-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d26ed-122">Tipo de URI del usuario que ha desconectado la sesión.</span><span class="sxs-lookup"><span data-stu-id="d26ed-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="d26ed-123">Consulte la [tabla UriTypes](uritypes.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d26ed-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="d26ed-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="d26ed-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="d26ed-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d26ed-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d26ed-126">Inquilino del usuario que ha desconectado la sesión.</span><span class="sxs-lookup"><span data-stu-id="d26ed-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="d26ed-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="d26ed-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="d26ed-128">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="d26ed-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="d26ed-129">URI de teléfono del usuario que ha desconectado la sesión.</span><span class="sxs-lookup"><span data-stu-id="d26ed-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="d26ed-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="d26ed-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="d26ed-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d26ed-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d26ed-132">Servidor de mediación usado por el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="d26ed-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="d26ed-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="d26ed-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="d26ed-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d26ed-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d26ed-135">Servidor de mediación usado por el usuario que ha iniciado la sesión.</span><span class="sxs-lookup"><span data-stu-id="d26ed-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="d26ed-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="d26ed-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="d26ed-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d26ed-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d26ed-138">Puerta de enlace usada por el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="d26ed-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="d26ed-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="d26ed-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="d26ed-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d26ed-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="d26ed-141">Puerta de enlace usada por el usuario que ha iniciado la sesión.</span><span class="sxs-lookup"><span data-stu-id="d26ed-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

