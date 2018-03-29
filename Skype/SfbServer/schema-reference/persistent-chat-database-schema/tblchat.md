---
title: tblChat
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: tblChat contiene todos los mensajes de charla.
ms.openlocfilehash: 1a1a2986d69e2f5efafe365da3394de01c911623
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tblchat"></a>tblChat
 
tblChat contiene todos los mensajes de charla.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|///ChannelID  <br/> |int, no nulo  <br/> |Identificador de nodo.  <br/> |
|chatId  <br/> |bigint, no nulo  <br/> |Número secuencial único (por identificador de nodo) que define el orden de salón de chat, generado por la tabla tblLastChatId.  <br/> |
|chatDate  <br/> |bigint, no nulo  <br/> |Marca de tiempo del mensaje de charla.  <br/> |
|ID de usuario  <br/> |int, no nulo  <br/> |Identificador principal del póster.  <br/> |
|isAlert  <br/> |bits, no nulo  <br/> |Es True si el mensaje es un mensaje de alerta. False si no lo es.  <br/> |
|contenido  <br/> |nvarchar (max), no nulo  <br/> | Contenido de Chat (versión de texto sin formato). El contenido suele ser en texto sin formato con las siguientes excepciones: <br/>  Los archivos se representan como ma filelink: vínculos. <br/>  Enlaces se representan como un elemento HTML (aunque el tipo de contenido no puede considerarse HTML). <br/>  Historias se codifican como "[artículo]..."-como formato. <br/> |
|RTF  <br/> |varchar (max)  <br/> |Contenido de Chat (la versión RTF). Puede ser Null si el cliente no lo proporciona.  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<///ChannelID, chatD\>  <br/> |Clave principal.  <br/> |
   

