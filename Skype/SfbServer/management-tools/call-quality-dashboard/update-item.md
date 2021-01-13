---
title: Actualizar elemento
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Resumen: obtenga información sobre la operación Actualizar elemento, que forma parte del servicio de elementos. El servicio de elementos forma parte de la API de repositorio para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: 78da2fa414b4ba266f9e6aba4feac5ff73150062
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803090"
---
# <a name="update-item"></a>Actualizar elemento
 
**Resumen:** Obtenga información sobre la operación Actualizar elemento, que forma parte del servicio de elementos. El servicio de elementos forma parte de la API de repositorio para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.
  
La operación Actualizar elemento forma parte del servicio de elementos en la API de repositorio para el panel de calidad de llamadas.
  
## <a name="update-item"></a>Actualizar elemento

Actualizar elemento actualiza un elemento específico en el repositorio.
  

|**Método**|**URI de solicitud**|**Versión HTTP**|
|:-----|:-----|:-----|
|PUT  <br/> |https:// \<portal\> /QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **Parámetros uri:** ninguno.
  
 **Encabezados de** solicitud -Content-Type: application/json.
  
 **Cuerpo de la** solicitud: JSON.
  
Carga de solicitud de ejemplo:
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *content*  Datos con formato JSON que se almacenarán como el nuevo contenido de un sub item existente. Técnicamente, un repositorio puede almacenar cualquier contenido de cualquier esquema, pero cuando se usa para el Panel de calidad de llamadas, debe ser un informe o una consulta. *type*  Especifique siempre "application/json" para el Panel de calidad de llamadas.
  
 **Respuesta:** la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado:** una operación correcta devuelve el código de estado 204 (sin contenido). Si no se encuentra un identificador de elemento especificado, devuelve el código de estado 404 (No encontrado).
  
> [!IMPORTANT]
> "Sin contenido" no es un estado de error. Esto significa que una respuesta no deseó nada en el cuerpo (en cambio, 200 OK devuelve contenido en Body). Indica que el elemento se actualizó correctamente. 
  
 **Encabezados de respuesta:** ninguno.
  
 **Cuerpo de la** respuesta: ninguno.
  

