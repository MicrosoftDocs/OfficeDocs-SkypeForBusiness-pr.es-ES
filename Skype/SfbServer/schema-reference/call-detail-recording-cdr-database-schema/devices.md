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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 532e2280-4bbc-4a6c-93da-45d9f80a30a0
description: La tabla dispositivos es una tabla de soporte. Cada registro almacena información acerca de un dispositivo (teléfono de escritorio).
ms.openlocfilehash: e53a8947d106d6a92d7cf5cb881f20022e1bac69
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815288"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Tabla dispositivos de Skype empresarial Server 2015
 
La tabla dispositivos es una tabla de soporte. Cada registro almacena información acerca de un dispositivo (teléfono de escritorio).
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Primary  <br/> |Número único que identifica esta versión de hardware.  <br/> |
|**ManufacturerId** <br/> |int  <br/> |Extranjero  <br/> |Fabricante de este dispositivo. Para obtener más información, consulte la [tabla de fabricantes en Skype empresarial Server 2015](manufacturers.md) . <br/> |
|**HardwareVersionId** <br/> |int  <br/> |Extranjero  <br/> |Versión de hardware de este dispositivo. Para obtener más información, consulte la [tabla HardwareVersions en Skype empresarial Server 2015](hardwareversions.md) . <br/> |
|**MacAddress** <br/> |BIGINT  <br/> ||Dirección MAC  <br/> |
   

