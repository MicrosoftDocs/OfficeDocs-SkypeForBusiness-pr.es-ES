---
title: tblComplianceData
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: la tabla tblComplianceData contiene los eventos de cumplimiento que aún no se han procesado por el adaptador de cumplimiento.
ms.openlocfilehash: e617f7821fcf026f279f333d45f526a1322509a1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212617"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="a26d5-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="a26d5-103">tblComplianceData</span></span>
 
<span data-ttu-id="a26d5-104">la tabla tblComplianceData contiene los eventos de cumplimiento que aún no se han procesado por el adaptador de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="a26d5-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="a26d5-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="a26d5-105">**Columns**</span></span>

|<span data-ttu-id="a26d5-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="a26d5-106">**Column**</span></span>|<span data-ttu-id="a26d5-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a26d5-107">**Type**</span></span>|<span data-ttu-id="a26d5-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a26d5-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a26d5-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="a26d5-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="a26d5-110">bigint, no es nulo</span><span class="sxs-lookup"><span data-stu-id="a26d5-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="a26d5-111">Identificador de evento.</span><span class="sxs-lookup"><span data-stu-id="a26d5-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="a26d5-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="a26d5-112">entryDate</span></span>  <br/> |<span data-ttu-id="a26d5-113">smalldatetime, no es nulo</span><span class="sxs-lookup"><span data-stu-id="a26d5-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="a26d5-114">Hora de inserción (puede estar lejos en el futuro para cmplType = 9 porque la entrada es un marcador de posición en ese caso).</span><span class="sxs-lookup"><span data-stu-id="a26d5-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="a26d5-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="a26d5-115">cmplType</span></span>  <br/> |<span data-ttu-id="a26d5-116">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="a26d5-116">int, not null</span></span>  <br/> | <span data-ttu-id="a26d5-117">Tipo de evento de cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="a26d5-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="a26d5-118">1: conversaciones</span><span class="sxs-lookup"><span data-stu-id="a26d5-118">1: Chat</span></span> <br/>  <span data-ttu-id="a26d5-119">2: backchat</span><span class="sxs-lookup"><span data-stu-id="a26d5-119">2: Backchat</span></span> <br/>  <span data-ttu-id="a26d5-120">3: descarga de archivos</span><span class="sxs-lookup"><span data-stu-id="a26d5-120">3: File download</span></span> <br/>  <span data-ttu-id="a26d5-121">4: carga de archivos</span><span class="sxs-lookup"><span data-stu-id="a26d5-121">4: File upload</span></span> <br/>  <span data-ttu-id="a26d5-122">9: transferencia de archivo provisional</span><span class="sxs-lookup"><span data-stu-id="a26d5-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="a26d5-123">10: conversaciones eliminación (con reemplazo)</span><span class="sxs-lookup"><span data-stu-id="a26d5-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="a26d5-124">11: depuración de chats</span><span class="sxs-lookup"><span data-stu-id="a26d5-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="a26d5-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="a26d5-125">cmplTime</span></span>  <br/> |<span data-ttu-id="a26d5-126">bigint, no es nulo</span><span class="sxs-lookup"><span data-stu-id="a26d5-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="a26d5-127">Marca de tiempo para el evento.</span><span class="sxs-lookup"><span data-stu-id="a26d5-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="a26d5-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="a26d5-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="a26d5-129">nvarchar (255), no es nulo</span><span class="sxs-lookup"><span data-stu-id="a26d5-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="a26d5-130">Identificador de canal uniforme de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="a26d5-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="a26d5-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="a26d5-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="a26d5-132">bigint</span><span class="sxs-lookup"><span data-stu-id="a26d5-132">bigint</span></span>  <br/> |<span data-ttu-id="a26d5-133">Identificador de Chat (correspondiente a la tabla tblChat.chatId).</span><span class="sxs-lookup"><span data-stu-id="a26d5-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="a26d5-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="a26d5-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="a26d5-135">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="a26d5-135">int, not null</span></span>  <br/> |<span data-ttu-id="a26d5-136">Identificador de entidad del póster (correspondiente a la tabla tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="a26d5-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="a26d5-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="a26d5-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="a26d5-138">nvarchar (255), no es nulo</span><span class="sxs-lookup"><span data-stu-id="a26d5-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="a26d5-139">URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="a26d5-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="a26d5-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="a26d5-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="a26d5-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="a26d5-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="a26d5-142">Mensaje (codificación depende de cmplType).</span><span class="sxs-lookup"><span data-stu-id="a26d5-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="a26d5-143">**Clave**</span><span class="sxs-lookup"><span data-stu-id="a26d5-143">**Key**</span></span>

|<span data-ttu-id="a26d5-144">**Columna**</span><span class="sxs-lookup"><span data-stu-id="a26d5-144">**Column**</span></span>|<span data-ttu-id="a26d5-145">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="a26d5-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a26d5-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="a26d5-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="a26d5-147">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="a26d5-147">Primary key.</span></span>  <br/> |
   

