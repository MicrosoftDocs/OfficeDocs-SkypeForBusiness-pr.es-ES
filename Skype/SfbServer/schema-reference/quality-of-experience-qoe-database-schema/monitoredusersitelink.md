---
title: Tabla MonitoredUserSiteLink
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
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: La tabla MonitoredUserSiteLink es una tabla auxiliar. Cada registro representa un vínculo entre dos sitios de usuario.
ms.openlocfilehash: 3cc8c11f049e98223c80756eb2dc83f1b9354ec7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768368"
---
# <a name="monitoredusersitelink-table"></a>Tabla MonitoredUserSiteLink
 
La tabla MonitoredUserSiteLink es una tabla auxiliar. Cada registro representa un vínculo entre dos sitios de usuario.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**UserSite1Key** <br/> |Entero  <br/> |Principal, Externa  <br/> |Se hace referencia desde la [tabla UserSite](usersite.md).  <br/> |
|**UserSite2Key** <br/> |Entero  <br/> |Principal, Externa  <br/> |Referencia de la [tabla UserSite](usersite.md).  <br/> |
   

