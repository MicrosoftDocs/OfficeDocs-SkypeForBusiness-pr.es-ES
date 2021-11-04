---
title: Tabla de servidor
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
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: La tabla Server es una tabla auxiliar. Cada registro representa a un servidor.
ms.openlocfilehash: e2a1007afa545a5b70b60f0e22f69826daebcda0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776040"
---
# <a name="server-table"></a>Tabla de servidor
 
La tabla Server es una tabla auxiliar. Cada registro representa a un servidor. 
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |Entero  <br/> |Principal  <br/> |Número único que identifica el servidor.  <br/> |
|**FQDNOrIP** <br/> |nvarchar(256)  <br/> |index  <br/> |Cadena de dirección MAC.  <br/> |
|**ServerType** <br/> |Entero  <br/> |Externo  <br/> |1: Servidor de mediación  <br/> 2: Servidor de conferencia A/V16394: Servicio perimetral A/V32769: Puerta de enlace  <br/> |
|**PoolName** <br/> |nvarchar(512)  <br/> ||Grupo al que pertenece el servidor. Solo aplicable para el servidor de conferencia A/V.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Únicamente para uso interno.  <br/> |
   

