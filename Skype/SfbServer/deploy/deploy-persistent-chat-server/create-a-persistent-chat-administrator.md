---
title: Crear un administrador de chat persistente en Skype Empresarial Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 'Resumen: Leer este tema para aprender a crear una función de administrador de servidor de charla persistente para habilitar la configuración inicial y la administración de servicios de Chat persistentes en Skype para Business Server 2015.'
ms.openlocfilehash: 4efe5dff2821784a24f51712b8a19dad83e47c3b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a>Crear un administrador de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para aprender a crear una función de administrador de servidor de charla persistente para habilitar la configuración inicial y la administración de servicios de Chat persistentes en Skype para Business Server 2015.
  
En Skype para Business Server, los usuarios que realizan tareas específicas deben asignarse como miembros de grupos específicos de uno o más. Control de acceso basado en roles (RBAC) se utiliza para conceder privilegios asignando usuarios a Skype predefinido para las funciones administrativas de Business Server. Estos roles corresponden a los grupos de seguridad universal de los Servicios de dominio de Active Directory. Los miembros del grupo de seguridad Administrador de Chat persistentes, CsPersistentChatAdministrator, se conceden acceso a los cmdlets persistente Chat Server, que se pueden ejecutar usando el Skype para el Shell de administración de servidor de negocios o el Skype para empresas Panel de Control de servidor.
  
Antes de configurar y administrar el servidor de chat persistente, asegúrese de que los derechos y permisos de usuario adecuados se encuentren en el lugar correcto, y que no se agregue ningún usuario que actuará como administrador de chat persistente al grupo de seguridad de administrador de chat persistente.
  
## <a name="create-a-persistent-chat-administrator"></a>Crear un administrador de chat persistente

Para agregar un usuario al grupo de seguridad Administrador de Chat persistentes, CsPersistentChatAdministrator, siga estos pasos:
  
1. Con una cuenta que tenga permisos para modificar la permanencia de un grupo de Active Directory, inicie sesión en un equipo en el que se hayan instalado los usuarios y equipos de Active Directory.
    
2. Haga clic en Inicio, en Todos los programas, en Herramientas administrativas y, luego, en Usuarios y equipos de Active Directory.
    
3. En Usuarios y equipos de Active Directory, expanda el nombre de su dominio y haga clic en el contenedor Usuarios.
    
4. Haga clic con el botón secundario en el grupo de seguridad CsPersistentChatAdministrator y, luego, seleccione Propiedades.
    
5. En el cuadro de diálogo Propiedades, en la ficha Miembros, haga clic en Agregar.
    
6. En el cuadro de diálogo Seleccionar usuarios, equipos, contactos o grupos, escriba el nombre del usuario o el nombre para mostrar del usuario que se desea agregar al grupo en el cuadro Escribir los nombres de objeto para seleccionar y, luego, haga clic en Aceptar.
    
7. En el cuadro de diálogo Propiedades, haga clic en Aceptar.
    

