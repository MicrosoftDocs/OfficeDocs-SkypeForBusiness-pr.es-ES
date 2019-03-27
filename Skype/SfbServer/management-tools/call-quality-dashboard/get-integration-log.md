---
title: Obtener integración de registro
ms.reviewer: ''
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
ms.openlocfilehash: e6d449a8ea973132b404e821f6a5d5f156e6ddd6
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897256"
---
# <a name="get-integration-log"></a>Obtener integración de registro
 
**Resumen:** Obtenga información acerca de la operación obtener Log de integración, que es parte de la API de datos para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.
  
La operación de obtener el registro de integración es parte de la API de datos para el panel de calidad de llamadas
  
## <a name="get-integration-log"></a>Obtener integración de registro

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


