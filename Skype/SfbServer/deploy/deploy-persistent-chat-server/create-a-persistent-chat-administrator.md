---
title: Crear un administrador de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Resumen: Lea este tema para obtener información sobre cómo crear un rol de administrador del servidor de Chat persistente para habilitar la configuración inicial y la administración de servicios de Chat persistente en Skype para Business Server 2015.'
ms.openlocfilehash: d483517afcb5d02667d431259f8a2e76804cc32b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894475"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a>Crear un administrador de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información sobre cómo crear un rol de administrador del servidor de Chat persistente para habilitar la configuración inicial y la administración de servicios de Chat persistente en Skype para Business Server 2015.
  
En Skype para Business Server, los usuarios que realizan tareas específicas deben asignarse como miembros de uno o varios grupos específicos. Control de acceso basado en roles (RBAC) se usa para conceder privilegios mediante la asignación de usuarios a Skype predefinido para las funciones administrativas de Business Server. Estos roles corresponden a los grupos de seguridad universal de los Servicios de dominio de Active Directory. Los miembros del grupo de seguridad Persistent Chat Administrator, CsPersistentChatAdministrator, se les concede acceso a los cmdlets de servidor de Chat persistente, que se pueden ejecutar mediante el Skype para Shell de administración de servidor empresarial o el Skype para la empresa Panel de Control de servidor.
  
Antes de configurar y administrar el servidor de chat persistente, asegúrese de que los derechos y permisos de usuario adecuados se encuentren en el lugar correcto, y que no se agregue ningún usuario que actuará como administrador de chat persistente al grupo de seguridad de administrador de chat persistente.
  
> [!NOTE] 
> Chat persistente está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019. La misma funcionalidad está disponible en los equipos. Para obtener más información, vea [viaje de Skype para la empresa a los equipos de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si necesita usar chat en grupo, las opciones son para migrar los usuarios que requieren esta funcionalidad a los equipos, o para continuar usando Skype para Business Server 2015.

## <a name="create-a-persistent-chat-administrator"></a>Create a Persistent Chat administrator

Para agregar un usuario al grupo de seguridad Persistent Chat Administrator, CsPersistentChatAdministrator, realice los pasos siguientes:
  
1. Con una cuenta que tenga permisos para modificar la permanencia de un grupo de Active Directory, inicie sesión en un equipo en el que se hayan instalado los usuarios y equipos de Active Directory.
    
2. Haga clic en Inicio, en Todos los programas, en Herramientas administrativas y, luego, en Usuarios y equipos de Active Directory.
    
3. En Usuarios y equipos de Active Directory, expanda el nombre de su dominio y haga clic en el contenedor Usuarios.
    
4. Haga clic con el botón secundario en el grupo de seguridad CsPersistentChatAdministrator y, luego, seleccione Propiedades.
    
5. En el cuadro de diálogo Propiedades, en la ficha Miembros, haga clic en Agregar.
    
6. En el cuadro de diálogo Seleccionar usuarios, equipos, contactos o grupos, escriba el nombre del usuario o el nombre para mostrar del usuario que se desea agregar al grupo en el cuadro Escribir los nombres de objeto para seleccionar y, luego, haga clic en Aceptar.
    
7. En el cuadro de diálogo Propiedades, haga clic en Aceptar.
    

