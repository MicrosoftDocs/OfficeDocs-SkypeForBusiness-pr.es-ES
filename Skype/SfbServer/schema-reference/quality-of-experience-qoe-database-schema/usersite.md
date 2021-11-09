---
title: Tabla UserSite
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: La tabla UserSite es una tabla de soporte técnico. Cada registro representa un sitio de usuario definido en la configuración de red.
ms.openlocfilehash: 80286b04e408a8f80e63364e3c7a822ce8e63505
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851774"
---
# <a name="usersite-table"></a>Tabla UserSite
 
La tabla UserSite es una tabla de soporte técnico. Cada registro representa un sitio de usuario definido en la configuración de red.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |Entero  <br/> |Principal  <br/> |Número único que identifica el sitio de usuario.  <br/> |
|**UserSiteName** <br/> |nvarchar(128)  <br/> |Única  <br/> |Nombre del sitio de usuario.  <br/> |
|**RegionKey** <br/> |Entero  <br/> |Externo  <br/> |Al que se hace referencia [desde la tabla Región](region.md).  <br/> |
   

