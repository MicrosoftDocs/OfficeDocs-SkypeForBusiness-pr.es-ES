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
ms.openlocfilehash: f30ba249f89a2247e0e03c71fc97f05e69c59bcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806350"
---
# <a name="monitoredregionlink-table"></a>Tabla MonitoredRegionLink
 
La tabla MonitoredRegionLink es una tabla auxiliar. Cada registro representa un vínculo entre dos países o regiones.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**Region1Key** <br/> |entero  <br/> |Principal, Externa  <br/> |Referencia desde la [tabla Región](region.md).  <br/> |
|**Region2Key** <br/> |entero  <br/> |Principal, Externa  <br/> |Referencia desde la [tabla Región](region.md).  <br/> |
   

