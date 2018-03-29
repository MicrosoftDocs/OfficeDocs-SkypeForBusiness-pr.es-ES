---
title: Obtener elementos
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: 'Resumen: Conozca la operación obtener elementos, que forma parte del elemento de servicio. El servicio del elemento es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 526d578d65ded98a6cd1a5cfc09a6749319683c3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="get-items"></a>Obtener elementos
 
**Resumen:** Obtener información sobre la operación de obtener elementos, que forma parte del elemento de servicio. El servicio del elemento es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.
  
La operación de obtener elementos forma parte del elemento de servicio en la API de repositorio para llamar al panel de calidad.
  
## <a name="get-items"></a>Obtener elementos

Obtener elementos devuelve todos los elementos en el repositorio.
  
|**Método**|**URI de la solicitud**|**Versión de HTTP**|
|:-----|:-----|:-----|
|Obtener  <br/> |https://\<portal\>/QoERepositoryService/repository/item  <br/> |HTTP/1.1  <br/> |
   
 **URI parámetros** : ninguno.
  
 **Encabezados de solicitud** - sin encabezados adicionales.
  
 **Cuerpo de la solicitud** - ninguno.
  
 **Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado** - una operación correcta devuelve el código de estado 200 (OK).
  
 **Encabezados de respuesta** - sin encabezados adicionales.
  
 **Cuerpo de la respuesta** : a continuación es una carga de respuesta de ejemplo en JSON.
  
> [!NOTE]
> Se devuelve una matriz de objetos de elemento. Para obtener más información acerca del objeto Item, consulte obtener el elemento. 
  
```
[{
"itemId": 1652,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1654,
"userId": 0,
"type": "application/json"
}]

```


