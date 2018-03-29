---
title: Borrar caché
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Resumen: Conozca la operación Borrar caché, que forma parte de la API de datos para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 2356997facfa0057f90ea3d6c8b4cda06add2615
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="clear-cache"></a>Borrar caché
 
**Resumen:** Obtener información sobre la operación de borrar la caché, que forma parte de la API de datos para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.
  
La operación Borrar caché forma parte de la API de datos para llamar al panel de calidad.
  
## <a name="clear-cache"></a>Borrar caché

Operación de caché borrado elimina la caché en el servidor para consultas y datos. Esto restablecerá la caché y le facilitaremos datos nuevos de cubo QoE posteriormente para las nuevas solicitudes.
  

|**Método**|**URI de la solicitud**|**Versión de HTTP**|
|:-----|:-----|:-----|
|Exponer  <br/> |https://\<portal\>/QoEDataService/ClearCache  <br/> |HTTP/1.1  <br/> |
   
 **URI parámetros** : ninguno.
  
 **Encabezados de solicitud** - sin encabezados adicionales.
  
 **Cuerpo de la solicitud** - ninguno.
  
 **Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado** - una operación correcta devuelve el código de estado 200 (OK).
  
 **Encabezados de respuesta** - sin encabezados adicionales.
  
 **Cuerpo de la respuesta** : ninguno.
  

