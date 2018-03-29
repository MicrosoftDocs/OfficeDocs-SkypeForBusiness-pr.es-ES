---
title: tblLastChatId
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contiene el último ID de charla que se ha generado (y utilizado en la tabla tblChat) para cada usuario.
ms.openlocfilehash: 4a22dc9ba1c2dbe15ae0a24de6e4f347a62deaee
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tbllastchatid"></a>tblLastChatId
 
tblLastChatId contiene el último ID de charla que se ha generado (y utilizado en la tabla tblChat) para cada usuario.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, no nulo  <br/> |Identificador de nodo (tipo de salón de chat sólo).  <br/> |
|lastChatID  <br/> |bigint, no nulo  <br/> |ID de chat utilizados anterior.  <br/> |
   
**Claves**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<nodeID, lastChatID\>  <br/> |Clave principal (sólo nodeID es suficiente para su procesamiento).  <br/> |
|nodeID  <br/> |Clave externa con la búsqueda en la tabla tblNode.nodeID.  <br/> |
   
## <a name="see-also"></a>Vea también

#### 

[tblChat](tblchat.md)

