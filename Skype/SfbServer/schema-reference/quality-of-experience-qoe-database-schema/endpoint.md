---
title: Tabla Endpoint
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 500f330d-4d7d-4e88-b1cc-fef9a9de6b5c
description: La tabla de extremos es una tabla de soporte que almacena información sobre los puntos de conexión que participaron en sesiones registradas en la base de datos. Cada registro de la tabla representa un punto final.
ms.openlocfilehash: 7d582d382784d04d4495de972aa20673862284f4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294995"
---
# <a name="endpoint-table"></a>Tabla Endpoint
 
La tabla de extremos es una tabla de soporte que almacena información sobre los puntos de conexión que participaron en sesiones registradas en la base de datos. Cada registro de la tabla representa un punto final.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**EndpointKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este punto final.  <br/> |
|**Nombre.** <br/> |nvarchar(256)  <br/> |Solo  <br/> |Nombre del extremo.  <br/> |
|**Sistema operativo** <br/> |nvarchar(128  <br/> | <br/> |Sistema operativo (SO) del punto de conexión.  <br/> |
|**CPUName** <br/> |nvarchar(128  <br/> ||Nombre de la CPU del extremo.  <br/> |
|**CPUNumberOfCores** <br/> |smallint  <br/> ||Número de núcleos de CPU del extremo.  <br/> |
|**CPUProcessorSpeed** <br/> |int  <br/> ||Velocidad del procesador de la CPU del punto de conexión.  <br/> |
|**VirtualizationFlag** <br/> |tinyint  <br/> || Marcador de bits que indica si el sistema se está ejecutando en un entorno virtualizado: <br/>  0x0000-ninguna <br/>  0x0001: HyperV <br/>  0x0002-VMWare <br/>  0x0004-Virtual PC <br/>  0x0008: Xen PC <br/> |
   

