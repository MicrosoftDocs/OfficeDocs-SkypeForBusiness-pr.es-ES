---
title: tblChat
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
ms.assetid: b7fcf1b4-7a3f-4585-a6d9-95e7f030c7dc
description: tblChat contiene todos los mensajes instantáneos.
ms.openlocfilehash: 7221136c435c1d4af836174ddfde5cbd02f4c5f6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814678"
---
# <a name="tblchat"></a>tblChat
 
tblChat contiene todos los mensajes instantáneos.
  
**Columnas**

|**Columna**|**Tipo**|**Descripción**|
|:-----|:-----|:-----|
|channelId  <br/> |int, not null  <br/> |IDENTIFICADOR de nodo.  <br/> |
|chatId  <br/> |BIGINT, not null  <br/> |Número secuencial único (por identificador de nodo) que define el pedido del salón de chat, generado por la tabla tblLastChatId.  <br/> |
|chatDate  <br/> |BIGINT, not null  <br/> |Marca de tiempo del mensaje de la conversación.  <br/> |
|Iddeusuario  <br/> |int, not null  <br/> |IDENTIFICADOR principal del póster.  <br/> |
|isAlert  <br/> |bit, not null  <br/> |True si el mensaje es un mensaje de alerta. Falso si no lo es.  <br/> |
|objetos  <br/> |nvarchar (Max), not null  <br/> | Contenido de la conversación (versión de texto sin formato). El contenido suele estar en texto sin formato, con las siguientes excepciones: <br/>  Los archivos se representan como ma-FileLink: links. <br/>  Los vínculos se representan como un elemento HTML (aunque el tipo de contenido no se puede considerar HTML). <br/>  Los casos se codifican como un formato "[artículo]....". <br/> |
|enriquecido  <br/> |VARCHAR (Max)  <br/> |Contenido de la conversación (la versión RTF). Puede ser null si el cliente no lo proporciona.  <br/> |
   
**Clave**

|**Columna**|**Descripción**|
|:-----|:-----|
|\<channelID, conversado\>  <br/> |Clave principal.  <br/> |
   

