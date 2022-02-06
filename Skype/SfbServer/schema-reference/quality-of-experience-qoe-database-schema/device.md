---
title: Tabla de dispositivos
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: La tabla Dispositivo es una tabla auxiliar que almacena información sobre los diversos dispositivos de captura o presentación. Cada registro de la tabla representa un dispositivo.
---

# <a name="device-table"></a>Tabla de dispositivos
 
La tabla Dispositivo es una tabla auxiliar que almacena información sobre los diversos dispositivos de captura o presentación. Cada registro de la tabla representa un dispositivo.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |Entero  <br/> |Principal  <br/> |Número único que identifica este dispositivo.  <br/> |
|**DeviceName** <br/> |nvarchar(256)  <br/> |DeviceName + DeviceType son únicos  <br/> |Nombre del dispositivo  <br/> |
|**DeviceType** <br/> |bit  <br/> |DeviceName + DeviceType son únicos  <br/> |Tipo de dispositivo. 1 es un dispositivo de captura, 0 es un dispositivo de presentación.  <br/> |
   

