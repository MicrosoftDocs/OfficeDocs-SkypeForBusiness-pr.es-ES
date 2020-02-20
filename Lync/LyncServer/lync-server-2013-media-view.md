---
title: 'Lync Server 2013: vista de medios'
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
ms.openlocfilehash: a760e3113cf12eceaa9f60c829b4d6a4a714ea25
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-view-in-lync-server-2013"></a><span data-ttu-id="dd9aa-102">Vista de elementos multimedia en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd9aa-102">Media view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd9aa-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="dd9aa-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="dd9aa-104">La vista Medios almacena información sobre un tipo de medios utilizado en una sesión punto a punto.</span><span class="sxs-lookup"><span data-stu-id="dd9aa-104">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="dd9aa-105">Una sesión estará representada por diferentes registros en la tabla, si se utilizan varios tipos de medios.</span><span class="sxs-lookup"><span data-stu-id="dd9aa-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="dd9aa-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dd9aa-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dd9aa-p102">La vista Medios no debería utilizarse para calcular la duración de medios de una sesión. Esta vista contiene los detalles de señalización del intercambio de medios en una sesión. El intercambio de medios se realiza mediante la solicitud INVITE, y StartTime indica la hora a la que se envió la solicitud INVITE. Esta hora no implica necesariamente la hora de inicio de los medios, ya que los medios se inician solamente después de que se acepta la sesión.</span><span class="sxs-lookup"><span data-stu-id="dd9aa-p102">The Media view should not be used to calculate the media duration for a session. This view contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span>



</div>

<span data-ttu-id="dd9aa-110">La vista de elementos multimedia contiene todas las columnas de la [vista SessionDetails en Lync Server 2013](lync-server-2013-sessiondetails-view.md) , además de las que se enumeran a continuación.</span><span class="sxs-lookup"><span data-stu-id="dd9aa-110">The Media view contains all of the columns in the [SessionDetails view in Lync Server 2013](lync-server-2013-sessiondetails-view.md) in addition the ones listed below.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dd9aa-111">Columna</span><span class="sxs-lookup"><span data-stu-id="dd9aa-111">Column</span></span></th>
<th><span data-ttu-id="dd9aa-112">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="dd9aa-112">Data Type</span></span></th>
<th><span data-ttu-id="dd9aa-113">Detalles</span><span class="sxs-lookup"><span data-stu-id="dd9aa-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd9aa-114"><strong>Medios</strong></span><span class="sxs-lookup"><span data-stu-id="dd9aa-114"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9aa-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="dd9aa-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dd9aa-116">Tipo de medio.</span><span class="sxs-lookup"><span data-stu-id="dd9aa-116">Media type.</span></span> <span data-ttu-id="dd9aa-117">Consulte la <a href="lync-server-2013-medialist-table.md">tabla de medial en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="dd9aa-117">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd9aa-118"><strong>MediaStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="dd9aa-118"><strong>MediaStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9aa-119">datetime</span><span class="sxs-lookup"><span data-stu-id="dd9aa-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="dd9aa-120">Hora a la que se envió la solicitud de medios.</span><span class="sxs-lookup"><span data-stu-id="dd9aa-120">Time that a media request was sent out.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd9aa-121"><strong>MediaEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="dd9aa-121"><strong>MediaEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dd9aa-122">datetime</span><span class="sxs-lookup"><span data-stu-id="dd9aa-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="dd9aa-123">Hora de finalización de la sesión.</span><span class="sxs-lookup"><span data-stu-id="dd9aa-123">End time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

