---
title: Tabla Phones
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: En la tabla de teléfonos es una tabla de apoyo. Cada registro en la tabla almacena información acerca de un número de teléfono que participan en llamadas VoIP que tienen registros en la base de datos.
ms.openlocfilehash: 733adec46e948c3b7f1d804f57011110355078f4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894645"
---
# <a name="phones-table"></a>Tabla Phones
 
En la tabla de teléfonos es una tabla de apoyo. Cada registro en la tabla almacena información acerca de un número de teléfono que participan en llamadas VoIP que tienen registros en la base de datos.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este teléfono.  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |Número de teléfono.  <br/> |
|**NextUpdateTS** <br/> |fecha y hora  <br/> ||Marca de tiempo (sólo para uso interno).  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
   

