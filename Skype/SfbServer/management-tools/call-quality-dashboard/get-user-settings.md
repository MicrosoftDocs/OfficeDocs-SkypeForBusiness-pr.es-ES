---
title: Obtener configuración de usuario
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Resumen: Obtenga información acerca de la operación de obtener la configuración de usuario, que es parte del servicio de configuración de usuario. El servicio de configuración de usuario es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: 3c94f02f305ee2f779b6a31ef78bea875d462cbf
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889024"
---
# <a name="get-user-settings"></a>Obtener configuración de usuario
 
**Resumen:** Obtenga información acerca de la operación de obtener la configuración de usuario, que es parte del servicio de configuración de usuario. El servicio de configuración de usuario es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.
  
La operación de obtener la configuración de usuario es parte del servicio de configuración de usuario de la API de repositorio para llamar al panel de calidad.
  
## <a name="get-user-settings"></a>Obtener configuración de usuario

Configuración del usuario Get devuelve una lista de valores para un usuario especificado.
  

|**(Método)**|**URI de la solicitud**|**Versión de HTTP**|
|:-----|:-----|:-----|
|Obtener  <br/> |https://\<portal\>/QoERepositoryService/repository/usuario / {userId} / configuración  <br/> |HTTP/1.1  <br/> |
   
 **Parámetros URI**
  
- *eficaz* - opcional. Este parámetro aplica sólo cuando se usa el valor predeterminado de identificador de usuario especiales. En otros casos, se omitirá. `True`Devuelve la configuración de usuario eficaz y `false` devuelve la configuración del usuario (valor predeterminado).
    
  **Encabezados de solicitud** - sin encabezados adicionales.
  
  **Cuerpo de la convocatoria** - ninguno.
  
  **Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
  **Código de estado** - una operación correcta devuelve código de estado 200 (Aceptar).
  
  **Encabezados de respuesta** - sin encabezados adicionales.
  
  **Cuerpo de la respuesta** - a continuación es una carga de respuesta de ejemplo en JSON.
  
```
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
