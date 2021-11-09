---
title: Tabla Teléfonos
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: La tabla Teléfonos es una tabla de soporte técnico. Cada registro de la tabla almacena información sobre un número de teléfono implicado en llamadas VoIP que tienen registros en la base de datos.
ms.openlocfilehash: 249b2a08e0751b6e8746f2da27a13e1151c375f7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836108"
---
# <a name="phones-table"></a>Tabla Teléfonos
 
La tabla Teléfonos es una tabla de soporte técnico. Cada registro de la tabla almacena información sobre un número de teléfono implicado en llamadas VoIP que tienen registros en la base de datos.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |Entero  <br/> |Principal  <br/> |Número único que identifica este teléfono.  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |Teléfono número.  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||Marca de tiempo (solo para uso interno).  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
   

