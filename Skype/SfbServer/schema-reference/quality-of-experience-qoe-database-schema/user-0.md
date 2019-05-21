---
title: Tabla User
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: La tabla de usuario es una tabla de soporte que almacena una lista de los distintos usuarios que participaron en sesiones registradas en la base de datos. Cada registro de la tabla representa un usuario.
ms.openlocfilehash: a9f72793d3b287406b1b3b7e1ad360e7f5abc598
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294617"
---
# <a name="user-table"></a>Tabla User
 
La tabla de usuario es una tabla de soporte que almacena una lista de los distintos usuarios que participaron en sesiones registradas en la base de datos. Cada registro de la tabla representa un usuario.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica a este usuario.  <br/> |
|**URL** <br/> |nvarchar (450)  <br/> |Solo  <br/> |Cadena URI.  <br/> |
|**URIType** <br/> |int  <br/> ||1 es un tipo de URI desconocido.  <br/> 2 es el URI del usuario.  <br/> 4 es el URI de la Conferencia.  <br/> 8 es el URI del teléfono.  <br/> |
|**TenantKey** <br/> |int  <br/> |Extranjero  <br/> |Espacio empresarial del usuario al que se hace referencia desde la tabla de inquilinos.  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||Última marca de tiempo cuando el usuario tenía una mala llamada de audio.  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||Solo para uso interno.  <br/> |
   

