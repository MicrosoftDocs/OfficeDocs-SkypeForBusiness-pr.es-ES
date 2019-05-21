---
title: tblFileToken
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: tblFileToken contiene tokens temporales para la transferencia de archivos.
ms.openlocfilehash: 108c9738657354881324ec720f50a51605530922
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295408"
---
# <a name="tblfiletoken"></a><span data-ttu-id="e8fe2-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="e8fe2-103">tblFileToken</span></span>
 
<span data-ttu-id="e8fe2-104">tblFileToken contiene tokens temporales para la transferencia de archivos.</span><span class="sxs-lookup"><span data-stu-id="e8fe2-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="e8fe2-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="e8fe2-105">**Columns**</span></span>

|<span data-ttu-id="e8fe2-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="e8fe2-106">**Column**</span></span>|<span data-ttu-id="e8fe2-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e8fe2-107">**Type**</span></span>|<span data-ttu-id="e8fe2-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e8fe2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e8fe2-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="e8fe2-109">fileToken</span></span>  <br/> |<span data-ttu-id="e8fe2-110">nvarchar (50), not null</span><span class="sxs-lookup"><span data-stu-id="e8fe2-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="e8fe2-111">Identificador exclusivo (un GUID).</span><span class="sxs-lookup"><span data-stu-id="e8fe2-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="e8fe2-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="e8fe2-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="e8fe2-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="e8fe2-113">int, not null</span></span>  <br/> |<span data-ttu-id="e8fe2-114">IDENTIFICADOR de la entidad de identidad que está transfiriendo el archivo.</span><span class="sxs-lookup"><span data-stu-id="e8fe2-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="e8fe2-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="e8fe2-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="e8fe2-116">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="e8fe2-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="e8fe2-117">GUID del nodo del salón de chat.</span><span class="sxs-lookup"><span data-stu-id="e8fe2-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="e8fe2-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="e8fe2-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="e8fe2-119">DateTime, not null</span><span class="sxs-lookup"><span data-stu-id="e8fe2-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="e8fe2-120">Fecha de expiración.</span><span class="sxs-lookup"><span data-stu-id="e8fe2-120">Expiration time.</span></span> <span data-ttu-id="e8fe2-121">(Los tokens vencen después de 30 minutos, a menos que se hayan anclado (vea las siguientes descripciones en esta columna).</span><span class="sxs-lookup"><span data-stu-id="e8fe2-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="e8fe2-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="e8fe2-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="e8fe2-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e8fe2-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e8fe2-124">Dirección URL del archivo transferido (para el uso del servicio de cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="e8fe2-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="e8fe2-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="e8fe2-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="e8fe2-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e8fe2-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e8fe2-127">Dirección URL de la miniatura del archivo transferido (para el uso del servicio de cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="e8fe2-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="e8fe2-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="e8fe2-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="e8fe2-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="e8fe2-129">datetime2</span></span>  <br/> |<span data-ttu-id="e8fe2-130">Marca de hora para la operación de transferencia de archivos real (para el uso del servicio de cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="e8fe2-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="e8fe2-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="e8fe2-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="e8fe2-132">bit</span><span class="sxs-lookup"><span data-stu-id="e8fe2-132">bit</span></span>  <br/> |<span data-ttu-id="e8fe2-133">Es verdadero si se carga; Falso si descargar (para uso del servicio de cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="e8fe2-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="e8fe2-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="e8fe2-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="e8fe2-135">bit, not null</span><span class="sxs-lookup"><span data-stu-id="e8fe2-135">bit, not null</span></span>  <br/> |<span data-ttu-id="e8fe2-136">True si el símbolo está anclado.</span><span class="sxs-lookup"><span data-stu-id="e8fe2-136">True if token is pinned.</span></span> <span data-ttu-id="e8fe2-137">Se usa para mantener el token en la tabla hasta que el servicio de cumplimiento tiene la posibilidad de recuperar los campos correspondientes de él.</span><span class="sxs-lookup"><span data-stu-id="e8fe2-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="e8fe2-138">**Sus**</span><span class="sxs-lookup"><span data-stu-id="e8fe2-138">**Keys**</span></span>

|<span data-ttu-id="e8fe2-139">**Columna**</span><span class="sxs-lookup"><span data-stu-id="e8fe2-139">**Column**</span></span>|<span data-ttu-id="e8fe2-140">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="e8fe2-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e8fe2-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="e8fe2-141">fileToken</span></span>  <br/> |<span data-ttu-id="e8fe2-142">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="e8fe2-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e8fe2-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="e8fe2-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="e8fe2-144">Clave externa con la búsqueda en la tabla tblNode. nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="e8fe2-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

