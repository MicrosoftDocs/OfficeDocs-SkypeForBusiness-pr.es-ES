---
title: 'Lync Server 2013: tblFileToken'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblFileToken
ms:assetid: 49e7dd79-1607-443c-818a-88c160e4ed06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558646(v=OCS.15)
ms:contentKeyID: 48184073
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9146c168e62bd0602a76cd77ab678c84ba5e44da
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="9dcd3-102">tblFileToken en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9dcd3-102">tblFileToken in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9dcd3-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="9dcd3-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="9dcd3-104">tblFileToken contiene tokens temporales para la transferencia de archivos.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="9dcd3-105">Columnas</span><span class="sxs-lookup"><span data-stu-id="9dcd3-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9dcd3-106">Columna</span><span class="sxs-lookup"><span data-stu-id="9dcd3-106">Column</span></span></th>
<th><span data-ttu-id="9dcd3-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="9dcd3-107">Type</span></span></th>
<th><span data-ttu-id="9dcd3-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="9dcd3-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9dcd3-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="9dcd3-109">fileToken</span></span></p></td>
<td><p><span data-ttu-id="9dcd3-110">nvarchar (50), not null</span><span class="sxs-lookup"><span data-stu-id="9dcd3-110">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="9dcd3-111">Identificador exclusivo (un GUID).</span><span class="sxs-lookup"><span data-stu-id="9dcd3-111">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9dcd3-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="9dcd3-112">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="9dcd3-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="9dcd3-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="9dcd3-114">IDENTIFICADOR de la entidad de identidad que está transfiriendo el archivo.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-114">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9dcd3-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="9dcd3-115">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="9dcd3-116">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="9dcd3-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="9dcd3-117">GUID del nodo del salón de chat.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-117">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9dcd3-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="9dcd3-118">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="9dcd3-119">DateTime, not null</span><span class="sxs-lookup"><span data-stu-id="9dcd3-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="9dcd3-120">Fecha de expiración.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-120">Expiration time.</span></span> <span data-ttu-id="9dcd3-121">(Los tokens vencen después de 30 minutos, a menos que se hayan anclado (vea las siguientes descripciones en esta columna).</span><span class="sxs-lookup"><span data-stu-id="9dcd3-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9dcd3-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="9dcd3-122">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="9dcd3-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9dcd3-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9dcd3-124">Dirección URL del archivo transferido (para el uso del servicio de cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="9dcd3-124">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9dcd3-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="9dcd3-125">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="9dcd3-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9dcd3-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9dcd3-127">Dirección URL de la miniatura del archivo transferido (para el uso del servicio de cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="9dcd3-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9dcd3-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="9dcd3-128">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="9dcd3-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="9dcd3-129">datetime2</span></span></p></td>
<td><p><span data-ttu-id="9dcd3-130">Marca de hora para la operación de transferencia de archivos real (para el uso del servicio de cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="9dcd3-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9dcd3-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="9dcd3-131">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="9dcd3-132">bit</span><span class="sxs-lookup"><span data-stu-id="9dcd3-132">bit</span></span></p></td>
<td><p><span data-ttu-id="9dcd3-133">Es verdadero si se carga; Falso si descargar (para uso del servicio de cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="9dcd3-133">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9dcd3-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="9dcd3-134">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="9dcd3-135">bit, not null</span><span class="sxs-lookup"><span data-stu-id="9dcd3-135">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="9dcd3-136">True si el símbolo está anclado.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-136">True if token is pinned.</span></span> <span data-ttu-id="9dcd3-137">Se usa para mantener el token en la tabla hasta que el servicio de cumplimiento tiene la posibilidad de recuperar los campos correspondientes de él.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-137">It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="9dcd3-138">Sus</span><span class="sxs-lookup"><span data-stu-id="9dcd3-138">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9dcd3-139">Columna</span><span class="sxs-lookup"><span data-stu-id="9dcd3-139">Column</span></span></th>
<th><span data-ttu-id="9dcd3-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="9dcd3-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9dcd3-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="9dcd3-141">fileToken</span></span></p></td>
<td><p><span data-ttu-id="9dcd3-142">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-142">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9dcd3-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="9dcd3-143">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="9dcd3-144">Clave externa con la búsqueda en la tabla tblNode. nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="9dcd3-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

