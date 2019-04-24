---
title: Tabla SIPResponseMetaData
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: El SIPResponseMetaDataTable contiene una lista de los códigos de respuesta SIP y la clasificación y la definición de cada uno de estos códigos. Estos códigos se generan en respuesta a eventos que ello afecte a los dispositivos SIP y SIP sesiones de comunicación; Por ejemplo, se genera el código de respuesta 403 cuando un dispositivo SIP realiza una solicitud, pero el servidor no acepta aceptar dicha solicitud.
ms.openlocfilehash: 7b60ffff90434c341fcf15fb75ddc93ac9f26201
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212799"
---
# <a name="sipresponsemetadata-table"></a>Tabla SIPResponseMetaData
 
El SIPResponseMetaDataTable contiene una lista de los códigos de respuesta SIP y la clasificación y la definición de cada uno de estos códigos. Estos códigos se generan en respuesta a eventos que ello afecte a los dispositivos SIP y SIP sesiones de comunicación; Por ejemplo, se genera el código de respuesta 403 cuando un dispositivo SIP realiza una solicitud, pero el servidor no acepta aceptar dicha solicitud.
  
En esta tabla se introdujo en Skype para Business Server 2015.
  
|**Columna**|**Tipo de datos**|**Clave o índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |Primary  <br/> |Valor numérico que representa el código de respuesta SIP.  <br/> |
|**Clase** <br/> |int  <br/> || Criterios generales de clasificación para el código de respuesta. Clasificaciones de incluyen: <br/>  1 - respuestas de tipo informativo <br/>  2 - respuestas correctas <br/>  3 - las respuestas de redirección <br/>  4 - respuestas de error cliente <br/>  5--Respuestas de error de servidor <br/>  6 - respuesta de error global <br/> |
|**Descripción** <br/> |nvarchar(256)  <br/> ||Descripción del código de respuesta SIP. Por ejemplo, el código de respuesta 181 tiene la siguiente descripción:  <br/> Se está desviando la llamada  <br/> |
   

