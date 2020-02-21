---
title: 'Lync Server 2013: tblFileToken'
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
ms.openlocfilehash: 23240588fae3895c7d4aa5b0ecbf642bd2db51a5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208116"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="b7f5f-102">tblFileToken en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7f5f-102">tblFileToken in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7f5f-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="b7f5f-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="b7f5f-104">La tabla tblFileToken contiene símbolos temporales con fines de transferencia de archivos.</span><span class="sxs-lookup"><span data-stu-id="b7f5f-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="b7f5f-105">Columns</span><span class="sxs-lookup"><span data-stu-id="b7f5f-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b7f5f-106">Columna</span><span class="sxs-lookup"><span data-stu-id="b7f5f-106">Column</span></span></th>
<th><span data-ttu-id="b7f5f-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="b7f5f-107">Type</span></span></th>
<th><span data-ttu-id="b7f5f-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7f5f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7f5f-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="b7f5f-109">fileToken</span></span></p></td>
<td><p><span data-ttu-id="b7f5f-110">nvarchar (50), no NULL</span><span class="sxs-lookup"><span data-stu-id="b7f5f-110">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="b7f5f-111">Símbolo único (un GUID).</span><span class="sxs-lookup"><span data-stu-id="b7f5f-111">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7f5f-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="b7f5f-112">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="b7f5f-113">int, no NULL</span><span class="sxs-lookup"><span data-stu-id="b7f5f-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="b7f5f-114">Id. de la entidad de seguridad que está transfiriendo el archivo.</span><span class="sxs-lookup"><span data-stu-id="b7f5f-114">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7f5f-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="b7f5f-115">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="b7f5f-116">GUID, no NULL</span><span class="sxs-lookup"><span data-stu-id="b7f5f-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="b7f5f-117">GUID del nodo de la sala de chat.</span><span class="sxs-lookup"><span data-stu-id="b7f5f-117">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7f5f-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="b7f5f-118">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="b7f5f-119">datetime, no NULL</span><span class="sxs-lookup"><span data-stu-id="b7f5f-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="b7f5f-p101">Tiempo de expiración; los tokens caducan después de 30 minutos, a menos que esté anclado (vea las siguientes descripciones en esta columna).</span><span class="sxs-lookup"><span data-stu-id="b7f5f-p101">Expiration time. (Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7f5f-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="b7f5f-122">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="b7f5f-123">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b7f5f-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b7f5f-124">URL del archivo transferido (para el uso del Servicio de cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="b7f5f-124">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7f5f-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="b7f5f-125">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="b7f5f-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b7f5f-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b7f5f-127">URL de la miniatura del archivo transferido (para el uso del Servicio de cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="b7f5f-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7f5f-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="b7f5f-128">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="b7f5f-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="b7f5f-129">datetime2</span></span></p></td>
<td><p><span data-ttu-id="b7f5f-130">Marca de tiempo para la operación de transferencia de archivo real (para el uso del Servicio de cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="b7f5f-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7f5f-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="b7f5f-131">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="b7f5f-132">bit</span><span class="sxs-lookup"><span data-stu-id="b7f5f-132">bit</span></span></p></td>
<td><p><span data-ttu-id="b7f5f-133">True si se carga; False si se descarga (para el uso del Servicio de cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="b7f5f-133">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b7f5f-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="b7f5f-134">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="b7f5f-135">bit, no NULL</span><span class="sxs-lookup"><span data-stu-id="b7f5f-135">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="b7f5f-p102">True si el token está anclado. Se usa para mantener el token en la tabla hasta que el Servicio de cumplimiento tenga la oportunidad de recuperar los campos relevantes de él.</span><span class="sxs-lookup"><span data-stu-id="b7f5f-p102">True if token is pinned. It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="b7f5f-138">Keys</span><span class="sxs-lookup"><span data-stu-id="b7f5f-138">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b7f5f-139">Columna</span><span class="sxs-lookup"><span data-stu-id="b7f5f-139">Column</span></span></th>
<th><span data-ttu-id="b7f5f-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7f5f-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b7f5f-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="b7f5f-141">fileToken</span></span></p></td>
<td><p><span data-ttu-id="b7f5f-142">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="b7f5f-142">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b7f5f-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="b7f5f-143">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="b7f5f-144">Clave externa con búsqueda en la tabla tblNode.nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="b7f5f-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

