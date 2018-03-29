---
title: Servicio de usuario para CQD
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/18/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: 'Resumen: Conozca el servicio de usuario, que forma parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.'
ms.openlocfilehash: c4bb2395ea3fa4541140a7966bbfb554ef53c168
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="user-service-for-cqd"></a>Servicio de usuario para CQD
 
**Resumen:** Obtenga información acerca del servicio de usuario, que forma parte de la API de repositorio para llamar al panel de calidad. Panel de calidad de la llamada es una herramienta de Skype para Business Server 2015.
  
El servicio de usuario forma parte de la API de repositorio para llamar al panel de calidad.
  
## <a name="user-service"></a>Servicio de usuario

API del depósito proporciona un modelo de administración de usuario simplificado donde usuario provisioning (creación de nuevas cuentas de usuario) es implícita y automática. Cuando un usuario realiza una solicitud de la API del depósito por primera vez, el repositorio crea un nuevo registro de usuario. 
  
Panel de calidad también crea automáticamente un usuario de llamada dedicado elementos para el nuevo usuario. Los nuevos elementos de usuario dedicado son clones completos de los elementos del usuario del sistema. De este modo, los usuarios comienzan con sus propias copias de informes y consultas que pueden iniciar inmediatamente personalizar. 
  
> [!NOTE]
> Con llamar al panel de calidad, los usuarios pueden restablecer sus elementos dedicados en cualquier momento. 
  
 **Identificadores de usuario especial**
  
API del depósito incluye a resto API URIs que espera un valor entero para especificar un usuario en particular. Ejemplo: `https://<portal>/QoERepositoryService/repository/user/{userId}`. En este caso, {ID} debe reemplazarse por un valor entero como 0, 1, etcetera.
  
Por otra parte, API de repositorio aceptará dos identificadores de usuario especial en {ID} de URI.
  
-  *predeterminado* - representa el usuario que actualmente está interactuando con la API. Esto permite que las aplicaciones tengan acceso a contenido del usuario actual sin seguimiento del valor de ID de usuario real. Ejemplo: ` https://<portal>/QoERepositoryService/repository/user/default`.
    
-  *sistema* - representa el usuario del sistema. Esto permite que las aplicaciones tengan acceso a contenido del usuario del sistema sin conocer el valor de ID de usuario real. Ejemplo: `https://<portal>/QoERepositoryService/repository/user/system`.
    
A menos que se indique lo contrario, se pueden utilizar los identificadores de usuario especial en {ID} en identificadores URI. 
  
Las operaciones de resto se incluyen en la tabla siguiente.
  
|**Operación**|**Descripción**|
|:-----|:-----|
|[Conseguir que los usuarios](get-users.md) <br/> |Devuelve una lista de usuarios del repositorio.  <br/> |
|[Obtener usuario](get-user.md) <br/> |Devuelve un registro de usuario.  <br/> |
   

