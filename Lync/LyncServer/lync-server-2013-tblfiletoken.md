---
title: 'Lync Server 2013: tblFileToken'
description: 'Lync Server 2013: tblFileToken.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblFileToken
ms:assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558646(v=OCS.15)
ms:contentKeyID: 48184073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c0a0465bd769cff5c23c00a98f79e2346232175
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547636"
---
# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="b3349-103">tblFileToken en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b3349-103">tblFileToken in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b3349-104">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="b3349-104">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="b3349-105">La tabla tblFileToken contiene símbolos temporales con fines de transferencia de archivos.</span><span class="sxs-lookup"><span data-stu-id="b3349-105">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="b3349-106">Columnas</span><span class="sxs-lookup"><span data-stu-id="b3349-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3349-107">Columna</span><span class="sxs-lookup"><span data-stu-id="b3349-107">Column</span></span></th>
<th><span data-ttu-id="b3349-108">Tipo</span><span class="sxs-lookup"><span data-stu-id="b3349-108">Type</span></span></th>
<th><span data-ttu-id="b3349-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="b3349-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3349-110">fileToken</span><span class="sxs-lookup"><span data-stu-id="b3349-110">fileToken</span></span></p></td>
<td><p><span data-ttu-id="b3349-111">nvarchar (50), no NULL</span><span class="sxs-lookup"><span data-stu-id="b3349-111">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="b3349-112">Símbolo único (un GUID).</span><span class="sxs-lookup"><span data-stu-id="b3349-112">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3349-113">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="b3349-113">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="b3349-114">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="b3349-114">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b3349-115">Id. de la entidad de seguridad que está transfiriendo el archivo.</span><span class="sxs-lookup"><span data-stu-id="b3349-115">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3349-116">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="b3349-116">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="b3349-117">GUID, no NULL</span><span class="sxs-lookup"><span data-stu-id="b3349-117">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="b3349-118">GUID del nodo de la sala de chat.</span><span class="sxs-lookup"><span data-stu-id="b3349-118">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3349-119">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="b3349-119">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="b3349-120">datetime, no NULL</span><span class="sxs-lookup"><span data-stu-id="b3349-120">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="b3349-p101">Tiempo de expiración; los tokens caducan después de 30 minutos, a menos que esté anclado (vea las siguientes descripciones en esta columna).</span><span class="sxs-lookup"><span data-stu-id="b3349-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3349-123">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="b3349-123">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="b3349-124">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b3349-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3349-125">URL del archivo transferido (para el uso del Servicio de cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="b3349-125">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3349-126">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="b3349-126">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="b3349-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b3349-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b3349-128">URL de la miniatura del archivo transferido (para el uso del Servicio de cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="b3349-128">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3349-129">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="b3349-129">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="b3349-130">datetime2</span><span class="sxs-lookup"><span data-stu-id="b3349-130">datetime2</span></span></p></td>
<td><p><span data-ttu-id="b3349-131">Marca de tiempo para la operación de transferencia de archivo real (para el uso del Servicio de cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="b3349-131">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3349-132">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="b3349-132">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="b3349-133">bit</span><span class="sxs-lookup"><span data-stu-id="b3349-133">bit</span></span></p></td>
<td><p><span data-ttu-id="b3349-134">True si se carga; False si se descarga (para el uso del Servicio de cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="b3349-134">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b3349-135">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="b3349-135">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="b3349-136">bit, no NULL</span><span class="sxs-lookup"><span data-stu-id="b3349-136">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="b3349-p102">True si el token está anclado. Se usa para mantener el token en la tabla hasta que el Servicio de cumplimiento tenga la oportunidad de recuperar los campos relevantes de él.</span><span class="sxs-lookup"><span data-stu-id="b3349-p102">True if token is pinned. It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="b3349-139">Keys</span><span class="sxs-lookup"><span data-stu-id="b3349-139">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b3349-140">Columna</span><span class="sxs-lookup"><span data-stu-id="b3349-140">Column</span></span></th>
<th><span data-ttu-id="b3349-141">Descripción</span><span class="sxs-lookup"><span data-stu-id="b3349-141">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b3349-142">fileToken</span><span class="sxs-lookup"><span data-stu-id="b3349-142">fileToken</span></span></p></td>
<td><p><span data-ttu-id="b3349-143">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="b3349-143">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b3349-144">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="b3349-144">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="b3349-145">Clave externa con búsqueda en la tabla tblNode.nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="b3349-145">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

