---
title: Obtener la configuración de usuario
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Resumen: Obtenga información acerca de la operación de obtener la configuración de usuario, que es parte del servicio de configuración de usuario. El servicio de configuración de usuario es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 41bc45f63366337000ad8c263ff8e6dbcb36a3b3
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375382"
---
# <a name="get-user-settings"></a>Obtener la configuración de usuario
 
**Resumen:** Obtenga información acerca de la operación de obtener la configuración de usuario, que es parte del servicio de configuración de usuario. El servicio de configuración de usuario es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server 2015.
  
La operación de obtener la configuración de usuario es parte del servicio de configuración de usuario de la API de repositorio para llamar al panel de calidad.
  
## <a name="get-user-settings"></a>Obtener la configuración de usuario

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