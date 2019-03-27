---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: la tabla tblComplianceParticipant contiene a los participantes actuales por canal y por servidor.
ms.openlocfilehash: a3d18c4a78af2892a837e1105a435a3ce46ea14b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881419"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="354c1-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="354c1-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="354c1-104">la tabla tblComplianceParticipant contiene a los participantes actuales por canal y por servidor.</span><span class="sxs-lookup"><span data-stu-id="354c1-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="354c1-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="354c1-105">**Columns**</span></span>

|<span data-ttu-id="354c1-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="354c1-106">**Column**</span></span>|<span data-ttu-id="354c1-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="354c1-107">**Type**</span></span>|<span data-ttu-id="354c1-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="354c1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="354c1-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="354c1-109">channelUri</span></span>  <br/> |<span data-ttu-id="354c1-110">nvarchar (255), no es nulo</span><span class="sxs-lookup"><span data-stu-id="354c1-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="354c1-111">Identificador de canal uniforme de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="354c1-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="354c1-112">userId</span><span class="sxs-lookup"><span data-stu-id="354c1-112">userId</span></span>  <br/> |<span data-ttu-id="354c1-113">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="354c1-113">int, not null</span></span>  <br/> |<span data-ttu-id="354c1-114">Identificador de entidad del participante (correspondiente a la tabla tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="354c1-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="354c1-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="354c1-115">joinedAt</span></span>  <br/> |<span data-ttu-id="354c1-116">bigint, no es nulo</span><span class="sxs-lookup"><span data-stu-id="354c1-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="354c1-117">Marca de tiempo del evento participante.</span><span class="sxs-lookup"><span data-stu-id="354c1-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="354c1-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="354c1-118">partedAt</span></span>  <br/> |<span data-ttu-id="354c1-119">bigint</span><span class="sxs-lookup"><span data-stu-id="354c1-119">bigint</span></span>  <br/> |<span data-ttu-id="354c1-120">Null si aún está unido participante.</span><span class="sxs-lookup"><span data-stu-id="354c1-120">Null if participant is still joined.</span></span> <span data-ttu-id="354c1-121">La marca de tiempo del canal dejando evento si no es nulo.</span><span class="sxs-lookup"><span data-stu-id="354c1-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="354c1-122">Estas entradas se quitan finalmente cuando todos los traductores procesan el evento.</span><span class="sxs-lookup"><span data-stu-id="354c1-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="354c1-123">userUri</span><span class="sxs-lookup"><span data-stu-id="354c1-123">userUri</span></span>  <br/> |<span data-ttu-id="354c1-124">nvarchar (255), no es nulo</span><span class="sxs-lookup"><span data-stu-id="354c1-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="354c1-125">URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="354c1-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="354c1-126">serverID</span><span class="sxs-lookup"><span data-stu-id="354c1-126">serverID</span></span>  <br/> |<span data-ttu-id="354c1-127">int</span><span class="sxs-lookup"><span data-stu-id="354c1-127">int</span></span>  <br/> |<span data-ttu-id="354c1-128">Identidad del servidor (como se muestra en la tabla tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="354c1-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="354c1-129">sessionId</span><span class="sxs-lookup"><span data-stu-id="354c1-129">sessionId</span></span>  <br/> |<span data-ttu-id="354c1-130">bigint</span><span class="sxs-lookup"><span data-stu-id="354c1-130">bigint</span></span>  <br/> |<span data-ttu-id="354c1-131">Sesión de servidor.</span><span class="sxs-lookup"><span data-stu-id="354c1-131">Server session.</span></span> <span data-ttu-id="354c1-132">Este es un número aleatorio generado cada vez que se inicia un servicio de Chat.</span><span class="sxs-lookup"><span data-stu-id="354c1-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="354c1-133">Se usa para diferenciar las sesiones con el fin de identificar a los participantes huérfanos.</span><span class="sxs-lookup"><span data-stu-id="354c1-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="354c1-134">**Clave**</span><span class="sxs-lookup"><span data-stu-id="354c1-134">**Key**</span></span>

|<span data-ttu-id="354c1-135">**Columna**</span><span class="sxs-lookup"><span data-stu-id="354c1-135">**Column**</span></span>|<span data-ttu-id="354c1-136">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="354c1-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="354c1-137">\<channelUri, userId, joinedAt\></span><span class="sxs-lookup"><span data-stu-id="354c1-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="354c1-138">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="354c1-138">Primary key.</span></span>  <br/> |
   

