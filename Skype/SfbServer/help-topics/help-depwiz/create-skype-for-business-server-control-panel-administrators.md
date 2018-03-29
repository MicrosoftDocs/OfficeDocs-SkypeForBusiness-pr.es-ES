---
title: Crear administradores del Panel de control de Skype Empresarial Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
description: 'Para conceder acceso a la Skype para Business Server 2015, haga lo siguiente:'
ms.openlocfilehash: db781611e2df2abf23c071673d3dfe0570f5700b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a>Crear administradores del Panel de control de Skype Empresarial Server
 
Para conceder acceso a la Skype para Business Server 2015, haga lo siguiente:
  
1. Inicie sesión como miembro del grupo Admins. del dominio o del grupo RTCUniversalServerAdmins.
    
2. Abra **Usuarios y equipos de Active Directory**, expanda el dominio, haga clic con el botón secundario en el contenedor **Usuarios** y, a continuación, haga clic en **Propiedades**.
    
3. En **Propiedades de CSAdministrator**, haga clic en la pestaña **Miembros**.
    
4. En la pestaña Miembros, haga clic en **Agregar**. En **Seleccionar usuarios, contactos, equipos, cuentas de servicio o grupos**, busque **Escribir los nombres de objeto para seleccionar**. Escriba el nombre o los nombres de usuario, o bien el nombre o los nombres de grupo que desee agregar al grupo CSAdministrators. Haga clic en **Aceptar**.
    
5. En la pestaña Miembros, confirme que estén los usuarios o los grupos que haya seleccionado. Haga clic en **Aceptar**.
    
> [!TIP]
> El Skype para Business Server Control Panel es una herramienta de control de acceso basado en funciones. Pertenencia al grupo CsAdministrator da a un usuario que está utilizando el Skype para control total del Panel de Control de servidor de negocios para todas las funciones de configuración disponibles. Hay otros roles disponibles diseñados para funciones específicas. Los usuarios no deben habilitarse para Skype para Business Server con el fin de hacerse miembros de los grupos de administración. 
  
Otras funciones incluyen:
  
- **CsArchiving:** Los miembros de este grupo pueden realizar todas las funciones de archiving, como configurar y administrar la función del servidor de archivado.
    
- **CsHelpDesk:** los miembros de este grupo pueden ver la configuración e implementar, incluidas las directivas y las propiedades de usuario. Asimismo, los miembros pueden llevar a cabo determinadas tareas de solución de problemas.
    
- **CsLocationAdministrator:** los miembros de este grupo son los que tienen el nivel más bajo de derechos asociados con la administración de 9-1-1 mejorado (E9-1-1). Pueden crear ubicaciones e identificadores de red de E9-1-1, y asociarlos en la implementación.
    
- **CsResponseGroupAdministrator:** los miembros pueden administrar y configurar el Servicio de grupo de respuesta.
    
- **CsServerAdministrator:** Los miembros pueden administrar, supervisar y solucionar problemas de todos los servidores de Skype para Business Server.
    
- **CsUserAdministrator:** los miembros pueden administrar, habilitar y deshabilitar usuarios, y asignar directivas existentes a usuarios.
    
- **CsViewOnlyAdministrator:** Los miembros pueden ver la implementación y configuración de la información del servidor. Esta suscripción permite a un miembro para supervisar el estado de los servidores que ejecutan Skype para Business Server 2015.
    
- **CsVoiceAdministrator:** Los miembros pueden crear, configurar y administrar la configuración relacionada con la voz de Skype para Business Server.
    
Para ayudar a mantener la seguridad y la integridad de control de acceso basado en funciones, agregar usuarios a los grupos que definen qué función realiza el usuario en la gestión de la Skype para la implementación de Business Server.
  

