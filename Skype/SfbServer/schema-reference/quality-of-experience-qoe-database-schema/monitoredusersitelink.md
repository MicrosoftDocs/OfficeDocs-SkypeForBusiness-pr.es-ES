---
title: Tabla MonitoredUserSiteLink
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: La tabla MonitoredUserSiteLink es un auxiliar. Cada registro representa un vínculo entre dos sitios de usuario.
ms.openlocfilehash: 7b9b2ddab3bff48105a24f586816666b15c0b9b6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="monitoredusersitelink-table"></a>Tabla MonitoredUserSiteLink
 
La tabla MonitoredUserSiteLink es un auxiliar. Cada registro representa un vínculo entre dos sitios de usuario.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Principal, externa  <br/> |Referencia de la [tabla UserSite](usersite.md).  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Principal, externa  <br/> |Referencia de la [tabla UserSite](usersite.md).  <br/> |
   

