---
title: Tabla dispositivos en Skype Empresarial Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: La tabla Dispositivos es una tabla de apoyo. Cada registro almacena información sobre un dispositivo (teléfono de escritorio).
---

# <a name="devices-table-in-skype-for-business-server-2015"></a>Tabla dispositivos en Skype Empresarial Server 2015
 
La tabla Dispositivos es una tabla de apoyo. Cada registro almacena información sobre un dispositivo (teléfono de escritorio).
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |Entero  <br/> |Principal  <br/> |Número único que identifica esta versión de hardware.  <br/> |
|**ManufacturerId** <br/> |Entero  <br/> |Externo  <br/> |Fabricante de este dispositivo. Vea la [tabla Fabricantes de Skype Empresarial Server 2015](manufacturers.md) para obtener más información. <br/> |
|**HardwareVersionId** <br/> |Entero  <br/> |Externo  <br/> |Versión de hardware de este dispositivo. Vea la [tabla HardwareVersions en Skype Empresarial Server 2015](hardwareversions.md) para obtener más información. <br/> |
|**MacAddress** <br/> |bigint  <br/> ||Dirección MAC  <br/> |
   

