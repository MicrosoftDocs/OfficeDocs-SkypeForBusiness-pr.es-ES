---
title: Tabla UserAgent
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: En la tabla UserAgent es una tabla de apoyo que almacena una lista de los distintos agentes de usuario que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa a un agente de usuario
ms.openlocfilehash: 17cb395569e8a634925be27705b878b104a3b70a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893107"
---
# <a name="useragent-table"></a>Tabla UserAgent
 
En la tabla UserAgent es una tabla de apoyo que almacena una lista de los distintos agentes de usuario que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa a un agente de usuario
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica a este agente de usuario.  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |Único  <br/> |Cadena de agente de usuario.  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 es el servidor de mediación.  <br/> 2 es / servidor de conferencia A/v.  <br/> 4 es Skype para la empresa.  <br/> 8 es teléfono IP.  <br/> 16 es consola de Live Meeting.  <br/> 32 es la herramienta de validación de implementación (DVT).  <br/> 64 es Skype para Business Server en equipos Macintosh.  <br/> 128 es Skype para Business Server Attendant.  <br/> 256 es el servicio de anuncio de conferencia.  <br/> 512 es operador automático de conferencia.  <br/> 1024 es la aplicación de grupo de respuesta.  <br/> 2048 es Control de voz externa.  <br/> |
   

