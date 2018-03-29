---
title: Tabla MonitoredRegionLink
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
description: La tabla MonitoredRegionLink es un auxiliar. Cada registro representa un vínculo entre dos países o regiones.
ms.openlocfilehash: 471291788dabee412bffef641624afad2a2c10b4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="monitoredregionlink-table"></a>Tabla MonitoredRegionLink
 
La tabla MonitoredRegionLink es un auxiliar. Cada registro representa un vínculo entre dos países o regiones.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |int  <br/> |Principal, externa  <br/> |Referencia de la [tabla de la región](region.md).  <br/> |
|**Region2Key** <br/> |int  <br/> |Principal, externa  <br/> |Referencia de la [tabla de la región](region.md).  <br/> |
   

