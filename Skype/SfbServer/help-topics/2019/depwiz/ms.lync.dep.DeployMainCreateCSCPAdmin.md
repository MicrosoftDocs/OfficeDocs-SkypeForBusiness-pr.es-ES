---
title: Crear administradores del Panel de control de Skype Empresarial Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para conceder acceso a la Skype para Business Server, realice lo siguiente:'
ms.openlocfilehash: c0f30910fb6f39f5e2f81b054ec2ca39dac742e4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897298"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a>Crear administradores del Panel de control de Skype Empresarial Server
 
Para conceder acceso a la Skype para Business Server, realice lo siguiente:
  
1. Inicie sesión como miembro del grupo Admins. del dominio o del grupo RTCUniversalServerAdmins.
    
2. Abra **Usuarios y equipos de Active Directory**, expanda el dominio, haga clic con el botón secundario en el contenedor **Usuarios** y, a continuación, haga clic en **Propiedades**.
    
3. En **Propiedades de CSAdministrator**, haga clic en la pestaña **Miembros**.
    
4. En la pestaña Miembros, haga clic en **Agregar**. En **Seleccionar usuarios, contactos, equipos, cuentas de servicio o grupos**, busque **Escribir los nombres de objeto para seleccionar**. Escriba el nombre o los nombres de usuario, o bien el nombre o los nombres de grupo que desee agregar al grupo CSAdministrators. Haga clic en **Aceptar**.
    
5. En la pestaña Miembros, confirme que estén los usuarios o los grupos que haya seleccionado. Haga clic en **Aceptar**.
    
> [!TIP]
> El Skype para el Panel de Control de servidor empresarial es una herramienta de control de acceso basado en roles. Pertenencia al grupo CsAdministrator proporciona a un usuario que está usando el Skype para control total del Panel de Control de servidor empresarial para todas las funciones de configuración disponibles. Hay otros roles disponibles diseñados para funciones específicas. Los usuarios no tienen a habilitarse para Skype para Business Server con el fin de hacerse miembros de los grupos de administración. 
  
Otras funciones incluyen:
  
- **CsArchiving:** Los miembros de este grupo pueden realizar todas las funciones de archivado, como la configuración y administración de la función de servidor de archivado.
    
- **CsHelpDesk:** los miembros de este grupo pueden ver la configuración e implementar, incluidas las directivas y las propiedades de usuario. Asimismo, los miembros pueden llevar a cabo determinadas tareas de solución de problemas.
    
- **CsLocationAdministrator:** los miembros de este grupo son los que tienen el nivel más bajo de derechos asociados con la administración de 9-1-1 mejorado (E9-1-1). Pueden crear ubicaciones e identificadores de red de E9-1-1, y asociarlos en la implementación.
    
- **CsResponseGroupAdministrator:** los miembros pueden administrar y configurar el Servicio de grupo de respuesta.
    
- **CsServerAdministrator:** Los miembros pueden administrar, supervisar y solucionar problemas de todos los servidores que ejecutan Skype para Business Server.
    
- **CsUserAdministrator:** los miembros pueden administrar, habilitar y deshabilitar usuarios, y asignar directivas existentes a usuarios.
    
- **CsViewOnlyAdministrator:** Los miembros pueden ver la implementación y configuración de la información del servidor. Esta pertenencia permite un miembro para supervisar el estado de los servidores que ejecutan Skype para Business Server.
    
- **CsVoiceAdministrator:** Los miembros pueden crear, configurar y administrar las opciones relacionadas con la voz de Skype para Business Server.
    
Para ayudar a mantener la seguridad y la integridad del control de acceso basado en roles, agregar usuarios a los grupos que definen qué rol realiza el usuario en administración de la Skype para la implementación de Business Server.
  

