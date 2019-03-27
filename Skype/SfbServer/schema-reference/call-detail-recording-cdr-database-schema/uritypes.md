---
title: Tabla UriTypes
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: En la tabla UriTypes contiene los diferentes tipos URI (identificador uniforme de recursos) que se supervisan en Skype para Business Server 2015.
ms.openlocfilehash: cb9c131901a322f9d22c8d29aa52a73dc27c9ea1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899648"
---
# <a name="uritypes-table"></a>Tabla UriTypes
 
En la tabla UriTypes contiene los diferentes tipos URI (identificador uniforme de recursos) que se supervisan en Skype para Business Server 2015.

Cuando se crea la CDR DB, se crean dos registros para representar PhoneUri y UserUri, y los registros se crean después de se asignan dinámicamente UriTypeId. 
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UriTypeId** <br/> |tinyint  <br/> |Primary  <br/> |Identificador único asignado a un tipo de URI.  <br/> Valores posibles: de 0 a 255 |
|**UriType** <br/> |nvarchar(256)  <br/> || Descripciones de los distintos tipos URI. Los siguientes valores son asignados previamente: <br/>  1: URI del teléfono <br/>  0 - URI del usuario <br/> <br/>  Otros tipos posibles son: <br/>conferencia:uso compartido de aplicaciones <br/> conferencia:audio-vídeo<br/> conf:chat<br/>    conferencia:foco<br/>   MRAS<br/>
