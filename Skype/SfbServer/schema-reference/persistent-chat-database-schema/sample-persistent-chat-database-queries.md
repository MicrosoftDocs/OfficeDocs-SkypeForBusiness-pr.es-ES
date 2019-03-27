---
title: Consultas de base de datos del chat persistente de ejemplo
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: Esta sección contiene consultas de ejemplo para la base de datos de Chat persistente.
ms.openlocfilehash: 9dace51aa882402cd7f4f6c58c9444c21263333c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881562"
---
# <a name="sample-persistent-chat-database-queries"></a><span data-ttu-id="aa8e4-103">Consultas de base de datos del chat persistente de ejemplo</span><span class="sxs-lookup"><span data-stu-id="aa8e4-103">Sample Persistent Chat database queries</span></span>
 
<span data-ttu-id="aa8e4-104">Esta sección contiene consultas de ejemplo para la base de datos de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="aa8e4-104">This section contains sample queries for the Persistent Chat database.</span></span>
  
<span data-ttu-id="aa8e4-105">Use el siguiente ejemplo para obtener una lista de sus salones de Chat persistente más activos tras una fecha determinada.</span><span class="sxs-lookup"><span data-stu-id="aa8e4-105">Use the following example to get a list of your most active Persistent Chat rooms after a certain date.</span></span>
  
```
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC
```

<span data-ttu-id="aa8e4-106">Use el siguiente ejemplo para obtener una lista de los usuarios más activos tras una fecha determinada.</span><span class="sxs-lookup"><span data-stu-id="aa8e4-106">Use the following example to get a list of your most active users after a certain date.</span></span>
  
```
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC
```

<span data-ttu-id="aa8e4-107">Use el siguiente ejemplo para obtener una lista de todas las personas que se envía un mensaje con "Hello World" en ella.</span><span class="sxs-lookup"><span data-stu-id="aa8e4-107">Use the following example to get a list of everyone who ever sent a message with "Hello World" in it.</span></span>
  
```
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

<span data-ttu-id="aa8e4-108">Use el siguiente ejemplo para obtener una lista de pertenencias a grupos de una determinada entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="aa8e4-108">Use the following example to get a list of group memberships for a certain principal.</span></span>
  
```
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

<span data-ttu-id="aa8e4-109">Use el siguiente ejemplo para obtener una lista de todos los salones de chat que un usuario, Jane Dow, es miembro directo.</span><span class="sxs-lookup"><span data-stu-id="aa8e4-109">Use the following example to get a list of every chat room that a user, Jane Dow, is a direct member of.</span></span>
  
```
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

<span data-ttu-id="aa8e4-110">Use el siguiente ejemplo para obtener una lista de las invitaciones que ha recibido un usuario.</span><span class="sxs-lookup"><span data-stu-id="aa8e4-110">Use the following example to get a list of invitations that a user has received.</span></span>
  
```
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```
