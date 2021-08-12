---
title: Tabla SIPResponseMetaData
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable contiene una lista de los códigos de respuesta SIP y la clasificación y definición de cada uno de estos códigos. Estos códigos se generan como respuesta a los eventos que afectan a los dispositivos SIP y a las sesiones de comunicación SIP; por ejemplo, se genera el código de respuesta 403 cuando un dispositivo SIP realiza una solicitud, pero el servidor rechaza responderla.
ms.openlocfilehash: 6e4c891aefb41b88fdaae1e9d80a25f878042d14e06c94fe510414f6a24ac1a0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54284500"
---
# <a name="sipresponsemetadata-table"></a>Tabla SIPResponseMetaData
 
SIPResponseMetaDataTable contiene una lista de los códigos de respuesta SIP y la clasificación y definición de cada uno de estos códigos. Estos códigos se generan como respuesta a los eventos que afectan a los dispositivos SIP y a las sesiones de comunicación SIP; por ejemplo, se genera el código de respuesta 403 cuando un dispositivo SIP realiza una solicitud, pero el servidor rechaza responderla.
  
Esta tabla se introdujo en Skype Empresarial Server 2015.
  
|**Columna**|**Tipo de datos**|**Clave/índice**|**Detalles**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |Entero  <br/> |Principal  <br/> |Valor numérico que representa el código de respuesta SIP.  <br/> |
|**Class** <br/> |Entero  <br/> || Clasificación general para el código de respuesta. Las clasificaciones incluyen: <br/>  1- Respuestas informativos <br/>  2: Respuestas correctas <br/>  3: respuestas de redirección <br/>  4: Respuestas de error de cliente <br/>  5: Respuestas de error del servidor <br/>  6: Respuesta global a errores <br/> |
|**Description** <br/> |nvarchar(256)  <br/> ||Descripción del código de respuesta SIP. Por ejemplo, el código de respuesta 181 tiene la siguiente descripción:  <br/> Se está desviando la llamada  <br/> |
   

