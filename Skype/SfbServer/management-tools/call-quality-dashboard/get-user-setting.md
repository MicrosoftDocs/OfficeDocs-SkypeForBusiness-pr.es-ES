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
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 'Resumen: obtenga información sobre la operación Obtener configuración de usuario, que forma parte del servicio de configuración de usuario. El servicio de configuración de usuario forma parte de la API de repositorio para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: 82632f5de7ae215d6f34d9f0b39e500fb713a1be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832490"
---
# <a name="get-user-setting"></a>Obtener configuración de usuario
 
**Resumen:** Obtenga información sobre la operación Obtener configuración de usuario, que forma parte del Servicio de configuración de usuario. El servicio de configuración de usuario forma parte de la API de repositorio para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.
  
La operación Obtener configuración de usuario forma parte del Servicio de configuración de usuario en la API de repositorio para el panel de calidad de llamadas.
  
## <a name="get-user-setting"></a>Obtener configuración de usuario

Obtener configuración de usuario devuelve una configuración de usuario único.
  

|**Método**|**URI de solicitud**|**Versión HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting/{key}  <br/> |HTTP/1.1  <br/> |
   
 **Parámetros de URI:** ninguno.
  
 **Encabezados de solicitud:** no hay encabezados adicionales.
  
 **Cuerpo de la** solicitud: ninguno.
  
 **Respuesta:** la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado:** una operación correcta devuelve el código de estado 200 (Correcto).
  
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
  
 *clave:*  clave de la configuración.
  
 *valor:*  valor de la configuración.
  

