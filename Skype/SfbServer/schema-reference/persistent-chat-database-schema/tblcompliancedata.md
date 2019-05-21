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
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData contiene los eventos de conformidad que aún no ha procesado el adaptador de cumplimiento.
ms.openlocfilehash: b505b3e05fb2aebba98804f5b7ad6a1d4d2da53e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295513"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="f1f3e-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="f1f3e-103">tblComplianceData</span></span>
 
<span data-ttu-id="f1f3e-104">tblComplianceData contiene los eventos de conformidad que aún no ha procesado el adaptador de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="f1f3e-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="f1f3e-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="f1f3e-105">**Columns**</span></span>

|<span data-ttu-id="f1f3e-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="f1f3e-106">**Column**</span></span>|<span data-ttu-id="f1f3e-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f1f3e-107">**Type**</span></span>|<span data-ttu-id="f1f3e-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f1f3e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f1f3e-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="f1f3e-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="f1f3e-110">BIGINT, not null</span><span class="sxs-lookup"><span data-stu-id="f1f3e-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="f1f3e-111">IDENTIFICADOR de evento.</span><span class="sxs-lookup"><span data-stu-id="f1f3e-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="f1f3e-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="f1f3e-112">entryDate</span></span>  <br/> |<span data-ttu-id="f1f3e-113">smalldatetime, not null</span><span class="sxs-lookup"><span data-stu-id="f1f3e-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="f1f3e-114">Hora de inserción (puede ser muy próxima para cmplType = 9 porque la entrada es solo un marcador de posición en ese caso).</span><span class="sxs-lookup"><span data-stu-id="f1f3e-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="f1f3e-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="f1f3e-115">cmplType</span></span>  <br/> |<span data-ttu-id="f1f3e-116">int, not null</span><span class="sxs-lookup"><span data-stu-id="f1f3e-116">int, not null</span></span>  <br/> | <span data-ttu-id="f1f3e-117">Tipo de evento de conformidad:</span><span class="sxs-lookup"><span data-stu-id="f1f3e-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="f1f3e-118">1: chatear</span><span class="sxs-lookup"><span data-stu-id="f1f3e-118">1: Chat</span></span> <br/>  <span data-ttu-id="f1f3e-119">2: chatear</span><span class="sxs-lookup"><span data-stu-id="f1f3e-119">2: Backchat</span></span> <br/>  <span data-ttu-id="f1f3e-120">3: descarga de archivos</span><span class="sxs-lookup"><span data-stu-id="f1f3e-120">3: File download</span></span> <br/>  <span data-ttu-id="f1f3e-121">4: carga de archivos</span><span class="sxs-lookup"><span data-stu-id="f1f3e-121">4: File upload</span></span> <br/>  <span data-ttu-id="f1f3e-122">9: transferencia provisional de archivos</span><span class="sxs-lookup"><span data-stu-id="f1f3e-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="f1f3e-123">10: eliminación de chat (con Replace)</span><span class="sxs-lookup"><span data-stu-id="f1f3e-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="f1f3e-124">11: purgado de chat</span><span class="sxs-lookup"><span data-stu-id="f1f3e-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="f1f3e-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="f1f3e-125">cmplTime</span></span>  <br/> |<span data-ttu-id="f1f3e-126">BIGINT, not null</span><span class="sxs-lookup"><span data-stu-id="f1f3e-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="f1f3e-127">Marca de tiempo del evento.</span><span class="sxs-lookup"><span data-stu-id="f1f3e-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="f1f3e-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="f1f3e-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="f1f3e-129">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="f1f3e-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="f1f3e-130">Identificador uniforme de recursos (URI) del canal.</span><span class="sxs-lookup"><span data-stu-id="f1f3e-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="f1f3e-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="f1f3e-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="f1f3e-132">BIGINT</span><span class="sxs-lookup"><span data-stu-id="f1f3e-132">bigint</span></span>  <br/> |<span data-ttu-id="f1f3e-133">IDENTIFICADOR de chat (corresponde a la tabla tblChat. chatId).</span><span class="sxs-lookup"><span data-stu-id="f1f3e-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="f1f3e-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="f1f3e-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="f1f3e-135">int, not null</span><span class="sxs-lookup"><span data-stu-id="f1f3e-135">int, not null</span></span>  <br/> |<span data-ttu-id="f1f3e-136">IDENTIFICADOR principal del póster (correspondiente a la tabla tblPrincipal. prinID).</span><span class="sxs-lookup"><span data-stu-id="f1f3e-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="f1f3e-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="f1f3e-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="f1f3e-138">nvarchar (255), not null</span><span class="sxs-lookup"><span data-stu-id="f1f3e-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="f1f3e-139">URI de usuario.</span><span class="sxs-lookup"><span data-stu-id="f1f3e-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="f1f3e-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="f1f3e-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="f1f3e-141">nvarchar (Max)</span><span class="sxs-lookup"><span data-stu-id="f1f3e-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="f1f3e-142">Mensaje (la codificación depende de cmplType).</span><span class="sxs-lookup"><span data-stu-id="f1f3e-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="f1f3e-143">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f1f3e-143">**Key**</span></span>

|<span data-ttu-id="f1f3e-144">**Columna**</span><span class="sxs-lookup"><span data-stu-id="f1f3e-144">**Column**</span></span>|<span data-ttu-id="f1f3e-145">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f1f3e-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f1f3e-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="f1f3e-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="f1f3e-147">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="f1f3e-147">Primary key.</span></span>  <br/> |
   

