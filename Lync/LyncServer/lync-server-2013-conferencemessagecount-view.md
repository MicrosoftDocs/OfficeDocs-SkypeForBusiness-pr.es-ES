---
title: 'Lync Server 2013: vista de ConferenceMessageCount'
description: 'Lync Server 2013: vista de ConferenceMessageCount.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceMessageCount view
ms:assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688129(v=OCS.15)
ms:contentKeyID: 49733727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 212d6e1a346253809fb70806424350cc7fc0dfe2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "48561616"
---
# <a name="conferencemessagecount-view-in-lync-server-2013"></a><span data-ttu-id="dd1b8-103">Vista ConferenceMessageCount en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dd1b8-103">ConferenceMessageCount view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd1b8-104">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="dd1b8-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="dd1b8-105">La vista ConferenceMessageCount almacena información acerca del número de mensajes enviados por un usuario a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="dd1b8-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="dd1b8-106">Esta vista se introdujo en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dd1b8-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dd1b8-107">La vista ConferenceMessageCount contiene todas las columnas de la <A href="lync-server-2013-conferencesessiondetails-view.md">vista ConferenceSessionDetails en Lync Server 2013</A> , además de las columnas que se enumeran a continuación.</span><span class="sxs-lookup"><span data-stu-id="dd1b8-107">The ConferenceMessageCount view contains all of the columns in the <A href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dd1b8-108">Columna</span><span class="sxs-lookup"><span data-stu-id="dd1b8-108">Column</span></span></th>
<th><span data-ttu-id="dd1b8-109">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="dd1b8-109">Data Type</span></span></th>
<th><span data-ttu-id="dd1b8-110">Detalles</span><span class="sxs-lookup"><span data-stu-id="dd1b8-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dd1b8-111"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="dd1b8-111"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="dd1b8-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="dd1b8-112">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="dd1b8-113">URI del usuario que envió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="dd1b8-113">URI of the user who sent the message.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd1b8-114"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="dd1b8-114"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="dd1b8-115">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="dd1b8-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dd1b8-116">Tipo de URI del usuario que envió los mensajes.</span><span class="sxs-lookup"><span data-stu-id="dd1b8-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="dd1b8-117">Consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="dd1b8-117">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dd1b8-118"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="dd1b8-118"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="dd1b8-119">identificador</span><span class="sxs-lookup"><span data-stu-id="dd1b8-119">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="dd1b8-120">Inquilino del usuario que envió los mensajes.</span><span class="sxs-lookup"><span data-stu-id="dd1b8-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="dd1b8-121">Consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos en Lync Server 2013</a> para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="dd1b8-121">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dd1b8-122"><strong>UserMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="dd1b8-122"><strong>UserMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="dd1b8-123">smallint</span><span class="sxs-lookup"><span data-stu-id="dd1b8-123">smallint</span></span></p></td>
<td><p><span data-ttu-id="dd1b8-124">Número de mensajes que envió el usuario durante la sesión de conferencia.</span><span class="sxs-lookup"><span data-stu-id="dd1b8-124">Number of messages sent by the user during the conference session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

