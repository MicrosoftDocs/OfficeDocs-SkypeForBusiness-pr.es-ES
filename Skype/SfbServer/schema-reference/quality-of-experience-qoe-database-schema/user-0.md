---
title: Tabla de usuario
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: La tabla User es una tabla de apoyo donde se almacena una lista de los distintos usuarios que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa un usuario.
ms.openlocfilehash: 87e6e24ea9bf1073411eeb8c930e8e6fb509ae115242b529331aa43a25d5ac11
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329335"
---
# <a name="user-table"></a>Tabla de usuario
 
La tabla User es una tabla de apoyo donde se almacena una lista de los distintos usuarios que han participado en sesiones registradas en la base de datos. Cada registro de la tabla representa un usuario.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |Entero  <br/> |Principal  <br/> |Número único que identifica a este usuario.  <br/> |
|**URI** <br/> |nvarchar(450)  <br/> |Única  <br/> |Cadena del URI.  <br/> |
|**URIType** <br/> |Entero  <br/> ||1 es un tipo de URI desconocido.  <br/> 2 es un URI de usuario.  <br/> 4 es un URI de conferencia.  <br/> 8 es un URI de teléfono.  <br/> |
|**TenantKey** <br/> |Entero  <br/> |Externo  <br/> |Inquilino del usuario, con referencia a la tabla Tenant.  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||Última marca de tiempo en la que el usuario tuvo una llamada de audio de mala calidad.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Únicamente para uso interno.  <br/> |
   

