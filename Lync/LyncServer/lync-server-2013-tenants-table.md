---
title: 'Lync Server 2013: tabla Tenants'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Tenants table
ms:assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412950(v=OCS.15)
ms:contentKeyID: 48185309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 091a1db8f19e44277d71371aa14c14635e6fba6e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521757"
---
# <a name="tenants-table-in-lync-server-2013"></a><span data-ttu-id="566b6-102">Tabla Tenants en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="566b6-102">Tenants table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="566b6-103">_**Última modificación del tema:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="566b6-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="566b6-p101">La tabla Inquilinos es una tabla auxiliar que almacena una lista de los diversos inquilinos. Cada registro de la tabla representa a un inquilino.</span><span class="sxs-lookup"><span data-stu-id="566b6-p101">The Tenants table is a supporting table that stores a list of the various tenants. Each record in the table represents one tenant.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="566b6-106">En una instalación local, el CDR usa el identificador de inquilino integrado para indicar distintos tipos de autenticación, como la de conectividad de mensajería instantánea pública, federada y anónima.</span><span class="sxs-lookup"><span data-stu-id="566b6-106">In on-premises deployment, CDR uses the build-in Tenant ID to indicate different authentication type, such as public IM connectivity, Federated and Anonymous.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="566b6-107">Columna</span><span class="sxs-lookup"><span data-stu-id="566b6-107">Column</span></span></th>
<th><span data-ttu-id="566b6-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="566b6-108">Data Type</span></span></th>
<th><span data-ttu-id="566b6-109">Clave o índice</span><span class="sxs-lookup"><span data-stu-id="566b6-109">Key/Index</span></span></th>
<th><span data-ttu-id="566b6-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="566b6-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="566b6-111"><strong>TenantId</strong></span><span class="sxs-lookup"><span data-stu-id="566b6-111"><strong>TenantId</strong></span></span></p></td>
<td><p><span data-ttu-id="566b6-112">entero</span><span class="sxs-lookup"><span data-stu-id="566b6-112">int</span></span></p></td>
<td><p><span data-ttu-id="566b6-113">Principal</span><span class="sxs-lookup"><span data-stu-id="566b6-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="566b6-114">Número único que identifica este identificador de inquilino.</span><span class="sxs-lookup"><span data-stu-id="566b6-114">Unique number identifying this Tenant ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="566b6-115"><strong>TenantKey</strong></span><span class="sxs-lookup"><span data-stu-id="566b6-115"><strong>TenantKey</strong></span></span></p></td>
<td><p><span data-ttu-id="566b6-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="566b6-116">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="566b6-117">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="566b6-117">Allowed values:</span></span></p>
<ul>
<li><p><span data-ttu-id="566b6-118">00000000-0000-0000-0000-000000000000: de empresa</span><span class="sxs-lookup"><span data-stu-id="566b6-118">00000000-0000-0000-0000-000000000000 – Enterprise</span></span></p></li>
<li><p><span data-ttu-id="566b6-119">00000000-0000-0000-0000-000000000001: federada</span><span class="sxs-lookup"><span data-stu-id="566b6-119">00000000-0000-0000-0000-000000000001 – Federated</span></span></p></li>
<li><p><span data-ttu-id="566b6-120">00000000-0000-0000-0000-000000000002: anónima</span><span class="sxs-lookup"><span data-stu-id="566b6-120">00000000-0000-0000-0000-000000000002 – Anonymous</span></span></p></li>
<li><p><span data-ttu-id="566b6-121">00000000-0000-0000-0000-000000000003: conectividad de mensajería instantánea pública</span><span class="sxs-lookup"><span data-stu-id="566b6-121">00000000-0000-0000-0000-000000000003 – Public IM connectivity</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

