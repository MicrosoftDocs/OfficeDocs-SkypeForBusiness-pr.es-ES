---
title: 'Lync Server 2013: tblADCookie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48183366
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2eef65e18de609f7e10fed4aaad9283612778070
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "34850495"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="33e4a-102">tblADCookie en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="33e4a-102">tblADCookie in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="33e4a-103">_**Última modificación del tema:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="33e4a-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="33e4a-104">tblADCookie contiene las cookies de sincronización LDAP (Protocolo ligero de acceso a directorios) actuales.</span><span class="sxs-lookup"><span data-stu-id="33e4a-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="33e4a-105">Columnas</span><span class="sxs-lookup"><span data-stu-id="33e4a-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="33e4a-106">Columna</span><span class="sxs-lookup"><span data-stu-id="33e4a-106">Column</span></span></th>
<th><span data-ttu-id="33e4a-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="33e4a-107">Type</span></span></th>
<th><span data-ttu-id="33e4a-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="33e4a-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33e4a-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="33e4a-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="33e4a-110">GUID, not null</span><span class="sxs-lookup"><span data-stu-id="33e4a-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="33e4a-111">GUID principal del dominio que se está supervisando.</span><span class="sxs-lookup"><span data-stu-id="33e4a-111">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33e4a-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="33e4a-112">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="33e4a-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="33e4a-113">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="33e4a-114">Nombre de dominio completo (FQDN) del controlador de dominio actual usado para la sincronización de servicios de dominio de Active Directory. Tiene valor informativo.</span><span class="sxs-lookup"><span data-stu-id="33e4a-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33e4a-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="33e4a-115">adcContent</span></span></p></td>
<td><p><span data-ttu-id="33e4a-116">imagen (binario)</span><span class="sxs-lookup"><span data-stu-id="33e4a-116">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="33e4a-117">Cookie de sincronización de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="33e4a-117">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33e4a-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="33e4a-118">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="33e4a-119">datetime</span><span class="sxs-lookup"><span data-stu-id="33e4a-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="33e4a-120">Marca de tiempo con la hora de actualización de la fila.</span><span class="sxs-lookup"><span data-stu-id="33e4a-120">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="33e4a-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="33e4a-121">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="33e4a-122">datetime</span><span class="sxs-lookup"><span data-stu-id="33e4a-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="33e4a-123">Tiempo hasta que se bloquean los cambios en la fila.</span><span class="sxs-lookup"><span data-stu-id="33e4a-123">Time until the row is locked for changes.</span></span> <span data-ttu-id="33e4a-124">Esto forma parte de un mecanismo de interbloqueo de software que garantiza que solo uno de los servicios de chat realiza la sincronización de Active Directory a la vez.</span><span class="sxs-lookup"><span data-stu-id="33e4a-124">This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="33e4a-125">Sus</span><span class="sxs-lookup"><span data-stu-id="33e4a-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="33e4a-126">Columna (s)</span><span class="sxs-lookup"><span data-stu-id="33e4a-126">Column(s)</span></span></th>
<th><span data-ttu-id="33e4a-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="33e4a-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="33e4a-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="33e4a-128">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="33e4a-129">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="33e4a-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="33e4a-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="33e4a-130">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="33e4a-131">Clave externa con la búsqueda en la tabla principal. prinGuid.</span><span class="sxs-lookup"><span data-stu-id="33e4a-131">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

