---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.openlocfilehash: 7ab281b31869b4a761a6360978b57ec9591daaf0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741886"
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
