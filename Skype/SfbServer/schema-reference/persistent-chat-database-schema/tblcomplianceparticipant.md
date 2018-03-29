---
title: tblComplianceParticipant
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant contiene a los participantes actuales por canal y por servidor.
ms.openlocfilehash: ba488f377592b48845880acaeed61074bc31ccd2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="d8fd2-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="d8fd2-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="d8fd2-104">tblComplianceParticipant contiene a los participantes actuales por canal y por servidor.</span><span class="sxs-lookup"><span data-stu-id="d8fd2-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="d8fd2-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="d8fd2-105">**Columns**</span></span>

|<span data-ttu-id="d8fd2-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d8fd2-106">**Column**</span></span>|<span data-ttu-id="d8fd2-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d8fd2-107">**Type**</span></span>|<span data-ttu-id="d8fd2-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d8fd2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d8fd2-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="d8fd2-109">channelUri</span></span>  <br/> |<span data-ttu-id="d8fd2-110">nvarchar (255), no nulo</span><span class="sxs-lookup"><span data-stu-id="d8fd2-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="d8fd2-111">Canal identificador de recursos uniforme (URI).</span><span class="sxs-lookup"><span data-stu-id="d8fd2-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="d8fd2-112">ID de usuario</span><span class="sxs-lookup"><span data-stu-id="d8fd2-112">userId</span></span>  <br/> |<span data-ttu-id="d8fd2-113">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="d8fd2-113">int, not null</span></span>  <br/> |<span data-ttu-id="d8fd2-114">Identificador principal del participante (correspondiente a la tabla de tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="d8fd2-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="d8fd2-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="d8fd2-115">joinedAt</span></span>  <br/> |<span data-ttu-id="d8fd2-116">bigint, no nulo</span><span class="sxs-lookup"><span data-stu-id="d8fd2-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="d8fd2-117">Marca de tiempo del evento que se va a unir.</span><span class="sxs-lookup"><span data-stu-id="d8fd2-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="d8fd2-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="d8fd2-118">partedAt</span></span>  <br/> |<span data-ttu-id="d8fd2-119">bigint</span><span class="sxs-lookup"><span data-stu-id="d8fd2-119">bigint</span></span>  <br/> |<span data-ttu-id="d8fd2-120">Null si todavía está unido participante.</span><span class="sxs-lookup"><span data-stu-id="d8fd2-120">Null if participant is still joined.</span></span> <span data-ttu-id="d8fd2-121">La marca de tiempo del canal dejando el evento si no es null.</span><span class="sxs-lookup"><span data-stu-id="d8fd2-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="d8fd2-122">Estas entradas más tarde se eliminan cuando todos los traductores procesan el evento.</span><span class="sxs-lookup"><span data-stu-id="d8fd2-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="d8fd2-123">userUri</span><span class="sxs-lookup"><span data-stu-id="d8fd2-123">userUri</span></span>  <br/> |<span data-ttu-id="d8fd2-124">nvarchar (255), no nulo</span><span class="sxs-lookup"><span data-stu-id="d8fd2-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="d8fd2-125">URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="d8fd2-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="d8fd2-126">serverID</span><span class="sxs-lookup"><span data-stu-id="d8fd2-126">serverID</span></span>  <br/> |<span data-ttu-id="d8fd2-127">int</span><span class="sxs-lookup"><span data-stu-id="d8fd2-127">int</span></span>  <br/> |<span data-ttu-id="d8fd2-128">Identidad del servidor (como en la tabla de tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="d8fd2-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="d8fd2-129">Id. de sesión</span><span class="sxs-lookup"><span data-stu-id="d8fd2-129">sessionId</span></span>  <br/> |<span data-ttu-id="d8fd2-130">bigint</span><span class="sxs-lookup"><span data-stu-id="d8fd2-130">bigint</span></span>  <br/> |<span data-ttu-id="d8fd2-131">Sesión del servidor.</span><span class="sxs-lookup"><span data-stu-id="d8fd2-131">Server session.</span></span> <span data-ttu-id="d8fd2-132">Se trata de un número aleatorio que se genera cada vez que se inicia un servicio de charla.</span><span class="sxs-lookup"><span data-stu-id="d8fd2-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="d8fd2-133">Sirve para diferenciar las sesiones con el fin de identificar a los participantes huérfanos.</span><span class="sxs-lookup"><span data-stu-id="d8fd2-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="d8fd2-134">**Clave**</span><span class="sxs-lookup"><span data-stu-id="d8fd2-134">**Key**</span></span>

|<span data-ttu-id="d8fd2-135">**Columna**</span><span class="sxs-lookup"><span data-stu-id="d8fd2-135">**Column**</span></span>|<span data-ttu-id="d8fd2-136">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="d8fd2-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d8fd2-137">\<channelUri, joinedAt, Id.\></span><span class="sxs-lookup"><span data-stu-id="d8fd2-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="d8fd2-138">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="d8fd2-138">Primary key.</span></span>  <br/> |
   

