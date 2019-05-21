---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contiene el último identificador de chat generado (y usado en la tabla tblChat) para cada usuario.
ms.openlocfilehash: f14d8090fd3252d88ef747de93a987f51870a63b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295401"
---
# <a name="tbllastchatid"></a>tblLastChatId
 
tblLastChatId contiene el último identificador de chat generado (y usado en la tabla tblChat) para cada usuario.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|nodeID  <br/> |int, not null  <br/> |IDENTIFICADOR de nodo (solo tipo salón de chat).  <br/> |
|lastChatID  <br/> |BIGINT, not null  <br/> |Último ID de chat usado.  <br/> |
   
**Sus**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<nodeID, lastChatID\>  <br/> |Clave principal (solo nodeID es suficiente para procesar).  <br/> |
|nodeID  <br/> |Clave externa con la búsqueda en la tabla tblNode. nodeID.  <br/> |
   
## <a name="see-also"></a>Vea también

[tblChat](tblchat.md)
