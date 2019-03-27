---
title: Obtener elemento
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 'Resumen: Obtenga información acerca de la operación obtener elemento, que es parte del servicio de elemento. El servicio de elemento es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: 1f86c318139d328f414bf1290c66ddd7ccb7e20a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889445"
---
# <a name="get-item"></a>Obtener elemento
 
**Resumen:** Obtenga información acerca de la operación obtener elemento, que es parte del servicio de elemento. El servicio de elemento es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.
  
La operación obtener elemento es parte del servicio de elemento de la API de repositorio para llamar al panel de calidad.
  
## <a name="get-item"></a>Obtener elemento

Obtener elemento devuelve un elemento específico en el repositorio.
  
|**(Método)**|**URI de la solicitud**|**Versión de HTTP**|
|:-----|:-----|:-----|
|Obtener  <br/> |https://\<portal\>/QoERepositoryService/repository/elemento / {itemId}  <br/> |HTTP/1.1  <br/> |
   
 **Los parámetros URI** - ninguno.
  
 **Encabezados de solicitud** - sin encabezados adicionales.
  
 **Cuerpo de la convocatoria** - ninguno.
  
 **Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado** - una operación correcta devuelve código de estado 200 (Aceptar). Si no se encuentra un identificador de elemento especificado, devuelve el código de estado 404 (no encontrado).
  
 **Encabezados de respuesta** - sin encabezados adicionales.
  
 **Cuerpo de la respuesta** - a continuación es una carga de respuesta de ejemplo en JSON.
  
```
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 *itemId* - identificador del elemento.
  
 *userId* : identificador del usuario que es propietario de este elemento.
  
 *contenido* : el contenido específico de la aplicación.
  
 *tipo* : el tipo de contenido. Este campo se establece por las aplicaciones.
  
 *subItemIds* - los identificadores de elementos secundarios, si hay alguno. Se trata de un máximo de operación obtener elementos secundarios para guardar una llamada. Las aplicaciones o bien pueden obtener la misma información de uso de la operación obtener elementos secundarios.
  

