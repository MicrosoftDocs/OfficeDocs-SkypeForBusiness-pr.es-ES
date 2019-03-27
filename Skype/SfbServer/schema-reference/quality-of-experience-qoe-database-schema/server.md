---
title: Tabla Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: En la tabla de servidor es una tabla de apoyo. Cada registro representa un servidor.
ms.openlocfilehash: 877743f5d589cd4fea34039786b33bd410069bb3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874311"
---
# <a name="server-table"></a>Tabla Server
 
En la tabla de servidor es una tabla de apoyo. Cada registro representa un servidor. 
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica el servidor.  <br/> |
|**FQDNOrIP** <br/> |nvarchar(256)  <br/> |índice  <br/> |Cadena de dirección MAC.  <br/> |
|**ServerType** <br/> |int  <br/> |Externa  <br/> |1: servidor de mediación  <br/> 2: A / V conferencia Server16394: A V perimetral v32769: puerta de enlace  <br/> |
|**PoolName** <br/> |nvarchar (512)  <br/> ||El servidor pertenece al grupo de servidores. Solo se aplica en lugar de A y servidor de conferencia A/v.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Sólo para uso interno.  <br/> |
   

