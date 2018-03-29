---
title: Tabla Dialog
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: El cuadro de diálogo es una tabla de soporte; cada registro representa un cuadro de diálogo Protocolo de inicio de sesión (SIP).
ms.openlocfilehash: 0380f9c7c48ff7d3b26b9ea5442fb5ac2155f785
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="dialog-table"></a>Tabla Dialog
 
El cuadro de diálogo es una tabla de soporte; cada registro representa un cuadro de diálogo Protocolo de inicio de sesión (SIP).
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Tiempo cuando el agente de excelencia de la calidad (QoE) recibe el primer informe de llamador o destinatario. Se utiliza junto con SessionSeq para identificar una sesión.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Número de secuencia para diferenciar las sesiones cuando tienen el mismo ConferenceDateTime.  <br/> |
|**DialogID** <br/> |varchar (256)  <br/> ||Id. de cuadro de diálogo que es globalmente único.  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |índice  <br/> |Suma de comprobación de la Id.  <br/> |
   

