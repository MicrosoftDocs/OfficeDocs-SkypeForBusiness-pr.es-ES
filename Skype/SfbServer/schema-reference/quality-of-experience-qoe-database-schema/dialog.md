---
title: Tabla Dialog
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
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: La tabla de diálogo es una tabla de soporte técnico; cada registro representa un cuadro de diálogo protocolo de inicio de sesión (SIP).
ms.openlocfilehash: 85d4a9f16a88db386565c065161eedeb61fba913
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809538"
---
# <a name="dialog-table"></a>Tabla Dialog
 
La tabla de diálogo es una tabla de soporte técnico; cada registro representa un cuadro de diálogo protocolo de inicio de sesión (SIP).
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Hora en que el agente de calidad de excelencia (QoE) recibe el primer informe de quien llama o de quien llama. Se usa en conjunción con SessionSeq para identificar de forma única una sesión.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Número de secuencia para diferenciar las sesiones cuando tienen el mismo ConferenceDateTime.  <br/> |
|**DialogID** <br/> |VARCHAR (256)  <br/> ||IDENTIFICADOR de cuadro de diálogo único de forma global.  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |clasificación  <br/> |Suma de comprobación del identificador de cuadro de diálogo.  <br/> |
   

