---
title: tblFileToken
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
description: la tabla tblFileToken contiene símbolos temporales con fines de transferencia de archivo de.
ms.openlocfilehash: c6735cf7da1412cca86817360c1a35030e8b0df4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929857"
---
# <a name="tblfiletoken"></a><span data-ttu-id="39e8b-103">tblFileToken</span><span class="sxs-lookup"><span data-stu-id="39e8b-103">tblFileToken</span></span>
 
<span data-ttu-id="39e8b-104">la tabla tblFileToken contiene símbolos temporales con fines de transferencia de archivo de.</span><span class="sxs-lookup"><span data-stu-id="39e8b-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>
  
<span data-ttu-id="39e8b-105">**Columnas**</span><span class="sxs-lookup"><span data-stu-id="39e8b-105">**Columns**</span></span>

|<span data-ttu-id="39e8b-106">**Columna**</span><span class="sxs-lookup"><span data-stu-id="39e8b-106">**Column**</span></span>|<span data-ttu-id="39e8b-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="39e8b-107">**Type**</span></span>|<span data-ttu-id="39e8b-108">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="39e8b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="39e8b-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="39e8b-109">fileToken</span></span>  <br/> |<span data-ttu-id="39e8b-110">nvarchar (50), no es nulo</span><span class="sxs-lookup"><span data-stu-id="39e8b-110">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="39e8b-111">Símbolo único (GUID).</span><span class="sxs-lookup"><span data-stu-id="39e8b-111">Unique token (a GUID).</span></span>  <br/> |
|<span data-ttu-id="39e8b-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="39e8b-112">fileTokenUserID</span></span>  <br/> |<span data-ttu-id="39e8b-113">int, no es nulo</span><span class="sxs-lookup"><span data-stu-id="39e8b-113">int, not null</span></span>  <br/> |<span data-ttu-id="39e8b-114">Identificador de la entidad de seguridad que va a transferir el archivo.</span><span class="sxs-lookup"><span data-stu-id="39e8b-114">ID of the principal that is transferring the file.</span></span>  <br/> |
|<span data-ttu-id="39e8b-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="39e8b-115">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="39e8b-116">GUID, no es nulo</span><span class="sxs-lookup"><span data-stu-id="39e8b-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="39e8b-117">GUID del nodo del salón de chat.</span><span class="sxs-lookup"><span data-stu-id="39e8b-117">GUID of the chat room node.</span></span>  <br/> |
|<span data-ttu-id="39e8b-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="39e8b-118">fileTokenExpireDate</span></span>  <br/> |<span data-ttu-id="39e8b-119">DateTime, no es nulo</span><span class="sxs-lookup"><span data-stu-id="39e8b-119">datetime, not null</span></span>  <br/> |<span data-ttu-id="39e8b-120">Tiempo de expiración.</span><span class="sxs-lookup"><span data-stu-id="39e8b-120">Expiration time.</span></span> <span data-ttu-id="39e8b-121">(Los tokens caducan después de 30 minutos, a menos que anclados (vea las siguientes descripciones en esta columna).</span><span class="sxs-lookup"><span data-stu-id="39e8b-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span>  <br/> |
|<span data-ttu-id="39e8b-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="39e8b-122">fileTokenComplianceFileUrl</span></span>  <br/> |<span data-ttu-id="39e8b-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="39e8b-123">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="39e8b-124">Dirección URL del archivo transferido (para el uso del servicio de cumplimiento de normas).</span><span class="sxs-lookup"><span data-stu-id="39e8b-124">URL of the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="39e8b-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="39e8b-125">fileTokenComplianceThumbnailUrl</span></span>  <br/> |<span data-ttu-id="39e8b-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="39e8b-126">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="39e8b-127">Dirección URL de la imagen en miniatura del archivo transferido (para el uso del servicio de cumplimiento de normas).</span><span class="sxs-lookup"><span data-stu-id="39e8b-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="39e8b-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="39e8b-128">fileTokenComplianceTime</span></span>  <br/> |<span data-ttu-id="39e8b-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="39e8b-129">datetime2</span></span>  <br/> |<span data-ttu-id="39e8b-130">Marca de tiempo para la operación de transferencia de archivo real (para el uso del servicio de cumplimiento de normas).</span><span class="sxs-lookup"><span data-stu-id="39e8b-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="39e8b-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="39e8b-131">fileTokenComplianceIsUpload</span></span>  <br/> |<span data-ttu-id="39e8b-132">bit</span><span class="sxs-lookup"><span data-stu-id="39e8b-132">bit</span></span>  <br/> |<span data-ttu-id="39e8b-133">True si la carga; False si descarga (para el uso del servicio de cumplimiento de normas).</span><span class="sxs-lookup"><span data-stu-id="39e8b-133">True if upload; False if download (for Compliance service use).</span></span>  <br/> |
|<span data-ttu-id="39e8b-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="39e8b-134">fileTokenCompliancePinned</span></span>  <br/> |<span data-ttu-id="39e8b-135">bit, no es nulo</span><span class="sxs-lookup"><span data-stu-id="39e8b-135">bit, not null</span></span>  <br/> |<span data-ttu-id="39e8b-136">True si se fija el símbolo (token).</span><span class="sxs-lookup"><span data-stu-id="39e8b-136">True if token is pinned.</span></span> <span data-ttu-id="39e8b-137">Se utiliza para mantener el token en la tabla hasta que el servicio de cumplimiento tiene una oportunidad para recuperar los campos correspondientes de él.</span><span class="sxs-lookup"><span data-stu-id="39e8b-137">It's used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span>  <br/> |
   
<span data-ttu-id="39e8b-138">**Claves**</span><span class="sxs-lookup"><span data-stu-id="39e8b-138">**Keys**</span></span>

|<span data-ttu-id="39e8b-139">**Columna**</span><span class="sxs-lookup"><span data-stu-id="39e8b-139">**Column**</span></span>|<span data-ttu-id="39e8b-140">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="39e8b-140">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="39e8b-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="39e8b-141">fileToken</span></span>  <br/> |<span data-ttu-id="39e8b-142">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="39e8b-142">Primary key.</span></span>  <br/> |
|<span data-ttu-id="39e8b-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="39e8b-143">fileTokenChannelID</span></span>  <br/> |<span data-ttu-id="39e8b-144">Clave externa con búsqueda en la tabla tblNode.nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="39e8b-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span>  <br/> |
   

