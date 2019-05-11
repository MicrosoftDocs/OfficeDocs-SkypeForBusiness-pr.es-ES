---
title: Tabla UserSite
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: En la tabla UserSite es una tabla de apoyo. Cada registro representa un sitio de usuario definido en la opción de configuración de red.
ms.openlocfilehash: 519cedc35c03fd9bcb5479ea3cecf75ec617917c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906956"
---
# <a name="usersite-table"></a>Tabla UserSite
 
En la tabla UserSite es una tabla de apoyo. Cada registro representa un sitio de usuario definido en la opción de configuración de red.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica el sitio del usuario.  <br/> |
|**UserSiteName** <br/> |nvarchar (128)  <br/> |Único  <br/> |Nombre del sitio de usuario.  <br/> |
|**RegionKey** <br/> |int  <br/> |Externa  <br/> |Referencia de la [tabla de región](region.md).  <br/> |
   

