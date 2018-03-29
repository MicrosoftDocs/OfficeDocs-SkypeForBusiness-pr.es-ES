---
title: Tabla UserSite
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: La tabla UserSite es un auxiliar. Cada registro representa un sitio de usuario definido en la configuración de red.
ms.openlocfilehash: effc2404a91bf122dc9be9ad371372e8355b230f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="usersite-table"></a>Tabla UserSite
 
La tabla UserSite es un auxiliar. Cada registro representa un sitio de usuario definido en la configuración de red.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UserSiteKey** <br/> |int  <br/> |Primary  <br/> |Número único que identifica el sitio del usuario.  <br/> |
|**UserSiteName** <br/> |nvarchar (128)  <br/> |Único  <br/> |Nombre del sitio del usuario.  <br/> |
|**RegionKey** <br/> |int  <br/> |Externa  <br/> |Referencia de [tabla de la región](region.md).  <br/> |
   

