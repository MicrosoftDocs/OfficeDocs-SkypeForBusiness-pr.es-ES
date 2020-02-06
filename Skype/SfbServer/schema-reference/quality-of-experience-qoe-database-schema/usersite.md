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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: La tabla UserSite es una tabla de soporte. Cada registro representa un sitio de usuario definido en la configuración de red.
ms.openlocfilehash: e1d6c4ddc3a756f2e5df0713d6abe1cb7b61295f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805008"
---
# <a name="usersite-table"></a>Tabla UserSite
 
La tabla UserSite es una tabla de soporte. Cada registro representa un sitio de usuario definido en la configuración de red.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica el sitio del usuario.  <br/> |
|**UserSiteName** <br/> |nvarchar(128  <br/> |Solo  <br/> |Nombre del sitio del usuario.  <br/> |
|**RegionKey** <br/> |int  <br/> |Extranjero  <br/> |[Tabla de regiones](region.md)a la que se hace referencia.  <br/> |
   

