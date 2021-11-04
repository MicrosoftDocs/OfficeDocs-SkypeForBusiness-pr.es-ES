---
title: Tabla AppliedBandwidthSource
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
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: La tabla AppliedBandwidthSource es una tabla auxiliar. Cada registro representa un origen.
ms.openlocfilehash: 772afa1ffe6ce34dc38676193825c0f2891d7bea
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60761838"
---
# <a name="appliedbandwidthsource-table"></a>Tabla AppliedBandwidthSource
 
La tabla AppliedBandwidthSource es una tabla auxiliar. Cada registro representa un origen.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |Entero  <br/> |Principal  <br/> |Número único que identifica el origen.  <br/> |
|**AppliedBandwidthSource** <br/> |varchar(256)  <br/> |Única  <br/> |Origen del límite de ancho de banda impuesto. Describe de dónde viene el límite de ancho de banda (por ejemplo, "Policy Server", "TURN Server" o "Modality").  <br/> |
   

