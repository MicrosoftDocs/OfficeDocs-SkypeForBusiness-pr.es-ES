---
title: Tabla Device
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d5a4f777-bc12-4ce8-bc0d-867d5e22b436
description: La tabla del dispositivo es una tabla de soporte que almacena información acerca de la captura de diferentes o representar los dispositivos. Cada registro de la tabla representa un dispositivo.
ms.openlocfilehash: 346ea171b9a0c1b7a874b65a68b582c4167c57fe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="device-table"></a>Tabla Device
 
La tabla del dispositivo es una tabla de soporte que almacena información acerca de la captura de diferentes o representar los dispositivos. Cada registro de la tabla representa un dispositivo.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**DeviceKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este dispositivo.  <br/> |
|**DeviceName** <br/> |nvarchar(256)  <br/> |DeviceName + DeviceType es único  <br/> |Nombre de dispositivo.  <br/> |
|**DeviceType** <br/> |bit  <br/> |DeviceName + DeviceType es único  <br/> |Tipo de dispositivo. 1 es un dispositivo de captura, 0 es un dispositivo de representación.  <br/> |
   

