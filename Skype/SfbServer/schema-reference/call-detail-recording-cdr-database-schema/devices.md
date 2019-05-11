---
title: Tabla de dispositivos en Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: En la tabla de dispositivos es una tabla de apoyo. Cada registro almacena información acerca de un dispositivo (teléfono de escritorio).
ms.openlocfilehash: efd0894a36e02948a3a8cd9f3465dcdbd30f3e2d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901097"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Tabla de dispositivos en Skype para Business Server 2015
 
En la tabla de dispositivos es una tabla de apoyo. Cada registro almacena información acerca de un dispositivo (teléfono de escritorio).
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |int  <br/> |Primary  <br/> |Número único que identifica esta versión de hardware.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Externa  <br/> |Fabricante de este dispositivo. Consulte la [tabla de los fabricantes de Skype para Business Server 2015](manufacturers.md) para obtener más información. <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Externa  <br/> |Versión de hardware de este dispositivo. Consulte la [tabla HardwareVersions en Skype para Business Server 2015](hardwareversions.md) para obtener más información. <br/> |
|**MacAddress** <br/> |bigint  <br/> ||Dirección MAC  <br/> |
   

