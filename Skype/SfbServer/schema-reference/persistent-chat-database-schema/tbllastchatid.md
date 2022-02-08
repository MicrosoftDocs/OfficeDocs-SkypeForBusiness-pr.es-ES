---
title: tblLastChatId
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contiene el último id. de chat generado (y usado en la tabla tblChat) para cada usuario.
ms.openlocfilehash: 219aa136ed24d6ffd0f5793fe12511c41c037da4
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390862"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
tblLastChatId contiene el último id. de chat generado (y usado en la tabla tblChat) para cada usuario.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, no NULL  <br/> |Identificador de nodo (tipo de salón de chat únicamente).  <br/> |
|lastChatID  <br/> |bigint, no NULL  <br/> |Identificador de chat usado por última vez.  <br/> |
   
**Keys**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<nodeID, lastChatID\>  <br/> |Clave principal (nodeID es suficiente para el procesamiento).  <br/> |
|nodeID  <br/> |Clave externa con búsqueda en la tabla tblNode.nodeID.  <br/> |
   
## <a name="see-also"></a>Vea también

[tblChat](tblchat.md)
