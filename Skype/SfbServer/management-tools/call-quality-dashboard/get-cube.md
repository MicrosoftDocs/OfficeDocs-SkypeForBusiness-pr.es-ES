---
title: Obtener el cubo
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Resumen: Conozca la operación de obtener el cubo, que forma parte de la API de datos para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: e39a88e249dc807b201b08d966285d93ae7f82a6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="get-cube"></a>Obtener el cubo
 
**Resumen:** Obtener información sobre la operación de obtener el cubo, que forma parte de la API de datos para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.
  
La operación Get Cube es parte de la API de datos para llamar al panel de calidad.
  
## <a name="get-cube"></a>Obtener el cubo

Operación de cubo Get devuelve la lista de medidas y dimensiones disponibles.
  

|**Método**|**URI de la solicitud**|**Versión de HTTP**|
|:-----|:-----|:-----|
|Obtener  <br/> |https://\<portal\>/QoEDataService/CubeStructure  <br/> |HTTP/1.1  <br/> |
   
 **URI parámetros** : ninguno.
  
 **Encabezados de solicitud** - sin encabezados adicionales.
  
 **Cuerpo de la solicitud** - ninguno.
  
 **Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado** - una operación correcta devuelve el código de estado 200 (OK).
  
 **Encabezados de respuesta** - sin encabezados adicionales.
  
 **Cuerpo de la respuesta** : a continuación es una carga de respuesta de ejemplo en JSON.
  
> [!NOTE]
> En este ejemplo sólo muestra dos primeros elementos de cada grupo de elementos del cubo. 
  
```
{
"Kpis": [{
"FriendlyName": "Poor Trend Month",
"DataModelName": "[KPIValue].Poor Trend Month",
"Description": null
},
{
"FriendlyName": "Poor Rate Trend Month",
"DataModelName": "[KPIValue].Poor Rate Trend Month",
"Description": null
}],
"Dimensions": [{
"Category": "Access Location Pair",
"Attributes": [{
"FriendlyName": "Location Pair",
"DataModelName": "[Access Location Pair].[Location Pair]",
"Description": "Description of Location Pair"
}]
},
{
"Category": "Audio Bandwidth Est",
"Attributes": [{
"FriendlyName": "Metric",
"DataModelName": "[Audio Bandwidth Est].[Metric]",
"Description": "Description of Metric"
}]
}],
"Measurements": [{
"FriendlyName": "Audio Streams Count",
"DataModelName": "[Measures].[Audio Streams Count]",
"Description": "Description of Audio Streams Count"
},
{
"FriendlyName": "Audio Good Streams JPDR Count",
"DataModelName": "[Measures].[Audio Good Streams JPDR Count]",
"Description": "Description of Audio Good Streams JPDR Count"
}]
}

```

 *KPI* - reservado La sección de KPI de una carga de solicitud permite ejecutar consulta devolver los valores de los KPI definidos en el cubo. No hay KPI aún existe en el cubo de la calidad de la experiencia.
  
 *Dimensiones* - la lista de dimensiones que pueden utilizarse en las secciones de filtros y las dimensiones de una carga de solicitud para la operación de ejecutar consulta. Para utilizar una dimensión en una expresión de filtro, debe especificar a un miembro de dimensión, que puede obtenerse mediante la operación de obtener miembros de dimensión.
  
 *Mediciones* : la lista de medidas que pueden utilizarse en la sección de mediciones de una carga de solicitud para la operación de ejecutar consulta.
  

