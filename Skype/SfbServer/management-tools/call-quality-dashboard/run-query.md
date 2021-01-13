---
title: Ejecutar consulta
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
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 'Resumen: obtenga información sobre la operación Ejecutar consulta, que forma parte de la API de datos para el Panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: bff24ca5a4d651ba276b4b0d795afabce3c6d0dd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803120"
---
# <a name="run-query"></a>Ejecutar consulta

**Resumen:** Obtenga información sobre la operación Ejecutar consulta, que forma parte de la API de datos para el Panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.

La operación Ejecutar consulta forma parte de la API de datos para el panel de calidad de llamadas.

## <a name="run-query"></a>Ejecutar consulta

La operación Ejecutar consulta permite ejecutar una consulta en el cubo en función de las dimensiones, medidas y filtros especificados y devolver los datos.


|**Método**|**URI de solicitud**|**Versión HTTP**|
|:-----|:-----|:-----|
|PUBLICAR  <br/> |https:// \<portal\> /QoEDataService/RunQuery  <br/> |HTTP/1.1  <br/> |

 **Parámetros uri:** ninguno.

 **Encabezados de solicitud:** no hay encabezados adicionales.

 **Cuerpo de la** solicitud: esta es una carga de solicitud de ejemplo en JSON. Contiene dimensiones, filtros y medidas necesarias para una consulta.

```json
{
"Filters": [{
"DataModelName": "[StartDate].[Month]",
"Caption": "July 2013",
"Value": "[2015-03-01T00:00:00]",
"Operand": 0,
"UnionGroup": ""
}],
"Dimensions": [{
"DataModelName": "[StartDate].[Month]"
}],
"Measurements": [{
"DataModelName": "[Measures].[Audio Good Streams Count]"
},
{
"DataModelName": "[Measures].[Audio UnClassified Streams Count]"
},
{
"DataModelName": "[Measures].[Audio Poor Streams Count]"
},
{
"DataModelName": "[Measures].[AudioPoorPercentage]"
}],
"Trend": {
"EnableTrend": true,
"SpanCount": 7,
"TrendDate": "2015-3",
"Type": 0
}
}
```

 *Filtros:*  una lista de expresiones de filtro que se aplicarán de manera que el conjunto de datos resultante refleje solo el subconjunto de los datos que son de interés.

 *Dimensiones:*  una lista de dimensiones que se usará para agregar los datos. Se requiere al menos una dimensión, pero se pueden especificar varias dimensiones para obtener un nivel adicional de agregaciones adicionales.

 *Medidas:*  una lista de medidas, también conocidas como hechos, que son las métricas deseadas que se agregarán en función de las dimensiones especificadas.

 *Tendencia:*  instrucciones de control adicionales para personalizar los datos de resultados.

 **Respuesta:** la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.

 **Código de estado:** una operación correcta devuelve el código de estado 200 (Correcto).

 **Encabezados de respuesta:** no hay encabezados adicionales.

 **Cuerpo de la** respuesta: a continuación se muestra una carga de respuesta de ejemplo en JSON. Contiene una tabla de datos que contiene los datos, además de un metadatos, que muestra el tiempo de ejecución de la consulta y si los datos son o no de la memoria caché.

```json
{
"ExecutionTime": "00:00:00.2102630",
"DataResult": [["September 2014",
        1792,
        34,
        78,
        4.171],
        ["October 2014",
        37017,
        1731,
        3305,
        8.197],
        ["November 2014",
        79184,
        3033,
        5556,
        6.557],
        ["December 2014",
        122253,
        4050,
        5444,
        4.263],
        ["January 2015",
        31246,
        1069,
        1342,
        4.118]],
"ResultIsFromCache": false,
"ErrorType": 0
}
```

 *Tiempo de*  ejecución: tiempo total que tardó el servidor en devolver los datos. Esto puede implicar o no la memoria caché.

 *Resultado de los*  datos: el resultado de la consulta. Es una matriz bidimensional que contiene todas las permutaciones de los miembros de las dimensiones y cada elemento que contiene los nombres de los miembros de las dimensiones, así como los valores agregados de las medidas especificadas.

 *El resultado es de la memoria*  caché: para diagnósticos. Indica si el resultado viene de la memoria caché o del cubo QoE.
