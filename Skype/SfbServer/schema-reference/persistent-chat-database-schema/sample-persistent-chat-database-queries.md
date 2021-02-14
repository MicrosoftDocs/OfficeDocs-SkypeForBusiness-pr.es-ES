---
title: Consultas de base de datos del chat persistente de ejemplo
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: Esta sección contiene consultas de ejemplo para la base de datos de chat persistente.
ms.openlocfilehash: 74cb6c1029cdeaabcd74a34898731b44c71f05a7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823110"
---
# <a name="sample-persistent-chat-database-queries"></a><span data-ttu-id="48e2e-103">Consultas de base de datos del chat persistente de ejemplo</span><span class="sxs-lookup"><span data-stu-id="48e2e-103">Sample Persistent Chat database queries</span></span>
 
<span data-ttu-id="48e2e-104">Esta sección contiene consultas de ejemplo para la base de datos de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="48e2e-104">This section contains sample queries for the Persistent Chat database.</span></span>
  
<span data-ttu-id="48e2e-105">Use el siguiente ejemplo para obtener una lista de los salón de chat persistente más activos después de una fecha determinada.</span><span class="sxs-lookup"><span data-stu-id="48e2e-105">Use the following example to get a list of your most active Persistent Chat rooms after a certain date.</span></span>
  
```SQL
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC
```

<span data-ttu-id="48e2e-106">Use el siguiente ejemplo para obtener  una lista de sus usuarios más activos tras una fecha determinada.</span><span class="sxs-lookup"><span data-stu-id="48e2e-106">Use the following example to get a list of your most active users after a certain date.</span></span>
  
```SQL
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC
```

<span data-ttu-id="48e2e-107">Use el siguiente ejemplo para obtener una lista de todas las personas que han enviado alguna vez un mensaje que incluya las palabras “Hello World”.</span><span class="sxs-lookup"><span data-stu-id="48e2e-107">Use the following example to get a list of everyone who ever sent a message with "Hello World" in it.</span></span>
  
```SQL
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

<span data-ttu-id="48e2e-108">Use el siguiente ejemplo para obtener una lista de pertenencia a grupos correspondiente a determinada entidad de seguridad.</span><span class="sxs-lookup"><span data-stu-id="48e2e-108">Use the following example to get a list of group memberships for a certain principal.</span></span>
  
```SQL
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

<span data-ttu-id="48e2e-109">Use el siguiente ejemplo para obtener una lista de todos los salones de chat de los que un usuario, Jane Dow, es miembro directo.</span><span class="sxs-lookup"><span data-stu-id="48e2e-109">Use the following example to get a list of every chat room that a user, Jane Dow, is a direct member of.</span></span>
  
```SQL
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

<span data-ttu-id="48e2e-110">Use el siguiente ejemplo para obtener una lista de las invitaciones que ha recibido un usuario.</span><span class="sxs-lookup"><span data-stu-id="48e2e-110">Use the following example to get a list of invitations that a user has received.</span></span>
  
```SQL
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```
