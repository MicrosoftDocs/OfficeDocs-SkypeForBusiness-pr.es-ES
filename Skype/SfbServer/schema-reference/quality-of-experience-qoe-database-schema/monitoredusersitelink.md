---
title: Tabla MonitoredUserSiteLink
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: En la tabla MonitoredUserSiteLink es una tabla de apoyo. Cada registro representa un vínculo entre dos sitios de usuario.
ms.openlocfilehash: 18f0931feb46e69db76c93225ccc11398b4d6daf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920015"
---
# <a name="monitoredusersitelink-table"></a>Tabla MonitoredUserSiteLink
 
En la tabla MonitoredUserSiteLink es una tabla de apoyo. Cada registro representa un vínculo entre dos sitios de usuario.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Principal, externa  <br/> |Referencia de la [tabla UserSite](usersite.md).  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Principal, externa  <br/> |Referencia de la [tabla UserSite](usersite.md).  <br/> |
   

