---
title: Actualizar artículo
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 6/8/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: 'Resumen: Conozca la operación de actualización elemento, que es parte del elemento de servicio. El servicio del elemento es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 04a0ebf29537bbc2e62e6d5b35008fe9e329ab4f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="update-item"></a>Actualizar artículo
 
**Resumen:** Obtener información sobre la operación de actualización elemento, que es parte del elemento de servicio. El servicio del elemento es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.
  
La operación de actualización artículo es parte del elemento de servicio en la API de repositorio para llamar al panel de calidad.
  
## <a name="update-item"></a>Actualizar artículo

Elemento de actualización actualiza un elemento específico en el repositorio.
  

|**Método**|**URI de la solicitud**|**Versión de HTTP**|
|:-----|:-----|:-----|
|PUT  <br/> |https://\<portal\>/QoERepositoryService/repository/elemento / {itemId}  <br/> |HTTP/1.1  <br/> |
   
 **URI parámetros** : ninguno.
  
 **Encabezados de solicitud** -contenido-tipo: application/json.
  
 **Cuerpo de la solicitud** - JSON.
  
Carga de solicitud de ejemplo:
  
```
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *contenido*  JSON con formato de datos que se almacenen como el nuevo contenido de un elemento secundario existente. Técnicamente, un repositorio puede almacenar cualquier contenido de cualquier esquema, pero cuando se utiliza para llamar al panel de calidad, debe ser un informe o una consulta. *tipo*  Especifique siempre "application/json" para llamar al panel de calidad.
  
 **Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado** - una operación correcta devuelve el código de estado 204 (sin contenido). Si no se encuentra un identificador de elemento especificado, devuelve el código de estado 404 (no encontrado).
  
> [!IMPORTANT]
> "Sin contenido" no es un estado de error. Significa que una respuesta no devolvió nada en el cuerpo (en contraste, 200 devuelve Aceptar contenido cuerpo). Indica que el elemento se ha actualizado correctamente. 
  
 **Encabezados de respuesta** : ninguno.
  
 **Cuerpo de la respuesta** : ninguno.
  

