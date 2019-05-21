---
title: Obtener usuario
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Resumen: Obtenga información sobre la operación obtener usuario, que es parte del servicio de usuario. El servicio de usuario es parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 6c38bb2db2bef1a21dfc5c4791de7a163c57ff5f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274600"
---
# <a name="get-user"></a>Obtener usuario
 
**Resumen:** Obtenga más información sobre la operación obtener usuario, que es parte del servicio de usuario. El servicio de usuario es parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.
  
La operación obtener usuarios forma parte del servicio de usuario en la API del repositorio para el panel de calidad de llamadas.
  
## <a name="get-user"></a>Obtener usuario

Obtener el usuario devuelve un registro de usuario del repositorio.
  
|**Método**|**Solicitar URI**|**Versión HTTP**|
|:-----|:-----|:-----|
|Obtener  <br/> |https://\<portal\>/QoERepositoryService/Repository/User/{userId}  <br/> |HTTP/1.1  <br/> |
   
 **Parámetros de URI** : ninguno.
  
 **Solicitar encabezados** : no hay encabezados adicionales.
  
 **Solicitar cuerpo** : ninguno.
  
 **Respuesta** : la respuesta incluye un código de estado http y un conjunto de encabezados de respuesta.
  
 **Código de estado** : una operación correcta devuelve el código de estado 200 (correcto). Si no se encuentra un identificador de usuario especificado, devuelve el código de estado 404 (no se encontró).
  
 **Encabezados de respuesta** : no hay encabezados adicionales.
  
 **Cuerpo de respuesta** : a continuación se muestra un ejemplo de carga de respuesta en JSON.
  
```
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 ** ID. de usuario.
  
 *loginName* : identificación de usuario externo para usuarios comunes. Si se usa la autenticación de Windows para autenticar a los usuarios, esto puede ser un FQDN del usuario.
  
 *defaultItemId* : identificador del elemento predeterminado para este usuario. El elemento predeterminado es el elemento de nivel superior asociado al usuario. El resto de los elementos a los que pertenece este usuario se puede navegar desde el elemento predeterminado.
  
> [!NOTE]
> Proporcione el `defaultItemId` valor para la operación obtener elemento para recuperar los detalles del elemento predeterminado.
  

