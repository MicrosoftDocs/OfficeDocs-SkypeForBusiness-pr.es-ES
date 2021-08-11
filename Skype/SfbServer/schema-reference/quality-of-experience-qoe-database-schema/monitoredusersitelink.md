---
title: Tabla MonitoredUserSiteLink
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
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: La tabla MonitoredUserSiteLink es una tabla auxiliar. Cada registro representa un vínculo entre dos sitios de usuario.
ms.openlocfilehash: 7c7edea00fdd680ece091d06aa7528fb0dc7fe25d5b5b4fa126c37c48b3ee81d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321612"
---
# <a name="monitoredusersitelink-table"></a>Tabla MonitoredUserSiteLink
 
La tabla MonitoredUserSiteLink es una tabla auxiliar. Cada registro representa un vínculo entre dos sitios de usuario.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |Entero  <br/> |Principal, Externa  <br/> |Se hace referencia desde la [tabla UserSite](usersite.md).  <br/> |
|**UserSite2Key** <br/> |Entero  <br/> |Principal, Externa  <br/> |Referencia de la [tabla UserSite](usersite.md).  <br/> |
   

