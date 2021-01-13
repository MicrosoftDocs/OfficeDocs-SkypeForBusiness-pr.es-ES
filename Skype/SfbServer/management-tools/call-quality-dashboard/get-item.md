---
title: Obtener elemento
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
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 'Resumen: obtenga información sobre la operación Obtener elemento, que forma parte del servicio de elementos. El servicio de elementos forma parte de la API de repositorio para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: 896540c4572fb3991356ce055f01690ed702c6f2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832570"
---
# <a name="get-item"></a>Obtener elemento
 
**Resumen:** Obtenga información sobre la operación Obtener elemento, que forma parte del servicio de elementos. El servicio de elementos forma parte de la API de repositorio para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.
  
La operación Obtener elemento forma parte del servicio de elementos en la API de repositorio para el panel de calidad de llamadas.
  
## <a name="get-item"></a>Obtener elemento

Obtener elemento devuelve un elemento específico en el repositorio.
  
|**Método**|**URI de solicitud**|**Versión HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **Parámetros uri:** ninguno.
  
 **Encabezados de solicitud:** no hay encabezados adicionales.
  
 **Cuerpo de la** solicitud: ninguno.
  
 **Respuesta:** la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado:** una operación correcta devuelve el código de estado 200 (Correcto). Si no se encuentra un identificador de elemento especificado, devuelve el código de estado 404 (No encontrado).
  
 **Encabezados de respuesta:** no hay encabezados adicionales.
  
 **Cuerpo de la** respuesta: a continuación se muestra una carga de respuesta de ejemplo en JSON.
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 *itemId:*  id. del elemento.
  
 *userId:*  identificador del usuario propietario de este elemento.
  
 *contenido:*  contenido específico de la aplicación.
  
 *type:*  el tipo de contenido. Las aplicaciones establecen este campo.
  
 *subItemIds:*  los id. de los subelementos, si los hay. Se trata de un corto circuito de la operación Get Sub-Items para guardar una llamada. Las aplicaciones también pueden obtener la misma información mediante la operación Get Sub-Items.
  

