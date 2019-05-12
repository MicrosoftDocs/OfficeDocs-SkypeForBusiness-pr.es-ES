---
title: Tabla Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: En la tabla de servidor es una tabla de apoyo. Cada registro representa un servidor.
ms.openlocfilehash: c0031e7181bb39895edadc40748f61626621f00e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920134"
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
   

