---
title: Obtener integración de registro
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8856f6bc-5460-4f35-acf2-f7662f01579b
description: 'Resumen: obtenga información sobre la operación Obtener registro de integración, que forma parte de la API de datos para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: 69827fa9f3fd3f56843a41867b029a071799ba66
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832600"
---
# <a name="get-integration-log"></a>Obtener integración de registro
 
**Resumen:** Obtenga información sobre la operación Obtener registro de integración, que forma parte de la API de datos para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.
  
La operación Obtener registro de integración forma parte de la API de datos para el panel de calidad de llamadas
  
## <a name="get-integration-log"></a>Obtener integración de registro

La operación Obtener registro de integración devuelve una lista de entradas de registro que describen las actividades en el procesamiento del cubo QoE.
  
Esta operación está deshabilitada de forma predeterminada por motivos de seguridad. Cuando se deshabilita, devuelve una cadena vacía. Para habilitar esta operación, los administradores deben configurar el web.config de la aplicación web host de la API de datos.
  

|Método|**URI de solicitud**|**Versión HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoEDataService/IntegrationLog  <br/> |HTTP/1.1  <br/> |
   
 **Parámetros uri:** ninguno.
  
 **Encabezados de solicitud:** no hay encabezados adicionales.
  
 **Cuerpo de la** solicitud: ninguno.
  
 **Respuesta:** la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado:** una operación correcta devuelve el código de estado 200 (Correcto).
  
 **Encabezados de respuesta:** no hay encabezados adicionales.
  
 **Cuerpo de la** respuesta: a continuación se muestra una estructura de ejemplo de entradas de registro.
  
```json
[
{"LogCategory":"<category>","LogTime":"2015-03-18T10:28:29.10","LogDescription":"<log description>"}
]
```


