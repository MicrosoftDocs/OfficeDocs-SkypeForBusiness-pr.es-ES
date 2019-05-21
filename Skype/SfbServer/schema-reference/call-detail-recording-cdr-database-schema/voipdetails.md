---
title: Vista VoIPDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: La vista VoIPDetails almacena información sobre sesiones de punto a punto, donde al menos un usuario es un usuario de VoIP. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: 7f5f1e3cf1540e1a12a9365753e494ff2d8a371e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295667"
---
# <a name="voipdetails-view"></a><span data-ttu-id="c2418-104">Vista VoIPDetails</span><span class="sxs-lookup"><span data-stu-id="c2418-104">VoIPDetails view</span></span>
 
<span data-ttu-id="c2418-105">La vista VoIPDetails almacena información sobre sesiones de punto a punto, donde al menos un usuario es un usuario de VoIP.</span><span class="sxs-lookup"><span data-stu-id="c2418-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="c2418-106">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c2418-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c2418-107">La vista VoIPDetails contiene todas las columnas de la [vista SessionDetails](sessiondetails-0.md) además de las columnas que se muestran a continuación.</span><span class="sxs-lookup"><span data-stu-id="c2418-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="c2418-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="c2418-108">**Column**</span></span>|<span data-ttu-id="c2418-109">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="c2418-109">**Data Type**</span></span>|<span data-ttu-id="c2418-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="c2418-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c2418-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="c2418-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="c2418-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c2418-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="c2418-113">URI de teléfono del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="c2418-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="c2418-114">**Teléfono**</span><span class="sxs-lookup"><span data-stu-id="c2418-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="c2418-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c2418-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="c2418-116">URI de teléfono del usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="c2418-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="c2418-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="c2418-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="c2418-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c2418-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="c2418-119">URI del usuario que desconectó la sesión.</span><span class="sxs-lookup"><span data-stu-id="c2418-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="c2418-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="c2418-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="c2418-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c2418-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c2418-122">Tipo de URI del usuario que ha desconectado la sesión.</span><span class="sxs-lookup"><span data-stu-id="c2418-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="c2418-123">Para obtener más información, consulte la [tabla UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="c2418-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="c2418-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="c2418-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="c2418-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c2418-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c2418-126">Espacio empresarial del usuario que desconectó la sesión.</span><span class="sxs-lookup"><span data-stu-id="c2418-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="c2418-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="c2418-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="c2418-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="c2418-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="c2418-129">URI de teléfono del usuario que desconectó la sesión.</span><span class="sxs-lookup"><span data-stu-id="c2418-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="c2418-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="c2418-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="c2418-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c2418-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c2418-132">Servidor de mediación usado por el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="c2418-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="c2418-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="c2418-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="c2418-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c2418-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c2418-135">Servidor de mediación usado por el usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="c2418-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="c2418-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="c2418-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="c2418-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c2418-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c2418-138">Puerta de enlace usada por el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="c2418-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="c2418-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="c2418-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="c2418-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c2418-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="c2418-141">Puerta de enlace usada por el usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="c2418-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

