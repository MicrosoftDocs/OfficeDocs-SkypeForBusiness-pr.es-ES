---
title: Ejecutar consulta
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 'Resumen: Obtenga información sobre la operación ejecutar consulta, que forma parte de la API de datos para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 0b4c44c93009e014579a53872de82297c1486573
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274565"
---
# <a name="run-query"></a>Ejecutar consulta

**Resumen:** Obtenga información sobre la operación ejecutar consulta, que forma parte de la API de datos para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.

La operación ejecutar consulta forma parte de la API de datos para el panel de calidad de llamadas.

## <a name="run-query"></a>Ejecutar consulta

Ejecutar la operación de consulta proporciona la capacidad de ejecutar una consulta en el cubo basándose en las dimensiones, medidas y filtros especificados y devolver los datos.


|**Método**|**Solicitar URI**|**Versión HTTP**|
|:-----|:-----|:-----|
|Exponer  <br/> |https://\<portal\>/QoEDataService/RunQuery  <br/> |HTTP/1.1  <br/> |

 **Parámetros de URI** : ninguno.

 **Solicitar encabezados** : no hay encabezados adicionales.

 **Solicitar cuerpo** : aquí es una carga de solicitud de ejemplo en JSON. Contiene dimensiones, filtros y medidas necesarias para una consulta.

```
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

 *Filtros* : una lista de expresiones de filtro que se aplicarán de tal modo que el conjunto de datos resultante solo reflejará el subconjunto de datos que son de interés.

 *Dimensiones* : una lista de las dimensiones que se usarán para agregar los datos. Se necesita al menos una dimensión, pero se pueden especificar varias dimensiones para obtener el nivel adicional de subagregaciones.

 *Medidas* : una lista de medidas, también conocidas como hechos, que son las métricas que se desean agregar según las dimensiones especificadas.

 *Tendencia* : instrucciones de control adicionales para personalizar los datos de resultado.

 **Respuesta** : la respuesta incluye un código de estado http y un conjunto de encabezados de respuesta.

 **Código de estado** : una operación correcta devuelve el código de estado 200 (correcto).

 **Encabezados de respuesta** : no hay encabezados adicionales.

 **Cuerpo de respuesta** : a continuación se muestra un ejemplo de carga de respuesta en JSON. Contiene una tabla de datos que contiene los datos; también contendrá un metadatos, que muestra el tiempo de ejecución de la consulta y si los datos proceden o no de la memoria caché.

```
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

 *Tiempo de ejecución* : el tiempo total que ha tardado el servidor en devolver los datos. Esto puede o no implicar caché.

 *Resultado de datos* : resultado de la consulta. Se trata de una matriz bidimensional que contiene todas las permutaciones de los miembros de las dimensiones, y cada elemento que contiene los nombres de los miembros de las dimensiones, así como los valores agregados de las medidas especificadas.

 El *resultado es de la caché* , para diagnósticos. Indica si el resultado procede de la caché o del cubo de calidad.
