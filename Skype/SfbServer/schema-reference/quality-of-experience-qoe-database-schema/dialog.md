---
title: Tabla de diálogo
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: La tabla Diálogo es una tabla de apoyo, en la que cada registro representa un cuadro de diálogo de protocolo de inicio de sesión (SIP).
ms.openlocfilehash: ab466a158ca059ff3110012a03e5c9c1e39b3d2d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851794"
---
# <a name="dialog-table"></a>Tabla de diálogo
 
La tabla Diálogo es una tabla de apoyo, en la que cada registro representa un cuadro de diálogo de protocolo de inicio de sesión (SIP).
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principal  <br/> |Momento en el que el agente de calidad de la experiencia (QoE) recibe el primer informe del autor o del destinatario de la llamada. Se usa junto con SessionSeq para identificar una sesión de forma exclusiva.  <br/> |
|**SessionSeq** <br/> |Entero  <br/> |Principal  <br/> |Número de secuencia que se usa para diferenciar sesiones cuando tienen el mismo ConferenceDateTime.  <br/> |
|**DialogID** <br/> |varchar(256)  <br/> ||Id. de diálogo, exclusivo a nivel global.  <br/> |
|**DialogIDChecksum** <br/> |Entero  <br/> |index  <br/> |Suma de comprobación del Id. de diálogo.  <br/> |
   

