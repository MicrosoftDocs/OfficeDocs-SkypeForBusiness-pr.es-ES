---
title: Obtener integración de registro
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Resumen: Obtenga información sobre la operación obtener registro de integración, que forma parte de la API de datos para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 58be983ff3b282c94a4b42619a6c37c6270afcb5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274761"
---
# <a name="get-integration-log"></a>Obtener integración de registro
 
**Resumen:** Obtenga más información sobre la operación obtener registro de integración, que forma parte de la API de datos para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.
  
La operación obtener registro de integración es parte de la API de datos para el panel de calidad de llamadas
  
## <a name="get-integration-log"></a>Obtener integración de registro

La operación obtener registro de integración devuelve una lista de entradas de registro que describen las actividades en el procesamiento del cubo QoE.
  
Esta operación está deshabilitada de forma predeterminada por razones de seguridad. Cuando se deshabilita, devuelve una cadena vacía. Para habilitar esta operación, los administradores deben configurar el archivo Web. config para la aplicación Web de host de la API de datos.
  

|Método|**Solicitar URI**|**Versión HTTP**|
|:-----|:-----|:-----|
|Obtener  <br/> |https://\<portal\>/QoEDataService/IntegrationLog  <br/> |HTTP/1.1  <br/> |
   
 **Parámetros de URI** : ninguno.
  
 **Solicitar encabezados** : no hay encabezados adicionales.
  
 **Solicitar cuerpo** : ninguno.
  
 **Respuesta** : la respuesta incluye un código de estado http y un conjunto de encabezados de respuesta.
  
 **Código de estado** : una operación correcta devuelve el código de estado 200 (correcto).
  
 **Encabezados de respuesta** : no hay encabezados adicionales.
  
 **Cuerpo de respuesta** : a continuación se muestra una estructura de ejemplo de entradas de registro.
  
```
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


