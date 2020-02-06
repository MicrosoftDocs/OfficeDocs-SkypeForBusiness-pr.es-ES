---
title: Servicio de usuario para el CQD
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Resumen: Obtenga información sobre el servicio de usuario, que forma parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.'
ms.openlocfilehash: 439df99c1c9d66547e681fdea90b33c6295344db
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816659"
---
# <a name="user-service-for-cqd"></a>Servicio de usuario para el CQD
 
**Resumen:** Obtenga más información sobre el servicio de usuario, que es parte de la API del repositorio para el panel de calidad de llamadas. El panel de calidad de llamadas es una herramienta para Skype empresarial Server.
  
El servicio de usuario es parte de la API del repositorio para el panel de calidad de llamadas.
  
## <a name="user-service"></a>Servicio de usuario

La API de repositorio ofrece un modelo de administración de usuarios simplificado donde el aprovisionamiento de usuarios (la creación de nuevas cuentas de usuario) es automático e implícito. Cuando un usuario hace una solicitud para la API de Repository por primera vez, el repositorio crea un nuevo registro de usuario. 
  
El panel de calidad de llamadas también crea automáticamente un usuario específico para el nuevo usuario. Los nuevos elementos dedicados al usuario son clones completos de los elementos del usuario del sistema. De esta manera, los usuarios comienzan con sus propias copias de informes y consultas que pueden empezar a personalizar de inmediato. 
  
> [!NOTE]
> Con el panel de calidad de llamadas, los usuarios pueden restablecer sus artículos dedicados en cualquier momento. 
  
 **Identificadores de usuario especiales**
  
La API de repositorio incluye URI de API de REST que espera un valor entero para especificar un usuario en particular. Ejemplo: `https://<portal>/QoERepositoryService/repository/user/{userId}`. Aquí, {userId} debe sustituirse por un valor entero, como 0, 1, etc.
  
Además, la API de repositorio aceptará dos identificadores de usuario especiales en {userId} en los URI.
  
-  *default* : representa el usuario que está interactuando actualmente con la API. Esto permite que las aplicaciones tengan acceso al contenido del usuario actual sin mantener el seguimiento del valor real del identificador de usuario. Ejemplo: `https://<portal>/QoERepositoryService/repository/user/default`.
    
-  *sistema* : representa al usuario del sistema. Esto permite que las aplicaciones tengan acceso al contenido del usuario del sistema sin conocer el valor real del identificador de usuario. Ejemplo: `https://<portal>/QoERepositoryService/repository/user/system`.
    
A menos que se indique lo contrario, los identificadores de usuario especiales se pueden usar en {userId} en URI. 
  
Las operaciones de REST se incluyen en la tabla siguiente.
  
|**Operación**|**Descripción**|
|:-----|:-----|
|[Obtener usuarios](get-users.md) <br/> |Devuelve una lista de los usuarios del repositorio.  <br/> |
|[Obtener usuario](get-user.md) <br/> |Devuelve un registro de usuario.  <br/> |
   

