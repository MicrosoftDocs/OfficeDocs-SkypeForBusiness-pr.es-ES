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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: La tabla MonitoredUserSiteLink es una tabla de soporte. Cada registro representa un vínculo entre dos sitios de usuario.
ms.openlocfilehash: 2cf229947da143fb01b3009020cfa432a4b558a0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807798"
---
# <a name="monitoredusersitelink-table"></a>Tabla MonitoredUserSiteLink
 
La tabla MonitoredUserSiteLink es una tabla de soporte. Cada registro representa un vínculo entre dos sitios de usuario.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |int  <br/> |Principal, extranjero  <br/> |Se hace referencia a ella desde la [tabla UserSite](usersite.md).  <br/> |
|**UserSite2Key** <br/> |int  <br/> |Principal, extranjero  <br/> |Referencia de la [tabla UserSite](usersite.md).  <br/> |
   

