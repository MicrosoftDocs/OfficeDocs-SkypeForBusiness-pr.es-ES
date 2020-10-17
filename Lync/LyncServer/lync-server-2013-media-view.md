---
title: 'Lync Server 2013: vista de medios'
description: 'Lync Server 2013: vista de medios.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media view
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49733570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74643986b12a30b1055a46a37febf90eeb70c514
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558016"
---
# <a name="media-view-in-lync-server-2013"></a><span data-ttu-id="dd311-103">Vista de elementos multimedia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd311-103">Media view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd311-104">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="dd311-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="dd311-105">La vista Medios almacena información sobre un tipo de medios utilizado en una sesión punto a punto.</span><span class="sxs-lookup"><span data-stu-id="dd311-105">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="dd311-106">Una sesión estará representada por diferentes registros en la tabla, si se utilizan varios tipos de medios.</span><span class="sxs-lookup"><span data-stu-id="dd311-106">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="dd311-107">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dd311-107">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dd311-p102">La vista Medios no debería utilizarse para calcular la duración de medios de una sesión. Esta vista contiene los detalles de señalización del intercambio de medios en una sesión. El intercambio de medios se realiza mediante la solicitud INVITE, y StartTime indica la hora a la que se envió la solicitud INVITE. Esta hora no implica necesariamente la hora de inicio de los medios, ya que los medios se inician solamente después de que se acepta la sesión.</span><span class="sxs-lookup"><span data-stu-id="dd311-p102">The Media view should not be used to calculate the media duration for a session. This view contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span>



</div>

<span data-ttu-id="dd311-111">La vista de elementos multimedia contiene todas las columnas de la [vista SessionDetails en Lync Server 2013](lync-server-2013-sessiondetails-view.md) , además de las que se enumeran a continuación.</span><span class="sxs-lookup"><span data-stu-id="dd311-111">The Media view contains all of the columns in the [SessionDetails view in Lync Server 2013](lync-server-2013-sessiondetails-view.md) in addition the ones listed below.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dd311-112">Columna</span><span class="sxs-lookup"><span data-stu-id="dd311-112">Column</span></span></th>
<th><span data-ttu-id="dd311-113">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="dd311-113">Data Type</span></span></th>
<th><span data-ttu-id="dd311-114">Detalles</span><span class="sxs-lookup"><span data-stu-id="dd311-114">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd311-115"><strong>Media</strong></span><span class="sxs-lookup"><span data-stu-id="dd311-115"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="dd311-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="dd311-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dd311-117">Tipo de medio.</span><span class="sxs-lookup"><span data-stu-id="dd311-117">Media type.</span></span> <span data-ttu-id="dd311-118">Consulte la <a href="lync-server-2013-medialist-table.md">tabla de medial en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="dd311-118">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd311-119"><strong>MediaStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="dd311-119"><strong>MediaStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dd311-120">datetime</span><span class="sxs-lookup"><span data-stu-id="dd311-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="dd311-121">Hora a la que se envió la solicitud de medios.</span><span class="sxs-lookup"><span data-stu-id="dd311-121">Time that a media request was sent out.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd311-122"><strong>MediaEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="dd311-122"><strong>MediaEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dd311-123">datetime</span><span class="sxs-lookup"><span data-stu-id="dd311-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="dd311-124">Hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="dd311-124">End time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

