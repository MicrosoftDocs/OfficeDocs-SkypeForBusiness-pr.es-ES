---
title: Tabla UserAgent
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: La tabla UserAgent es una tabla auxiliar que almacena una lista de los distintos agentes de usuario que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa un agente de usuario
ms.openlocfilehash: a1d0e647ff78d409555988a27592228fac2643be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799940"
---
# <a name="useragent-table"></a>Tabla UserAgent
 
La tabla UserAgent es una tabla auxiliar que almacena una lista de los distintos agentes de usuario que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa un agente de usuario
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |entero  <br/> |Principal  <br/> |Número único que identifica este agente de usuario.  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |Única  <br/> |Cadena de agente de usuario.  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 es el servidor de mediación.  <br/> 2 es un servidor de conferencia A/V.  <br/> 4 es Skype Empresarial.  <br/> 8 es teléfono IP.  <br/> 16 es Live Meeting Console.  <br/> 32 es la Herramienta de validación de implementación (DVT).  <br/> 64 es Skype Empresarial Server en equipos Macintosh.  <br/> 128 es el Operador de Skype Empresarial Server.  <br/> 256 es el servicio de anuncio de conferencia.  <br/> 512 es el número de conferencias Operador automático.  <br/> 1024 es una aplicación de grupo de respuesta.  <br/> 2048 es Fuera del control de voz.  <br/> |
   

