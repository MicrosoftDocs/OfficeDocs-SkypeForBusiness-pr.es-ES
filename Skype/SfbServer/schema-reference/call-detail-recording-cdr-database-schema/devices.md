---
title: Tabla dispositivos de Skype empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: La tabla dispositivos es una tabla de soporte. Cada registro almacena información acerca de un dispositivo (teléfono de escritorio).
ms.openlocfilehash: 145637b6385677007efa47cd21b3f0ea7d7f88f2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296381"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Tabla dispositivos de Skype empresarial Server 2015
 
La tabla dispositivos es una tabla de soporte. Cada registro almacena información acerca de un dispositivo (teléfono de escritorio).
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Primary  <br/> |Número único que identifica esta versión de hardware.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Extranjero  <br/> |Fabricante de este dispositivo. Para obtener más información, consulte la [tabla de fabricantes en Skype empresarial Server 2015](manufacturers.md) . <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Extranjero  <br/> |Versión de hardware de este dispositivo. Para obtener más información, consulte la [tabla HardwareVersions en Skype empresarial Server 2015](hardwareversions.md) . <br/> |
|**MacAddress** <br/> |BIGINT  <br/> ||Dirección MAC  <br/> |
   

