---
title: Servicio de usuario para CQD
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Resumen: obtenga información sobre el servicio de usuario, que forma parte de la API de repositorio para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.'
ms.openlocfilehash: d9f4b771a1bf5efeece4f8fb87195d8567f0426e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803080"
---
# <a name="user-service-for-cqd"></a>Servicio de usuario para CQD
 
**Resumen:** Obtenga información sobre el servicio de usuario, que forma parte de la API de repositorio para el panel de calidad de llamadas. El Panel de calidad de llamadas es una herramienta para Skype Empresarial Server.
  
El servicio de usuario forma parte de la API de repositorio para el panel de calidad de llamadas.
  
## <a name="user-service"></a>Servicio de usuario

La API de repositorio proporciona un modelo de administración de usuarios simplificado donde el aprovisionamiento de usuarios (creación de cuentas de usuario nuevas) es automático e implícito. Cuando un usuario realiza una solicitud a la API de repositorio por primera vez, el repositorio crea un nuevo registro de usuario. 
  
El Panel de calidad de llamadas también crea automáticamente elementos dedicados para el nuevo usuario. Los nuevos elementos dedicados del usuario son clones completos de los elementos del usuario del sistema. De esta forma, los usuarios empiezan con sus propias copias de informes y consultas que pueden empezar a personalizar inmediatamente. 
  
> [!NOTE]
> Con el Panel de calidad de llamadas, los usuarios pueden restablecer sus elementos dedicados en cualquier momento. 
  
 **Id. de usuario especiales**
  
La API de repositorio incluye URI de API de REST que espera que un valor entero especifique un usuario determinado. Ejemplo:  `https://<portal>/QoERepositoryService/repository/user/{userId}` . Aquí, {userId} debe reemplazarse por un valor entero como 0, 1, etc.
  
Además, la API de repositorio aceptará dos id. de usuario especiales en {userId} en URI.
  
-  *predeterminado:*  representa el usuario que está interactuando actualmente con la API. Esto permite que las aplicaciones accedan al contenido del usuario actual sin realizar un seguimiento del valor real del identificador de usuario. Ejemplo: `https://<portal>/QoERepositoryService/repository/user/default`.
    
-  *system:*  representa al usuario del sistema. Esto permite que las aplicaciones obtengan acceso al contenido del usuario del sistema sin conocer el valor real del identificador de usuario. Ejemplo: `https://<portal>/QoERepositoryService/repository/user/system`.
    
A menos que se indique lo contrario, los id. de usuario especiales se pueden usar en {userId} en URI. 
  
Las operaciones rest se incluyen en la tabla siguiente.
  
|**Operación**|**Descripción**|
|:-----|:-----|
|[Obtener usuarios](get-users.md) <br/> |Devuelve una lista de usuarios en el repositorio.  <br/> |
|[Obtener usuario](get-user.md) <br/> |Devuelve un registro de usuario.  <br/> |
   

