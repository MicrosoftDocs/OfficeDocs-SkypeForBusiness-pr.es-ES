---
title: Tabla UserAgent
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: La tabla UserAgent es un auxiliar que almacena una lista de los distintos agentes de usuario que han participado en las sesiones que se registran en la base de datos. Cada registro de la tabla representa a un agente de usuario
ms.openlocfilehash: 5b9bcc35fbad3d20a006410aeb3538b6f5daa77e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="useragent-table"></a>Tabla UserAgent
 
La tabla UserAgent es un auxiliar que almacena una lista de los distintos agentes de usuario que han participado en las sesiones que se registran en la base de datos. Cada registro de la tabla representa a un agente de usuario
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica a este agente de usuario.  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |Único  <br/> |Cadena de agente de usuario.  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 es el servidor de mediación.  <br/> es de 2 A / V Conferencing Server.  <br/> 4 es Skype para el negocio.  <br/> 8 es el teléfono IP.  <br/> 16 es la consola Live Meeting.  <br/> 32 es la herramienta de validación de implementación (TVP).  <br/> 64 es Skype para Business Server en equipos Macintosh.  <br/> 128 es Skype para operador de servidor empresarial.  <br/> 256 es servicio de anuncio de conferencia.  <br/> Operador automático de conferencia es de 512.  <br/> 1024 es la aplicación de grupo de respuesta.  <br/> 2048 está fuera de Control de voz.  <br/> |
   

