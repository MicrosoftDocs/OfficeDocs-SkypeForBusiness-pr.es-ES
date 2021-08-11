---
title: Tabla MonitoredRegionLink
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
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: La tabla MonitoredRegionLink es una tabla auxiliar. Cada registro representa un vínculo entre dos países o regiones.
ms.openlocfilehash: 991cc3b6ce2f442ad13c350d2e37cc7c9d592d40d16da51932975a4907040569
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54321632"
---
# <a name="monitoredregionlink-table"></a>Tabla MonitoredRegionLink
 
La tabla MonitoredRegionLink es una tabla auxiliar. Cada registro representa un vínculo entre dos países o regiones.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |Entero  <br/> |Principal, Externa  <br/> |Se hace referencia desde la [tabla Region](region.md).  <br/> |
|**Region2Key** <br/> |Entero  <br/> |Principal, Externa  <br/> |Se hace referencia desde la [tabla Region](region.md).  <br/> |
   

