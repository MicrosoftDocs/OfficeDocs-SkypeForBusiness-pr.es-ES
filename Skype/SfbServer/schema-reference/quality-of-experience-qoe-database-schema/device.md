---
title: Tabla Device
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: En la tabla de dispositivo es una tabla de apoyo que almacena información acerca de la captura diversos o dispositivos de presentación. Cada registro de la tabla representa un dispositivo.
ms.openlocfilehash: 0b3c27708cd8e9d1b02914e6f2cba414e353609c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920029"
---
# <a name="device-table"></a>Tabla Device
 
En la tabla de dispositivo es una tabla de apoyo que almacena información acerca de la captura diversos o dispositivos de presentación. Cada registro de la tabla representa un dispositivo.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este dispositivo.  <br/> |
|**DeviceName** <br/> |nvarchar(256)  <br/> |DeviceName + DeviceType son únicos  <br/> |Nombre del dispositivo.  <br/> |
|**DeviceType** <br/> |bit  <br/> |DeviceName + DeviceType son únicos  <br/> |Tipo de dispositivo. 1 es un dispositivo de captura, 0 es un dispositivo de presentación.  <br/> |
   

