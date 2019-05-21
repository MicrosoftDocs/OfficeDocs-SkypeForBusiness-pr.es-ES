---
title: Tabla MonitoredUserSiteLink
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: La tabla MonitoredUserSiteLink es una tabla de soporte. Cada registro representa un vínculo entre dos sitios de usuario.
ms.openlocfilehash: 789c1a721e1a8c204ff6e214f419de77d1b7f7bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294855"
---
# <a name="monitoredusersitelink-table"></a>Tabla MonitoredUserSiteLink
 
La tabla MonitoredUserSiteLink es una tabla de soporte. Cada registro representa un vínculo entre dos sitios de usuario.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Principal, extranjero  <br/> |Se hace referencia a ella desde la [tabla UserSite](usersite.md).  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Principal, extranjero  <br/> |Referencia de la [tabla UserSite](usersite.md).  <br/> |
   

