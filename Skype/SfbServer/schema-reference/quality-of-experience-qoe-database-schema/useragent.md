---
title: Tabla UserAgent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: La tabla UserAgent es una tabla de soporte que almacena una lista de los diversos agentes de usuario que participaron en sesiones registradas en la base de datos. Cada registro de la tabla representa un agente de usuario
ms.openlocfilehash: f0c8a2f182611887db1324d17b6b7c28d6a9393d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294589"
---
# <a name="useragent-table"></a>Tabla UserAgent
 
La tabla UserAgent es una tabla de soporte que almacena una lista de los diversos agentes de usuario que participaron en sesiones registradas en la base de datos. Cada registro de la tabla representa un agente de usuario
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica a este agente de usuario.  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |Solo  <br/> |Cadena de agente de usuario.  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 es el servidor de mediación.  <br/> 2 es un servidor de conferencia A/V.  <br/> 4 es Skype empresarial.  <br/> 8 es teléfono IP.  <br/> 16 es la consola de Live Meeting.  <br/> 32 es la herramienta de validación de implementación (DVT).  <br/> 64 es Skype empresarial Server en equipos Macintosh.  <br/> 128 es operador de servidor de Skype empresarial.  <br/> 256 es el servicio de anuncios de conferencia.  <br/> 512 es operador automático de conferencia.  <br/> 1024 es una aplicación de grupo de respuesta.  <br/> 2048 está fuera del control de voz.  <br/> |
   

