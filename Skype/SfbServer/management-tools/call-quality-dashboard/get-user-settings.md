---
title: Obtener configuración de usuario
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Summary: Learn about the Get User Configuración operation, which is part of the User Configuración Service. El servicio de Configuración usuario forma parte de la API de repositorio para el Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: b7be08df46aa63287d931a566d26671bfecfc3b8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778180"
---
# <a name="get-user-settings"></a>Obtener configuración de usuario
 
**Resumen:** Obtenga información sobre la operación Obtener Configuración usuario, que forma parte del Servicio de Configuración usuario. El servicio de Configuración usuario forma parte de la API de repositorio para el Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.
  
La operación Obtener Configuración usuario forma parte del Servicio de Configuración usuario en la API de repositorio para el Panel de calidad de llamadas.
  
## <a name="get-user-settings"></a>Obtener configuración de usuario

Get User Configuración devuelve una lista de opciones de configuración para un usuario especificado.
  

|**Método**|**URI de solicitud**|**Versión HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting  <br/> |HTTP/1.1  <br/> |
   
 **Parámetros de URI**
  
- *efectivo:*  opcional. Este parámetro solo se aplica cuando se usa el identificador de usuario especial predeterminado. En otros casos, se omitirá. `True` devuelve una configuración de usuario eficaz `false` y devuelve solo la configuración de usuario (valor predeterminado).
    
  **Encabezados de solicitud:** no hay encabezados adicionales.
  
  **Cuerpo de la** solicitud: ninguno.
  
  **Respuesta:** la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
  **Código de estado:** una operación correcta devuelve el código de estado 200 (Aceptar).
  
  **Encabezados de respuesta:** no hay encabezados adicionales.
  
  **Cuerpo de la** respuesta: a continuación se muestra una carga de respuesta de ejemplo en JSON.
  
```json
[{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
},
{
"userId": 6,
"key": "ShowTimeStamps",
"value": "true"
}]
```
