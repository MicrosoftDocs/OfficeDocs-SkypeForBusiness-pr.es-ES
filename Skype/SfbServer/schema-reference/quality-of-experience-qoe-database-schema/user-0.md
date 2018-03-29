---
title: Tabla User
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: La tabla de usuario es una tabla de soporte que almacena una lista de los distintos usuarios que han participado en las sesiones que se registran en la base de datos. Cada registro de la tabla representa un usuario.
ms.openlocfilehash: 3261133b8c36fe96fd847c075dce0be2a903c417
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="user-table"></a>Tabla User
 
La tabla de usuario es una tabla de soporte que almacena una lista de los distintos usuarios que han participado en las sesiones que se registran en la base de datos. Cada registro de la tabla representa un usuario.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**AutoCAD** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este usuario.  <br/> |
|**URI** <br/> |nvarchar(450)  <br/> |Único  <br/> |Cadena URI.  <br/> |
|**URIType** <br/> |int  <br/> ||1 es de tipo desconocido de URI.  <br/> 2 es el URI del usuario.  <br/> 4 es la conferencia URI.  <br/> 8 es el URI del teléfono.  <br/> |
|**TenantKey** <br/> |int  <br/> |Externa  <br/> |Inquilinos del usuario, se hace referenciado en la tabla de inquilinos.  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||Marca de hora más reciente cuando el usuario tenía una llamada de audio deficiente.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Sólo para uso interno.  <br/> |
   

