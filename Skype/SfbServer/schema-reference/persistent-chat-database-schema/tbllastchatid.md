---
title: tblLastChatId
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
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contiene el último id. de chat generado (y usado en la tabla tblChat) para cada usuario.
ms.openlocfilehash: 80664d6b296fce9b4909674f9d21b1aa13285826
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816010"
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
