---
title: Tabla Server
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9af89d08-d35a-48e8-b56d-6df292f973cc
description: La tabla de servidor es una tabla de soporte. Cada registro representa a un servidor.
ms.openlocfilehash: be48b90cc727ebfd0320b38ac0d89a302dab6b07
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="server-table"></a>Tabla Server
 
La tabla de servidor es una tabla de soporte. Cada registro representa a un servidor. 
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ServerKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica el servidor.  <br/> |
|**FQDNOrIP** <br/> |nvarchar(256)  <br/> |índice  <br/> |Cadena de la dirección MAC.  <br/> |
|**ServerType** <br/> |int  <br/> |Externa  <br/> |1: servidor de mediación  <br/> 2: A / V conferencia Server16394: A / V borde service32769: puerta de enlace  <br/> |
|**PoolName** <br/> |nvarchar (512)  <br/> ||Grupo al que pertenece el servidor. Sólo aplicable en lugar de A / V Conferencing Server.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Sólo para uso interno.  <br/> |
   

