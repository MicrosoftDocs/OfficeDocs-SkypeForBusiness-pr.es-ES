---
title: tblLastChatId
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contiene el último identificador de chat generado (y utilizado en la tabla tblChat) para cada usuario.
ms.openlocfilehash: 3208ada77643957295f9894cb58187c2b4bc7493
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884932"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
tblLastChatId contiene el último identificador de chat generado (y utilizado en la tabla tblChat) para cada usuario.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, no es nulo  <br/> |Identificador de nodo (tipo de salón de chat únicamente).  <br/> |
|lastChatID  <br/> |bigint, no es nulo  <br/> |Último identificador de chat usado.  <br/> |
   
**Claves**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<nodeID, lastChatID\>  <br/> |Clave principal (nodeID es suficiente para el procesamiento).  <br/> |
|nodeID  <br/> |Clave externa con búsqueda en la tabla tblNode.nodeID.  <br/> |
   
## <a name="see-also"></a>Consulte también

[tblChat](tblchat.md)
