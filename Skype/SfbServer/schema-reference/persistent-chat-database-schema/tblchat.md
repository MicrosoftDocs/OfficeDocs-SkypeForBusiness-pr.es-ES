---
title: tblChat
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
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: tblChat contiene todos los mensajes de chat.
ms.openlocfilehash: 6f28c067361d6b1391e48aa7b78e282d2f865725
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62390902"
---
# <a name="tblchat"></a>tblChat
 
tblChat contiene todos los mensajes de chat.
  
**Columns**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|channelId  <br/> |int, no NULL  <br/> |Identificador del nodo.  <br/> |
|chatId  <br/> |bigint, no NULL  <br/> |Número secuencial único (por identificador de nodo) que define el orden de los salones de chat, generado por la tabla tblLastChatId.  <br/> |
|chatDate  <br/> |bigint, no NULL  <br/> |Marca de tiempo del mensaje de chat.  <br/> |
|userId  <br/> |int, no NULL  <br/> |Identificador principal de la persona que publicó el mensaje.  <br/> |
|isAlert  <br/> |bit, no NULL  <br/> |True si el mensaje es de alerta. False si no lo es.  <br/> |
|contenido  <br/> |nvarchar (max), no NULL  <br/> | Contenido del chat (versión de texto sin formato). El contenido suele ser texto sin formato con las siguientes excepciones: <br/>  Los archivos se representan como vínculos ma-filelink:. <br/>  Los vínculos se representan como un elemento HTML (aunque el tipo de contenido no puede considerarse como HTML). <br/>  Las historias se codifican como un formato "[STORY]...."-like. <br/> |
|rtf  <br/> |varchar(max)  <br/> |Contenido del chat (versión RTF). Puede ser Null si el cliente no lo proporciona.  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<channelID, chatD\>  <br/> |Clave principal.  <br/> |
   

