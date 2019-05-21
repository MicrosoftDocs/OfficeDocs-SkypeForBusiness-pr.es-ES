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
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: La tabla de diálogo es una tabla de soporte técnico; cada registro representa un cuadro de diálogo protocolo de inicio de sesión (SIP).
ms.openlocfilehash: e6bbaa3c40ebf53c5fd9fc410acca7779128bf39
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294960"
---
# <a name="dialog-table"></a>Tabla Dialog
 
La tabla de diálogo es una tabla de soporte técnico; cada registro representa un cuadro de diálogo protocolo de inicio de sesión (SIP).
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |Hora en que el agente de calidad de excelencia (QoE) recibe el primer informe de quien llama o de quien llama. Se usa en conjunción con SessionSeq para identificar de forma única una sesión.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |Número de secuencia para diferenciar las sesiones cuando tienen el mismo ConferenceDateTime.  <br/> |
|**DialogID** <br/> |VARCHAR (256)  <br/> ||IDENTIFICADOR de cuadro de diálogo único de forma global.  <br/> |
|**DialogIDChecksum** <br/> |int  <br/> |clasificación  <br/> |Suma de comprobación del identificador de cuadro de diálogo.  <br/> |
   

