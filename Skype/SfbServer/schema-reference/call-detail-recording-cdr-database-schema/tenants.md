---
title: Tabla Tenants
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: La tabla de inquilinos es una tabla de soporte que almacena una lista de los distintos inquilinos. Cada registro de la tabla representa un inquilino.
ms.openlocfilehash: 58c8a2e36ed6d95da46523597b455d228a24586c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295772"
---
# <a name="tenants-table"></a>Tabla Tenants
 
La tabla de inquilinos es una tabla de soporte que almacena una lista de los distintos inquilinos. Cada registro de la tabla representa un inquilino.
  
> [!NOTE]
> En la implementación local, CDR usa el identificador de inquilino de la compilación para indicar un tipo de autenticación diferente, como la conectividad de mensajería instantánea pública, federada y anónima. 
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este ID de inquilino.  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  00000000-0000-0000-0000-000000000000-empresa <br/>  00000000-0000-0000-0000-000000000001-federado <br/>  00000000-0000-0000-0000-000000000002-anónimo <br/>  00000000-0000-0000-0000-000000000003-conectividad de mensajería instantánea pública <br/> |
   

