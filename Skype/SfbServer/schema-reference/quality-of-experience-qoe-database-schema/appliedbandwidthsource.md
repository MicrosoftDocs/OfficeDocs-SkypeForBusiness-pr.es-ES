---
title: Tabla AppliedBandwidthSource
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
ms.assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
description: La tabla AppliedBandwidthSource es una tabla auxiliar. Cada registro representa un origen.
ms.openlocfilehash: bf7e1be3b98bcd56fea16dbd7aa7171b056a7f3c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831410"
---
# <a name="appliedbandwidthsource-table"></a>Tabla AppliedBandwidthSource
 
La tabla AppliedBandwidthSource es una tabla auxiliar. Cada registro representa un origen.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**AppliedBandwidthSourceKey** <br/> |entero  <br/> |Principal  <br/> |Número único que identifica el origen.  <br/> |
|**AppliedBandwidthSource** <br/> |varchar(256)  <br/> |Única  <br/> |Origen del límite de ancho de banda impuesto. Describe de dónde viene el límite de ancho de banda (por ejemplo, "Servidor de directivas", "Servidor TURN" o "Modalidad").  <br/> |
   

