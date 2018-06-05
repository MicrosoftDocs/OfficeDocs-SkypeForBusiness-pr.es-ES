---
title: Obtención de usuarios
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 'Resumen: Obtenga información acerca de la operación obtener los usuarios, que es parte del servicio de usuario. El servicio de usuario es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: 4d4de424776514479ed2204eeb0a5315a7323662
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569701"
---
# <a name="get-users"></a>Obtención de usuarios
 
**Resumen:** Obtenga información acerca de la operación obtener los usuarios, que es parte del servicio de usuario. El servicio de usuario es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server 2015.
  
La operación de obtener los usuarios es parte del servicio de usuario de la API de repositorio para llamar al panel de calidad.
  
## <a name="get-users"></a>Obtención de usuarios

Obtener una lista de los usuarios de devuelve los usuarios en el repositorio.
  
|**(Método)**|**URI de la solicitud**|**Versión de HTTP**|
|:-----|:-----|:-----|
|Obtener  <br/> |https://\<portal\>/QoERepositoryService/repository/user  <br/> |HTTP/1.1  <br/> |
   
 **Los parámetros URI** - ninguno.
  
 **Encabezados de solicitud** - sin encabezados adicionales.
  
 **Cuerpo de la convocatoria** - ninguno.
  
 **Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado** - una operación correcta devuelve código de estado 200 (Aceptar).
  
 **Encabezados de respuesta** - sin encabezados adicionales.
  
 **Cuerpo de la respuesta** - a continuación es una carga de respuesta de ejemplo en JSON.
  
> [!NOTE]
> Se devuelve una matriz de objetos de usuario. Para obtener información detallada sobre el objeto de usuario, vea obtener el usuario. 
  
```
[{
"userId": 0,
"loginName": "system",
"defaultItemId": 1652
},
{
"userId": 1,
"loginName": "SAMPLEDOMAIN\\testuser1",
"defaultItemId": 1652
},
{
"userId": 2,
"loginName": "SAMPLEDOMAIN\\testuser2",
"defaultItemId": 1774
}]
```


