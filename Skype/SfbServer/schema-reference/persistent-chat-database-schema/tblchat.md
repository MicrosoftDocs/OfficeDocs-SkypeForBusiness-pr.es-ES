---
title: tblChat
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: tblChat contiene todos los mensajes de chat.
ms.openlocfilehash: 54e19fe729d9f96afb04d22a917864118de75efe
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212652"
---
# <a name="tblchat"></a>tblChat
 
tblChat contiene todos los mensajes de chat.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|///ChannelID  <br/> |int, no es nulo  <br/> |Identificador del nodo.  <br/> |
|chatId  <br/> |bigint, no es nulo  <br/> |Número secuencial único (por identificador de nodo) que define el orden de salón de chat, generado por la tabla tblLastChatId.  <br/> |
|chatDate  <br/> |bigint, no es nulo  <br/> |Marca de tiempo del mensaje de chat.  <br/> |
|userId  <br/> |int, no es nulo  <br/> |Identificador de entidad del póster de.  <br/> |
|isAlert  <br/> |bit, no es nulo  <br/> |Es True si el mensaje es un mensaje de alerta. False si no lo está.  <br/> |
|contenido  <br/> |nvarchar (max), no es nulo  <br/> | Contenido de Chat (la versión de texto sin formato). El contenido es normalmente en texto sin formato con las siguientes excepciones: <br/>  Los archivos se representan como ma-filelink: vínculos. <br/>  Vínculos se representan como un elemento HTML (aunque el tipo de contenido no puede considerarse como HTML). <br/>  Historias se codifican como un "[STORY]..."-como formato. <br/> |
|RTF  <br/> |varchar (max)  <br/> |Contenido de Chat (la versión RTF). Puede ser Null si el cliente no proporcionarlo.  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<///ChannelID, chatD\>  <br/> |Clave principal.  <br/> |
   

