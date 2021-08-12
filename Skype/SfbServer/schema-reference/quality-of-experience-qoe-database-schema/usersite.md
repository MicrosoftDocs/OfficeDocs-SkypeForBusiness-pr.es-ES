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
description: La tabla UserSite es una tabla de soporte técnico. Cada registro representa un sitio de usuario definido en la configuración de red.
ms.openlocfilehash: 01ab76218040d37176355d62768c6a8b8f4b7336d22ce7263c61ac9fc8c289ed
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54314336"
---
# <a name="usersite-table"></a>Tabla UserSite
 
La tabla UserSite es una tabla de soporte técnico. Cada registro representa un sitio de usuario definido en la configuración de red.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |Entero  <br/> |Principal  <br/> |Número único que identifica el sitio de usuario.  <br/> |
|**UserSiteName** <br/> |nvarchar(128)  <br/> |Única  <br/> |Nombre del sitio de usuario.  <br/> |
|**RegionKey** <br/> |Entero  <br/> |Externo  <br/> |Al que se hace referencia [desde la tabla Región](region.md).  <br/> |
   

