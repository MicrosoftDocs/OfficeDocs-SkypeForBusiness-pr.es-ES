---
title: 'Lync Server 2013: vista multimedia'
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
ms.openlocfilehash: 6ad833bc84d488221d46822686077cfde2cda0ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765098"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-view-in-lync-server-2013"></a><span data-ttu-id="e3108-102">Vista de elementos multimedia de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3108-102">Media view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3108-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e3108-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e3108-104">La vista multimedia almacena información sobre un tipo de medio usado en una sesión de punto a punto.</span><span class="sxs-lookup"><span data-stu-id="e3108-104">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="e3108-105">Una sesión estaría representada por varios registros de la tabla, si se usa más de un tipo de medio.</span><span class="sxs-lookup"><span data-stu-id="e3108-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="e3108-106">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e3108-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e3108-107">La vista de elementos multimedia no debe usarse para calcular la duración multimedia de una sesión.</span><span class="sxs-lookup"><span data-stu-id="e3108-107">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="e3108-108">Esta vista contiene los detalles de señalización de intercambio de medios en una sesión.</span><span class="sxs-lookup"><span data-stu-id="e3108-108">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="e3108-109">El intercambio de medios se realiza mediante la solicitud INVITE y StartTime indica el momento en que se envió la invitación. La hora de la invitación no significa necesariamente la hora de inicio del medio, porque los medios solo se inician una vez que se acepta la sesión.</span><span class="sxs-lookup"><span data-stu-id="e3108-109">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span>



</div>

<span data-ttu-id="e3108-110">La vista contenido multimedia contiene todas las columnas de la [vista SessionDetails de Lync Server 2013](lync-server-2013-sessiondetails-view.md) , además de las que se muestran a continuación.</span><span class="sxs-lookup"><span data-stu-id="e3108-110">The Media view contains all of the columns in the [SessionDetails view in Lync Server 2013](lync-server-2013-sessiondetails-view.md) in addition the ones listed below.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e3108-111">Columna</span><span class="sxs-lookup"><span data-stu-id="e3108-111">Column</span></span></th>
<th><span data-ttu-id="e3108-112">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="e3108-112">Data Type</span></span></th>
<th><span data-ttu-id="e3108-113">Detalles</span><span class="sxs-lookup"><span data-stu-id="e3108-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e3108-114"><strong>Media</strong></span><span class="sxs-lookup"><span data-stu-id="e3108-114"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="e3108-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e3108-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e3108-116">Tipo de medio.</span><span class="sxs-lookup"><span data-stu-id="e3108-116">Media type.</span></span> <span data-ttu-id="e3108-117">Para obtener más información, consulte la <a href="lync-server-2013-medialist-table.md">tabla medial en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="e3108-117">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e3108-118"><strong>MediaStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="e3108-118"><strong>MediaStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e3108-119">datetime</span><span class="sxs-lookup"><span data-stu-id="e3108-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="e3108-120">Hora en que se envió una solicitud de medios.</span><span class="sxs-lookup"><span data-stu-id="e3108-120">Time that a media request was sent out.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e3108-121"><strong>MediaEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="e3108-121"><strong>MediaEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e3108-122">datetime</span><span class="sxs-lookup"><span data-stu-id="e3108-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="e3108-123">Hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="e3108-123">End time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

