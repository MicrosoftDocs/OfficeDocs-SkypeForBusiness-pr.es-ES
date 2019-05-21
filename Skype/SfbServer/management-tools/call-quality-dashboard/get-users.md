---
title: Obtener usuarios
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 'Resumen: Obtenga información sobre la operación obtener usuarios, que forma parte del servicio de usuario. El servicio de usuario es parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 22223c37dad39f171afc27eb9e0520b8b32335c5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274649"
---
# <a name="get-users"></a>Obtener usuarios
 
**Resumen:** Obtenga más información sobre la operación obtener usuarios, que es parte del servicio de usuario. El servicio de usuario es parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.
  
La operación obtener usuarios forma parte del servicio de usuario en la API del repositorio para el panel de calidad de llamadas.
  
## <a name="get-users"></a>Obtener usuarios

Obtener usuarios devuelve una lista de usuarios del repositorio.
  
|**Método**|**Solicitar URI**|**Versión HTTP**|
|:-----|:-----|:-----|
|Obtener  <br/> |https://\<portal\>/QoERepositoryService/Repository/User  <br/> |HTTP/1.1  <br/> |
   
 **Parámetros de URI** : ninguno.
  
 **Solicitar encabezados** : no hay encabezados adicionales.
  
 **Solicitar cuerpo** : ninguno.
  
 **Respuesta** : la respuesta incluye un código de estado http y un conjunto de encabezados de respuesta.
  
 **Código de estado** : una operación correcta devuelve el código de estado 200 (correcto).
  
 **Encabezados de respuesta** : no hay encabezados adicionales.
  
 **Cuerpo de respuesta** : a continuación se muestra un ejemplo de carga de respuesta en JSON.
  
> [!NOTE]
> Se devuelve una matriz de objetos de usuario. Para obtener más información sobre el objeto de usuario, vea obtener usuario. 
  
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


