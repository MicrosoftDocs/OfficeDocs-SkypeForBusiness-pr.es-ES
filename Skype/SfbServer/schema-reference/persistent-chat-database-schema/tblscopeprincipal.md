---
title: tblScopePrincipal
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: 84fa792a6698a474e41c0e623b826fb0b8c48d65
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60844033"
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
   

