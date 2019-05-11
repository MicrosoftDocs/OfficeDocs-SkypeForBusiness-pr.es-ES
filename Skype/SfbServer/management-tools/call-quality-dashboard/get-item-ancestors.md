---
title: Obtener predecesores del elemento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 'Resumen: Obtenga información acerca de la operación obtener antecesores del elemento, que es parte del servicio de elemento. El servicio de elemento es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: 22672146ec9ab071041c85c31a466d766ffe31b9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930640"
---
# <a name="get-item-ancestors"></a>Obtener predecesores del elemento
 
**Resumen:** Obtenga información acerca de la operación obtener antecesores del elemento, que es parte del servicio de elemento. El servicio de elemento es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.
  
La operación obtener elemento antecesores es parte del servicio de elemento de la API de repositorio para llamar al panel de calidad.
  
## <a name="get-item-ancestors"></a>Obtener predecesores del elemento

Get elemento antecesores devuelve a un antecesores elementos específicos del repositorio.
  

|**(Método)**|**URI de la solicitud**|**Versión de HTTP**|
|:-----|:-----|:-----|
|Obtener  <br/> |https://\<portal\>/QoERepositoryService/repository/itemAncestors / {itemId}  <br/> |HTTP/1.1  <br/> |
   
 **Los parámetros URI** - ninguno.
  
 **Encabezados de solicitud** - sin encabezados adicionales.
  
 **Cuerpo de la convocatoria** - ninguno.
  
 **Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado** - una operación correcta devuelve código de estado 200 (Aceptar). Si un usuario especificado que no se encuentra el identificador, devuelve el código de estado 404 (no encontrado).
  
 **Encabezados de respuesta** - sin encabezados adicionales.
  
 **Cuerpo de la respuesta** - a continuación es una carga de respuesta de ejemplo en JSON.
  
```
[{
"item1": 1653,
"item2": 0,
"item3": "Audio Streams Monthly Trend"
},
{
"item1": 1652,
"item2": 1,
"item3": "All Audio Streams"
}]
```

 *Item1* - identificador del elemento.
  
 *Item2* - profundidad es la distancia desde el elemento. 0 es el objeto primario inmediato.
  
 *Item3* - título del elemento.
  

