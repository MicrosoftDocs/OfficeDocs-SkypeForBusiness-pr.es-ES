---
title: tblPrincipalInvites
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
description: tblPrincipalInvites contiene invitaciones para todos los usuarios aprovisionados para todos los nodos con invitación automática activada.
ms.openlocfilehash: fbf61265f4970b57ffa95a52c8bafa395fb3a331
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212470"
---
# <a name="tblprincipalinvites"></a>tblPrincipalInvites
 
tblPrincipalInvites contiene invitaciones para todos los usuarios aprovisionados para todos los nodos con invitación automática activada.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|prinID  <br/> |int, no es nulo  <br/> |Identificador de entidad de seguridad.  <br/> |
|invID  <br/> |int, no es nulo  <br/> |Número secuencial único (por identificador de entidad de seguridad) generado desde la tabla tblLastInviteId.  <br/> |
|nodeID  <br/> |int, no es nulo  <br/> |Identificador de nodo (solo salón de chat).  <br/> |
|createdOn  <br/> |DateTime, no es nulo  <br/> |Hora de creación.  <br/> |
   
**Claves**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<prinID, nodeID\>  <br/> |Clave principal.  <br/> |
|prinID  <br/> |Clave externa con búsqueda en la tabla tblPrincipal.prinID.  <br/> |
|nodeID  <br/> |Clave externa con búsqueda en la tabla tblNode.nodeID.  <br/> |
   

