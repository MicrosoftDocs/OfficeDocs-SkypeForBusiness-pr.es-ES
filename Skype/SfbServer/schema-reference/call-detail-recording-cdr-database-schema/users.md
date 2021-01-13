---
title: Tabla Users
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
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: La tabla Usuarios es una tabla de apoyo. Cada registro de la tabla almacena información sobre un usuario que participa en llamadas o sesiones que tienen registros en la base de datos.
ms.openlocfilehash: 1905efa9b87b0b94c55e3a72e8be86e9ab191661
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831620"
---
# <a name="users-table"></a>Tabla Users
 
La tabla Usuarios es una tabla de apoyo. Cada registro de la tabla almacena información sobre un usuario que participa en llamadas o sesiones que tienen registros en la base de datos.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||Marca de tiempo para uso interno.  <br/> |
|**UserId** <br/> |entero  <br/> |Principal  <br/> |Número único que identifica a este usuario.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> | <br/> |URI del usuario.  <br/> |
|**TenantId** <br/> |entero  <br/> |Externo  <br/> |El id. de inquilino de este usuario. Vea la [tabla Inquilinos](tenants.md) para obtener más información. <br/> |
|**UriTypeId** <br/> |entero  <br/> |Externo  <br/> |El tipo de URI de este usuario. Vea la [tabla UriTypes](uritypes.md) para obtener más información. <br/> |
   

