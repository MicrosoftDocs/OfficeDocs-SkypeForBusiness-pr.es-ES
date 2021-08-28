---
title: Tabla Teléfonos
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
ms.localizationpriority: medium
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: La tabla Teléfonos es una tabla de soporte técnico. Cada registro de la tabla almacena información sobre un número de teléfono implicado en llamadas VoIP que tienen registros en la base de datos.
ms.openlocfilehash: 37adaaa1885d91c84ee657c422b19debad294c01
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58584864"
---
# <a name="phones-table"></a>Tabla Teléfonos
 
La tabla Teléfonos es una tabla de soporte técnico. Cada registro de la tabla almacena información sobre un número de teléfono implicado en llamadas VoIP que tienen registros en la base de datos.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |Entero  <br/> |Principal  <br/> |Número único que identifica este teléfono.  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |Teléfono número.  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||Marca de tiempo (solo para uso interno).  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
   

