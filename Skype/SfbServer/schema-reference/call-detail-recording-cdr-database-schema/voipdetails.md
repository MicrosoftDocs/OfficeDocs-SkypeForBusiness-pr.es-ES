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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: La vista VoIPDetails almacena información sobre sesiones de punto a punto, donde al menos un usuario es un usuario de VoIP. Esta vista se presentó en Microsoft Lync Server 2013.
ms.openlocfilehash: 4d3aec4c58c2cb11f21ec6403f7532bcde46b05e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814778"
---
# <a name="voipdetails-view"></a><span data-ttu-id="f4f65-104">Vista VoIPDetails</span><span class="sxs-lookup"><span data-stu-id="f4f65-104">VoIPDetails view</span></span>
 
<span data-ttu-id="f4f65-105">La vista VoIPDetails almacena información sobre sesiones de punto a punto, donde al menos un usuario es un usuario de VoIP.</span><span class="sxs-lookup"><span data-stu-id="f4f65-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="f4f65-106">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4f65-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f4f65-107">La vista VoIPDetails contiene todas las columnas de la [vista SessionDetails](sessiondetails-0.md) además de las columnas que se muestran a continuación.</span><span class="sxs-lookup"><span data-stu-id="f4f65-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="f4f65-108">**Columna**</span><span class="sxs-lookup"><span data-stu-id="f4f65-108">**Column**</span></span>|<span data-ttu-id="f4f65-109">**Tipo de datos**</span><span class="sxs-lookup"><span data-stu-id="f4f65-109">**Data Type**</span></span>|<span data-ttu-id="f4f65-110">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="f4f65-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f4f65-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="f4f65-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="f4f65-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f4f65-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="f4f65-113">URI de teléfono del usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="f4f65-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="f4f65-114">**Teléfono**</span><span class="sxs-lookup"><span data-stu-id="f4f65-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="f4f65-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f4f65-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="f4f65-116">URI de teléfono del usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="f4f65-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="f4f65-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="f4f65-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="f4f65-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f4f65-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="f4f65-119">URI del usuario que desconectó la sesión.</span><span class="sxs-lookup"><span data-stu-id="f4f65-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="f4f65-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="f4f65-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="f4f65-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f4f65-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="f4f65-122">Tipo de URI del usuario que ha desconectado la sesión.</span><span class="sxs-lookup"><span data-stu-id="f4f65-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="f4f65-123">Para obtener más información, consulte la [tabla UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="f4f65-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="f4f65-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="f4f65-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="f4f65-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f4f65-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="f4f65-126">Espacio empresarial del usuario que desconectó la sesión.</span><span class="sxs-lookup"><span data-stu-id="f4f65-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="f4f65-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="f4f65-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="f4f65-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f4f65-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="f4f65-129">URI de teléfono del usuario que desconectó la sesión.</span><span class="sxs-lookup"><span data-stu-id="f4f65-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="f4f65-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="f4f65-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="f4f65-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f4f65-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="f4f65-132">Servidor de mediación usado por el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="f4f65-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="f4f65-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="f4f65-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="f4f65-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f4f65-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="f4f65-135">Servidor de mediación usado por el usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="f4f65-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="f4f65-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="f4f65-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="f4f65-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f4f65-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="f4f65-138">Puerta de enlace usada por el usuario que inició la sesión.</span><span class="sxs-lookup"><span data-stu-id="f4f65-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="f4f65-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="f4f65-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="f4f65-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f4f65-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="f4f65-141">Puerta de enlace usada por el usuario que se unió a la sesión.</span><span class="sxs-lookup"><span data-stu-id="f4f65-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

