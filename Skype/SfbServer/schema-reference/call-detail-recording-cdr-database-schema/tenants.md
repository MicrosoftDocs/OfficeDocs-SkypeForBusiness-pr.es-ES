---
title: Tabla Tenants
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
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: La tabla Inquilinos es una tabla auxiliar que almacena una lista de los diversos inquilinos. Cada registro de la tabla representa a un inquilino.
ms.openlocfilehash: f22837f21bd431c83848d3b055a36930c9db2fd5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831720"
---
# <a name="tenants-table"></a>Tabla Tenants
 
La tabla Inquilinos es una tabla auxiliar que almacena una lista de los diversos inquilinos. Cada registro de la tabla representa a un inquilino.
  
> [!NOTE]
> En una instalación local, el CDR usa el identificador de inquilino integrado para indicar distintos tipos de autenticación, como la de conectividad de mensajería instantánea pública, federada y anónima. 
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |entero  <br/> |Principal  <br/> |Número único que identifica este identificador de inquilino.  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  00000000-0000-0000-0000-000000000000 - Enterprise <br/>  00000000-0000-0000-0000-000000000001 - Federado <br/>  00000000-0000-0000-0000-000000000002 - Anónimo <br/>  00000000-0000-0000-0000-000000000003- Conectividad de mensajería instantánea pública <br/> |
   

