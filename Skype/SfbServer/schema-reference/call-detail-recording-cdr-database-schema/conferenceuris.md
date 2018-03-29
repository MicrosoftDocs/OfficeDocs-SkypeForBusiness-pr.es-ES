---
title: Tabla ConferenceUris en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
description: La tabla ConfereneUris es un auxiliar que almacena una lista de la conferencia varios identificadores URI que participaron en sesiones de conferencia registradas en la base de datos. Cada registro de la tabla representa una conferencia URI.
ms.openlocfilehash: 921bb448ffe50d62aa7680db0e8097c186eef8e7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="conferenceuris-table-in-skype-for-business-server-2015"></a>Tabla ConferenceUris en Skype para Business Server 2015
 
La tabla ConfereneUris es un auxiliar que almacena una lista de la conferencia varios identificadores URI que participaron en sesiones de conferencia registradas en la base de datos. Cada registro de la tabla representa una conferencia URI.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> |Primary  <br/> |Marca de tiempo interno utilizado.  <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Primary  <br/> |Número único que identifica esta conferencia URI.  <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> ||Conferencia de URI.  <br/> |
|**Suma de comprobación** <br/> |int  <br/> ||Suma de comprobación de ConferenceUri. Utilizado para aumenta la velocidad de las búsquedas de base de datos.  <br/> |
|**UriTypeId** <br/> |int  <br/> |Externa  <br/> |Tipo de identificador URI, como conf:chat para la conferencia de mensajes Instantáneos o conf:audio-vídeo para conferencias de audio y vídeo. Consulte la tabla [UriTypes](uritypes.md) para obtener más información. <br/> |
   

