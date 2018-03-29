---
title: tblComplianceData
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: tblComplianceData contiene los eventos de cumplimiento de normas que aún no se ha procesado por el adaptador de cumplimiento de normas.
ms.openlocfilehash: 6fcee20a96a83a69a3671fe9255f1336590b42de
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblcompliancedata"></a><span data-ttu-id="2f2d0-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="2f2d0-103">tblComplianceData</span></span>
 
<span data-ttu-id="2f2d0-104">tblComplianceData contiene los eventos de cumplimiento de normas que aún no se ha procesado por el adaptador de cumplimiento de normas.</span><span class="sxs-lookup"><span data-stu-id="2f2d0-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="2f2d0-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="2f2d0-105">**Columns**</span></span>

|<span data-ttu-id="2f2d0-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="2f2d0-106">**Column**</span></span>|<span data-ttu-id="2f2d0-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2f2d0-107">**Type**</span></span>|<span data-ttu-id="2f2d0-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2f2d0-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2f2d0-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="2f2d0-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="2f2d0-110">bigint, no nulo</span><span class="sxs-lookup"><span data-stu-id="2f2d0-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="2f2d0-111">ID de evento.</span><span class="sxs-lookup"><span data-stu-id="2f2d0-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="2f2d0-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="2f2d0-112">entryDate</span></span>  <br/> |<span data-ttu-id="2f2d0-113">smalldatetime, no nulo</span><span class="sxs-lookup"><span data-stu-id="2f2d0-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="2f2d0-114">Hora de inserción (puede ser el momento en el futuro para cmplType = 9, porque la entrada es un marcador de posición en este caso).</span><span class="sxs-lookup"><span data-stu-id="2f2d0-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="2f2d0-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="2f2d0-115">cmplType</span></span>  <br/> |<span data-ttu-id="2f2d0-116">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="2f2d0-116">int, not null</span></span>  <br/> | <span data-ttu-id="2f2d0-117">Tipo de evento de conformidad:</span><span class="sxs-lookup"><span data-stu-id="2f2d0-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="2f2d0-118">1: chat</span><span class="sxs-lookup"><span data-stu-id="2f2d0-118">1: Chat</span></span> <br/>  <span data-ttu-id="2f2d0-119">2: backchat</span><span class="sxs-lookup"><span data-stu-id="2f2d0-119">2: Backchat</span></span> <br/>  <span data-ttu-id="2f2d0-120">3: Descargar archivo</span><span class="sxs-lookup"><span data-stu-id="2f2d0-120">3: File download</span></span> <br/>  <span data-ttu-id="2f2d0-121">4: carga de archivos</span><span class="sxs-lookup"><span data-stu-id="2f2d0-121">4: File upload</span></span> <br/>  <span data-ttu-id="2f2d0-122">9: transferencia de archivos provisionales</span><span class="sxs-lookup"><span data-stu-id="2f2d0-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="2f2d0-123">10: chat eliminación (con reemplazar)</span><span class="sxs-lookup"><span data-stu-id="2f2d0-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="2f2d0-124">11: purga de charla</span><span class="sxs-lookup"><span data-stu-id="2f2d0-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="2f2d0-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="2f2d0-125">cmplTime</span></span>  <br/> |<span data-ttu-id="2f2d0-126">bigint, no nulo</span><span class="sxs-lookup"><span data-stu-id="2f2d0-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="2f2d0-127">Marca de tiempo para el evento.</span><span class="sxs-lookup"><span data-stu-id="2f2d0-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="2f2d0-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="2f2d0-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="2f2d0-129">nvarchar (255), no nulo</span><span class="sxs-lookup"><span data-stu-id="2f2d0-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="2f2d0-130">Canal identificador de recursos uniforme (URI).</span><span class="sxs-lookup"><span data-stu-id="2f2d0-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="2f2d0-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="2f2d0-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="2f2d0-132">bigint</span><span class="sxs-lookup"><span data-stu-id="2f2d0-132">bigint</span></span>  <br/> |<span data-ttu-id="2f2d0-133">Charla ID (correspondiente a la tabla de tblChat.chatId).</span><span class="sxs-lookup"><span data-stu-id="2f2d0-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="2f2d0-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="2f2d0-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="2f2d0-135">int, no nulo</span><span class="sxs-lookup"><span data-stu-id="2f2d0-135">int, not null</span></span>  <br/> |<span data-ttu-id="2f2d0-136">Identificador principal del póster (correspondiente a la tabla de tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="2f2d0-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="2f2d0-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="2f2d0-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="2f2d0-138">nvarchar (255), no nulo</span><span class="sxs-lookup"><span data-stu-id="2f2d0-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="2f2d0-139">URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="2f2d0-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="2f2d0-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="2f2d0-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="2f2d0-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="2f2d0-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="2f2d0-142">Mensajes (codificación depende de cmplType).</span><span class="sxs-lookup"><span data-stu-id="2f2d0-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="2f2d0-143">**Clave**</span><span class="sxs-lookup"><span data-stu-id="2f2d0-143">**Key**</span></span>

|<span data-ttu-id="2f2d0-144">**Columna**</span><span class="sxs-lookup"><span data-stu-id="2f2d0-144">**Column**</span></span>|<span data-ttu-id="2f2d0-145">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="2f2d0-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2f2d0-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="2f2d0-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="2f2d0-147">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="2f2d0-147">Primary key.</span></span>  <br/> |
   

