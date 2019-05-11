---
title: Tabla Dialog
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: La tabla diálogo es una tabla de apoyo; cada registro representa un cuadro de diálogo de protocolo de inicio de sesión (SIP).
ms.openlocfilehash: 36ab76d147673ca85371ca4cdfb151fa953e29b2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920092"
---
# <a name="dialog-table"></a>Tabla Dialog
 
La tabla diálogo es una tabla de apoyo; cada registro representa un cuadro de diálogo de protocolo de inicio de sesión (SIP).
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Hora cuando el agente de calidad de excelencia (QoE) recibe el primer informe de autor de la llamada o destinatario de la llamada. Se utiliza junto con SessionSeq para identificar de forma exclusiva una sesión.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Número de secuencia para diferenciar sesiones cuando tienen el mismo ConferenceDateTime.  <br/> |
|**DialogID** <br/> |varchar (256)  <br/> ||Identificador del cuadro de diálogo que es globalmente único.  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |índice  <br/> |Suma de comprobación del identificador del cuadro de diálogo.  <br/> |
   

