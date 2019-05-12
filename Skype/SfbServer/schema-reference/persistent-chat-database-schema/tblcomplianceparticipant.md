---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: la tabla tblComplianceParticipant contiene a los participantes actuales por canal y por servidor.
ms.openlocfilehash: 6644796d88f303c6614cbd73d98224fe0e41eabb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929941"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="ce9fe-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="ce9fe-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="ce9fe-104">la tabla tblComplianceParticipant contiene a los participantes actuales por canal y por servidor.</span><span class="sxs-lookup"><span data-stu-id="ce9fe-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="ce9fe-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="ce9fe-105">**Columns**</span></span>

|<span data-ttu-id="ce9fe-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="ce9fe-106">**Column**</span></span>|<span data-ttu-id="ce9fe-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ce9fe-107">**Type**</span></span>|<span data-ttu-id="ce9fe-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ce9fe-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ce9fe-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="ce9fe-109">channelUri</span></span>  <br/> |<span data-ttu-id="ce9fe-110">nvarchar (255), no es nulo</span><span class="sxs-lookup"><span data-stu-id="ce9fe-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="ce9fe-111">Identificador de canal uniforme de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="ce9fe-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="ce9fe-112">userId</span><span class="sxs-lookup"><span data-stu-id="ce9fe-112">userId</span></span>  <br/> |<span data-ttu-id="ce9fe-113">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="ce9fe-113">int, not null</span></span>  <br/> |<span data-ttu-id="ce9fe-114">Identificador de entidad del participante (correspondiente a la tabla tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="ce9fe-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="ce9fe-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="ce9fe-115">joinedAt</span></span>  <br/> |<span data-ttu-id="ce9fe-116">bigint, no es nulo</span><span class="sxs-lookup"><span data-stu-id="ce9fe-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="ce9fe-117">Marca de tiempo del evento participante.</span><span class="sxs-lookup"><span data-stu-id="ce9fe-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="ce9fe-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="ce9fe-118">partedAt</span></span>  <br/> |<span data-ttu-id="ce9fe-119">bigint</span><span class="sxs-lookup"><span data-stu-id="ce9fe-119">bigint</span></span>  <br/> |<span data-ttu-id="ce9fe-120">Null si aún está unido participante.</span><span class="sxs-lookup"><span data-stu-id="ce9fe-120">Null if participant is still joined.</span></span> <span data-ttu-id="ce9fe-121">La marca de tiempo del canal dejando evento si no es nulo.</span><span class="sxs-lookup"><span data-stu-id="ce9fe-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="ce9fe-122">Estas entradas se quitan finalmente cuando todos los traductores procesan el evento.</span><span class="sxs-lookup"><span data-stu-id="ce9fe-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="ce9fe-123">userUri</span><span class="sxs-lookup"><span data-stu-id="ce9fe-123">userUri</span></span>  <br/> |<span data-ttu-id="ce9fe-124">nvarchar (255), no es nulo</span><span class="sxs-lookup"><span data-stu-id="ce9fe-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="ce9fe-125">URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="ce9fe-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="ce9fe-126">serverID</span><span class="sxs-lookup"><span data-stu-id="ce9fe-126">serverID</span></span>  <br/> |<span data-ttu-id="ce9fe-127">int</span><span class="sxs-lookup"><span data-stu-id="ce9fe-127">int</span></span>  <br/> |<span data-ttu-id="ce9fe-128">Identidad del servidor (como se muestra en la tabla tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="ce9fe-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="ce9fe-129">sessionId</span><span class="sxs-lookup"><span data-stu-id="ce9fe-129">sessionId</span></span>  <br/> |<span data-ttu-id="ce9fe-130">bigint</span><span class="sxs-lookup"><span data-stu-id="ce9fe-130">bigint</span></span>  <br/> |<span data-ttu-id="ce9fe-131">Sesión de servidor.</span><span class="sxs-lookup"><span data-stu-id="ce9fe-131">Server session.</span></span> <span data-ttu-id="ce9fe-132">Este es un número aleatorio generado cada vez que se inicia un servicio de Chat.</span><span class="sxs-lookup"><span data-stu-id="ce9fe-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="ce9fe-133">Se usa para diferenciar las sesiones con el fin de identificar a los participantes huérfanos.</span><span class="sxs-lookup"><span data-stu-id="ce9fe-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="ce9fe-134">**Clave**</span><span class="sxs-lookup"><span data-stu-id="ce9fe-134">**Key**</span></span>

|<span data-ttu-id="ce9fe-135">**Columna**</span><span class="sxs-lookup"><span data-stu-id="ce9fe-135">**Column**</span></span>|<span data-ttu-id="ce9fe-136">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ce9fe-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ce9fe-137">\<channelUri, userId, joinedAt\></span><span class="sxs-lookup"><span data-stu-id="ce9fe-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="ce9fe-138">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="ce9fe-138">Primary key.</span></span>  <br/> |
   

