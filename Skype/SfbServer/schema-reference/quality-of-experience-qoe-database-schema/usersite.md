---
title: Tabla UserSite
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
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: La tabla UserSite es una tabla compatible. Cada registro representa un sitio de usuario definido en la configuración de red.
ms.openlocfilehash: 88df08875ea3254ee355a96aa3b12d3ee7f5ccaf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799920"
---
# <a name="usersite-table"></a>Tabla UserSite
 
La tabla UserSite es una tabla compatible. Cada registro representa un sitio de usuario definido en la configuración de red.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |entero  <br/> |Principal  <br/> |Número único que identifica el sitio de usuario.  <br/> |
|**UserSiteName** <br/> |nvarchar(128)  <br/> |Única  <br/> |Nombre del sitio de usuario.  <br/> |
|**RegionKey** <br/> |entero  <br/> |Externo  <br/> |Referencia de la [tabla Región](region.md).  <br/> |
   

