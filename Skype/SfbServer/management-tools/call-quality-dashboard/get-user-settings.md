---
title: Obtener configuración de usuario
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
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Resumen: obtenga información sobre la operación Obtener configuración de usuario, que forma parte del Servicio de configuración de usuario. El servicio de configuración de usuario forma parte de la API de repositorio para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: e2ebf39ba5a7de5d36a8b1ea0441808b6e71f97b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832480"
---
# <a name="get-user-settings"></a>Obtener configuración de usuario
 
**Resumen:** Obtenga información sobre la operación Obtener configuración de usuario, que forma parte del Servicio de configuración de usuario. El servicio de configuración de usuario forma parte de la API de repositorio para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.
  
La operación Obtener configuración de usuario forma parte del Servicio de configuración de usuario en la API de repositorio para el panel de calidad de llamadas.
  
## <a name="get-user-settings"></a>Obtener configuración de usuario

Obtener configuración de usuario devuelve una lista de configuraciones para un usuario especificado.
  

|**Método**|**URI de solicitud**|**Versión HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting  <br/> |HTTP/1.1  <br/> |
   
 **Parámetros de URI**
  
- *efectivo:*  opcional. Este parámetro solo se aplica cuando se usa el identificador de usuario especial predeterminado. En otros casos, se omitirá. `True` devuelve una configuración de usuario efectiva `false` y devuelve solo la configuración de usuario (valor predeterminado).
    
  **Encabezados de solicitud:** no hay encabezados adicionales.
  
  **Cuerpo de la** solicitud: ninguno.
  
  **Respuesta:** la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
  **Código de estado:** una operación correcta devuelve el código de estado 200 (Correcto).
  
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
