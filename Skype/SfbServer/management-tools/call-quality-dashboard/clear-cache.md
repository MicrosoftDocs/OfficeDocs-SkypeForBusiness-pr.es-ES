---
title: Borrar caché
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: 'Resumen: Obtenga información sobre la operación Borrar caché, que forma parte de la API de datos para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 38648e1a910f93a30bd6da8807321acad0330e62
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274838"
---
# <a name="clear-cache"></a>Borrar caché
 
**Resumen:** Obtenga información sobre la operación Borrar caché, que forma parte de la API de datos para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.
  
La operación Borrar caché es parte de la API de datos para el panel de calidad de llamadas.
  
## <a name="clear-cache"></a>Borrar caché

Operación de borrar caché elimina la caché del servidor de consultas y datos. Esto restablecerá la memoria caché y recibirá datos nuevos de la actualización del cubo de QoE después para solicitudes nuevas.
  

|**Método**|**Solicitar URI**|**Versión HTTP**|
|:-----|:-----|:-----|
|Exponer  <br/> |https://\<portal\>/QoEDataService/ClearCache  <br/> |HTTP/1.1  <br/> |
   
 **Parámetros de URI** : ninguno.
  
 **Solicitar encabezados** : no hay encabezados adicionales.
  
 **Solicitar cuerpo** : ninguno.
  
 **Respuesta** : la respuesta incluye un código de estado http y un conjunto de encabezados de respuesta.
  
 **Código de estado** : una operación correcta devuelve el código de estado 200 (correcto).
  
 **Encabezados de respuesta** : no hay encabezados adicionales.
  
 **Cuerpo** de la respuesta: ninguno.
  

