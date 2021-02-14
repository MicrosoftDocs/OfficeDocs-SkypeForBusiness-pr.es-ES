---
title: Vista VoIPDetails
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: La vista VoIPDetails almacena información acerca de las sesiones punto a punto, donde al menos un usuario es un usuario voIP. Esta vista se introdujo en Microsoft Lync Server 2013.
ms.openlocfilehash: b42fecc7a0f43f86dba2439a373c7013c605a5e0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813080"
---
# <a name="voipdetails-view"></a><span data-ttu-id="fa4c8-104">Vista VoIPDetails</span><span class="sxs-lookup"><span data-stu-id="fa4c8-104">VoIPDetails view</span></span>
 
<span data-ttu-id="fa4c8-105">La vista VoIPDetails almacena información acerca de las sesiones punto a punto, donde al menos un usuario es un usuario voIP.</span><span class="sxs-lookup"><span data-stu-id="fa4c8-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="fa4c8-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="fa4c8-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fa4c8-107">La vista VoIPDetails contiene todas las columnas de la vista [SessionDetails](sessiondetails-0.md) además de las columnas que se enumeran a continuación.</span><span class="sxs-lookup"><span data-stu-id="fa4c8-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="fa4c8-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="fa4c8-108">**Column**</span></span>|<span data-ttu-id="fa4c8-109">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="fa4c8-109">**Data Type**</span></span>|<span data-ttu-id="fa4c8-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="fa4c8-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fa4c8-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="fa4c8-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="fa4c8-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="fa4c8-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="fa4c8-113">URI de teléfono del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="fa4c8-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="fa4c8-114">**ToPhone**</span><span class="sxs-lookup"><span data-stu-id="fa4c8-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="fa4c8-115">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="fa4c8-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="fa4c8-116">URI de teléfono del usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="fa4c8-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="fa4c8-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="fa4c8-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="fa4c8-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="fa4c8-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="fa4c8-119">URI del usuario que desconectó la sesión.</span><span class="sxs-lookup"><span data-stu-id="fa4c8-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="fa4c8-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="fa4c8-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="fa4c8-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa4c8-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="fa4c8-122">Tipo de URI del usuario que desconectó la sesión.</span><span class="sxs-lookup"><span data-stu-id="fa4c8-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="fa4c8-123">Vea la [tabla UriTypes](uritypes.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="fa4c8-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="fa4c8-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="fa4c8-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="fa4c8-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa4c8-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="fa4c8-126">Inquilino del usuario que desconectó la sesión.</span><span class="sxs-lookup"><span data-stu-id="fa4c8-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="fa4c8-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="fa4c8-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="fa4c8-128">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="fa4c8-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="fa4c8-129">URI de teléfono del usuario que desconectó la sesión.</span><span class="sxs-lookup"><span data-stu-id="fa4c8-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="fa4c8-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="fa4c8-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="fa4c8-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa4c8-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="fa4c8-132">Servidor de mediación usado por el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="fa4c8-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="fa4c8-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="fa4c8-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="fa4c8-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa4c8-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="fa4c8-135">Servidor de mediación usado por el usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="fa4c8-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="fa4c8-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="fa4c8-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="fa4c8-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa4c8-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="fa4c8-138">Puerta de enlace usada por el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="fa4c8-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="fa4c8-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="fa4c8-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="fa4c8-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="fa4c8-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="fa4c8-141">Puerta de enlace usada por el usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="fa4c8-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

