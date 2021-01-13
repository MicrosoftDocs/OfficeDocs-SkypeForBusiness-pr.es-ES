---
title: tblComplianceParticipant
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
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: La tabla tblComplianceParticipant contiene los participantes actuales por canal y por servidor.
ms.openlocfilehash: c6aae3c1e7b13456708034512c6b68d67d6d1f92
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809750"
---
# <a name="tblcomplianceparticipant"></a><span data-ttu-id="b0b42-103">tblComplianceParticipant</span><span class="sxs-lookup"><span data-stu-id="b0b42-103">tblComplianceParticipant</span></span>
 
<span data-ttu-id="b0b42-104">La tabla tblComplianceParticipant contiene los participantes actuales por canal y por servidor.</span><span class="sxs-lookup"><span data-stu-id="b0b42-104">tblComplianceParticipant contains the current participants per channel and per server.</span></span>
  
<span data-ttu-id="b0b42-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="b0b42-105">**Columns**</span></span>

|<span data-ttu-id="b0b42-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="b0b42-106">**Column**</span></span>|<span data-ttu-id="b0b42-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b0b42-107">**Type**</span></span>|<span data-ttu-id="b0b42-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="b0b42-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b0b42-109">channelUri</span><span class="sxs-lookup"><span data-stu-id="b0b42-109">channelUri</span></span>  <br/> |<span data-ttu-id="b0b42-110">nvarchar (255), no NULL</span><span class="sxs-lookup"><span data-stu-id="b0b42-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="b0b42-111">Identificador uniforme de recursos (URI) del canal.</span><span class="sxs-lookup"><span data-stu-id="b0b42-111">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="b0b42-112">userId</span><span class="sxs-lookup"><span data-stu-id="b0b42-112">userId</span></span>  <br/> |<span data-ttu-id="b0b42-113">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="b0b42-113">int, not null</span></span>  <br/> |<span data-ttu-id="b0b42-114">Identificador de la entidad de seguridad del participante (correspondiente a la tabla tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="b0b42-114">Principal ID of the participant (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="b0b42-115">joinedAt</span><span class="sxs-lookup"><span data-stu-id="b0b42-115">joinedAt</span></span>  <br/> |<span data-ttu-id="b0b42-116">bigint, no NULL</span><span class="sxs-lookup"><span data-stu-id="b0b42-116">bigint, not null</span></span>  <br/> |<span data-ttu-id="b0b42-117">Marca de tiempo del evento participante.</span><span class="sxs-lookup"><span data-stu-id="b0b42-117">Time stamp of the joining event.</span></span>  <br/> |
|<span data-ttu-id="b0b42-118">partedAt</span><span class="sxs-lookup"><span data-stu-id="b0b42-118">partedAt</span></span>  <br/> |<span data-ttu-id="b0b42-119">bigint</span><span class="sxs-lookup"><span data-stu-id="b0b42-119">bigint</span></span>  <br/> |<span data-ttu-id="b0b42-p101">Nulo si el participante aún está participando. La marca de tiempo del canal que abandona el evento si no es nulo.</span><span class="sxs-lookup"><span data-stu-id="b0b42-p101">Null if participant is still joined. The time stamp of the channel leaving event if not null.</span></span>  <br/> <span data-ttu-id="b0b42-122">Estas entradas se quitan finalmente cuando todos los traductores procesan el evento.</span><span class="sxs-lookup"><span data-stu-id="b0b42-122">These entries are eventually removed when all translators process the event.</span></span>  <br/> |
|<span data-ttu-id="b0b42-123">userUri</span><span class="sxs-lookup"><span data-stu-id="b0b42-123">userUri</span></span>  <br/> |<span data-ttu-id="b0b42-124">nvarchar(255), no NULL</span><span class="sxs-lookup"><span data-stu-id="b0b42-124">nvarchar(255), not null</span></span>  <br/> |<span data-ttu-id="b0b42-125">URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="b0b42-125">User URI.</span></span>  <br/> |
|<span data-ttu-id="b0b42-126">serverID</span><span class="sxs-lookup"><span data-stu-id="b0b42-126">serverID</span></span>  <br/> |<span data-ttu-id="b0b42-127">entero</span><span class="sxs-lookup"><span data-stu-id="b0b42-127">int</span></span>  <br/> |<span data-ttu-id="b0b42-128">Identidad del servidor (como en la tabla tblServerIdentity.serverID).</span><span class="sxs-lookup"><span data-stu-id="b0b42-128">Server identity (as in tblServerIdentity.serverID table).</span></span>  <br/> |
|<span data-ttu-id="b0b42-129">sessionId</span><span class="sxs-lookup"><span data-stu-id="b0b42-129">sessionId</span></span>  <br/> |<span data-ttu-id="b0b42-130">bigint</span><span class="sxs-lookup"><span data-stu-id="b0b42-130">bigint</span></span>  <br/> |<span data-ttu-id="b0b42-p102">Sesión del servidor. Es un número aleatorio que se genera cada vez que se inicia un servicio de chat. Sirve para diferenciar las sesiones con el fin de identificar a los participantes huérfanos.</span><span class="sxs-lookup"><span data-stu-id="b0b42-p102">Server session. This is a random number generated each time a Chat service starts. It is used to differentiate sessions for the purpose of identifying orphaned participants.</span></span>  <br/> |
   
<span data-ttu-id="b0b42-134">**Clave**</span><span class="sxs-lookup"><span data-stu-id="b0b42-134">**Key**</span></span>

|<span data-ttu-id="b0b42-135">**Columna**</span><span class="sxs-lookup"><span data-stu-id="b0b42-135">**Column**</span></span>|<span data-ttu-id="b0b42-136">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="b0b42-136">**Description**</span></span>|
|:-----|:-----|
|\<channelUri, userId, joinedAt\>  <br/> |<span data-ttu-id="b0b42-137">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="b0b42-137">Primary key.</span></span>  <br/> |
   

