---
title: Tabla Inquilinos
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
ms.openlocfilehash: 905e8f3be57601f65d3cb5f6bebff7b4af9ef89dc744a53798f6a6932d269558
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281673"
---
# <a name="tenants-table"></a>Tabla Inquilinos
 
La tabla Inquilinos es una tabla auxiliar que almacena una lista de los diversos inquilinos. Cada registro de la tabla representa a un inquilino.
  
> [!NOTE]
> En una instalación local, el CDR usa el identificador de inquilino integrado para indicar distintos tipos de autenticación, como la de conectividad de mensajería instantánea pública, federada y anónima. 
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**TenantId** <br/> |Entero  <br/> |Principal  <br/> |Número único que identifica este identificador de inquilino.  <br/> |
|**TenantKey** <br/> |nvarchar(256)  <br/> || Valores permitidos: <br/>  00000000-0000-0000-0000-00000000000000000000 - Enterprise <br/>  00000000-0000-0000-0000-000000000001 - Federado <br/>  00000000-0000-0000-0000-000000000002 - Anónimo <br/>  00000000-0000-0000-0000-00000000003: conectividad de mensajería instantánea pública <br/> |
   

