---
title: 'Lync Server 2013: tblADCookie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblADCookie
ms:assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558610(v=OCS.15)
ms:contentKeyID: 48183366
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fa3543d04ff4da2782d8848f820a7651578448e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tbladcookie-in-lync-server-2013"></a><span data-ttu-id="b474f-102">tblADCookie en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b474f-102">tblADCookie in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b474f-103">_**Última modificación del tema:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="b474f-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="b474f-104">tblADCookie contiene las cookies actuales de sincronización del Protocolo ligero de acceso a directorios (LDAP).</span><span class="sxs-lookup"><span data-stu-id="b474f-104">tblADCookie contains the current Lightweight Directory Access Protocol (LDAP) Sync cookies.</span></span>

### <a name="columns"></a><span data-ttu-id="b474f-105">Columns</span><span class="sxs-lookup"><span data-stu-id="b474f-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b474f-106">Columna</span><span class="sxs-lookup"><span data-stu-id="b474f-106">Column</span></span></th>
<th><span data-ttu-id="b474f-107">Tipo</span><span class="sxs-lookup"><span data-stu-id="b474f-107">Type</span></span></th>
<th><span data-ttu-id="b474f-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="b474f-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b474f-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="b474f-109">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="b474f-110">GUID, no NULL</span><span class="sxs-lookup"><span data-stu-id="b474f-110">GUID, not null</span></span></p></td>
<td><p><span data-ttu-id="b474f-111">GUID de entidad de seguridad del dominio supervisado.</span><span class="sxs-lookup"><span data-stu-id="b474f-111">Principal GUID of the domain being monitored.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b474f-112">prinDCHost</span><span class="sxs-lookup"><span data-stu-id="b474f-112">prinDCHost</span></span></p></td>
<td><p><span data-ttu-id="b474f-113">nvarchar (255)</span><span class="sxs-lookup"><span data-stu-id="b474f-113">nvarchar (255)</span></span></p></td>
<td><p><span data-ttu-id="b474f-114">Nombre de dominio completo (FQDN) del controlador de dominio actual usado para la sincronización de servicios de dominio de Active Directory. Tiene un valor informativo.</span><span class="sxs-lookup"><span data-stu-id="b474f-114">Fully qualified domain name (FQDN) of the current domain controller used for Active Directory Domain Services Sync. Has informational value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b474f-115">adcContent</span><span class="sxs-lookup"><span data-stu-id="b474f-115">adcContent</span></span></p></td>
<td><p><span data-ttu-id="b474f-116">imagen (binario)</span><span class="sxs-lookup"><span data-stu-id="b474f-116">image (binary)</span></span></p></td>
<td><p><span data-ttu-id="b474f-117">Cookie de sincronización de Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b474f-117">Active Directory Sync cookie.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b474f-118">lastUpdated</span><span class="sxs-lookup"><span data-stu-id="b474f-118">lastUpdated</span></span></p></td>
<td><p><span data-ttu-id="b474f-119">datetime</span><span class="sxs-lookup"><span data-stu-id="b474f-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="b474f-120">Marca de tiempo con la hora de actualización de la fila.</span><span class="sxs-lookup"><span data-stu-id="b474f-120">Time stamp with the row update time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b474f-121">lockedUntil</span><span class="sxs-lookup"><span data-stu-id="b474f-121">lockedUntil</span></span></p></td>
<td><p><span data-ttu-id="b474f-122">datetime</span><span class="sxs-lookup"><span data-stu-id="b474f-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="b474f-p101">Fecha/hora en que finalizará el bloqueo de la fila para efectuar cambios. Esto forma parte del mecanismo de bloqueo de software que garantiza que solo uno de los servicios de chat realice una sincronización de Active Directory por vez.</span><span class="sxs-lookup"><span data-stu-id="b474f-p101">Time until the row is locked for changes. This is part of a software interlock mechanism that ensures that only one of the chat services does the Active Directory Sync at a time.</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="keys"></a><span data-ttu-id="b474f-125">Keys</span><span class="sxs-lookup"><span data-stu-id="b474f-125">Keys</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b474f-126">Columna (s)</span><span class="sxs-lookup"><span data-stu-id="b474f-126">Column(s)</span></span></th>
<th><span data-ttu-id="b474f-127">Descripción</span><span class="sxs-lookup"><span data-stu-id="b474f-127">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b474f-128">prinGuid</span><span class="sxs-lookup"><span data-stu-id="b474f-128">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="b474f-129">Clave principal.</span><span class="sxs-lookup"><span data-stu-id="b474f-129">Primary key.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b474f-130">prinGuid</span><span class="sxs-lookup"><span data-stu-id="b474f-130">prinGuid</span></span></p></td>
<td><p><span data-ttu-id="b474f-131">Clave externa con búsqueda en la tabla Principal.prinGuid.</span><span class="sxs-lookup"><span data-stu-id="b474f-131">Foreign key with lookup in Principal.prinGuid table.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

