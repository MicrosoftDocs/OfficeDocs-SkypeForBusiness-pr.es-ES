---
title: Tabla UserSite
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.openlocfilehash: d8e7ccea49d00355a3e114833518cf5e6f762674
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60737486"
---
# <a name="usersite-table"></a>Tabla UserSite
 
La tabla UserSite es una tabla de soporte técnico. Cada registro representa un sitio de usuario definido en la configuración de red.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |Entero  <br/> |Principal  <br/> |Número único que identifica el sitio de usuario.  <br/> |
|**UserSiteName** <br/> |nvarchar(128)  <br/> |Única  <br/> |Nombre del sitio de usuario.  <br/> |
|**RegionKey** <br/> |Entero  <br/> |Externo  <br/> |Al que se hace referencia [desde la tabla Región](region.md).  <br/> |
   

