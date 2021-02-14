---
title: tblFileToken
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
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: La tabla tblFileToken contiene símbolos temporales con fines de transferencia de archivos.
ms.openlocfilehash: 75d3d4df3affe3d12f94499efdb4337ade11af27
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816020"
---
# <a name="tblfiletoken"></a><span data-ttu-id="97c54-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="97c54-103">tblFileToken</span></span>
 
<span data-ttu-id="97c54-104">La tabla tblFileToken contiene símbolos temporales con fines de transferencia de archivos.</span><span class="sxs-lookup"><span data-stu-id="97c54-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="97c54-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="97c54-105">**Columns**</span></span>

|<span data-ttu-id="97c54-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="97c54-106">**Column**</span></span>|<span data-ttu-id="97c54-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="97c54-107">**Type**</span></span>|<span data-ttu-id="97c54-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="97c54-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="97c54-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="97c54-109">fileToken</span></span>  <br/> |<span data-ttu-id="97c54-110">nvarchar (50), no NULL</span><span class="sxs-lookup"><span data-stu-id="97c54-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="97c54-111">Símbolo único (un GUID).</span><span class="sxs-lookup"><span data-stu-id="97c54-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="97c54-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="97c54-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="97c54-113">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="97c54-113">int, not null</span></span>  <br/> |<span data-ttu-id="97c54-114">Id. de la entidad de seguridad que está transfiriendo el archivo.</span><span class="sxs-lookup"><span data-stu-id="97c54-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="97c54-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="97c54-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="97c54-116">GUID, no NULL</span><span class="sxs-lookup"><span data-stu-id="97c54-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="97c54-117">GUID del nodo de la sala de chat.</span><span class="sxs-lookup"><span data-stu-id="97c54-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="97c54-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="97c54-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="97c54-119">datetime, no NULL</span><span class="sxs-lookup"><span data-stu-id="97c54-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="97c54-p101">Tiempo de expiración; los tokens caducan después de 30 minutos, a menos que esté anclado (vea las siguientes descripciones en esta columna).</span><span class="sxs-lookup"><span data-stu-id="97c54-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="97c54-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="97c54-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="97c54-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="97c54-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="97c54-124">URL del archivo transferido (para el uso del Servicio de cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="97c54-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="97c54-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="97c54-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="97c54-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="97c54-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="97c54-127">URL de la miniatura del archivo transferido (para el uso del Servicio de cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="97c54-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="97c54-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="97c54-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="97c54-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="97c54-129">datetime2</span></span>  <br/> |<span data-ttu-id="97c54-130">Marca de tiempo para la operación de transferencia de archivo real (para el uso del Servicio de cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="97c54-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="97c54-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="97c54-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="97c54-132">bit</span><span class="sxs-lookup"><span data-stu-id="97c54-132">bit</span></span>  <br/> |<span data-ttu-id="97c54-133">True si se carga; False si se descarga (para el uso del Servicio de cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="97c54-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="97c54-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="97c54-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="97c54-135">bit, no NULL</span><span class="sxs-lookup"><span data-stu-id="97c54-135">bit, not null</span></span>  <br/> |<span data-ttu-id="97c54-136">True si el token está anclado.</span><span class="sxs-lookup"><span data-stu-id="97c54-136">True if token is pinned.</span></span> <span data-ttu-id="97c54-137">Se usa para mantener el token en la tabla hasta que el servicio de cumplimiento tenga la oportunidad de recuperar los campos relevantes de él.</span><span class="sxs-lookup"><span data-stu-id="97c54-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="97c54-138">**Keys**</span><span class="sxs-lookup"><span data-stu-id="97c54-138">**Keys**</span></span>

|<span data-ttu-id="97c54-139">**Columna**</span><span class="sxs-lookup"><span data-stu-id="97c54-139">**Column**</span></span>|<span data-ttu-id="97c54-140">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="97c54-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="97c54-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="97c54-141">fileToken</span></span>  <br/> |<span data-ttu-id="97c54-142">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="97c54-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="97c54-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="97c54-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="97c54-144">Clave externa con búsqueda en la tabla tblNode.nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="97c54-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

