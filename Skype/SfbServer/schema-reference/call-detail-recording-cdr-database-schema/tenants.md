---
title: Tabla Tenants
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: En la tabla de inquilinos es una tabla de apoyo que almacena una lista de los inquilinos distintos. Cada registro de la tabla representa a un inquilino.
ms.openlocfilehash: cf7d0271c9cacfd76079a80a7e5db63d669a8dfb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873993"
---
# <a name="tenants-table"></a>Tabla Tenants
 
En la tabla de inquilinos es una tabla de apoyo que almacena una lista de los inquilinos distintos. Cada registro de la tabla representa a un inquilino.
  
> [!NOTE]
> En la implementación local, CDR usa el identificador de inquilino de compilación para indicar distintos tipos de autenticación, como la conectividad de mensajería instantánea pública, federada y anónima. 
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este identificador de inquilino.  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  00000000-0000-0000-0000-000000000000-Enterprise <br/>  00000000-0000-0000-0000-000000000001-federado <br/>  00000000-0000-0000-0000-000000000002 - anónimo <br/>  00000000-0000-0000-0000-000000000003-conectividad de mensajería instantánea pública <br/> |
   

