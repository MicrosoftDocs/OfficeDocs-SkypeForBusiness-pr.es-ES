---
title: 'Lync Server 2013: vista ConferenceMessageCount'
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
ms.openlocfilehash: 73944e1561b88301b740fcb52cf301645154c6e7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencemessagecount-view-in-lync-server-2013"></a><span data-ttu-id="254fa-102">Vista ConferenceMessageCount en Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="254fa-102">ConferenceMessageCount view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="254fa-103">_**Última modificación del tema:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="254fa-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="254fa-104">La vista ConferenceMessageCount almacena información acerca de cuántos mensajes envió un usuario a una conferencia.</span><span class="sxs-lookup"><span data-stu-id="254fa-104">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="254fa-105">Esta vista se presentó en Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="254fa-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="254fa-106">La vista ConferenceMessageCount contiene todas las columnas de la <A href="lync-server-2013-conferencesessiondetails-view.md">vista ConferenceSessionDetails de Lync Server 2013</A> , además de las columnas que figuran a continuación.</span><span class="sxs-lookup"><span data-stu-id="254fa-106">The ConferenceMessageCount view contains all of the columns in the <A href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="254fa-107">Columna</span><span class="sxs-lookup"><span data-stu-id="254fa-107">Column</span></span></th>
<th><span data-ttu-id="254fa-108">Tipo de datos</span><span class="sxs-lookup"><span data-stu-id="254fa-108">Data Type</span></span></th>
<th><span data-ttu-id="254fa-109">Detalles</span><span class="sxs-lookup"><span data-stu-id="254fa-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="254fa-110"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="254fa-110"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="254fa-111">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="254fa-111">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="254fa-112">Identificador URI del usuario que envió el mensaje.</span><span class="sxs-lookup"><span data-stu-id="254fa-112">URI of the user who sent the message.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="254fa-113"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="254fa-113"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="254fa-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="254fa-114">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="254fa-115">Tipo de URI del usuario que envió los mensajes.</span><span class="sxs-lookup"><span data-stu-id="254fa-115">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="254fa-116">Para obtener más información, consulte la <a href="lync-server-2013-uritypes-table.md">tabla UriTypes en Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="254fa-116">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="254fa-117"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="254fa-117"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="254fa-118">identificador</span><span class="sxs-lookup"><span data-stu-id="254fa-118">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="254fa-119">Espacio empresarial del usuario que envió los mensajes.</span><span class="sxs-lookup"><span data-stu-id="254fa-119">Tenant of user who sent the messages.</span></span> <span data-ttu-id="254fa-120">Para obtener más información, consulte la <a href="lync-server-2013-tenants-table.md">tabla de inquilinos de Lync Server 2013</a> .</span><span class="sxs-lookup"><span data-stu-id="254fa-120">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="254fa-121"><strong>UserMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="254fa-121"><strong>UserMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="254fa-122">smallint</span><span class="sxs-lookup"><span data-stu-id="254fa-122">smallint</span></span></p></td>
<td><p><span data-ttu-id="254fa-123">Número de mensajes enviados por el usuario durante la sesión de conferencia.</span><span class="sxs-lookup"><span data-stu-id="254fa-123">Number of messages sent by the user during the conference session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

