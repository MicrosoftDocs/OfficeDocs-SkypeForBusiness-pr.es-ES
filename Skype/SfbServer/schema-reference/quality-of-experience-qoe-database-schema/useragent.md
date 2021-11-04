---
title: Tabla UserAgent
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: La tabla UserAgent es una tabla auxiliar que almacena una lista de los distintos agentes de usuario que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa un agente de usuario
ms.openlocfilehash: 7e870e9d63f3d1c9e199df36c5225af704388746
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60771826"
---
# <a name="useragent-table"></a>Tabla UserAgent
 
La tabla UserAgent es una tabla auxiliar que almacena una lista de los distintos agentes de usuario que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa un agente de usuario
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UserAgentKey** <br/> |Entero  <br/> |Principal  <br/> |Número único que identifica este agente de usuario.  <br/> |
|**UserAgent** <br/> |nvarchar(256)  <br/> |Única  <br/> |Cadena de agente de usuario.  <br/> |
|**UAType** <br/> |smallint  <br/> | <br/> |1 es servidor de mediación.  <br/> 2 es un servidor de conferencia A/V.  <br/> 4 es Skype Empresarial.  <br/> 8 es IP Teléfono.  <br/> 16 es Live Meeting Console.  <br/> 32 es Deployment Validation Tool (DVT).  <br/> 64 se Skype Empresarial Server en equipos Macintosh.  <br/> 128 es Skype Empresarial Server Attendant.  <br/> 256 es Anuncio de conferencia servicio.  <br/> 512 es conferencia Operador automático.  <br/> 1024 es la aplicación grupo de respuesta.  <br/> 2048 es Fuera del control de voz.  <br/> |
   

