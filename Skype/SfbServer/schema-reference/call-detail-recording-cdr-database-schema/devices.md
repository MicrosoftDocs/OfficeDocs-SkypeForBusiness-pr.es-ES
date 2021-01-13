---
title: Tabla Devices en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: La tabla Dispositivos es una tabla de apoyo. Cada registro almacena información sobre un dispositivo (teléfono de escritorio).
ms.openlocfilehash: da0d6ea8143fb8c81225e885fba1f05a90e2fda5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831820"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Tabla Devices en Skype Empresarial Server 2015
 
La tabla Dispositivos es una tabla de apoyo. Cada registro almacena información sobre un dispositivo (teléfono de escritorio).
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |entero  <br/> |Principal  <br/> |Número único que identifica esta versión de hardware.  <br/> |
|**ManufacturerId** <br/> |entero  <br/> |Externo  <br/> |Fabricante de este dispositivo. Consulte la [tabla Fabricantes de Skype Empresarial Server 2015](manufacturers.md) para obtener más información. <br/> |
|**HardwareVersionId** <br/> |entero  <br/> |Externo  <br/> |Versión de hardware de este dispositivo. Consulte la [tabla HardwareVersions en Skype Empresarial Server 2015](hardwareversions.md) para obtener más información. <br/> |
|**MacAddress** <br/> |bigint  <br/> ||Dirección MAC  <br/> |
   

