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
description: 'Resumen: obtenga información sobre la operación Obtener elemento, que forma parte del servicio de elementos. El servicio de elementos forma parte de la API de repositorio para el Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: fa82d158b41826a950a852633e6c039e9262543d4aabece5c04397eba40be8ae
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278448"
---
# <a name="get-item"></a>Obtener elemento
 
**Resumen:** Obtenga información sobre la operación Obtener elemento, que forma parte del servicio de elementos. El servicio de elementos forma parte de la API de repositorio para el Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.
  
La operación Obtener elemento forma parte del servicio de elementos de la API de repositorio para el Panel de calidad de llamadas.
  
## <a name="get-item"></a>Obtener elemento

Get Item devuelve un elemento específico en el repositorio.
  
|**Método**|**URI de solicitud**|**Versión HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **Parámetros uri:** ninguno.
  
 **Encabezados de solicitud:** no hay encabezados adicionales.
  
 **Cuerpo de la** solicitud: ninguno.
  
 **Respuesta:** la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado:** una operación correcta devuelve el código de estado 200 (Aceptar). Si no se encuentra un identificador de elemento especificado, devuelve el código de estado 404 (No encontrado).
  
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
  
 *userId:*  id. del usuario propietario de este elemento.
  
 *content:*  el contenido específico de la aplicación.
  
 *type:*  el tipo del contenido. Las aplicaciones establecen este campo.
  
 *subItemIds:*  los id. de los subelementos, si los hay. Se trata de un corto circuito de Obtener Sub-Items operación para guardar una llamada. Las aplicaciones también pueden obtener la misma información mediante Obtener Sub-Items operación.
  

