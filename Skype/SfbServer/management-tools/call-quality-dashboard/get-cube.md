---
title: Obtener cubo
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Resumen: Obtenga información acerca de la operación obtener cubo, que es parte de la API de datos para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: 5c0623b92c9169a9e54f92d21358fb377c84a8f8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897139"
---
# <a name="get-cube"></a>Obtener cubo
 
**Resumen:** Obtenga información acerca de la operación obtener cubo, que es parte de la API de datos para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.
  
La operación obtener Cube es parte de la API de datos para llamar al panel de calidad.
  
## <a name="get-cube"></a>Obtener cubo

Operación de cubo Get devuelve la lista de dimensiones disponibles y las medidas.
  

|**(Método)**|**URI de la solicitud**|**Versión de HTTP**|
|:-----|:-----|:-----|
|Obtener  <br/> |https://\<portal\>/QoEDataService/CubeStructure  <br/> |HTTP/1.1  <br/> |
   
 **Los parámetros URI** - ninguno.
  
 **Encabezados de solicitud** - sin encabezados adicionales.
  
 **Cuerpo de la convocatoria** - ninguno.
  
 **Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado** - una operación correcta devuelve código de estado 200 (Aceptar).
  
 **Encabezados de respuesta** - sin encabezados adicionales.
  
 **Cuerpo de la respuesta** - a continuación es una carga de respuesta de ejemplo en JSON.
  
> [!NOTE]
> En este ejemplo se muestra sólo dos primeros elementos de cada grupos de elementos de cubo. 
  
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

 *Los KPI* - reservado La sección de KPI de una carga de solicitud permite el funcionamiento de ejecutar la consulta devolver los valores para los KPI definidos en el cubo. Ningún KPI aún existe en el cubo de QoE.
  
 *Dimensiones* - la lista de dimensiones que se puede usar en las secciones de filtros y las dimensiones de una carga de solicitud para la operación de ejecutar la consulta. Para usar una dimensión en una expresión de filtro, debe especificar a un miembro de dimensión, que puede obtenerse mediante la operación de obtener miembros de dimensión.
  
 *Las medidas* : la lista de las medidas que pueden utilizarse en la sección de las medidas de una carga de solicitud para la operación de ejecutar la consulta.
  

