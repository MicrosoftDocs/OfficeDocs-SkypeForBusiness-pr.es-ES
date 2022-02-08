---
title: Actualizar elemento
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
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Resumen: obtenga información sobre la operación Actualizar elemento, que forma parte del servicio de elementos. El servicio de elementos forma parte de la API de repositorio para el Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: 9ea8a72f70b252cb44a1e4cb15e24cc3718e4be2
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384258"
---
# <a name="update-item"></a>Actualizar elemento
 
**Resumen:** Obtenga información sobre la operación Actualizar elemento, que forma parte del servicio de elementos. El servicio de elementos forma parte de la API de repositorio para el Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.
  
La operación Actualizar elemento forma parte del servicio de elementos de la API de repositorio para el Panel de calidad de llamadas.
  
## <a name="update-item"></a>Actualizar elemento

Actualizar elemento actualiza un elemento específico en el repositorio.
  

|**Método**|**URI de solicitud**|**Versión HTTP**|
|:-----|:-----|:-----|
|PUT  <br/> |\<portal\>https:///QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **Parámetros uri** : ninguno.
  
 **Encabezados de** solicitud -Content-Type: application/json.
  
 **Cuerpo de la** solicitud: JSON.
  
Carga de solicitud de ejemplo:
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *contenido*  Datos con formato JSON que se almacenarán como el nuevo contenido de un sub-elemento existente. Técnicamente, un repositorio puede almacenar cualquier contenido de cualquier esquema, pero cuando se usa para el Panel de calidad de llamadas, debe ser un informe o una consulta. *tipo*  Especifique siempre "application/json" para el Panel de calidad de llamadas.
  
 **Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado** : una operación correcta devuelve el código de estado 204 (Sin contenido). Si no se encuentra un identificador de elemento especificado, devuelve el código de estado 404 (No encontrado).
  
> [!IMPORTANT]
> "Sin contenido" no es un estado de error. Significa que una respuesta no devuelve nada en el cuerpo (en cambio, 200 Ok devuelve contenido en Body). Indica que el elemento se actualizó correctamente. 
  
 **Encabezados de respuesta** : ninguno.
  
 **Cuerpo de la** respuesta: ninguno.
  

