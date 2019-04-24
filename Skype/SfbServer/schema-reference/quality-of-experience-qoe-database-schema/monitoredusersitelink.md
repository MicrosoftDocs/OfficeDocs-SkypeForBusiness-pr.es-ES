---
title: Tabla MonitoredUserSiteLink
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: En la tabla MonitoredUserSiteLink es una tabla de apoyo. Cada registro representa un vínculo entre dos sitios de usuario.
ms.openlocfilehash: 8022286289d4acd5fab8ea821c72897d9500597b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212526"
---
# <a name="monitoredusersitelink-table"></a>Tabla MonitoredUserSiteLink
 
En la tabla MonitoredUserSiteLink es una tabla de apoyo. Cada registro representa un vínculo entre dos sitios de usuario.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Principal, externa  <br/> |Referencia de la [tabla UserSite](usersite.md).  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Principal, externa  <br/> |Referencia de la [tabla UserSite](usersite.md).  <br/> |
   

