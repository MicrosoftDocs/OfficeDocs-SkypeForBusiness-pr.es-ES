---
title: Consultas de base de datos del chat persistente de ejemplo
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: Esta sección contiene consultas de ejemplo para la base de datos de chat persistente.
---

# <a name="sample-persistent-chat-database-queries"></a>Consultas de base de datos del chat persistente de ejemplo
 
Esta sección contiene consultas de ejemplo para la base de datos de chat persistente.
  
Use el siguiente ejemplo para obtener una lista de los salas de chat persistente más activos después de una fecha determinada.
  
```SQL
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC
```

Use el siguiente ejemplo para obtener  una lista de sus usuarios más activos tras una fecha determinada.
  
```SQL
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC
```

Use el siguiente ejemplo para obtener una lista de todas las personas que han enviado alguna vez un mensaje que incluya las palabras “Hello World”.
  
```SQL
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

Use el siguiente ejemplo para obtener una lista de pertenencia a grupos correspondiente a determinada entidad de seguridad.
  
```SQL
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

Use el siguiente ejemplo para obtener una lista de todos los salones de chat de los que un usuario, Jane Dow, es miembro directo.
  
```SQL
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

Use el siguiente ejemplo para obtener una lista de las invitaciones que ha recibido un usuario.
  
```SQL
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```
