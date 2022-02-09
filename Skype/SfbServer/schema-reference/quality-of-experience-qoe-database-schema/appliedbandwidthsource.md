---
title: Tabla AppliedBandwidthSource
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
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: La tabla AppliedBandwidthSource es una tabla auxiliar. Cada registro representa un origen.
ms.openlocfilehash: c886c5179d40063c1325bea3167e06ae7fe37666
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62411513"
---
# <a name="appliedbandwidthsource-table"></a>Tabla AppliedBandwidthSource
 
La tabla AppliedBandwidthSource es una tabla auxiliar. Cada registro representa un origen.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |Entero  <br/> |Principal  <br/> |Número único que identifica el origen.  <br/> |
|**AppliedBandwidthSource** <br/> |varchar(256)  <br/> |Única  <br/> |Origen del límite de ancho de banda impuesto. Describe de dónde viene el límite de ancho de banda (por ejemplo, "Policy Server", "TURN Server" o "Modality").  <br/> |
   

