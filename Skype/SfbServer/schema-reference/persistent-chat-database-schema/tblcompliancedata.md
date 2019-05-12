---
title: tblComplianceData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05b28f9b-4aba-4b69-ba8d-2ceeb6cbfaac
description: la tabla tblComplianceData contiene los eventos de cumplimiento que aún no se han procesado por el adaptador de cumplimiento.
ms.openlocfilehash: 88319da90c1f3e03b6ca3e441259972f51d0bcf9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929934"
---
# <a name="tblcompliancedata"></a><span data-ttu-id="f215c-103">tblComplianceData</span><span class="sxs-lookup"><span data-stu-id="f215c-103">tblComplianceData</span></span>
 
<span data-ttu-id="f215c-104">la tabla tblComplianceData contiene los eventos de cumplimiento que aún no se han procesado por el adaptador de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="f215c-104">tblComplianceData contains the compliance events that have not been processed by the compliance adapter yet.</span></span>
  
<span data-ttu-id="f215c-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="f215c-105">**Columns**</span></span>

|<span data-ttu-id="f215c-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="f215c-106">**Column**</span></span>|<span data-ttu-id="f215c-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f215c-107">**Type**</span></span>|<span data-ttu-id="f215c-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f215c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f215c-109">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="f215c-109">cmplEventID</span></span>  <br/> |<span data-ttu-id="f215c-110">bigint, no es nulo</span><span class="sxs-lookup"><span data-stu-id="f215c-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="f215c-111">Identificador de evento.</span><span class="sxs-lookup"><span data-stu-id="f215c-111">Event ID.</span></span>  <br/> |
|<span data-ttu-id="f215c-112">entryDate</span><span class="sxs-lookup"><span data-stu-id="f215c-112">entryDate</span></span>  <br/> |<span data-ttu-id="f215c-113">smalldatetime, no es nulo</span><span class="sxs-lookup"><span data-stu-id="f215c-113">smalldatetime, not null</span></span>  <br/> |<span data-ttu-id="f215c-114">Hora de inserción (puede estar lejos en el futuro para cmplType = 9 porque la entrada es un marcador de posición en ese caso).</span><span class="sxs-lookup"><span data-stu-id="f215c-114">Time of insertion (may be far in the future for cmplType=9 because the entry is just a placeholder in that case).</span></span>  <br/> |
|<span data-ttu-id="f215c-115">cmplType</span><span class="sxs-lookup"><span data-stu-id="f215c-115">cmplType</span></span>  <br/> |<span data-ttu-id="f215c-116">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="f215c-116">int, not null</span></span>  <br/> | <span data-ttu-id="f215c-117">Tipo de evento de cumplimiento:</span><span class="sxs-lookup"><span data-stu-id="f215c-117">Type of compliance event:</span></span> <br/>  <span data-ttu-id="f215c-118">1: conversaciones</span><span class="sxs-lookup"><span data-stu-id="f215c-118">1: Chat</span></span> <br/>  <span data-ttu-id="f215c-119">2: backchat</span><span class="sxs-lookup"><span data-stu-id="f215c-119">2: Backchat</span></span> <br/>  <span data-ttu-id="f215c-120">3: descarga de archivos</span><span class="sxs-lookup"><span data-stu-id="f215c-120">3: File download</span></span> <br/>  <span data-ttu-id="f215c-121">4: carga de archivos</span><span class="sxs-lookup"><span data-stu-id="f215c-121">4: File upload</span></span> <br/>  <span data-ttu-id="f215c-122">9: transferencia de archivo provisional</span><span class="sxs-lookup"><span data-stu-id="f215c-122">9: Provisional file transfer</span></span> <br/>  <span data-ttu-id="f215c-123">10: conversaciones eliminación (con reemplazo)</span><span class="sxs-lookup"><span data-stu-id="f215c-123">10: Chat deletion (with replace)</span></span> <br/>  <span data-ttu-id="f215c-124">11: depuración de chats</span><span class="sxs-lookup"><span data-stu-id="f215c-124">11: Chat purging</span></span> <br/> |
|<span data-ttu-id="f215c-125">cmplTime</span><span class="sxs-lookup"><span data-stu-id="f215c-125">cmplTime</span></span>  <br/> |<span data-ttu-id="f215c-126">bigint, no es nulo</span><span class="sxs-lookup"><span data-stu-id="f215c-126">bigint, not null</span></span>  <br/> |<span data-ttu-id="f215c-127">Marca de tiempo para el evento.</span><span class="sxs-lookup"><span data-stu-id="f215c-127">Time stamp for the event.</span></span>  <br/> |
|<span data-ttu-id="f215c-128">cmplChannelUri</span><span class="sxs-lookup"><span data-stu-id="f215c-128">cmplChannelUri</span></span>  <br/> |<span data-ttu-id="f215c-129">nvarchar (255), no es nulo</span><span class="sxs-lookup"><span data-stu-id="f215c-129">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="f215c-130">Identificador de canal uniforme de recursos (URI).</span><span class="sxs-lookup"><span data-stu-id="f215c-130">Channel Uniform Resource Identifier (URI).</span></span>  <br/> |
|<span data-ttu-id="f215c-131">cmplChatID</span><span class="sxs-lookup"><span data-stu-id="f215c-131">cmplChatID</span></span>  <br/> |<span data-ttu-id="f215c-132">bigint</span><span class="sxs-lookup"><span data-stu-id="f215c-132">bigint</span></span>  <br/> |<span data-ttu-id="f215c-133">Identificador de Chat (correspondiente a la tabla tblChat.chatId).</span><span class="sxs-lookup"><span data-stu-id="f215c-133">Chat ID (corresponding to tblChat.chatId table).</span></span>  <br/> |
|<span data-ttu-id="f215c-134">cmplUserID</span><span class="sxs-lookup"><span data-stu-id="f215c-134">cmplUserID</span></span>  <br/> |<span data-ttu-id="f215c-135">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="f215c-135">int, not null</span></span>  <br/> |<span data-ttu-id="f215c-136">Identificador de entidad del póster (correspondiente a la tabla tblPrincipal.prinID).</span><span class="sxs-lookup"><span data-stu-id="f215c-136">Principal ID of the poster (corresponding to tblPrincipal.prinID table).</span></span>  <br/> |
|<span data-ttu-id="f215c-137">cmplUserUri</span><span class="sxs-lookup"><span data-stu-id="f215c-137">cmplUserUri</span></span>  <br/> |<span data-ttu-id="f215c-138">nvarchar (255), no es nulo</span><span class="sxs-lookup"><span data-stu-id="f215c-138">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="f215c-139">URI del usuario.</span><span class="sxs-lookup"><span data-stu-id="f215c-139">User URI.</span></span>  <br/> |
|<span data-ttu-id="f215c-140">cmplMessage</span><span class="sxs-lookup"><span data-stu-id="f215c-140">cmplMessage</span></span>  <br/> |<span data-ttu-id="f215c-141">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="f215c-141">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="f215c-142">Mensaje (codificación depende de cmplType).</span><span class="sxs-lookup"><span data-stu-id="f215c-142">Message (encoding depends on cmplType).</span></span>  <br/> |
   
<span data-ttu-id="f215c-143">**Clave**</span><span class="sxs-lookup"><span data-stu-id="f215c-143">**Key**</span></span>

|<span data-ttu-id="f215c-144">**Columna**</span><span class="sxs-lookup"><span data-stu-id="f215c-144">**Column**</span></span>|<span data-ttu-id="f215c-145">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f215c-145">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f215c-146">cmplEventID</span><span class="sxs-lookup"><span data-stu-id="f215c-146">cmplEventID</span></span>  <br/> |<span data-ttu-id="f215c-147">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="f215c-147">Primary key.</span></span>  <br/> |
   

