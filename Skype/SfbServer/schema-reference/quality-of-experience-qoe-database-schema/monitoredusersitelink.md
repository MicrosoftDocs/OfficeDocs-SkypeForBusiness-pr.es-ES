---
title: Tabla MonitoredUserSiteLink
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: La tabla MonitoredUserSiteLink es una tabla auxiliar. Cada registro representa un vínculo entre dos sitios de usuario.
ms.openlocfilehash: 7c9e924092b687abe6fefe579109e943fd7c71ca
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399534"
---
# <a name="monitoredusersitelink-table"></a>Tabla MonitoredUserSiteLink
 
La tabla MonitoredUserSiteLink es una tabla auxiliar. Cada registro representa un vínculo entre dos sitios de usuario.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |Entero  <br/> |Principal, Externa  <br/> |Se hace referencia desde la [tabla UserSite](usersite.md).  <br/> |
|**UserSite2Key** <br/> |Entero  <br/> |Principal, Externa  <br/> |Referencia de la [tabla UserSite](usersite.md).  <br/> |
   

