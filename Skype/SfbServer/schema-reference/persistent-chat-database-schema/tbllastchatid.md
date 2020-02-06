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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contiene el último identificador de chat generado (y usado en la tabla tblChat) para cada usuario.
ms.openlocfilehash: 95498f077948e1b400d0a370762c121def703e8c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814588"
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
