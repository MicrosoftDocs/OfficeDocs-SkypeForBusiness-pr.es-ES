---
title: Crear un administrador de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Resumen: Lea este tema para obtener información sobre cómo crear un rol de administrador del servidor de chat persistente para habilitar la configuración inicial y la administración de los servicios de chat persistentes en Skype empresarial Server 2015.'
ms.openlocfilehash: 987183b8ca5cc32e2888040b43d61e5d6fcac09b
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41794108"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a>Crear un administrador de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información sobre cómo crear un rol de administrador del servidor de chat persistente para habilitar la configuración inicial y la administración de los servicios de chat persistentes en Skype empresarial Server 2015.
  
En Skype empresarial Server, los usuarios que realizan tareas específicas deben asignarse como miembros de uno o varios grupos específicos. El control de acceso basado en roles (RBAC) se usa para conceder privilegios asignando a los usuarios a roles administrativos predefinidos de Skype empresarial Server. Estos roles corresponden a los grupos de seguridad universal de los Servicios de dominio de Active Directory. Los miembros del grupo de seguridad de administrador de chat persistente, CsPersistentChatAdministrator, tienen acceso a los cmdlets del servidor de chat persistentes, que se pueden ejecutar con el shell de administración de Skype empresarial Server o Skype empresarial. Panel de control del servidor.
  
Antes de configurar y administrar el servidor de chat persistente, asegúrese de que los derechos y permisos de usuario adecuados se encuentren en el lugar correcto, y que no se agregue ningún usuario que actuará como administrador de chat persistente al grupo de seguridad de administrador de chat persistente.
  
> [!NOTE] 
> Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams](/microsoftteams/upgrade-start-here). Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015.

## <a name="create-a-persistent-chat-administrator"></a>Create a Persistent Chat administrator

Para agregar un usuario al grupo de seguridad del administrador de chat persistente, CsPersistentChatAdministrator, siga estos pasos:
  
1. Con una cuenta que tenga permisos para modificar la permanencia de un grupo de Active Directory, inicie sesión en un equipo en el que se hayan instalado los usuarios y equipos de Active Directory.
    
2. Haga clic en Inicio, en Todos los programas, en Herramientas administrativas y, luego, en Usuarios y equipos de Active Directory.
    
3. En Usuarios y equipos de Active Directory, expanda el nombre de su dominio y haga clic en el contenedor Usuarios.
    
4. Haga clic con el botón secundario en el grupo de seguridad CsPersistentChatAdministrator y, luego, seleccione Propiedades.
    
5. En el cuadro de diálogo Propiedades, en la ficha Miembros, haga clic en Agregar.
    
6. En el cuadro de diálogo Seleccionar usuarios, equipos, contactos o grupos, escriba el nombre del usuario o el nombre para mostrar del usuario que se desea agregar al grupo en el cuadro Escribir los nombres de objeto para seleccionar y, luego, haga clic en Aceptar.
    
7. En el cuadro de diálogo Propiedades, haga clic en Aceptar.
    

