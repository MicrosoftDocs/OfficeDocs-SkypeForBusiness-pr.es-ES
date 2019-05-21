---
title: Consultas de base de datos del chat persistente de ejemplo
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 545b1a93-9758-4344-98cc-aa0e559d494f
description: Esta sección contiene consultas de ejemplo de la base de datos de chat persistente.
ms.openlocfilehash: fef40c2f36547fb0772d2e938bf8259246ec2055
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295611"
---
# <a name="sample-persistent-chat-database-queries"></a>Consultas de base de datos del chat persistente de ejemplo
 
Esta sección contiene consultas de ejemplo de la base de datos de chat persistente.
  
Use el siguiente ejemplo para obtener una lista de sus salones de chat persistentes más activos después de una fecha determinada.
  
```
SELECT nodeName as ChatRoom, COUNT(*) as ChatMessages
  FROM tblChat, tblNode
  WHERE channelId = nodeID AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY nodeName
  ORDER BY ChatMessages DESC
```

Use el ejemplo siguiente para obtener una lista de los usuarios más activos después de una fecha determinada.
  
```
SELECT prinName as Name, count(*) as ChatMessages
  FROM tblChat, tblPrincipal
  WHERE prinID = userId AND dbo.fnTicksToDate(chatDate) > '1/1/2011'
  GROUP BY prinName
  ORDER BY ChatMessages DESC
```

Use el ejemplo siguiente para obtener una lista de todas las personas que hayan enviado un mensaje con "Hola a todos".
  
```
SELECT nodeName as ChatRoom, prinName as Name, content as Message
  FROM tblChat, tblNode, tblPrincipal
  WHERE channelId = nodeID AND userId = prinID AND content like '%Hello World%'
```

Use el ejemplo siguiente para obtener una lista de pertenencias a grupos de un determinado principal.
  
```
SELECT prinName as Name    
  FROM tblPrincipalAffiliations as pa, tblPrincipal
  where principalID = 7 and affiliationID = prinID
```

Use el ejemplo siguiente para obtener una lista de todos los salones de chat con los que un usuario, Julia Dow, es miembro directo.
  
```
SELECT DISTINCT nodeName as ChatRoom, prinName as Name          
  FROM tblPrincipalRole, tblPrincipal, tblNode
  WHERE  prinRoleNodeID = nodeID AND prinRolePrinID = prinID AND prinName = 'Jane Dow'
```

Use el ejemplo siguiente para obtener una lista de las invitaciones que un usuario ha recibido.
  
```
SELECT prinName
      ,nodeName
      ,invID   
      ,createdOn
  FROM tblPrincipalInvites as inv, tblPrincipal as p, tblNode as n
  where inv.prinID = 5 AND inv.prinID = p.prinID and inv.nodeID = n.nodeID
  ORDER BY invID DESC
```
