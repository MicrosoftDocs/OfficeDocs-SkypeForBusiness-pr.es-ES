---
title: Obtener miembros de dimensión
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 'Resumen: Obtenga información sobre la operación obtener miembros de dimensión. La operación obtener miembros de dimensión forma parte de la API de datos para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 40e5ac8b95c24c3a8cb759da99f7d7aeaa391576
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888819"
---
# <a name="get-dimension-members"></a>Obtener miembros de dimensión
 
**Resumen:** Obtenga más información sobre la operación obtener miembros de dimensión. La operación obtener miembros de dimensión forma parte de la API de datos para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.
  
La operación obtener miembros de dimensión forma parte de la API de datos para el panel de calidad de llamadas.
  
## <a name="get-dimension-members"></a>Obtener miembros de dimensión

Operación de obtención de miembros de dimensión devuelve la lista de miembros de una dimensión específica. También ofrece la posibilidad de filtrar la lista de miembros y obtener un subconjunto, para reducir el coste de la transferencia bancaria.
  

|**Método**|**Solicitar URI**|**Versión HTTP**|
|:-----|:-----|:-----|
|Exponer  <br/> |https://\<portal\>/QoEDataService/DimensionMembers  <br/> |HTTP/1.1  <br/> |
   
 **Parámetros de URI** : ninguno.
  
 **Solicitar encabezados** : no hay encabezados adicionales.
  
 **Solicitar cuerpo** : contiene el nombre de la dimensión para la que deseamos los miembros. También se devuelve un número máximo de miembros, junto a usted puede especificar algunos filtros para limitar los miembros devueltos.
  
```json
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 **Respuesta** : la respuesta incluye un código de estado http y un conjunto de encabezados de respuesta.
  
 **Código de estado** : una operación correcta devuelve el código de estado 200 (correcto).
  
 **Encabezados de respuesta** : no hay encabezados adicionales.
  
 **Cuerpo de respuesta** : a continuación se muestra una carga de respuesta de ejemplo en JSON en respuesta a una solicitud de "[fechainicio]. [Month] "dimensión.
  
> [!NOTE]
> La lista solo muestra una pequeña parte de la lista. 
  
```json
{
"MembersCount": 493,
"Members": [["[1990-01-01T00:00:00]",
"January 1990"],
["[1990-02-01T00:00:00]",
"February 1990"],
["[1990-03-01T00:00:00]",
"March 1990"],
 
    ...
    
["[2030-10-01T00:00:00]",
"October 2030"],
["[2030-11-01T00:00:00]",
"November 2030"],
["[2030-12-01T00:00:00]",
"December 2030"],
["[2031-01-01T00:00:00]",
"January 2031"]]
}
```
