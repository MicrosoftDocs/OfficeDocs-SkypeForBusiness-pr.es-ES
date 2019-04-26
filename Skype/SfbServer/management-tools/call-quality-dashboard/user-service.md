---
title: Servicio de usuario para CQD
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Resumen: Información sobre el servicio de usuario, que forma parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.'
ms.openlocfilehash: 4ee4594e86b14655c94472b516b9e04da674e3f0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217645"
---
# <a name="user-service-for-cqd"></a>Servicio de usuario para CQD
 
**Resumen:** Obtenga información sobre el servicio de usuario, que forma parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de llamada es una herramienta de Skype para Business Server.
  
El servicio de usuario es parte de la API de repositorio para llamar al panel de calidad.
  
## <a name="user-service"></a>Servicio de usuario

Repositorio de API proporciona un modelo de administración de usuario simplificada donde aprovisionamiento (creación de nuevas cuentas de usuario) del usuario es automática e implícita. Cuando un usuario realiza una solicitud de la API de repositorio por primera vez, el repositorio crea un nuevo registro de usuario. 
  
Panel de calidad también crea automáticamente un usuario de llamada dedicado elementos para el nuevo usuario. Los nuevos elementos de usuario dedicada sean copias completados de los elementos del usuario del sistema. De este modo, los usuarios comienzan con sus propias copias de los informes y las consultas que puede iniciar inmediatamente personalización. 
  
> [!NOTE]
> Con el panel de calidad de llamadas, los usuarios pueden restablecer sus elementos dedicados en cualquier momento. 
  
 **Identificadores de usuario especiales**
  
API del depósito incluye a REST API URIs que espera un valor entero para especificar un usuario en particular. Ejemplo: `https://<portal>/QoERepositoryService/repository/user/{userId}`. En este caso, {userId} debe reemplazarse por un valor entero como 0, 1, etcetera.
  
Además, API de repositorio aceptará dos identificadores de usuario especial en {userId} en los URI.
  
-  *predeterminado* - representa el usuario que actualmente está interactuando con la API. Esto permite a las aplicaciones tener acceso a contenido del usuario actual sin seguimiento del valor de identificador de usuario real. Ejemplo: ` https://<portal>/QoERepositoryService/repository/user/default`.
    
-  *sistema* - representa el usuario del sistema. Esto permite a las aplicaciones tener acceso a contenido del usuario del sistema sin necesidad de conocer el valor de identificador de usuario real. Ejemplo: `https://<portal>/QoERepositoryService/repository/user/system`.
    
A menos que se indique lo contrario, se pueden usar los identificadores de usuario especial en {userId} en los URI. 
  
Las operaciones de REST se incluyen en la siguiente tabla.
  
|**Operación**|**Descripción**|
|:-----|:-----|
|[Obtener usuarios](get-users.md) <br/> |Devuelve una lista de los usuarios en el repositorio.  <br/> |
|[Obtener usuario](get-user.md) <br/> |Devuelve un registro de usuario.  <br/> |
   

