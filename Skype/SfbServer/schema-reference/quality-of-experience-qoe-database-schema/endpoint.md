---
title: Tabla Endpoint
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: La tabla de extremo es un auxiliar que almacena información sobre los extremos que han participado en las sesiones que se registran en la base de datos. Cada registro de la tabla representa un extremo.
ms.openlocfilehash: 64eb55a0c1bebe7f2ce992351ce21db2fdc575d7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="endpoint-table"></a>Tabla Endpoint
 
La tabla de extremo es un auxiliar que almacena información sobre los extremos que han participado en las sesiones que se registran en la base de datos. Cada registro de la tabla representa un extremo.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este extremo.  <br/> |
|**Nombre.** <br/> |nvarchar(256)  <br/> |Único  <br/> |Nombre del extremo.  <br/> |
|**SISTEMA OPERATIVO** <br/> |nvarchar (128)  <br/> | <br/> |Sistema operativo (OS) del extremo.  <br/> |
|**CPUName** <br/> |nvarchar (128)  <br/> ||Nombre de la CPU del extremo.  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||Número de núcleos de CPU del extremo.  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||Velocidad de procesador de la CPU del extremo.  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || Indicador de bits que indica si el sistema se está ejecutando en un entorno virtualizado: <br/>  0 x 0000 - ninguno <br/>  0 x 0001 - HyperV <br/>  0 x 0002 - VMWare <br/>  0 x 0004 - virtual PC <br/>  0 x 0008 - Xen PC <br/> |
   

