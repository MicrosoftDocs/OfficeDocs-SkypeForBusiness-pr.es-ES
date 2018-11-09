---
title: Obtener Log integración
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Resumen: Obtenga información acerca de la operación obtener Log de integración, que es parte de la API de datos para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: 6408d0a773ee00854f82c4430e4402e79db23fa6
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035564"
---
# <a name="get-integration-log"></a>Obtener Log integración
 
**Resumen:** Obtenga información acerca de la operación obtener Log de integración, que es parte de la API de datos para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.
  
La operación de obtener el registro de integración es parte de la API de datos para el panel de calidad de llamadas
  
## <a name="get-integration-log"></a>Obtener Log integración

Obtenga la operación devuelve una lista de entradas de registro que describe las actividades en el cubo de QoE de procesamiento de registro de integración.
  
Esta operación está deshabilitada de forma predeterminada por motivos de seguridad. Cuando deshabilitado, devuelve una cadena vacía. Para habilitar esta operación, los administradores deben configurar el archivo web.config para la aplicación web de host de la API de datos.
  

|(Método)|**URI de la solicitud**|**Versión de HTTP**|
|:-----|:-----|:-----|
|Obtener  <br/> |https://\<portal\>/QoEDataService/IntegrationLog  <br/> |HTTP/1.1  <br/> |
   
 **Los parámetros URI** - ninguno.
  
 **Encabezados de solicitud** - sin encabezados adicionales.
  
 **Cuerpo de la convocatoria** - ninguno.
  
 **Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado** - una operación correcta devuelve código de estado 200 (Aceptar).
  
 **Encabezados de respuesta** - sin encabezados adicionales.
  
 **Cuerpo de la respuesta** - a continuación es un ejemplo de estructura de entradas de registro.
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


