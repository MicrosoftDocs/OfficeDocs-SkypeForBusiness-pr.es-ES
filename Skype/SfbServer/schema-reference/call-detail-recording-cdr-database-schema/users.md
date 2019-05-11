---
title: Tabla Users
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: En la tabla de usuarios es una tabla de apoyo. Cada registro en la tabla almacena información sobre un usuario que participó en las llamadas o las sesiones que tienen registros en la base de datos.
ms.openlocfilehash: fbe3ff7d2570f78cdf3b3418629fb9fd6209d944
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929990"
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
   

