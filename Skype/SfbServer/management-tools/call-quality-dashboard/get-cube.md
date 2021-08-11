---
title: Obtener cubo
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
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: 'Resumen: obtenga información sobre la operación Obtener cubo, que forma parte de la API de datos para el Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: bc65a9d6886b9375a799c62a6abaefd33738dae5fd8a4d4aee83a536d9a82948
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278728"
---
# <a name="get-cube"></a>Obtener cubo
 
**Resumen:** Obtenga información sobre la operación Obtener cubo, que forma parte de la API de datos para el Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.
  
La operación Obtener cubo forma parte de la API de datos para el Panel de calidad de llamadas.
  
## <a name="get-cube"></a>Obtener cubo

La operación Obtener cubo devuelve la lista de dimensiones y medidas disponibles.
  

|**Método**|**URI de solicitud**|**Versión HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoEDataService/CubeStructure  <br/> |HTTP/1.1  <br/> |
   
 **Parámetros uri:** ninguno.
  
 **Encabezados de solicitud:** no hay encabezados adicionales.
  
 **Cuerpo de la** solicitud: ninguno.
  
 **Respuesta:** la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado:** una operación correcta devuelve el código de estado 200 (Aceptar).
  
 **Encabezados de respuesta:** no hay encabezados adicionales.
  
 **Cuerpo de la** respuesta: a continuación se muestra una carga de respuesta de ejemplo en JSON.
  
> [!NOTE]
> En este ejemplo solo se muestran los dos primeros elementos de cada grupo de elementos Cube. 
  
```json
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

 *KPI:*  reservados. La sección KPI de una carga de solicitud permite que la operación Ejecutar consulta devuelva los valores de los KPI definidos en el cubo. Todavía no hay KPI en el cubo de QoE.
  
 *Dimensiones:*  la lista de dimensiones que se pueden usar en las secciones Filtros y dimensiones de una carga de solicitud para la operación Ejecutar consulta. Para usar una dimensión en una expresión de filtro, debe especificar un miembro de dimensión, que se puede obtener mediante la operación Obtener miembros de dimensión.
  
 *Medidas:*  lista de medidas que se pueden usar en la sección Medidas de una carga de solicitud para la operación Ejecutar consulta.
  

