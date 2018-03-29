---
title: tblPrincipalInvites
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites contiene las invitaciones para todos los usuarios configurados para todos los nodos con auto invite en.
ms.openlocfilehash: ae33d45e14340b6374299343f13c8352db1a5021
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites contiene las invitaciones para todos los usuarios configurados para todos los nodos con auto invite en.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinID  <br/> |int, no nulo  <br/> |Id. principal  <br/> |
|invID  <br/> |int, no nulo  <br/> |Número secuencial único (por ID. principal) generado a partir de la tabla tblLastInviteId.  <br/> |
|nodeID  <br/> |int, no nulo  <br/> |Identificador de nodo (sólo sala de charlas).  <br/> |
|createdOn  <br/> |fecha y hora, no nulo  <br/> |Hora de creación.  <br/> |
   
**Claves**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |Clave principal.  <br/> |
|prinID  <br/> |Clave externa con la búsqueda en la tabla tblPrincipal.prinID.  <br/> |
|nodeID  <br/> |Clave externa con la búsqueda en la tabla tblNode.nodeID.  <br/> |
   

