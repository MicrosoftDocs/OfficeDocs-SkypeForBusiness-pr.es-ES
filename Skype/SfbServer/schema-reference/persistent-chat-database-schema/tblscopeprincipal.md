---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: la tabla tblScopePrincipal contiene ámbitos asignados a nodos.
ms.openlocfilehash: e93b92280605dfe01f288435c7cb42b724c22064
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212400"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
la tabla tblScopePrincipal contiene ámbitos asignados a nodos.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|scopeNodeID  <br/> |int, no es nulo  <br/> |Identificador de nodo que se aplica el ámbito.  <br/> |
|scopePrinID  <br/> |int, no es nulo  <br/> |Identificador de entidad de seguridad.  <br/> |
|scopeIsDenied  <br/> |bit, no es nulo  <br/> |Es True si el tipo de ámbito es Denegar; False si es permitir.  <br/> |
|scopeUpdatedBy  <br/> |int, no es nulo  <br/> |Identificador de la entidad de seguridad que actualizó por última vez esta entrada.  <br/> |
   
**Claves**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |Clave principal.  <br/> |
|scopeNodeID  <br/> |Clave externa con búsqueda en la tabla tblNode.nodeID.  <br/> |
|scopePrinID  <br/> |Clave externa con búsqueda en la tabla tblPrincipal.prinID.  <br/> |
   

