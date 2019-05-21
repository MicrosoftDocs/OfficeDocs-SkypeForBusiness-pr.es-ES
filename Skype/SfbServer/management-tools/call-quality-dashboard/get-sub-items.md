---
title: Obtener elementos secundarios
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Resumen: Obtenga información sobre la operación de obtención de subelementos, que es parte del servicio de elementos. El servicio de artículo forma parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 7be427ed4ea90cd46c6f8cea4ffe3a97be98479b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274663"
---
# <a name="get-sub-items"></a>Obtener elementos secundarios
 
**Resumen:** Obtenga más información sobre la operación obtener subelementos, que es parte del servicio de artículos. El servicio de artículo forma parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.
  
La operación obtener subelementos es parte del servicio de elemento en la API del repositorio para el panel de calidad de llamadas.
  
## <a name="get-sub-items"></a>Obtener elementos secundarios

Obtener subelementos devuelve los subelementos de un elemento específico.
  

|**Método**|**Solicitar URI**|**Versión HTTP**|
|:-----|:-----|:-----|
|Obtener  <br/> |https://\<portal\>/QoERepositoryService/Repository/Item/{Itemid}/SubItem  <br/> |HTTP/1.1  <br/> |
   
 **Parámetros de URI** : ninguno.
  
 **Solicitar encabezados** : no hay encabezados adicionales.
  
 **Solicitar cuerpo** : ninguno.
  
 **Respuesta** : la respuesta incluye un código de estado http y un conjunto de encabezados de respuesta.
  
 **Código de estado** : una operación correcta devuelve el código de estado 200 (correcto). Si no se encuentra un identificador de usuario especificado, devuelve el código de estado 404 (no se encontró).
  
 **Encabezados de respuesta** : no hay encabezados adicionales.
  
 **Cuerpo de respuesta** : a continuación se muestra un ejemplo de carga de respuesta en JSON.
  
> [!NOTE]
> Se devuelve una matriz de objetos de elemento. 
  
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

El objeto de elemento devuelto por la operación SubItems solo contiene los tres campos siguientes. 
  
 *Itemid* -ID del elemento.
  
 ** identificador de usuario del usuario que es el propietario de este elemento.
  
 *Type* : el tipo del contenido. Este campo lo establecen las aplicaciones.
  
> [!NOTE]
>  `Content`y `subItems` los campos no se incluyen en la respuesta para reducir la cantidad de datos que se transmiten a través de la red.
  

