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
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: La tabla Teléfonos es una tabla de apoyo. Cada registro de la tabla almacena información sobre un número de teléfono implicado en las llamadas VoIP que tienen registros en la base de datos.
ms.openlocfilehash: 12825423b9a03bff93e0d70705a4083bb8c881c9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823270"
---
# <a name="phones-table"></a>Tabla Teléfonos
 
La tabla Teléfonos es una tabla de apoyo. Cada registro de la tabla almacena información sobre un número de teléfono implicado en las llamadas VoIP que tienen registros en la base de datos.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**PhoneId** <br/> |entero  <br/> |Principal  <br/> |Número único que identifica este teléfono.  <br/> |
|**PhoneUri** <br/> |nvarchar(450)  <br/> | <br/> |Número de teléfono.  <br/> |
|**NextUpdateTS** <br/> |dateTime  <br/> ||Marca de tiempo (solo para uso interno).  <br/> Este campo se introdujo en Microsoft Lync Server 2013.  <br/> |
   

