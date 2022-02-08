---
title: Tabla Usuarios
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 66f3e1247d29969ecef36a5d6247510b5eae022c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389782"
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
   

