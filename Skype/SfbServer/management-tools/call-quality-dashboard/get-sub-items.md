---
title: Obtener elementos secundarios
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Summary: Learn about the Get Sub-Items operation, which is part of the Item Service. El servicio de elementos forma parte de la API de repositorio para el Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: 3d17ab46ece202ea36dce45b6266a1cd3de74928
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774650"
---
# <a name="get-sub-items"></a>Obtener elementos secundarios
 
**Resumen:** Obtenga información sobre la operación Obtener Sub-Items, que forma parte del servicio de elementos. El servicio de elementos forma parte de la API de repositorio para el Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.
  
La operación Obtener Sub-Items forma parte del servicio de elementos de la API de repositorio para el Panel de calidad de llamadas.
  
## <a name="get-sub-items"></a>Obtener elementos secundarios

Get Sub-Items devuelve los sub-elementos de un elemento específico.
  

|**Método**|**URI de solicitud**|**Versión HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/item/{itemId}/subitem  <br/> |HTTP/1.1  <br/> |
   
 **Parámetros uri:** ninguno.
  
 **Encabezados de solicitud:** no hay encabezados adicionales.
  
 **Cuerpo de la** solicitud: ninguno.
  
 **Respuesta:** la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado:** una operación correcta devuelve el código de estado 200 (Aceptar). Si no se encuentra un identificador de usuario especificado, devuelve el código de estado 404 (No encontrado).
  
 **Encabezados de respuesta:** no hay encabezados adicionales.
  
 **Cuerpo de la** respuesta: a continuación se muestra una carga de respuesta de ejemplo en JSON.
  
> [!NOTE]
> Se devuelve una matriz de objeto Item. 
  
```json
[{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1710,
"userId": 0,
"type": "json"
}]
```

El objeto Item devuelto Sub-Items operación solo contiene los tres campos siguientes. 
  
 *itemId:*  id. del elemento.
  
 *userId:*  id. del usuario propietario de este elemento.
  
 *type:*  el tipo del contenido. Las aplicaciones establecen este campo.
  
> [!NOTE]
>  `Content` y `subItems` los campos no se incluyen en la respuesta para reducir la cantidad de datos transmitidos a través de la red.
  

