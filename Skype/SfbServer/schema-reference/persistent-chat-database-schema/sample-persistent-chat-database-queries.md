---
title: Consultas de base de datos del chat persistente de ejemplo
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: Esta sección contiene ejemplos de consultas de la base de datos persistente de charla.
ms.openlocfilehash: 1e2d457a31061dcfb3c332a067069cbd4a8a9ebd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="sample-persistent-chat-database-queries"></a><span data-ttu-id="29634-103">Consultas de base de datos del chat persistente de ejemplo</span><span class="sxs-lookup"><span data-stu-id="29634-103">Sample Persistent Chat database queries</span></span>
 
<span data-ttu-id="29634-104">Esta sección contiene ejemplos de consultas de la base de datos persistente de charla.</span><span class="sxs-lookup"><span data-stu-id="29634-104">This section contains sample queries for the Persistent Chat database.</span></span>
  
<span data-ttu-id="29634-105">Utilice el ejemplo siguiente para obtener una lista de los salones de Chat persistentes más activos después de una fecha determinada.</span><span class="sxs-lookup"><span data-stu-id="29634-105">Use the following example to get a list of your most active Persistent Chat rooms after a certain date.</span></span>
  
```
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC

```

<span data-ttu-id="29634-106">Utilice el ejemplo siguiente para obtener una lista de los usuarios más activos después de una fecha determinada.</span><span class="sxs-lookup"><span data-stu-id="29634-106">Use the following example to get a list of your most active users after a certain date.</span></span>
  
```
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC

```

<span data-ttu-id="29634-107">Utilice el ejemplo siguiente para obtener una lista de todas las personas que jamás haya enviado un mensaje con "Hello World" en él.</span><span class="sxs-lookup"><span data-stu-id="29634-107">Use the following example to get a list of everyone who ever sent a message with "Hello World" in it.</span></span>
  
```
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

<span data-ttu-id="29634-108">Utilice el ejemplo siguiente para obtener una lista de pertenencias a grupos para una entidad de seguridad determinados.</span><span class="sxs-lookup"><span data-stu-id="29634-108">Use the following example to get a list of group memberships for a certain principal.</span></span>
  
```
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

<span data-ttu-id="29634-109">Utilice el ejemplo siguiente para obtener una lista de cada sala de chat en el que un usuario, Jane Dow, es miembro directo de.</span><span class="sxs-lookup"><span data-stu-id="29634-109">Use the following example to get a list of every chat room that a user, Jane Dow, is a direct member of.</span></span>
  
```
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

<span data-ttu-id="29634-110">Utilice el ejemplo siguiente para obtener una lista de las invitaciones que un usuario ha recibido.</span><span class="sxs-lookup"><span data-stu-id="29634-110">Use the following example to get a list of invitations that a user has received.</span></span>
  
```
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```


