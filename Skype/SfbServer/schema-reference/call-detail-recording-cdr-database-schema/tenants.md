---
title: Tabla Tenants
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: La tabla de los inquilinos es una tabla de soporte que almacena una lista de los varios inquilinos. Cada registro de la tabla representa a un arrendatario.
ms.openlocfilehash: 4dde1baaf553c1a0d8a0efe65d72e8326cbb3bad
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="tenants-table"></a>Tabla Tenants
 
La tabla de los inquilinos es una tabla de soporte que almacena una lista de los varios inquilinos. Cada registro de la tabla representa a un arrendatario.
  
> [!NOTE]
> En la implementación local, CDR utiliza el identificador de inquilinos de compilación para indicar el tipo de autenticación diferentes, como la conectividad con IM pública, federados y anónimos. 
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |int  <br/> |Primary  <br/> |Número único que identifica este ID de inquilinos.  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  00000000-0000-0000-0000-000000000000-corporativo <br/>  00000000-0000-0000-0000-000000000001-federado <br/>  00000000-0000-0000-0000-000000000002 - anónimo <br/>  00000000-0000-0000-0000-000000000003-conectividad con IM pública <br/> |
   

