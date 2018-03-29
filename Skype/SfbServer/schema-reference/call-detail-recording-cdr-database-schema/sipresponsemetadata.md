---
title: Tabla SIPResponseMetaData
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: El SIPResponseMetaDataTable contiene una lista de códigos de respuesta SIP y la clasificación y la definición de cada uno de dichos códigos. Estos códigos se generan en respuesta a los eventos que afectan a los dispositivos SIP y SIP sesiones de comunicación; Por ejemplo, el código de respuesta 403 se genera cuando un dispositivo SIP realiza una solicitud, pero el servidor rechaza atender esa solicitud.
ms.openlocfilehash: a90a248837dd705746fe3b342874aad10480e8a6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="sipresponsemetadata-table"></a>Tabla SIPResponseMetaData
 
El SIPResponseMetaDataTable contiene una lista de códigos de respuesta SIP y la clasificación y la definición de cada uno de dichos códigos. Estos códigos se generan en respuesta a los eventos que afectan a los dispositivos SIP y SIP sesiones de comunicación; Por ejemplo, el código de respuesta 403 se genera cuando un dispositivo SIP realiza una solicitud, pero el servidor rechaza atender esa solicitud.
  
Esta tabla se introdujo en Skype para Business Server 2015.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |Primary  <br/> |Valor numérico que representa el código de respuesta SIP.  <br/> |
|**Clase** <br/> |int  <br/> || Criterios generales de clasificación para el código de respuesta. Las clasificaciones son: <br/>  1 - respuestas informativas <br/>  2 - correcta respuestas <br/>  3 - las respuestas de redirección <br/>  4 - respuestas de error cliente <br/>  5--Respuestas de error de servidor <br/>  6 - respuesta de error global <br/> |
|**Descripción** <br/> |nvarchar(256)  <br/> ||Descripción del código de respuesta SIP. Por ejemplo, el código de respuesta 181 tiene la siguiente descripción:  <br/> Llamada se está reenviando  <br/> |
   

