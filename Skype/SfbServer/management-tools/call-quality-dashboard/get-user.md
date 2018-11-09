---
title: Obtener el usuario
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: 'Resumen: Obtenga información acerca de la operación obtener usuario, que es parte del servicio de usuario. El servicio de usuario es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: 3508336eda934cf317f857d7ad7e903cb7298e00
ms.sourcegitcommit: b680505c5dad435d98fbd0b235e0e7c67b9d8c9c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2018
ms.locfileid: "26035592"
---
# <a name="get-user"></a>Obtener el usuario
 
**Resumen:** Obtenga información acerca de la operación obtener usuario, que es parte del servicio de usuario. El servicio de usuario es parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.
  
La operación de obtener los usuarios es parte del servicio de usuario de la API de repositorio para llamar al panel de calidad.
  
## <a name="get-user"></a>Obtener el usuario

Obtener devuelve de usuario en un registro de usuario desde el repositorio.
  
|**(Método)**|**URI de la solicitud**|**Versión de HTTP**|
|:-----|:-----|:-----|
|Obtener  <br/> |https://\<portal\>/QoERepositoryService/repository/usuario / {userId}  <br/> |HTTP/1.1  <br/> |
   
 **Los parámetros URI** - ninguno.
  
 **Encabezados de solicitud** - sin encabezados adicionales.
  
 **Cuerpo de la convocatoria** - ninguno.
  
 **Respuesta** : la respuesta incluye un código de estado HTTP y un conjunto de encabezados de respuesta.
  
 **Código de estado** - una operación correcta devuelve código de estado 200 (Aceptar). Si un usuario especificado que no se encuentra el identificador, devuelve el código de estado 404 (no encontrado).
  
 **Encabezados de respuesta** - sin encabezados adicionales.
  
 **Cuerpo de la respuesta** - a continuación es una carga de respuesta de ejemplo en JSON.
  
```
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 *userId* : identificador del usuario.
  
 *loginName* - identificación de usuarios externos para los usuarios normales. Si se usa la autenticación de Windows para autenticar a los usuarios, esto puede resultar un FQDN del usuario.
  
 *defaultItemId* - ID del elemento predeterminado para este usuario. El valor predeterminado de elemento es el elemento de nivel superior que está asociado al usuario. Todos los demás elementos que posee este usuario se pueden navegar desde el elemento predeterminado.
  
> [!NOTE]
> Proporcionar la `defaultItemId` valor de la operación de obtener elemento para recuperar los detalles del elemento predeterminado.
  

