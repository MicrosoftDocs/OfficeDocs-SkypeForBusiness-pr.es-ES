---
title: Obtener predecesores del elemento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: 'Resumen: Obtenga información sobre la operación obtener elementos antecesores de elemento, que es parte del servicio de elemento. El servicio de artículo forma parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: c82ae699cab0bf812f281fc2f2ad54323bcf8f7f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992687"
---
# <a name="get-item-ancestors"></a>Obtener predecesores del elemento
 
**Resumen:** Obtenga más información sobre la operación obtener elementos antecesores de elemento, que es parte del servicio de elemento. El servicio de artículo forma parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.
  
La operación obtener elementos antecesores del elemento es parte del servicio de elemento en la API del repositorio para el panel de calidad de llamadas.
  
## <a name="get-item-ancestors"></a>Obtener predecesores del elemento

Obtener elementos antecesores del elemento devuelve los elementos antecesores específicos del repositorio.
  

|**Método**|**Solicitar URI**|**Versión HTTP**|
|:-----|:-----|:-----|
|Obtener  <br/> |https://\<portal\>/QoERepositoryService/Repository/itemAncestors/{Itemid}  <br/> |HTTP/1.1  <br/> |
   
 **Parámetros de URI** : ninguno.
  
 **Solicitar encabezados** : no hay encabezados adicionales.
  
 **Solicitar cuerpo** : ninguno.
  
 **Respuesta** : la respuesta incluye un código de estado http y un conjunto de encabezados de respuesta.
  
 **Código de estado** : una operación correcta devuelve el código de estado 200 (correcto). Si no se encuentra un identificador de usuario especificado, devuelve el código de estado 404 (no se encontró).
  
 **Encabezados de respuesta** : no hay encabezados adicionales.
  
 **Cuerpo de respuesta** : a continuación se muestra un ejemplo de carga de respuesta en JSON.
  
```json
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

 *Item1* -ID del elemento.
  
 *Item2* -profundidad es la distancia desde el elemento. 0 es el elemento primario inmediato.
  
 *Item3* : título del elemento.
  

