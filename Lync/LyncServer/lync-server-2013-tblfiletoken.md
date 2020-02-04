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
ms.openlocfilehash: b469b79e680c202654024d1ac20a55b9929e4b10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblfiletoken-in-lync-server-2013"></a><span data-ttu-id="69328-102">tblFileToken en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69328-102">tblFileToken in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69328-103">_**Última modificación del tema:** 2012-09-12_</span><span class="sxs-lookup"><span data-stu-id="69328-103">_**Topic Last Modified:** 2012-09-12_</span></span>

<span data-ttu-id="69328-104">tblFileToken contiene tokens temporales para la transferencia de archivos.</span><span class="sxs-lookup"><span data-stu-id="69328-104">tblFileToken contains temporary tokens for file transfer purposes.</span></span>

### <a name="columns"></a><span data-ttu-id="69328-105">Columnas</span><span class="sxs-lookup"><span data-stu-id="69328-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69328-106">Columna</span><span class="sxs-lookup"><span data-stu-id="69328-106">Column</span></span></th>
<th><span data-ttu-id="69328-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="69328-107">Type</span></span></th>
<th><span data-ttu-id="69328-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="69328-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69328-109">fileToken</span><span class="sxs-lookup"><span data-stu-id="69328-109">fileToken</span></span></p></td>
<td><p><span data-ttu-id="69328-110">nvarchar (50), not null</span><span class="sxs-lookup"><span data-stu-id="69328-110">nvarchar (50), not null</span></span></p></td>
<td><p><span data-ttu-id="69328-111">Identificador exclusivo (un GUID).</span><span class="sxs-lookup"><span data-stu-id="69328-111">Unique token (a GUID).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69328-112">fileTokenUserID</span><span class="sxs-lookup"><span data-stu-id="69328-112">fileTokenUserID</span></span></p></td>
<td><p><span data-ttu-id="69328-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="69328-113">int, not null</span></span></p></td>
<td><p><span data-ttu-id="69328-114">IDENTIFICADOR de la entidad de identidad que está transfiriendo el archivo.</span><span class="sxs-lookup"><span data-stu-id="69328-114">ID of the principal that is transferring the file.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69328-115">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="69328-115">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="69328-116">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="69328-116">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="69328-117">GUID del nodo del salón de chat.</span><span class="sxs-lookup"><span data-stu-id="69328-117">GUID of the chat room node.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69328-118">fileTokenExpireDate</span><span class="sxs-lookup"><span data-stu-id="69328-118">fileTokenExpireDate</span></span></p></td>
<td><p><span data-ttu-id="69328-119">DateTime, not null</span><span class="sxs-lookup"><span data-stu-id="69328-119">datetime, not null</span></span></p></td>
<td><p><span data-ttu-id="69328-120">Fecha de expiración.</span><span class="sxs-lookup"><span data-stu-id="69328-120">Expiration time.</span></span> <span data-ttu-id="69328-121">(Los tokens vencen después de 30 minutos, a menos que se hayan anclado (vea las siguientes descripciones en esta columna).</span><span class="sxs-lookup"><span data-stu-id="69328-121">(Tokens expire after 30 minutes, unless pinned (see the following descriptions in this column).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69328-122">fileTokenComplianceFileUrl</span><span class="sxs-lookup"><span data-stu-id="69328-122">fileTokenComplianceFileUrl</span></span></p></td>
<td><p><span data-ttu-id="69328-123">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="69328-123">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="69328-124">Dirección URL del archivo transferido (para el uso del servicio de cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="69328-124">URL of the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69328-125">fileTokenComplianceThumbnailUrl</span><span class="sxs-lookup"><span data-stu-id="69328-125">fileTokenComplianceThumbnailUrl</span></span></p></td>
<td><p><span data-ttu-id="69328-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="69328-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="69328-127">Dirección URL de la miniatura del archivo transferido (para el uso del servicio de cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="69328-127">URL of the thumbnail for the transferred file (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69328-128">fileTokenComplianceTime</span><span class="sxs-lookup"><span data-stu-id="69328-128">fileTokenComplianceTime</span></span></p></td>
<td><p><span data-ttu-id="69328-129">datetime2</span><span class="sxs-lookup"><span data-stu-id="69328-129">datetime2</span></span></p></td>
<td><p><span data-ttu-id="69328-130">Marca de hora para la operación de transferencia de archivos real (para el uso del servicio de cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="69328-130">Timestamp for the actual file transfer operation (for Compliance service use).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69328-131">fileTokenComplianceIsUpload</span><span class="sxs-lookup"><span data-stu-id="69328-131">fileTokenComplianceIsUpload</span></span></p></td>
<td><p><span data-ttu-id="69328-132">bit</span><span class="sxs-lookup"><span data-stu-id="69328-132">bit</span></span></p></td>
<td><p><span data-ttu-id="69328-133">Es verdadero si se carga; Falso si descargar (para uso del servicio de cumplimiento).</span><span class="sxs-lookup"><span data-stu-id="69328-133">True if upload; False if download (for Compliance service use).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69328-134">fileTokenCompliancePinned</span><span class="sxs-lookup"><span data-stu-id="69328-134">fileTokenCompliancePinned</span></span></p></td>
<td><p><span data-ttu-id="69328-135">bit, not null</span><span class="sxs-lookup"><span data-stu-id="69328-135">bit, not null</span></span></p></td>
<td><p><span data-ttu-id="69328-136">True si el símbolo está anclado.</span><span class="sxs-lookup"><span data-stu-id="69328-136">True if token is pinned.</span></span> <span data-ttu-id="69328-137">Se usa para mantener el token en la tabla hasta que el servicio de cumplimiento tiene la posibilidad de recuperar los campos correspondientes de él.</span><span class="sxs-lookup"><span data-stu-id="69328-137">It’s used to keep the token in the table until Compliance service has a chance to retrieve the relevant fields from it.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="69328-138">Sus</span><span class="sxs-lookup"><span data-stu-id="69328-138">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69328-139">Columna</span><span class="sxs-lookup"><span data-stu-id="69328-139">Column</span></span></th>
<th><span data-ttu-id="69328-140">Descripción</span><span class="sxs-lookup"><span data-stu-id="69328-140">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69328-141">fileToken</span><span class="sxs-lookup"><span data-stu-id="69328-141">fileToken</span></span></p></td>
<td><p><span data-ttu-id="69328-142">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="69328-142">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69328-143">fileTokenChannelID</span><span class="sxs-lookup"><span data-stu-id="69328-143">fileTokenChannelID</span></span></p></td>
<td><p><span data-ttu-id="69328-144">Clave externa con la búsqueda en la tabla tblNode. nodeGuid.</span><span class="sxs-lookup"><span data-stu-id="69328-144">Foreign key with lookup in tblNode.nodeGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

