---
title: Conseguir que los usuarios
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
description: 'Resumen: Conozca la operación obtener usuarios, que forma parte del servicio de usuario de. El servicio de usuario forma parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: ed26614c0fd4b443e9c5d698d1db9467291ca3d0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="get-users"></a>Conseguir que los usuarios
 
**Resumen:** Obtener información sobre la operación de obtener usuarios, que forma parte del servicio de usuario de. El servicio de usuario forma parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.
  
La operación de obtener usuarios forma parte del servicio de usuario de la API de repositorio para llamar al panel de calidad.
  
## <a name="get-users"></a>Conseguir que los usuarios

Obtener una rentabilidad de los usuarios una lista de usuarios en el repositorio.
  
|**Método**|**URI de la solicitud**|**Versión de HTTP**|
|:-----|:-----|:-----|
|Obtener  <br/> |https://\<portal\>/QoERepositoryService/repository/user  <br/> |HTTP/1.1  <br/> |
   
 **URI parámetros** : ninguno.
  
 **Encabezados de solicitud** - sin encabezados adicionales.
  
 **Cuerpo de la solicitud** - ninguno.
  
 **Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado** - una operación correcta devuelve el código de estado 200 (OK).
  
 **Encabezados de respuesta** - sin encabezados adicionales.
  
 **Cuerpo de la respuesta** : a continuación es una carga de respuesta de ejemplo en JSON.
  
> [!NOTE]
> Se devuelve una matriz de objetos de usuario. Para obtener más información acerca del objeto de usuario, consulte obtener el usuario. 
  
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


