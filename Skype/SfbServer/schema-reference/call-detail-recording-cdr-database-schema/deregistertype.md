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
ms.localizationpriority: medium
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: La tabla DeRegisterType es una tabla estática que almacena la lista de posibles tipos de desregladores de usuarios, como "cliente iniciado", "el registro expiró" o "el cliente dejó de responder".
ms.openlocfilehash: 93d06117974377b6df489f376aedf4ad88235fa2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599885"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Tabla DeRegisterType en Skype Empresarial Server 2015
 
La tabla DeRegisterType es una tabla estática que almacena la lista de posibles tipos de desregladores de usuarios, como "cliente iniciado", "el registro expiró" o "el cliente dejó de responder".
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Principal  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  0 -- Desconocido <br/>  1 -- Anulación del registro iniciada por el cliente <br/>  2 -- Registro expirado <br/>  3: Cliente que se ha estrellado <br/>  4 -- Atributos de usuario modificados <br/>  5: Registrador preferido cambiado <br/>  6 -- Cliente heredado en modo de supervivencia <br/> |
   

