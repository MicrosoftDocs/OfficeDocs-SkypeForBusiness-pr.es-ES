---
title: Obtener Log integración
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Resumen: Conozca la operación obtener Log de integración, que forma parte de la API de datos para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 8ccd4fc299cbf5310a5974d55b181aa1f42255ce
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="get-integration-log"></a>Obtener Log integración
 
**Resumen:** Obtener información sobre la operación de obtener el Log de integración, que forma parte de la API de datos para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.
  
La operación Get Log integración forma parte de la API para llamar al panel de calidad de datos
  
## <a name="get-integration-log"></a>Obtener Log integración

Obtener Log integración operación devuelve una lista de entradas del registro que describe las actividades en el cubo de la calidad de procesamiento.
  
Esta operación está deshabilitada de forma predeterminada por motivos de seguridad. Cuando se deshabilita, devuelve una cadena vacía. Para habilitar esta operación, los administradores deben configurar el archivo web.config para la aplicación web de API de datos host.
  

|Método|**URI de la solicitud**|**Versión de HTTP**|
|:-----|:-----|:-----|
|Obtener  <br/> |https://\<portal\>/QoEDataService/IntegrationLog  <br/> |HTTP/1.1  <br/> |
   
 **URI parámetros** : ninguno.
  
 **Encabezados de solicitud** - sin encabezados adicionales.
  
 **Cuerpo de la solicitud** - ninguno.
  
 **Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado** - una operación correcta devuelve el código de estado 200 (OK).
  
 **Encabezados de respuesta** - sin encabezados adicionales.
  
 **Cuerpo de la respuesta** : a continuación es un ejemplo de estructura de entradas de registro.
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]

```


