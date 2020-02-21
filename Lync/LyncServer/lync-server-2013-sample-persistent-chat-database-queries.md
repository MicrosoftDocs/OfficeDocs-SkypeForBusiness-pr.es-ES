---
title: 'Lync Server 2013: consultas de base de datos de chat persistente de ejemplo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Sample Persistent Chat database queries
ms:assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558649(v=OCS.15)
ms:contentKeyID: 48184133
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0b9bab437d34ca6b095050fa6536f32c07b64b3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sample-persistent-chat-database-queries-for-lync-server-2013"></a><span data-ttu-id="2b78f-102">Consultas de base de datos de chat persistente de ejemplo para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b78f-102">Sample Persistent Chat database queries for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b78f-103">_**Última modificación del tema:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="2b78f-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="2b78f-104">Esta sección contiene consultas de ejemplo para la base de datos de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2b78f-104">This section contains sample queries for the Persistent Chat database.</span></span>

<span data-ttu-id="2b78f-105">Use el siguiente ejemplo para obtener una lista de los salones de chat persistente más activos después de una fecha determinada.</span><span class="sxs-lookup"><span data-stu-id="2b78f-105">Use the following example to get a list of your most active Persistent Chat rooms after a certain date.</span></span>

    SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
      FROM tblChat, tblNode
      WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
      GROUP BY nodeName
      ORDER BY ChatMessages DESC

<span data-ttu-id="2b78f-106">Use el siguiente ejemplo para obtener  una lista de sus usuarios más activos tras una fecha determinada.</span><span class="sxs-lookup"><span data-stu-id="2b78f-106">Use the following example to get a list of your most active users after a certain date.</span></span>

    SELECT prinName as Name, count(*) as ChatMessages
      FROM tblChat, tblPrincipal
      WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
      GROUP BY prinName
      ORDER BY ChatMessages DESC

<span data-ttu-id="2b78f-107">Use el siguiente ejemplo para obtener una lista de todas las personas que han enviado alguna vez un mensaje que incluya las palabras “Hello World”.</span><span class="sxs-lookup"><span data-stu-id="2b78f-107">Use the following example to get a list of everyone who ever sent a message with "Hello World" in it.</span></span>

    SELECT nodeName as ChatRoom, prinName as Name, content as Message
      FROM tblChat, tblNode, tblPrincipal
      WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'

<span data-ttu-id="2b78f-108">Use el siguiente ejemplo para obtener una lista de pertenencia a grupos correspondiente a determinada entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="2b78f-108">Use the following example to get a list of group memberships for a certain principal.</span></span>

    SELECT prinName as Name    
      FROM tblPrincipalAffiliations as pa, tblPrincipal
      where principalID = 7 and affiliationID = prinID

<span data-ttu-id="2b78f-109">Use el siguiente ejemplo para obtener una lista de todos los salones de chat de los que un usuario, Jane Dow, es miembro directo.</span><span class="sxs-lookup"><span data-stu-id="2b78f-109">Use the following example to get a list of every chat room that a user, Jane Dow, is a direct member of.</span></span>

    SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
      FROM tblPrincipalRole, tblPrincipal, tblNode
      WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'

<span data-ttu-id="2b78f-110">Use el siguiente ejemplo para obtener una lista de las invitaciones que ha recibido un usuario.</span><span class="sxs-lookup"><span data-stu-id="2b78f-110">Use the following example to get a list of invitations that a user has received.</span></span>

    SELECT prinName
          ,nodeName
          ,invID   
          ,createdOn
      FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
      where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
      ORDER BY invID DESC

</div>

<span> </span>

</div>

</div>

</div>

