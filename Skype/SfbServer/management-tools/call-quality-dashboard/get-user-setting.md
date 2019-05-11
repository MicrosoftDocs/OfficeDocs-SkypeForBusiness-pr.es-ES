---
title: Obtener configuración de usuario
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: 'Resumen: Obtenga información acerca de la operación de obtener la configuración de usuario, que es parte del servicio de configuración de usuario. El servicio de configuración de usuario es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: 91f8c60a33c6126f61901c4d73e4a6f2c5b5e1f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930731"
---
# <a name="get-user-setting"></a>Obtener configuración de usuario
 
**Resumen:** Obtenga información acerca de la operación de obtener la configuración de usuario, que es parte del servicio de configuración de usuario. El servicio de configuración de usuario es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.
  
La operación de obtener la configuración de usuario es parte del servicio de configuración de usuario de la API de repositorio para llamar al panel de calidad.
  
## <a name="get-user-setting"></a>Obtener configuración de usuario

Obtener configuración de usuario devuelve una configuración de usuario único.
  

|**(Método)**|**URI de la solicitud**|**Versión de HTTP**|
|:-----|:-----|:-----|
|Obtener  <br/> |https://\<portal\>/QoERepositoryService/repositorio/usuario / {userId} /setting/ {clave}  <br/> |HTTP/1.1  <br/> |
   
 **Los parámetros URI** - ninguno.
  
 **Encabezados de solicitud** - sin encabezados adicionales.
  
 **Cuerpo de la convocatoria** - ninguno.
  
 **Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado** - una operación correcta devuelve código de estado 200 (Aceptar).
  
 **Encabezados de respuesta** - sin encabezados adicionales.
  
 **Cuerpo de la respuesta** - a continuación es una carga de respuesta de ejemplo en JSON.
  
```
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 *userId* : identificador del usuario.
  
 *clave* : clave de la configuración.
  
 *valor* : valor de la opción.
  

