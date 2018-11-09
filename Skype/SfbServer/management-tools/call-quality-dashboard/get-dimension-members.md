---
title: Obtener a miembros de dimensión
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 'Resumen: Obtenga información acerca de la operación obtener miembros de dimensión. La operación de obtener miembros de dimensión forma parte de la API de datos para el panel de calidad de llamadas. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: 4c53e809d13b1ceb386c6727805402be9dfaf7f8
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035669"
---
# <a name="get-dimension-members"></a>Obtener a miembros de dimensión
 
**Resumen:** Obtenga información acerca de la operación obtener miembros de dimensión. La operación de obtener miembros de dimensión forma parte de la API de datos para el panel de calidad de llamadas. Panel de calidad de llamada es una herramienta de Skype para Business Server.
  
La operación de obtener miembros de dimensión forma parte de la API de datos para el panel de calidad de llamadas.
  
## <a name="get-dimension-members"></a>Obtener a miembros de dimensión

Operación de obtención de miembros de dimensión, devuelve la lista de miembros de una dimensión específica. También proporcionan la capacidad de filtrar la lista de miembros y obtener un subconjunto, para reducir el costo de transferencia de cable.
  

|**(Método)**|**URI de la solicitud**|**Versión de HTTP**|
|:-----|:-----|:-----|
|Exponer  <br/> |https://\<portal\>/QoEDataService/DimensionMembers  <br/> |HTTP/1.1  <br/> |
   
 **Los parámetros URI** - ninguno.
  
 **Encabezados de solicitud** - sin encabezados adicionales.
  
 **Cuerpo de la solicitud** - contiene el nombre de dimensión que se desea que los miembros de. También se devuelve el número máximo de miembros, junto a puede especificar algunos filtrado para limitar a los miembros devueltos.
  
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
  
 **Código de estado** - una operación correcta devuelve código de estado 200 (Aceptar).
  
 **Encabezados de respuesta** - sin encabezados adicionales.
  
 **Cuerpo de la respuesta** - a continuación es una carga de respuesta de ejemplo en JSON en respuesta a una solicitud de "[StartDate]. [Mes] "dimensión.
  
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