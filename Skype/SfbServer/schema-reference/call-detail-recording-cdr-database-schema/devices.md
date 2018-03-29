---
title: Tabla de dispositivos en Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: La tabla de dispositivos es una tabla de soporte. Cada registro almacena información acerca de un dispositivo (teléfono de escritorio).
ms.openlocfilehash: c7a5a5933d4fe2e465faf039a8ac2ed2a65fa563
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Tabla de dispositivos en Skype para Business Server 2015
 
La tabla de dispositivos es una tabla de soporte. Cada registro almacena información acerca de un dispositivo (teléfono de escritorio).
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Primary  <br/> |Número único que identifica la versión del hardware.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Externa  <br/> |Fabricante de este dispositivo. Consulte la [tabla de fabricantes en Skype para Business Server 2015](manufacturers.md) para obtener más información. <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Externa  <br/> |Versión de hardware de este dispositivo. Consulte la [tabla HardwareVersions en Skype para Business Server 2015](hardwareversions.md) para obtener más información. <br/> |
|**Dirección MAC** <br/> |bigint  <br/> ||Dirección MAC  <br/> |
   

