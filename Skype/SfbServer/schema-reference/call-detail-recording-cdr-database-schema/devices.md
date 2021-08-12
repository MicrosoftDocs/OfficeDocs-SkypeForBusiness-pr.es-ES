---
title: Tabla dispositivos en Skype Empresarial Server 2015
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
ms.openlocfilehash: eac31407de3f5a648ebe5f3819b2d7f3556e9bd6c2be930450e8e27700ead178
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295377"
---
# <a name="devices-table-in-skype-for-business-server-2015"></a>Tabla dispositivos en Skype Empresarial Server 2015
 
La tabla Dispositivos es una tabla de apoyo. Cada registro almacena información sobre un dispositivo (teléfono de escritorio).
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**DeviceId** <br/> |Entero  <br/> |Principal  <br/> |Número único que identifica esta versión de hardware.  <br/> |
|**ManufacturerId** <br/> |Entero  <br/> |Externo  <br/> |Fabricante de este dispositivo. Vea la [tabla Fabricantes de Skype Empresarial Server 2015](manufacturers.md) para obtener más información. <br/> |
|**HardwareVersionId** <br/> |Entero  <br/> |Externo  <br/> |Versión de hardware de este dispositivo. Vea la [tabla HardwareVersions de Skype Empresarial Server 2015](hardwareversions.md) para obtener más información. <br/> |
|**MacAddress** <br/> |bigint  <br/> ||Dirección MAC  <br/> |
   

