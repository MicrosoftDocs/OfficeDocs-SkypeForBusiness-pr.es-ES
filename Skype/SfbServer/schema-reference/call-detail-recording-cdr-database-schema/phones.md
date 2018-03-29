---
title: Tabla Phones
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: La tabla de teléfonos es un auxiliar. Cada registro de la tabla almacena información sobre un número de teléfono en llamadas VoIP que tengan registros en la base de datos.
ms.openlocfilehash: 8ec2095b857ba474a92bf0766d86119500919f51
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="phones-table"></a>Tabla Phones
 
La tabla de teléfonos es un auxiliar. Cada registro de la tabla almacena información sobre un número de teléfono en llamadas VoIP que tengan registros en la base de datos.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este teléfono.  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |Número de teléfono.  <br/> |
|**NextUpdateTS** <br/> |fecha y hora  <br/> ||Marca de hora (sólo para uso interno).  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
   

