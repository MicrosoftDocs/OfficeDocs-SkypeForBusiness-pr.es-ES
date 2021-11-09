---
title: Crear un administrador de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Summary: Read this topic to learn how to create a Persistent Chat Server administrator role to enable initial configuration and management of Persistent Chat services in Skype Empresarial Server 2015.'
ms.openlocfilehash: c8878867d05b285e8275e63ba2e6e16a83b0a82e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60846973"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a>Crear un administrador de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información sobre cómo crear un rol de administrador del servidor de chat persistente para habilitar la configuración inicial y la administración de los servicios de chat persistente en Skype Empresarial Server 2015.
  
En Skype Empresarial Server, los usuarios que realizan tareas específicas deben asignarse como miembros de uno o más grupos específicos. Role-Based control de acceso (RBAC) se usa para conceder privilegios mediante la asignación de usuarios a roles Skype Empresarial Server administrativos predefinidos. Estos roles corresponden a grupos de seguridad universales en servicios de dominio de Active Directory. Los miembros del grupo de seguridad Administrador de chat persistente, CsPersistentChatAdministrator, tienen acceso a los cmdlets del servidor de chat persistente, que se pueden ejecutar mediante el Shell de administración de Skype Empresarial Server o el Panel de control de Skype Empresarial Server.
  
Antes de configurar y administrar el servidor de chat persistente, asegúrese de que los derechos y permisos de usuario adecuados están en su lugar y de que los usuarios que actuarán como administradores de chat persistente se agregarán al grupo de seguridad Administrador de chat persistente.
  
> [!NOTE] 
> El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, vea [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Si necesita usar el chat persistente, las opciones son migrar usuarios que requieren esta funcionalidad a Teams, o bien seguir usando Skype Empresarial Server 2015.

## <a name="create-a-persistent-chat-administrator"></a>Crear un administrador de chat persistente

Para agregar un usuario al grupo de seguridad Administrador de chat persistente, CsPersistentChatAdministrator, siga estos pasos:
  
1. Con una cuenta que tenga permiso para modificar la pertenencia a un grupo de Active Directory, inicie sesión en un equipo donde se hayan instalado usuarios y equipos de Active Directory.
    
2. Haga clic en Inicio, en Todos los programas, en Herramientas administrativas y después en Usuarios y equipos de Active Directory.
    
3. En Usuarios y equipos de Active Directory, expanda el nombre de su dominio y haga clic en el contenedor Usuarios.
    
4. Haga clic con el botón secundario en el grupo de seguridad CsPersistentChatAdministrator y, a continuación, haga clic en Propiedades.
    
5. En el cuadro de diálogo Propiedades, en la pestaña Miembros, haga clic en Agregar.
    
6. En el cuadro de diálogo Seleccionar usuarios, equipos, contactos o grupos, escriba el nombre de usuario o el nombre para mostrar del usuario que se va a agregar al grupo en el cuadro Escribir los nombres de objeto que se van a seleccionar y, a continuación, haga clic en Aceptar.
    
7. En el cuadro de diálogo Propiedades, haga clic en Aceptar.
    

