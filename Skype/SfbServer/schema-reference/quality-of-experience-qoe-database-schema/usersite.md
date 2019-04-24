---
title: Tabla UserSite
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: En la tabla UserSite es una tabla de apoyo. Cada registro representa un sitio de usuario definido en la opción de configuración de red.
ms.openlocfilehash: a52f5cd9aa7059e2b545dec3bcc7ccb86191347a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212049"
---
# <a name="usersite-table"></a>Tabla UserSite
 
En la tabla UserSite es una tabla de apoyo. Cada registro representa un sitio de usuario definido en la opción de configuración de red.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica el sitio del usuario.  <br/> |
|**UserSiteName** <br/> |nvarchar (128)  <br/> |Único  <br/> |Nombre del sitio de usuario.  <br/> |
|**RegionKey** <br/> |int  <br/> |Externa  <br/> |Referencia de la [tabla de región](region.md).  <br/> |
   

