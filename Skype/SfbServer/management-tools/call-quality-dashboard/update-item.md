---
title: Actualizar elemento
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Resumen: Obtenga información acerca de la operación Actualizar elemento, que es parte del servicio de elemento. El servicio de elemento es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: 3ac56b8761f565663ffaa689c666e285b2347ed5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217652"
---
# <a name="update-item"></a>Actualizar elemento
 
**Resumen:** Obtenga información acerca de la operación Actualizar elemento, que es parte del servicio de elemento. El servicio de elemento es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.
  
La operación Actualizar elemento es parte del servicio de elemento de la API de repositorio para llamar al panel de calidad.
  
## <a name="update-item"></a>Actualizar elemento

Actualizar elemento de actualiza un elemento específico en el repositorio.
  

|**(Método)**|**URI de la solicitud**|**Versión de HTTP**|
|:-----|:-----|:-----|
|PUT  <br/> |https://\<portal\>/QoERepositoryService/repository/elemento / {itemId}  <br/> |HTTP/1.1  <br/> |
   
 **Los parámetros URI** - ninguno.
  
 **Encabezados de solicitud** -contenido-tipo: application/json.
  
 **Cuerpo de la convocatoria** - JSON.
  
Carga de solicitudes de ejemplo:
  
```
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *contenido*  Datos se almacenen como el nuevo contenido de un elemento subcaracterística existente con formato JSON. Técnicamente, un repositorio puede almacenar cualquier contenido de cualquier esquema, pero cuando se usa para llamar al panel de calidad, debe ser un informe o una consulta. *tipo de*  Especifique siempre "application/json" para llamar al panel de calidad.
  
 **Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado** - una operación correcta devuelve código de estado 204 (sin contenido). Si no se encuentra un identificador de elemento especificado, devuelve el código de estado 404 (no encontrado).
  
> [!IMPORTANT]
> "Sin contenido" no es un estado de error. Esto significa que una respuesta no devolvió nada en el cuerpo (en contraste, 200 devuelve Aceptar el contenido de cuerpo). Indica que el elemento se ha actualizado correctamente. 
  
 **Encabezados de respuesta** : ninguno.
  
 **Cuerpo de la respuesta** - ninguno.
  

