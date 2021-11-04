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
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 'Summary: Learn about the Get User Setting operation, which is part of the User Configuración Service. El servicio de Configuración usuario forma parte de la API de repositorio para el Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: 2be81d09c45a93c967af2556ba7ed8fbca9ce0f9
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774630"
---
# <a name="get-user-setting"></a>Obtener configuración de usuario
 
**Resumen:** Obtenga información sobre la operación Obtener configuración de usuario, que forma parte del servicio de Configuración usuario. El servicio de Configuración usuario forma parte de la API de repositorio para el Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.
  
La operación Obtener configuración de usuario forma parte del Servicio de Configuración usuario en la API de repositorio para el Panel de calidad de llamadas.
  
## <a name="get-user-setting"></a>Obtener configuración de usuario

Obtener configuración de usuario devuelve una única configuración de usuario.
  

|**Método**|**URI de solicitud**|**Versión HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting/{key}  <br/> |HTTP/1.1  <br/> |
   
 **Parámetros uri:** ninguno.
  
 **Encabezados de solicitud:** no hay encabezados adicionales.
  
 **Cuerpo de la** solicitud: ninguno.
  
 **Respuesta:** la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado:** una operación correcta devuelve el código de estado 200 (Aceptar).
  
 **Encabezados de respuesta:** no hay encabezados adicionales.
  
 **Cuerpo de la** respuesta: a continuación se muestra una carga de respuesta de ejemplo en JSON.
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 *userId:*  id. del usuario.
  
 *key:*  clave de la configuración.
  
 *value:*  valor de la configuración.
  

