---
title: Tabla Users
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: La tabla de usuarios es una tabla de soporte. Cada registro de la tabla almacena información sobre un usuario implicado en llamadas o sesiones que tengan registros en la base de datos.
ms.openlocfilehash: b14350d060485a57b4af42cbfe26db729872f6f8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="users-table"></a>Tabla Users
 
La tabla de usuarios es una tabla de soporte. Cada registro de la tabla almacena información sobre un usuario implicado en llamadas o sesiones que tengan registros en la base de datos.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||Marca de tiempo para uso interno.  <br/> |
|**ID de usuario** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este usuario.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> | <br/> |URI del usuario.  <br/> |
|**TenantId** <br/> |int  <br/> |Externa  <br/> |Id. de inquilinos de este usuario Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**UriTypeId** <br/> |int  <br/> |Externa  <br/> |Este tipo de usuario URI. Consulte la [tabla de UriTypes](uritypes.md) para obtener más información. <br/> |
   

