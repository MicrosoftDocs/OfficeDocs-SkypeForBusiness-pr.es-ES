---
title: Obtener elementos secundarios
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: 'Resumen: Conozca la operación obtener elementos secundarios, que forma parte del elemento de servicio. El servicio del elemento es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 8b9ec0c1c849e22f285ef1b5bbb2db806a153b76
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="get-sub-items"></a>Obtener elementos secundarios
 
**Resumen:** Obtener información sobre la operación de obtener elementos secundarios, que forma parte del elemento de servicio. El servicio del elemento es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.
  
La operación de obtener elementos secundarios es parte del elemento de servicio en la API de repositorio para llamar al panel de calidad.
  
## <a name="get-sub-items"></a>Obtener elementos secundarios

Obtener elementos secundarios devuelve subelementos de un elemento específico.
  

|**Método**|**URI de la solicitud**|**Versión de HTTP**|
|:-----|:-----|:-----|
|Obtener  <br/> |https://\<portal\>/QoERepositoryService/repository/elemento / {itemId} / subelemento  <br/> |HTTP/1.1  <br/> |
   
 **URI parámetros** : ninguno.
  
 **Encabezados de solicitud** - sin encabezados adicionales.
  
 **Cuerpo de la solicitud** - ninguno.
  
 **Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado** - una operación correcta devuelve el código de estado 200 (OK). Si un usuario especificado que no se encuentra el identificador, devuelve el código de estado 404 (no encontrado).
  
 **Encabezados de respuesta** - sin encabezados adicionales.
  
 **Cuerpo de la respuesta** : a continuación es una carga de respuesta de ejemplo en JSON.
  
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

El objeto de elemento devuelto por la operación de subelementos sólo contiene los tres campos siguientes. 
  
 *itemId* - ID del elemento.
  
 *userId* : identificador del usuario que es propietario de este elemento.
  
 *tipo* : el tipo de contenido. Este campo está definido por las aplicaciones.
  
> [!NOTE]
>  `Content`y `subItems` campos no se incluyen en la respuesta al reducir la cantidad de datos que se transmiten por la red.
  

