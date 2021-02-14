---
title: tblComplianceData
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
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: La tabla tblComplianceData contiene los eventos de cumplimiento que aún no procesó el adaptador de cumplimiento.
ms.openlocfilehash: e4ceda662b2f601660c144319a4231cebeea39ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809860"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="9b92e-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="9b92e-103">tblComplianceData</span></span>
 
<span data-ttu-id="9b92e-104">La tabla tblComplianceData contiene los eventos de cumplimiento que aún no procesó el adaptador de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="9b92e-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="9b92e-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="9b92e-105">**Columns**</span></span>

|<span data-ttu-id="9b92e-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="9b92e-106">**Column**</span></span>|<span data-ttu-id="9b92e-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9b92e-107">**Type**</span></span>|<span data-ttu-id="9b92e-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="9b92e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9b92e-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="9b92e-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="9b92e-110">bigint, no NULL</span><span class="sxs-lookup"><span data-stu-id="9b92e-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="9b92e-111">Id. del evento.</span><span class="sxs-lookup"><span data-stu-id="9b92e-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="9b92e-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="9b92e-112">entryDate</span></span>  <br/> |<span data-ttu-id="9b92e-113">smalldatetime, no NULL</span><span class="sxs-lookup"><span data-stu-id="9b92e-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="9b92e-114">Hora de inserción (puede estar lejos en el futuro para cmplType=9 porque la entrada solo es un marcador de posición en ese caso).</span><span class="sxs-lookup"><span data-stu-id="9b92e-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="9b92e-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="9b92e-115">cmplType</span></span>  <br/> |<span data-ttu-id="9b92e-116">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="9b92e-116">int, not null</span></span>  <br/> | <span data-ttu-id="9b92e-117">Tipo de evento de cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="9b92e-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="9b92e-118">1: Chat</span><span class="sxs-lookup"><span data-stu-id="9b92e-118">1: Chat</span></span> <br/>  <span data-ttu-id="9b92e-119">2: Backchat</span><span class="sxs-lookup"><span data-stu-id="9b92e-119">2: Backchat</span></span> <br/>  <span data-ttu-id="9b92e-120">3: Descarga de archivos</span><span class="sxs-lookup"><span data-stu-id="9b92e-120">3: File download</span></span> <br/>  <span data-ttu-id="9b92e-121">4: Carga de archivos</span><span class="sxs-lookup"><span data-stu-id="9b92e-121">4: File upload</span></span> <br/>  <span data-ttu-id="9b92e-122">9: Transferencia de archivo provisional</span><span class="sxs-lookup"><span data-stu-id="9b92e-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="9b92e-123">10: Eliminación de chats (con reemplazo)</span><span class="sxs-lookup"><span data-stu-id="9b92e-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="9b92e-124">11: Depuración de chats</span><span class="sxs-lookup"><span data-stu-id="9b92e-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="9b92e-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="9b92e-125">cmplTime</span></span>  <br/> |<span data-ttu-id="9b92e-126">bigint, no NULL</span><span class="sxs-lookup"><span data-stu-id="9b92e-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="9b92e-127">Marca de tiempo del evento.</span><span class="sxs-lookup"><span data-stu-id="9b92e-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="9b92e-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="9b92e-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="9b92e-129">nvarchar (255), no NULL</span><span class="sxs-lookup"><span data-stu-id="9b92e-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="9b92e-130">Identificador uniforme de recursos (URI) del canal.</span><span class="sxs-lookup"><span data-stu-id="9b92e-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="9b92e-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="9b92e-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="9b92e-132">bigint</span><span class="sxs-lookup"><span data-stu-id="9b92e-132">bigint</span></span>  <br/> |<span data-ttu-id="9b92e-133">Identificador de chat (correspondiente a la tabla tblChat.chatId).</span><span class="sxs-lookup"><span data-stu-id="9b92e-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="9b92e-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="9b92e-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="9b92e-135">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="9b92e-135">int, not null</span></span>  <br/> |<span data-ttu-id="9b92e-136">Identificador de entidad de seguridad del póster (correspondiente a la tabla tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="9b92e-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="9b92e-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="9b92e-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="9b92e-138">nvarchar (255), no NULL</span><span class="sxs-lookup"><span data-stu-id="9b92e-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="9b92e-139">URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="9b92e-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="9b92e-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="9b92e-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="9b92e-141">nvarchar (máx.)</span><span class="sxs-lookup"><span data-stu-id="9b92e-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="9b92e-142">Mensaje (la codificación depende de cmplType).</span><span class="sxs-lookup"><span data-stu-id="9b92e-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="9b92e-143">**Clave**</span><span class="sxs-lookup"><span data-stu-id="9b92e-143">**Key**</span></span>

|<span data-ttu-id="9b92e-144">**Columna**</span><span class="sxs-lookup"><span data-stu-id="9b92e-144">**Column**</span></span>|<span data-ttu-id="9b92e-145">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="9b92e-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9b92e-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="9b92e-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="9b92e-147">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="9b92e-147">Primary key.</span></span>  <br/> |
   

