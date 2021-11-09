---
title: Servicio de usuario para CQD
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Summary: Learn about the User Service, which is part of the Repository API for Call Quality Dashboard. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: e8be18304cad02e1ed39cf84327a58f84d134c6d
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851013"
---
# <a name="user-service-for-cqd"></a>Servicio de usuario para CQD
 
**Resumen:** Obtenga información sobre el Servicio de usuario, que forma parte de la API de repositorio para el Panel de calidad de llamadas. Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.
  
El servicio de usuario forma parte de la API de repositorio para el Panel de calidad de llamadas.
  
## <a name="user-service"></a>Servicio de usuario

La API de repositorio proporciona un modelo de administración de usuarios simplificado donde el aprovisionamiento de usuarios (creación de nuevas cuentas de usuario) es automático e implícito. Cuando un usuario realiza una solicitud en la API de repositorio por primera vez, el repositorio crea un nuevo registro de usuario. 
  
El Panel de calidad de llamadas también crea automáticamente elementos dedicados para el usuario nuevo. Los nuevos elementos dedicados al usuario son clones completos de los elementos del usuario del sistema. De este modo, los usuarios comienzan con sus propias copias de informes y consultas que pueden empezar a personalizar inmediatamente. 
  
> [!NOTE]
> Con el Panel de calidad de llamadas, los usuarios pueden restablecer sus elementos dedicados en cualquier momento. 
  
 **Id. de usuario especial**
  
La API de repositorio incluye URI de API de REST que espera que un valor entero especifique un usuario determinado. Ejemplo:  `https://<portal>/QoERepositoryService/repository/user/{userId}` . Aquí, {userId} debe reemplazarse por un valor entero como 0, 1, etc.
  
Además, la API de repositorio aceptará dos id. de usuario especiales en {userId} en URI.
  
-  *predeterminado:*  representa el usuario que está interactuando actualmente con la API. Esto permite que las aplicaciones obtengan acceso al contenido del usuario actual sin realizar un seguimiento del valor real del identificador de usuario. Ejemplo: `https://<portal>/QoERepositoryService/repository/user/default`.
    
-  *system:*  representa al usuario del sistema. Esto permite que las aplicaciones accedan al contenido del usuario del sistema sin conocer el valor real del identificador de usuario. Ejemplo: `https://<portal>/QoERepositoryService/repository/user/system`.
    
A menos que se indique lo contrario, los id. de usuario especiales se pueden usar en {userId} en URI. 
  
Las operaciones rest se incluyen en la tabla siguiente.
  
|**Operación**|**Descripción**|
|:-----|:-----|
|[Obtener usuarios](get-users.md) <br/> |Devuelve una lista de usuarios en el repositorio.  <br/> |
|[Obtener usuario](get-user.md) <br/> |Devuelve un registro de usuario.  <br/> |
   

