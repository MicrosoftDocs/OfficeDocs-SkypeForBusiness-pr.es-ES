---
title: Tabla Usuarios
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: La tabla Usuarios es una tabla de soporte técnico. Cada registro de la tabla almacena información sobre un usuario implicado en llamadas o sesiones que tienen registros en la base de datos.
ms.openlocfilehash: 7f3fb7fc015da4f96ab458a4ad40ccd1b2addbee
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741916"
---
# <a name="users-table"></a>Tabla Usuarios
 
La tabla Usuarios es una tabla de soporte técnico. Cada registro de la tabla almacena información sobre un usuario implicado en llamadas o sesiones que tienen registros en la base de datos.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||Marca de tiempo para uso interno.  <br/> |
|**UserId** <br/> |Entero  <br/> |Principal  <br/> |Número único que identifica a este usuario.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> | <br/> |URI del usuario.  <br/> |
|**TenantId** <br/> |Entero  <br/> |Externo  <br/> |Identificador de inquilino de este usuario. Vea la [tabla Inquilinos](tenants.md) para obtener más información. <br/> |
|**UriTypeId** <br/> |Entero  <br/> |Externo  <br/> |Tipo de URI de este usuario. Vea la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
   

