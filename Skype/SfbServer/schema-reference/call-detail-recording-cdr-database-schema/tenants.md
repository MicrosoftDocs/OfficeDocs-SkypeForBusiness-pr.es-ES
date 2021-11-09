---
title: Tabla Inquilinos
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c1b070c1-2c59-4ca9-910b-43f673f97fda
description: La tabla Inquilinos es una tabla auxiliar que almacena una lista de los diversos inquilinos. Cada registro de la tabla representa a un inquilino.
ms.openlocfilehash: 37387fe3bbb4bae7b09a0898ee65373f5342c488
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863337"
---
# <a name="tenants-table"></a>Tabla Inquilinos
 
La tabla Inquilinos es una tabla auxiliar que almacena una lista de los diversos inquilinos. Cada registro de la tabla representa a un inquilino.
  
> [!NOTE]
> En una instalación local, el CDR usa el identificador de inquilino integrado para indicar distintos tipos de autenticación, como la de conectividad de mensajería instantánea pública, federada y anónima. 
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |Entero  <br/> |Principal  <br/> |Número único que identifica este identificador de inquilino.  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  00000000-0000-0000-0000-00000000000000000000 - Enterprise <br/>  00000000-0000-0000-0000-000000000001 - Federado <br/>  00000000-0000-0000-0000-000000000002 - Anónimo <br/>  00000000-0000-0000-0000-00000000003: conectividad de mensajería instantánea pública <br/> |
   

