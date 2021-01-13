---
title: Tabla DeRegisterType en Skype Empresarial Server 2015
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
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: La tabla DeRegisterType es una tabla estática que almacena la lista de posibles tipos de anulación de registros de usuario, como "iniciado por el cliente", "el registro expiró" o "el cliente dejó de responder".
ms.openlocfilehash: 388aebc1ac180e1298addd54859cff6759b28be0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816080"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Tabla DeRegisterType en Skype Empresarial Server 2015
 
La tabla DeRegisterType es una tabla estática que almacena la lista de posibles tipos de anulación de registros de usuario, como "iniciado por el cliente", "el registro expiró" o "el cliente dejó de responder".
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Principal  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0 -- Desconocido <br/>  1 -- Anulación del registro iniciada por el cliente <br/>  2 -- Registro expirado <br/>  3- Cliente con bloqueo <br/>  4 -- Atributos de usuario modificados <br/>  5- Registrador preferido cambiado <br/>  6 -- Cliente heredado en modo de supervivencia <br/> |
   

