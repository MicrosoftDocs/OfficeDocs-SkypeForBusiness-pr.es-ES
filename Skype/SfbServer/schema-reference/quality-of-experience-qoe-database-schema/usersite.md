---
title: Tabla UserSite
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: La tabla UserSite es una tabla de soporte. Cada registro representa un sitio de usuario definido en la configuración de red.
ms.openlocfilehash: 21f60afdb1690024f85dc74e11f856642413e6a8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294575"
---
# <a name="usersite-table"></a>Tabla UserSite
 
La tabla UserSite es una tabla de soporte. Cada registro representa un sitio de usuario definido en la configuración de red.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica el sitio del usuario.  <br/> |
|**UserSiteName** <br/> |nvarchar(128  <br/> |Solo  <br/> |Nombre del sitio del usuario.  <br/> |
|**RegionKey** <br/> |int  <br/> |Extranjero  <br/> |[Tabla de regiones](region.md)a la que se hace referencia.  <br/> |
   

