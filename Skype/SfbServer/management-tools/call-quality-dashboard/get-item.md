---
title: Obtener elemento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: 'Resumen: Obtenga información sobre la operación obtener elemento, que forma parte del servicio de artículo. El servicio de artículo forma parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: bfd5015603ac73fb48c4e30635cf8ae0fb14bf13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274719"
---
# <a name="get-item"></a>Obtener elemento
 
**Resumen:** Obtenga más información sobre la operación obtener elemento, que es parte del servicio de artículos. El servicio de artículo forma parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.
  
La operación obtener elemento forma parte del servicio de elemento en la API del repositorio para el panel de calidad de llamadas.
  
## <a name="get-item"></a>Obtener elemento

Obtener elemento devuelve un elemento específico del repositorio.
  
|**Método**|**Solicitar URI**|**Versión HTTP**|
|:-----|:-----|:-----|
|Obtener  <br/> |https://\<portal\>/QoERepositoryService/Repository/Item/{Itemid}  <br/> |HTTP/1.1  <br/> |
   
 **Parámetros de URI** : ninguno.
  
 **Solicitar encabezados** : no hay encabezados adicionales.
  
 **Solicitar cuerpo** : ninguno.
  
 **Respuesta** : la respuesta incluye un código de estado http y un conjunto de encabezados de respuesta.
  
 **Código de estado** : una operación correcta devuelve el código de estado 200 (correcto). Si no se encuentra un identificador de elemento especificado, devuelve el código de estado 404 (no se encontró).
  
 **Encabezados de respuesta** : no hay encabezados adicionales.
  
 **Cuerpo de respuesta** : a continuación se muestra un ejemplo de carga de respuesta en JSON.
  
```
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 *Itemid* -ID del elemento.
  
 ** identificador de usuario del usuario que es el propietario de este elemento.
  
 *contenido* : el contenido específico de la aplicación.
  
 *Type* : el tipo del contenido. Este campo lo establecen las aplicaciones.
  
 *subItemIds* : los identificadores de subelementos, si los hay. Este es un cortocircuito de la operación de obtención de subelementos para guardar una llamada. Las aplicaciones también pueden obtener la misma información mediante la operación de obtención de subelementos.
  

