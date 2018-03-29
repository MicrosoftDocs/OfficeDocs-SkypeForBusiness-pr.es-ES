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
description: 'Resumen: Conozca la operación de obtener la configuración de usuario, que es parte del servicio de configuración de usuario. El servicio de configuración de usuario es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 55c3247f0412a9ce10927496ee65255129edfd93
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="get-user-settings"></a>Obtener la configuración de usuario
 
**Resumen:** Obtener información sobre la operación de obtener la configuración de usuario, que es parte del servicio de configuración de usuario. El servicio de configuración de usuario es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.
  
La operación de obtener la configuración de usuario es parte del servicio de configuración de usuario en la API de repositorio para llamar al panel de calidad.
  
## <a name="get-user-settings"></a>Obtener la configuración de usuario

Configuración de usuario de Get devuelve una lista de valores para un usuario especificado.
  

|**Método**|**URI de la solicitud**|**Versión de HTTP**|
|:-----|:-----|:-----|
|Obtener  <br/> |https://\<portal\>/QoERepositoryService/repository/usuario / {ID} / configuración  <br/> |HTTP/1.1  <br/> |
   
 **Parámetros del URI**
  
-  *efectivo* : opcional. Este parámetro aplica únicamente cuando se utiliza el valor predeterminado de ID de usuario especial. En otros casos, se omitirá. `True`Devuelve la configuración de usuario eficaz y `false` devuelve la configuración del usuario (predeterminado).
    
 **Encabezados de solicitud** - sin encabezados adicionales.
  
 **Cuerpo de la solicitud** - ninguno.
  
 **Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado** - una operación correcta devuelve el código de estado 200 (OK).
  
 **Encabezados de respuesta** - sin encabezados adicionales.
  
 **Cuerpo de la respuesta** : a continuación es una carga de respuesta de ejemplo en JSON.
  
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


