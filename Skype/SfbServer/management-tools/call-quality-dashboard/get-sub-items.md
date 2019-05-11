---
title: Obtener elementos secundarios
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Resumen: Obtenga información acerca de la operación obtener elementos secundarios, que es parte del servicio de elemento. El servicio de elemento es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: 4d0e5c19a4bfb5d66db95738cab5b0c2eaf33985
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930682"
---
# <a name="get-sub-items"></a>Obtener elementos secundarios
 
**Resumen:** Obtenga información acerca de la operación obtener elementos secundarios, que es parte del servicio de elemento. El servicio de elemento es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.
  
La operación obtener elementos secundarios es parte del servicio de elemento de la API de repositorio para llamar al panel de calidad.
  
## <a name="get-sub-items"></a>Obtener elementos secundarios

Obtener elementos secundarios devuelve elementos secundarios de un elemento específico.
  

|**(Método)**|**URI de la solicitud**|**Versión de HTTP**|
|:-----|:-----|:-----|
|Obtener  <br/> |https://\<portal\>/QoERepositoryService/repository/elemento / {itemId} / subelemento  <br/> |HTTP/1.1  <br/> |
   
 **Los parámetros URI** - ninguno.
  
 **Encabezados de solicitud** - sin encabezados adicionales.
  
 **Cuerpo de la convocatoria** - ninguno.
  
 **Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado** - una operación correcta devuelve código de estado 200 (Aceptar). Si un usuario especificado que no se encuentra el identificador, devuelve el código de estado 404 (no encontrado).
  
 **Encabezados de respuesta** - sin encabezados adicionales.
  
 **Cuerpo de la respuesta** - a continuación es una carga de respuesta de ejemplo en JSON.
  
> [!NOTE]
> Se devuelve una matriz de objeto de elemento. 
  
```
[{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1710,
"userId": 0,
"type": "json"
}]
```

El objeto de elemento devuelto por la operación de subelementos sólo contiene los siguientes tres campos. 
  
 *itemId* - identificador del elemento.
  
 *userId* : identificador del usuario que es propietario de este elemento.
  
 *tipo* : el tipo de contenido. Este campo se establece por las aplicaciones.
  
> [!NOTE]
>  `Content`y `subItems` campos no se incluyen en la respuesta a reducir la cantidad de datos que se transmiten a través de la red.
  

