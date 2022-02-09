---
title: Borrar caché
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Resumen: obtenga información sobre la operación Borrar caché, que forma parte de la API de datos para el Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: f81e22b11851f4b2121f2444d7ded824f3d8530a
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62396372"
---
# <a name="clear-cache"></a>Borrar caché
 
**Resumen:** Obtenga información sobre la operación Borrar caché, que forma parte de la API de datos para el Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.
  
La operación Borrar caché forma parte de la API de datos para el Panel de calidad de llamadas.
  
## <a name="clear-cache"></a>Borrar caché

La operación Borrar caché elimina la memoria caché del servidor para consultas y datos. Esto restablecerá la memoria caché y, posteriormente, se obtienen datos nuevos de QoE Cube para las nuevas solicitudes.
  

|**Método**|**URI de solicitud**|**Versión HTTP**|
|:-----|:-----|:-----|
|POST  <br/> |\<portal\>https:///QoEDataService/ClearCache  <br/> |HTTP/1.1  <br/> |
   
 **Parámetros uri** : ninguno.
  
 **Encabezados de solicitud** : no hay encabezados adicionales.
  
 **Cuerpo de la** solicitud: ninguno.
  
 **Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado** : una operación correcta devuelve el código de estado 200 (Aceptar).
  
 **Encabezados de respuesta** : no hay encabezados adicionales.
  
 **Cuerpo de la** respuesta: ninguno.
  

