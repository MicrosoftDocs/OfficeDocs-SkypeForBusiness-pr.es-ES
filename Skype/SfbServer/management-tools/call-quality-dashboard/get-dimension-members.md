---
title: Los miembros de dimensión
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 'Resumen: Conozca la operación de obtener miembros de dimensión. La operación de obtener miembros de la dimensión es parte de la API de datos para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 6da1b8f6d93dc197df320f1fb5875a6269a9b45a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="get-dimension-members"></a>Los miembros de dimensión
 
**Resumen:** Obtener información sobre la operación de obtener miembros de dimensión. La operación de obtener miembros de la dimensión es parte de la API de datos para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.
  
La operación de obtener miembros de la dimensión es parte de la API de datos para llamar al panel de calidad.
  
## <a name="get-dimension-members"></a>Los miembros de dimensión

Operación de obtención de miembros de dimensión, devuelve la lista de miembros de una dimensión específica. También proporcionan la capacidad para filtrar la lista de miembros y obtener un subconjunto, para reducir el costo de la transferencia de alambre.
  

|**Método**|**URI de la solicitud**|**Versión de HTTP**|
|:-----|:-----|:-----|
|Exponer  <br/> |https://\<portal\>/QoEDataService/DimensionMembers  <br/> |HTTP/1.1  <br/> |
   
 **URI parámetros** : ninguno.
  
 **Encabezados de solicitud** - sin encabezados adicionales.
  
 **Solicitar cuerpo** : contiene el nombre de la dimensión que queremos que los miembros de. También devuelve el número máximo de miembros, al lado puede especificar algunos filtros para limitar a los miembros devueltos.
  
```
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}

```

 **Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado** - una operación correcta devuelve el código de estado 200 (OK).
  
 **Encabezados de respuesta** - sin encabezados adicionales.
  
 **Cuerpo de la respuesta** : a continuación es una carga de respuesta de ejemplo en JSON en respuesta a una solicitud de "[FechaInicio]. [Mes] "dimensión.
  
> [!NOTE]
> La lista muestra sólo una pequeña parte de la lista. 
  
```
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


