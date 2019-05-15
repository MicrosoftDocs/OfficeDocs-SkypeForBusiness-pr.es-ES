---
title: Ejecutar consulta
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 'Resumen: Obtenga información acerca de la operación de ejecutar la consulta, que es parte de la API de datos para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: a979ea7d8202365e939e075c2628ca4f3987fa63
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33914962"
---
# <a name="run-query"></a>Ejecutar consulta

**Resumen:** Obtenga información acerca de la operación de ejecutar la consulta, que es parte de la API de datos para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.

La operación de ejecutar la consulta forma parte de la API de datos para el panel de calidad de llamadas.

## <a name="run-query"></a>Ejecutar consulta

Ejecutar consulta operación proporciona la capacidad de ejecutar una consulta en el cubo en función de los filtros, las medidas y dimensiones especificadas y volver atrás los datos.


|**(Método)**|**URI de la solicitud**|**Versión de HTTP**|
|:-----|:-----|:-----|
|Exponer  <br/> |https://\<portal\>/QoEDataService/RunQuery  <br/> |HTTP/1.1  <br/> |

 **Los parámetros URI** - ninguno.

 **Encabezados de solicitud** - sin encabezados adicionales.

 **Cuerpo de la solicitud** - aquí es una carga de solicitud de ejemplo en JSON. Contiene las dimensiones, filtros y medida necesaria para una consulta.

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

 *Filtros* : una lista de expresiones de filtro que se aplique tal que el conjunto de datos resultante reflejará sólo el subconjunto de los datos que son de interés.

 *Dimensiones* - una lista de las dimensiones que se usará para la agregación de los datos. Se requiere al menos una dimensión, pero se pueden especificar varias dimensiones para obtener un nivel adicional de agregaciones subcaracterística.

 *Las medidas* : una lista de las medidas, también conocido como hechos, que son las métricas que desee para agregarse según las dimensiones que especificó.

 *Tendencia* - instrucciones adicionales de control para personalizar los datos de resultado.

 **Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.

 **Código de estado** - una operación correcta devuelve código de estado 200 (Aceptar).

 **Encabezados de respuesta** - sin encabezados adicionales.

 **Cuerpo de la respuesta** - a continuación es una carga de respuesta de ejemplo en JSON. Contiene una tabla de datos que contiene los datos, también va a contener metadatos, que muestra el tiempo de ejecución de la consulta y si está o no los datos de la memoria caché.

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

 *Tiempo de ejecución* : el tiempo total que tardó el servidor devuelva los datos. Esto puede o no puede implicar la memoria caché.

 *Resultado de los datos* - el resultado de la consulta. Es una matriz bidimensional que contiene todas las permutaciones de miembros de las dimensiones y cada elemento que contiene los nombres de miembros de las dimensiones, así como los valores agregados de las mediciones especificados.

 *Resultado es de la caché* - para diagnósticos. Indica si el resultado procede de la memoria caché o desde el cubo de QoE.
