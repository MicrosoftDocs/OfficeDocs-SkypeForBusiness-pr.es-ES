---
title: Obtener los antecesores del elemento
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 'Resumen: Conozca la operación obtener antecesores del elemento, que es parte del elemento de servicio. El servicio del elemento es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: ab5cc9dd388d1192922430e2a728bb8073b3e0d7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="get-item-ancestors"></a>Obtener los antecesores del elemento
 
**Resumen:** Obtener información sobre la operación de obtener antecesores del elemento, que es parte del elemento de servicio. El servicio del elemento es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.
  
La operación de obtener elementos antecesores es parte del elemento de servicio en la API de repositorio para llamar al panel de calidad.
  
## <a name="get-item-ancestors"></a>Obtener los antecesores del elemento

Antecesores del elemento Get devuelve a un antecesores de elementos específicos del repositorio.
  

|**Método**|**URI de la solicitud**|**Versión de HTTP**|
|:-----|:-----|:-----|
|Obtener  <br/> |https://\<portal\>/QoERepositoryService/repository/itemAncestors / {itemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI parámetros** : ninguno.
  
 **Encabezados de solicitud** - sin encabezados adicionales.
  
 **Cuerpo de la solicitud** - ninguno.
  
 **Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado** - una operación correcta devuelve el código de estado 200 (OK). Si un usuario especificado que no se encuentra el identificador, devuelve el código de estado 404 (no encontrado).
  
 **Encabezados de respuesta** - sin encabezados adicionales.
  
 **Cuerpo de la respuesta** : a continuación es una carga de respuesta de ejemplo en JSON.
  
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

 *Item1* - ID del elemento.
  
 *Item2* - profundidad es la distancia desde el elemento. 0 es el elemento primario inmediato.
  
 *Item3* : título del artículo.
  

