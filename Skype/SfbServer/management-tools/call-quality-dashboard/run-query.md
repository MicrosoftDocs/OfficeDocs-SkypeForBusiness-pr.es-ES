---
title: Ejecutar consulta
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: 'Resumen: Conozca la operación Ejecutar consulta, que forma parte de la API de datos para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 6e294625e173854382e39abc098a0480871586ac
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="run-query"></a>Ejecutar consulta
 
**Resumen:** Obtener información sobre la operación de ejecutar consulta, que forma parte de la API de datos para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.
  
La operación de ejecutar consulta forma parte de la API de datos para llamar al panel de calidad.
  
## <a name="run-query"></a>Ejecutar consulta

Ejecutar consulta operación proporciona la capacidad de ejecutar una consulta en el cubo basándose en los filtros, las medidas y dimensiones especificadas y devolver los datos de nuevo.
  

|**Método**|**URI de la solicitud**|**Versión de HTTP**|
|:-----|:-----|:-----|
|Exponer  <br/> |https://\<portal\>/QoEDataService/RunQuery  <br/> |HTTP/1.1  <br/> |
   
 **URI parámetros** : ninguno.
  
 **Encabezados de solicitud** - sin encabezados adicionales.
  
 El **Cuerpo de la solicitud** - aquí es una carga de solicitud muestra en JSON. Contiene dimensiones, filtros y medida necesaria para una consulta.
  
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

 *Filtros* : una lista de expresiones de filtro para aplicar tales que el conjunto de datos resultante se reflejan sólo el subconjunto de los datos que son de interés.
  
 *Dimensiones* - una lista de las dimensiones que se utilizará para la agregación de los datos. Se requiere al menos una dimensión pero pueden especificarse varias dimensiones para obtener un nivel adicional de agregados secundarios.
  
 *Medidas* : una lista de medidas, también conocido como hechos, que son las métricas a agregarse deseadas se basan en las dimensiones que especificó.
  
 *Trend* - instrucciones de control adicional para personalizar los datos de resultado.
  
 **Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado** - una operación correcta devuelve el código de estado 200 (OK).
  
 **Encabezados de respuesta** - sin encabezados adicionales.
  
 **Cuerpo de la respuesta** : a continuación es una carga de respuesta de ejemplo en JSON. Contiene una tabla de datos que contiene los datos, también contendrá metadatos, que muestra el tiempo de ejecución de la consulta y si son o no los datos de la caché.
  
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

 *Tiempo de ejecución* - el tiempo total que tarda el servidor devuelva los datos. Esto puede o no puede implicar la caché.
  
 *Resultados de datos* - el resultado de la consulta. Es una matriz bidimensional que contiene todas las permutaciones de los miembros de las dimensiones y cada elemento que contiene los nombres de miembros de las dimensiones, así como los valores agregados de las medidas especificadas.
  
 *Resultado es de la caché* - para diagnósticos. Indica si el resultado procede de la memoria caché o del cubo de la calidad de la experiencia.
  

