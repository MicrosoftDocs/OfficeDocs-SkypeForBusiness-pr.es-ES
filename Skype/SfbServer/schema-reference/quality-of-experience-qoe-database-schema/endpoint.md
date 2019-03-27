---
title: Tabla Endpoint
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: En la tabla de extremo es una tabla de apoyo que almacena información sobre los extremos que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa uno de los extremos.
ms.openlocfilehash: f9c304408006ef9caf5521b8f0bbe28c2d917abe
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883000"
---
# <a name="endpoint-table"></a>Tabla Endpoint
 
En la tabla de extremo es una tabla de apoyo que almacena información sobre los extremos que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa uno de los extremos.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este extremo.  <br/> |
|**Nombre.** <br/> |nvarchar(256)  <br/> |Único  <br/> |Nombre del extremo.  <br/> |
|**Sistema operativo** <br/> |nvarchar (128)  <br/> | <br/> |Sistema operativo (SO) del extremo.  <br/> |
|**CPUName** <br/> |nvarchar (128)  <br/> ||Nombre de la CPU del extremo.  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||Número de núcleos de CPU del extremo.  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||Velocidad del procesador de CPU del extremo.  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || Indicador de bits que indica si el sistema se está ejecutando en un entorno virtualizado: <br/>  0 x 0000 - ninguno <br/>  0 x 0001 - HyperV <br/>  0 x 0002 - VMWare <br/>  0 x 0004 - virtual PC <br/>  0 x 0008 - Xen PC <br/> |
   

