---
title: tblComplianceData
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
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData contiene los eventos de conformidad que aún no ha procesado el adaptador de cumplimiento.
ms.openlocfilehash: f09acd44e803c629e45afa18683ac7bc863564a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814668"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="7db99-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="7db99-103">tblComplianceData</span></span>
 
<span data-ttu-id="7db99-104">tblComplianceData contiene los eventos de conformidad que aún no ha procesado el adaptador de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="7db99-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="7db99-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="7db99-105">**Columns**</span></span>

|<span data-ttu-id="7db99-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="7db99-106">**Column**</span></span>|<span data-ttu-id="7db99-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7db99-107">**Type**</span></span>|<span data-ttu-id="7db99-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7db99-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7db99-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="7db99-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="7db99-110">BIGINT, not null</span><span class="sxs-lookup"><span data-stu-id="7db99-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="7db99-111">IDENTIFICADOR de evento.</span><span class="sxs-lookup"><span data-stu-id="7db99-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="7db99-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="7db99-112">entryDate</span></span>  <br/> |<span data-ttu-id="7db99-113">smalldatetime, not null</span><span class="sxs-lookup"><span data-stu-id="7db99-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="7db99-114">Hora de inserción (puede ser muy próxima para cmplType = 9 porque la entrada es solo un marcador de posición en ese caso).</span><span class="sxs-lookup"><span data-stu-id="7db99-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="7db99-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="7db99-115">cmplType</span></span>  <br/> |<span data-ttu-id="7db99-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="7db99-116">int, not null</span></span>  <br/> | <span data-ttu-id="7db99-117">Tipo de evento de conformidad:</span><span class="sxs-lookup"><span data-stu-id="7db99-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="7db99-118">1: chatear</span><span class="sxs-lookup"><span data-stu-id="7db99-118">1: Chat</span></span> <br/>  <span data-ttu-id="7db99-119">2: chatear</span><span class="sxs-lookup"><span data-stu-id="7db99-119">2: Backchat</span></span> <br/>  <span data-ttu-id="7db99-120">3: descarga de archivos</span><span class="sxs-lookup"><span data-stu-id="7db99-120">3: File download</span></span> <br/>  <span data-ttu-id="7db99-121">4: carga de archivos</span><span class="sxs-lookup"><span data-stu-id="7db99-121">4: File upload</span></span> <br/>  <span data-ttu-id="7db99-122">9: transferencia provisional de archivos</span><span class="sxs-lookup"><span data-stu-id="7db99-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="7db99-123">10: eliminación de chat (con Replace)</span><span class="sxs-lookup"><span data-stu-id="7db99-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="7db99-124">11: purgado de chat</span><span class="sxs-lookup"><span data-stu-id="7db99-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="7db99-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="7db99-125">cmplTime</span></span>  <br/> |<span data-ttu-id="7db99-126">BIGINT, not null</span><span class="sxs-lookup"><span data-stu-id="7db99-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="7db99-127">Marca de tiempo del evento.</span><span class="sxs-lookup"><span data-stu-id="7db99-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="7db99-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="7db99-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="7db99-129">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="7db99-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="7db99-130">Identificador uniforme de recursos (URI) del canal.</span><span class="sxs-lookup"><span data-stu-id="7db99-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="7db99-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="7db99-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="7db99-132">BIGINT</span><span class="sxs-lookup"><span data-stu-id="7db99-132">bigint</span></span>  <br/> |<span data-ttu-id="7db99-133">IDENTIFICADOR de chat (corresponde a la tabla tblChat. chatId).</span><span class="sxs-lookup"><span data-stu-id="7db99-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="7db99-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="7db99-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="7db99-135">int, not null</span><span class="sxs-lookup"><span data-stu-id="7db99-135">int, not null</span></span>  <br/> |<span data-ttu-id="7db99-136">IDENTIFICADOR principal del póster (correspondiente a la tabla tblPrincipal. prinID).</span><span class="sxs-lookup"><span data-stu-id="7db99-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="7db99-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="7db99-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="7db99-138">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="7db99-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="7db99-139">URI de usuario.</span><span class="sxs-lookup"><span data-stu-id="7db99-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="7db99-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="7db99-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="7db99-141">nvarchar (Max)</span><span class="sxs-lookup"><span data-stu-id="7db99-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="7db99-142">Mensaje (la codificación depende de cmplType).</span><span class="sxs-lookup"><span data-stu-id="7db99-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="7db99-143">**Clave**</span><span class="sxs-lookup"><span data-stu-id="7db99-143">**Key**</span></span>

|<span data-ttu-id="7db99-144">**Columna**</span><span class="sxs-lookup"><span data-stu-id="7db99-144">**Column**</span></span>|<span data-ttu-id="7db99-145">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="7db99-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7db99-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="7db99-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="7db99-147">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="7db99-147">Primary key.</span></span>  <br/> |
   

