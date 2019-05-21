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
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: La tabla usuarios es una tabla de soporte técnico. Cada registro de la tabla almacena información acerca de un usuario implicado en llamadas o sesiones que tienen registros en la base de datos.
ms.openlocfilehash: 0dcc2fda73305be2bbe6a7a5c546dac0b05f8273
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295702"
---
# <a name="users-table"></a>Tabla Users
 
La tabla usuarios es una tabla de soporte técnico. Cada registro de la tabla almacena información acerca de un usuario implicado en llamadas o sesiones que tienen registros en la base de datos.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||Marca de tiempo para uso interno.  <br/> |
|**Iddeusuario** <br/> |int  <br/> |Primary  <br/> |Número único que identifica a este usuario.  <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> | <br/> |URI de usuario.  <br/> |
|**TenantId** <br/> |int  <br/> |Extranjero  <br/> |El identificador de inquilino de este usuario. Para obtener más información, consulte la [tabla](tenants.md) de inquilinos. <br/> |
|**UriTypeId** <br/> |int  <br/> |Extranjero  <br/> |Tipo de URI de este usuario. Para obtener más información, consulte la [tabla UriTypes](uritypes.md) . <br/> |
   

