---
title: Tabla User
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: En la tabla de usuario es una tabla de apoyo que almacena una lista de los distintos usuarios que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa un usuario.
ms.openlocfilehash: 426d272a5c8bee2fd37511edc62bcb3e1a0c533e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907041"
---
# <a name="user-table"></a>Tabla User
 
En la tabla de usuario es una tabla de apoyo que almacena una lista de los distintos usuarios que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa un usuario.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica a este usuario.  <br/> |
|**URI** <br/> |nvarchar(450)  <br/> |Único  <br/> |Cadena URI.  <br/> |
|**URIType** <br/> |int  <br/> ||1 es el tipo de URI desconocido.  <br/> 2 es el URI del usuario.  <br/> 4 es el URI de conferencia.  <br/> 8 es el URI del teléfono.  <br/> |
|**TenantKey** <br/> |int  <br/> |Externa  <br/> |Inquilino del usuario, de inquilino table.  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||Marca de tiempo más reciente cuando el usuario tuvo una llamada de audio deficiente.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Sólo para uso interno.  <br/> |
   

