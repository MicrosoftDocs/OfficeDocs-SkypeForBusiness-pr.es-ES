---
title: Obtener miembros de dimensión
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
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: 'Resumen: obtenga información sobre la operación Obtener miembros de dimensión. La operación Obtener miembros de dimensión forma parte de la API de datos para el Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: 3a0c01b310ed60c4b0808d669b553391277f3877bff4c4800bea1b5b765bf5b7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278718"
---
# <a name="get-dimension-members"></a>Obtener miembros de dimensión
 
**Resumen:** Obtenga información sobre la operación Obtener miembros de dimensión. La operación Obtener miembros de dimensión forma parte de la API de datos para el Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.
  
La operación Obtener miembros de dimensión forma parte de la API de datos para el Panel de calidad de llamadas.
  
## <a name="get-dimension-members"></a>Obtener miembros de dimensión

La operación Obtener miembros de dimensión devuelve la lista de miembros de una dimensión específica. También permite filtrar la lista de miembros y obtener un subconjunto para reducir el costo de transferencia bancaria.
  

|**Método**|**URI de solicitud**|**Versión HTTP**|
|:-----|:-----|:-----|
|POST  <br/> |https:// \<portal\> /QoEDataService/DimensionMembers  <br/> |HTTP/1.1  <br/> |
   
 **Parámetros uri:** ninguno.
  
 **Encabezados de solicitud:** no hay encabezados adicionales.
  
 **Cuerpo de** la solicitud: contiene el nombre de la dimensión para la que queremos los miembros. También número máximo de miembros devueltos, además de especificar algunos filtrados para limitar los miembros devueltos.
  
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

 **Respuesta:** la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado:** una operación correcta devuelve el código de estado 200 (Aceptar).
  
 **Encabezados de respuesta:** no hay encabezados adicionales.
  
 **Cuerpo de la** respuesta: a continuación se muestra una carga de respuesta de ejemplo en JSON en respuesta a una solicitud de "[StartDate]. Dimensión [Mes]".
  
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
