---
title: tblScopePrincipal
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: tblScopePrincipal contiene ámbitos asignados a los nodos.
ms.openlocfilehash: ba2927598cdff07368cb017866ec41bfa7540f48
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
tblScopePrincipal contiene ámbitos asignados a los nodos.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|scopeNodeID  <br/> |int, no nulo  <br/> |Identificador de nodo al que se aplica el ámbito.  <br/> |
|scopePrinID  <br/> |int, no nulo  <br/> |Id. principal  <br/> |
|scopeIsDenied  <br/> |bits, no nulo  <br/> |True si el tipo de ámbito es Denegar; False si se permite.  <br/> |
|scopeUpdatedBy  <br/> |int, no nulo  <br/> |Identificador de la entidad de seguridad que se actualizó por última vez esta entrada.  <br/> |
   
**Claves**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |Clave principal.  <br/> |
|scopeNodeID  <br/> |Clave externa con la búsqueda en la tabla tblNode.nodeID.  <br/> |
|scopePrinID  <br/> |Clave externa con la búsqueda en la tabla tblPrincipal.prinID.  <br/> |
   

