---
title: Tabla Users
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: En la tabla de usuarios es una tabla de apoyo. Cada registro en la tabla almacena información sobre un usuario que participó en las llamadas o las sesiones que tienen registros en la base de datos.
ms.openlocfilehash: 3929ba33737c107ee60ec1e31beebb1addbb2e3f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885564"
---
# <a name="users-table"></a>Tabla Users
 
En la tabla de usuarios es una tabla de apoyo. Cada registro en la tabla almacena información sobre un usuario que participó en las llamadas o las sesiones que tienen registros en la base de datos.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||Marca de tiempo para uso interno.  <br/> |
|**UserId** <br/> |int  <br/> |Primary  <br/> |Número único que identifica a este usuario.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> | <br/> |URI del usuario.  <br/> |
|**TenantId** <br/> |int  <br/> |Externa  <br/> |Identificador del inquilino. de este usuario Consulte la [tabla de los inquilinos](tenants.md) para obtener más información. <br/> |
|**UriTypeId** <br/> |int  <br/> |Externa  <br/> |Tipo de URI de este usuario. Consulte la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
   

