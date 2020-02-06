---
title: Tabla MonitoredRegionLink
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
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: La tabla MonitoredRegionLink es una tabla de soporte. Cada registro representa un vínculo entre dos países o regiones.
ms.openlocfilehash: a6b92460e2b097460681023f7d6877f02c046bdc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807818"
---
# <a name="monitoredregionlink-table"></a>Tabla MonitoredRegionLink
 
La tabla MonitoredRegionLink es una tabla de soporte. Cada registro representa un vínculo entre dos países o regiones.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |Principal, extranjero  <br/> |Se hace referencia a ella desde la [tabla region](region.md).  <br/> |
|**Region2Key** <br/> |int  <br/> |Principal, extranjero  <br/> |Se hace referencia a ella desde la [tabla region](region.md).  <br/> |
   

