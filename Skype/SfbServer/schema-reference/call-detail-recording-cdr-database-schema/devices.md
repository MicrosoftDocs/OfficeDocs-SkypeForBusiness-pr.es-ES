---
title: Tabla de dispositivos en Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: En la tabla de dispositivos es una tabla de apoyo. Cada registro almacena información acerca de un dispositivo (teléfono de escritorio).
ms.openlocfilehash: f770f19fb94bf25bdb4c13e74dc41e05f6674788
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213168"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Tabla de dispositivos en Skype para Business Server 2015
 
En la tabla de dispositivos es una tabla de apoyo. Cada registro almacena información acerca de un dispositivo (teléfono de escritorio).
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Primary  <br/> |Número único que identifica esta versión de hardware.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Externa  <br/> |Fabricante de este dispositivo. Consulte la [tabla de los fabricantes de Skype para Business Server 2015](manufacturers.md) para obtener más información. <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Externa  <br/> |Versión de hardware de este dispositivo. Consulte la [tabla HardwareVersions en Skype para Business Server 2015](hardwareversions.md) para obtener más información. <br/> |
|**MacAddress** <br/> |bigint  <br/> ||Dirección MAC  <br/> |
   

