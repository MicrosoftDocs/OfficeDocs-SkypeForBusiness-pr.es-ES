---
title: Obtener configuración de usuario
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Resumen: Obtenga información sobre la operación obtener configuración de usuario, que es parte del servicio de configuración de usuario. El servicio de configuración de usuario es parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 8d1bb1da9e9a186cbc10f0c8ba36275348bb7267
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274621"
---
# <a name="get-user-settings"></a>Obtener configuración de usuario
 
**Resumen:** Obtenga más información sobre la operación obtener configuración del usuario, que es parte del servicio de configuración de usuario. El servicio de configuración de usuario es parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.
  
La operación obtener configuración del usuario es parte del servicio de configuración de usuario en la API del repositorio para el panel de calidad de llamadas.
  
## <a name="get-user-settings"></a>Obtener configuración de usuario

Obtener configuración de usuario devuelve una lista de opciones de configuración para un usuario especificado.
  

|**Método**|**Solicitar URI**|**Versión HTTP**|
|:-----|:-----|:-----|
|Obtener  <br/> |https://\<portal\>/QoERepositoryService/Repository/User/{userId}/setting  <br/> |HTTP/1.1  <br/> |
   
 **Parámetros de URI**
  
- *eficaz* : opcional. Este parámetro solo se aplica cuando se usa el identificador de usuario especial predeterminado. En otros casos, se omitirá. `True`Devuelve la configuración de usuario `false` eficaz y devuelve solo la configuración del usuario (valor predeterminado).
    
  **Solicitar encabezados** : no hay encabezados adicionales.
  
  **Solicitar cuerpo** : ninguno.
  
  **Respuesta** : la respuesta incluye un código de estado http y un conjunto de encabezados de respuesta.
  
  **Código de estado** : una operación correcta devuelve el código de estado 200 (correcto).
  
  **Encabezados de respuesta** : no hay encabezados adicionales.
  
  **Cuerpo de respuesta** : a continuación se muestra un ejemplo de carga de respuesta en JSON.
  
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
