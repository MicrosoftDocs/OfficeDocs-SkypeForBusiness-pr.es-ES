---
title: tblComplianceParticipant
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
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant contiene los participantes actuales por canal y por servidor.
ms.openlocfilehash: 8f4b90cd7e8949451c2b6c1b9bc3cfabbab826e9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814648"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="415af-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="415af-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="415af-104">tblComplianceParticipant contiene los participantes actuales por canal y por servidor.</span><span class="sxs-lookup"><span data-stu-id="415af-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="415af-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="415af-105">**Columns**</span></span>

|<span data-ttu-id="415af-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="415af-106">**Column**</span></span>|<span data-ttu-id="415af-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="415af-107">**Type**</span></span>|<span data-ttu-id="415af-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="415af-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="415af-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="415af-109">channelUri</span></span>  <br/> |<span data-ttu-id="415af-110">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="415af-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="415af-111">Identificador uniforme de recursos (URI) del canal.</span><span class="sxs-lookup"><span data-stu-id="415af-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="415af-112">Iddeusuario</span><span class="sxs-lookup"><span data-stu-id="415af-112">userId</span></span>  <br/> |<span data-ttu-id="415af-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="415af-113">int, not null</span></span>  <br/> |<span data-ttu-id="415af-114">IDENTIFICADOR principal del participante (correspondiente a la tabla tblPrincipal. prinID).</span><span class="sxs-lookup"><span data-stu-id="415af-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="415af-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="415af-115">joinedAt</span></span>  <br/> |<span data-ttu-id="415af-116">BIGINT, not null</span><span class="sxs-lookup"><span data-stu-id="415af-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="415af-117">Marca de tiempo del evento de Unión.</span><span class="sxs-lookup"><span data-stu-id="415af-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="415af-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="415af-118">partedAt</span></span>  <br/> |<span data-ttu-id="415af-119">BIGINT</span><span class="sxs-lookup"><span data-stu-id="415af-119">bigint</span></span>  <br/> |<span data-ttu-id="415af-120">NULL si el participante aún se ha unido.</span><span class="sxs-lookup"><span data-stu-id="415af-120">Null if participant is still joined.</span></span> <span data-ttu-id="415af-121">Marca de tiempo del canal dejando el evento si no es NULL.</span><span class="sxs-lookup"><span data-stu-id="415af-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="415af-122">Estas entradas se eliminan en algún momento cuando todos los traductores procesan el evento.</span><span class="sxs-lookup"><span data-stu-id="415af-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="415af-123">userUri</span><span class="sxs-lookup"><span data-stu-id="415af-123">userUri</span></span>  <br/> |<span data-ttu-id="415af-124">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="415af-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="415af-125">URI de usuario.</span><span class="sxs-lookup"><span data-stu-id="415af-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="415af-126">serverID</span><span class="sxs-lookup"><span data-stu-id="415af-126">serverID</span></span>  <br/> |<span data-ttu-id="415af-127">int</span><span class="sxs-lookup"><span data-stu-id="415af-127">int</span></span>  <br/> |<span data-ttu-id="415af-128">Identidad del servidor (como en la tabla tblServerIdentity. serverID).</span><span class="sxs-lookup"><span data-stu-id="415af-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="415af-129">Identificador</span><span class="sxs-lookup"><span data-stu-id="415af-129">sessionId</span></span>  <br/> |<span data-ttu-id="415af-130">BIGINT</span><span class="sxs-lookup"><span data-stu-id="415af-130">bigint</span></span>  <br/> |<span data-ttu-id="415af-131">Sesión de servidor.</span><span class="sxs-lookup"><span data-stu-id="415af-131">Server session.</span></span> <span data-ttu-id="415af-132">Este es un número aleatorio generado cada vez que se inicia un servicio de chat.</span><span class="sxs-lookup"><span data-stu-id="415af-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="415af-133">Se usa para diferenciar las sesiones con el fin de identificar a los participantes huérfanos.</span><span class="sxs-lookup"><span data-stu-id="415af-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="415af-134">**Clave**</span><span class="sxs-lookup"><span data-stu-id="415af-134">**Key**</span></span>

|<span data-ttu-id="415af-135">**Columna**</span><span class="sxs-lookup"><span data-stu-id="415af-135">**Column**</span></span>|<span data-ttu-id="415af-136">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="415af-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="415af-137">\<channelUri, userId, joinedAt\></span><span class="sxs-lookup"><span data-stu-id="415af-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="415af-138">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="415af-138">Primary key.</span></span>  <br/> |
   

