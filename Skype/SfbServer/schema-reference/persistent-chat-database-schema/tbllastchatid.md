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
ms.openlocfilehash: ecd707a8e6c9dbec220f137c69042c22ac6e1d8a4e46a46e4c2d8a6f035c8a0d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322942"
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
   
## <a name="see-also"></a>Consulte también

[tblChat](tblchat.md)
