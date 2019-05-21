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
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: tblComplianceParticipant contiene los participantes actuales por canal y por servidor.
ms.openlocfilehash: bf6913d8bcc11db1589169c4479cec4a0238825d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295464"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="60d33-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="60d33-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="60d33-104">tblComplianceParticipant contiene los participantes actuales por canal y por servidor.</span><span class="sxs-lookup"><span data-stu-id="60d33-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="60d33-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="60d33-105">**Columns**</span></span>

|<span data-ttu-id="60d33-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="60d33-106">**Column**</span></span>|<span data-ttu-id="60d33-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="60d33-107">**Type**</span></span>|<span data-ttu-id="60d33-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="60d33-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="60d33-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="60d33-109">channelUri</span></span>  <br/> |<span data-ttu-id="60d33-110">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="60d33-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="60d33-111">Identificador uniforme de recursos (URI) del canal.</span><span class="sxs-lookup"><span data-stu-id="60d33-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="60d33-112">Iddeusuario</span><span class="sxs-lookup"><span data-stu-id="60d33-112">userId</span></span>  <br/> |<span data-ttu-id="60d33-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="60d33-113">int, not null</span></span>  <br/> |<span data-ttu-id="60d33-114">IDENTIFICADOR principal del participante (correspondiente a la tabla tblPrincipal. prinID).</span><span class="sxs-lookup"><span data-stu-id="60d33-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="60d33-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="60d33-115">joinedAt</span></span>  <br/> |<span data-ttu-id="60d33-116">BIGINT, not null</span><span class="sxs-lookup"><span data-stu-id="60d33-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="60d33-117">Marca de tiempo del evento de Unión.</span><span class="sxs-lookup"><span data-stu-id="60d33-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="60d33-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="60d33-118">partedAt</span></span>  <br/> |<span data-ttu-id="60d33-119">BIGINT</span><span class="sxs-lookup"><span data-stu-id="60d33-119">bigint</span></span>  <br/> |<span data-ttu-id="60d33-120">NULL si el participante aún se ha unido.</span><span class="sxs-lookup"><span data-stu-id="60d33-120">Null if participant is still joined.</span></span> <span data-ttu-id="60d33-121">Marca de tiempo del canal dejando el evento si no es NULL.</span><span class="sxs-lookup"><span data-stu-id="60d33-121">The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="60d33-122">Estas entradas se eliminan en algún momento cuando todos los traductores procesan el evento.</span><span class="sxs-lookup"><span data-stu-id="60d33-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="60d33-123">userUri</span><span class="sxs-lookup"><span data-stu-id="60d33-123">userUri</span></span>  <br/> |<span data-ttu-id="60d33-124">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="60d33-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="60d33-125">URI de usuario.</span><span class="sxs-lookup"><span data-stu-id="60d33-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="60d33-126">serverID</span><span class="sxs-lookup"><span data-stu-id="60d33-126">serverID</span></span>  <br/> |<span data-ttu-id="60d33-127">int</span><span class="sxs-lookup"><span data-stu-id="60d33-127">int</span></span>  <br/> |<span data-ttu-id="60d33-128">Identidad del servidor (como en la tabla tblServerIdentity. serverID).</span><span class="sxs-lookup"><span data-stu-id="60d33-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="60d33-129">Identificador</span><span class="sxs-lookup"><span data-stu-id="60d33-129">sessionId</span></span>  <br/> |<span data-ttu-id="60d33-130">BIGINT</span><span class="sxs-lookup"><span data-stu-id="60d33-130">bigint</span></span>  <br/> |<span data-ttu-id="60d33-131">Sesión de servidor.</span><span class="sxs-lookup"><span data-stu-id="60d33-131">Server session.</span></span> <span data-ttu-id="60d33-132">Este es un número aleatorio generado cada vez que se inicia un servicio de chat.</span><span class="sxs-lookup"><span data-stu-id="60d33-132">This is a random number generated each time a Chat service starts.</span></span> <span data-ttu-id="60d33-133">Se usa para diferenciar las sesiones con el fin de identificar a los participantes huérfanos.</span><span class="sxs-lookup"><span data-stu-id="60d33-133">It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="60d33-134">**Clave**</span><span class="sxs-lookup"><span data-stu-id="60d33-134">**Key**</span></span>

|<span data-ttu-id="60d33-135">**Columna**</span><span class="sxs-lookup"><span data-stu-id="60d33-135">**Column**</span></span>|<span data-ttu-id="60d33-136">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="60d33-136">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="60d33-137">\<channelUri, userId, joinedAt\></span><span class="sxs-lookup"><span data-stu-id="60d33-137">\<channelUri, userId, joinedAt\></span></span>  <br/> |<span data-ttu-id="60d33-138">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="60d33-138">Primary key.</span></span>  <br/> |
   

