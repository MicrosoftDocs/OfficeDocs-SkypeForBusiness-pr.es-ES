---
title: Tabla Endpoint
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
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: La tabla Endpoint es una tabla de apoyo que almacena información sobre los extremos que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa un extremo.
ms.openlocfilehash: 9caa0571e562a84c1678208f0e70c27317deda3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823070"
---
# <a name="endpoint-table"></a>Tabla Endpoint
 
La tabla Endpoint es una tabla de apoyo que almacena información sobre los extremos que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa un extremo.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |entero  <br/> |Principal  <br/> |Número único que identifica este punto de conexión.  <br/> |
|**Nombre** <br/> |nvarchar(256)  <br/> |Única  <br/> |Nombre del extremo.  <br/> |
|**Sistema operativo** <br/> |nvarchar(128)  <br/> | <br/> |Sistema operativo (SO) del punto de conexión.  <br/> |
|**CPUName** <br/> |nvarchar(128)  <br/> ||Nombre de CPU del punto de conexión.  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||Número de núcleos de CPU del punto de conexión.  <br/> |
|**CPUProcessorSpeed** <br/> |entero  <br/> ||Velocidad del procesador de CPU del punto de conexión.  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || Marca de bits que indica si el sistema se ejecuta en un entorno virtualizado: <br/>  0x0000- Ninguno <br/>  0x0001: HyperV <br/>  0x0002 - VMWare <br/>  0x0004- Virtual PC <br/>  0x0008 - Xen PC <br/> |
   

