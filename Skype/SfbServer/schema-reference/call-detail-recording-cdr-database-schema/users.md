---
title: Tabla Users
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: La tabla usuarios es una tabla de soporte técnico. Cada registro de la tabla almacena información acerca de un usuario implicado en llamadas o sesiones que tienen registros en la base de datos.
ms.openlocfilehash: 21d03dc2214ac74188094c10a7b53ec84b8a51a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814808"
---
# <a name="users-table"></a>Tabla Users
 
La tabla usuarios es una tabla de soporte técnico. Cada registro de la tabla almacena información acerca de un usuario implicado en llamadas o sesiones que tienen registros en la base de datos.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||Marca de tiempo para uso interno.  <br/> |
|**Iddeusuario** <br/> |int  <br/> |Primary  <br/> |Número único que identifica a este usuario.  <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> | <br/> |URI de usuario.  <br/> |
|**TenantId** <br/> |int  <br/> |Extranjero  <br/> |El identificador de inquilino de este usuario. Para obtener más información, consulte la [tabla de inquilinos](tenants.md) . <br/> |
|**UriTypeId** <br/> |int  <br/> |Extranjero  <br/> |Tipo de URI de este usuario. Para obtener más información, consulte la [tabla UriTypes](uritypes.md) . <br/> |
   

