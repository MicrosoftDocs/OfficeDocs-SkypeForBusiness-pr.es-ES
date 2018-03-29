---
title: Vista de VoIPDetails
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: La vista VoIPDetails almacena información acerca de las sesiones de peer-to-peer, donde al menos un usuario es un usuario de VoIP. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: 93c2afb6383817a4d3941d5b427565fb1d0db098
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="voipdetails-view"></a><span data-ttu-id="6bc34-104">Vista de VoIPDetails</span><span class="sxs-lookup"><span data-stu-id="6bc34-104">VoIPDetails view</span></span>
 
<span data-ttu-id="6bc34-105">La vista VoIPDetails almacena información acerca de las sesiones de peer-to-peer, donde al menos un usuario es un usuario de VoIP.</span><span class="sxs-lookup"><span data-stu-id="6bc34-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="6bc34-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6bc34-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6bc34-107">La vista VoIPDetails contiene todas las columnas en la [vista SessionDetails](sessiondetails-0.md) además las columnas enumeradas a continuación.</span><span class="sxs-lookup"><span data-stu-id="6bc34-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="6bc34-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="6bc34-108">**Column**</span></span>|<span data-ttu-id="6bc34-109">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="6bc34-109">**Data Type**</span></span>|<span data-ttu-id="6bc34-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="6bc34-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6bc34-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="6bc34-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="6bc34-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="6bc34-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="6bc34-113">Teléfono URI del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="6bc34-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="6bc34-114">**ToPhone**</span><span class="sxs-lookup"><span data-stu-id="6bc34-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="6bc34-115">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="6bc34-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="6bc34-116">URI del usuario que ha unido a la sesión del teléfono.</span><span class="sxs-lookup"><span data-stu-id="6bc34-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="6bc34-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="6bc34-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="6bc34-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="6bc34-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="6bc34-119">URI del usuario que se ha desconectado la sesión.</span><span class="sxs-lookup"><span data-stu-id="6bc34-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="6bc34-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="6bc34-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="6bc34-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6bc34-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="6bc34-122">Tipo de URI del usuario que se ha desconectado la sesión.</span><span class="sxs-lookup"><span data-stu-id="6bc34-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="6bc34-123">Consulte la [tabla de UriTypes](uritypes.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="6bc34-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="6bc34-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="6bc34-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="6bc34-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6bc34-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="6bc34-126">Inquilinos del usuario que ha desconectado la sesión.</span><span class="sxs-lookup"><span data-stu-id="6bc34-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="6bc34-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="6bc34-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="6bc34-128">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="6bc34-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="6bc34-129">URI del usuario que se ha desconectado la sesión del teléfono.</span><span class="sxs-lookup"><span data-stu-id="6bc34-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="6bc34-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="6bc34-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="6bc34-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6bc34-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="6bc34-132">Servidor de mediación utilizado por el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="6bc34-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="6bc34-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="6bc34-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="6bc34-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6bc34-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="6bc34-135">Servidor de mediación utilizado por el usuario al que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="6bc34-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="6bc34-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="6bc34-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="6bc34-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6bc34-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="6bc34-138">Puerta de enlace utilizada por el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="6bc34-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="6bc34-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="6bc34-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="6bc34-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6bc34-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="6bc34-141">Puerta de enlace utilizada por el usuario al que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="6bc34-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

