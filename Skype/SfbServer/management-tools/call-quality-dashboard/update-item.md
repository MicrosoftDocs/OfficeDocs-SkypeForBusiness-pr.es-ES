---
title: Actualizar elemento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Resumen: Obtenga información sobre la operación de actualización de elementos, que es parte del servicio de elementos. El servicio de artículo forma parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 460e6b26375bba28887d170c9827864bfc600138
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816679"
---
# <a name="update-item"></a>Actualizar elemento
 
**Resumen:** Obtenga más información sobre la operación de actualización de elementos, que es parte del servicio de elementos. El servicio de artículo forma parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.
  
La operación actualizar elemento forma parte del servicio de elemento en la API del repositorio para el panel de calidad de llamadas.
  
## <a name="update-item"></a>Actualizar elemento

Actualizar elemento actualiza un elemento específico en el repositorio.
  

|**Método**|**Solicitar URI**|**Versión HTTP**|
|:-----|:-----|:-----|
|CORRER  <br/> |https://\<portal\>/QoERepositoryService/Repository/Item/{Itemid}  <br/> |HTTP/1.1  <br/> |
   
 **Parámetros de URI** : ninguno.
  
 **Solicitar encabezados** -tipo de contenido: aplicación/JSON.
  
 **Solicitar cuerpo** : JSON.
  
Carga de solicitud de ejemplo:
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *contenido*  Datos con formato JSON que se almacenan como el nuevo contenido de un elemento secundario existente. Técnicamente, un repositorio puede almacenar cualquier contenido de cualquier esquema, pero cuando se usa para el panel de calidad de llamadas, debe ser un informe o una consulta. *Escriba*  Especifica siempre "Application/JSON" para el panel de calidad de llamadas.
  
 **Respuesta** : la respuesta incluye un código de estado http y un conjunto de encabezados de respuesta.
  
 **Código de estado** : una operación correcta devuelve el código de estado 204 (sin contenido). Si no se encuentra un identificador de elemento especificado, devuelve el código de estado 404 (no se encontró).
  
> [!IMPORTANT]
> "Sin contenido" no es un estado de error. Significa que una respuesta no devolvió nada en el cuerpo (por el contrario, 200 aceptar devuelve contenido en cuerpo). Indica que el elemento se ha actualizado correctamente. 
  
 **Encabezados de respuesta** : ninguno.
  
 **Cuerpo** de la respuesta: ninguno.
  

