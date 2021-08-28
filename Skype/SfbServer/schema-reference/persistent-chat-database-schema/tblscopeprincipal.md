---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: La tabla tblScopePrincipal contiene ámbitos asignados a nodos.
ms.openlocfilehash: 2848d3dd6c0dcc99933dba9dda1bc712e9ad0564
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613850"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
La tabla tblScopePrincipal contiene ámbitos asignados a nodos.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|scopeNodeID  <br/> |int, no NULL  <br/> |Id. de nodo al que se aplica el ámbito.  <br/> |
|scopePrinID  <br/> |int, no NULL  <br/> |Id. de entidad  <br/> |
|scopeIsDenied  <br/> |bit, no NULL  <br/> |True si el tipo de ámbito es Denegar; False si es Permitir.  <br/> |
|scopeUpdatedBy  <br/> |int, no NULL  <br/> |Id. de la entidad que actualizó esta entrada por última vez.  <br/> |
   
**Keys**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<scopeNodeID, scopePrinID\>  <br/> |Clave principal.  <br/> |
|scopeNodeID  <br/> |Clave externa con búsqueda en la tabla tblNode.nodeID.  <br/> |
|scopePrinID  <br/> |Clave externa con búsqueda en la tabla tblPrincipal.prinID.  <br/> |
   

