---
title: Tabla de extremo
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: La tabla Endpoint es una tabla de soporte técnico que almacena información sobre los puntos de conexión que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa un extremo.
ms.openlocfilehash: 7e892d0e913f8b06fc78f00fbbb348774b9548d3
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834006"
---
# <a name="endpoint-table"></a>Tabla de extremo
 
La tabla Endpoint es una tabla de soporte técnico que almacena información sobre los puntos de conexión que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa un extremo.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |Entero  <br/> |Principal  <br/> |Número único que identifica este extremo.  <br/> |
|**Nombre** <br/> |nvarchar(256)  <br/> |Única  <br/> |Nombre del extremo.  <br/> |
|**SO** <br/> |nvarchar(128)  <br/> | <br/> |Sistema operativo (SO) del extremo.  <br/> |
|**CPUName** <br/> |nvarchar(128)  <br/> ||Nombre de CPU del extremo.  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||Número de núcleos de CPU del extremo.  <br/> |
|**CPUProcessorSpeed** <br/> |Entero  <br/> ||Velocidad del procesador de CPU del punto de conexión.  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || Marca de bits que indica si el sistema se está ejecutando en un entorno virtualizado: <br/>  0x0000- Ninguno <br/>  0x0001: HyperV <br/>  0x0002 - VMWare <br/>  0x0004: PC virtual <br/>  0x0008- Xen PC <br/> |
   

