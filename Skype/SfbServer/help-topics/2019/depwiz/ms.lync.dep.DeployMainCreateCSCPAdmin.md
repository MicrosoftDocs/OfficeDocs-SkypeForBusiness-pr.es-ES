---
title: Crear administradores del Panel de control de Skype Empresarial Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para conceder acceso a la Skype Empresarial Server, haga lo siguiente:'
ms.openlocfilehash: 191149db88df737d0f20cdeb510bb03b4f17ddc40a4e85918240571a50ba5e5e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282163"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a>Crear administradores del Panel de control de Skype Empresarial Server
 
Para conceder acceso a la Skype Empresarial Server, haga lo siguiente:
  
1. Inicie sesión como miembro del grupo Admins. del dominio o del grupo RTCUniversalServerAdmins.
    
2. Abra **Usuarios y equipos de Active Directory**, expanda el dominio, haga clic con el botón secundario en el contenedor **Usuarios** y, a continuación, haga clic en **Propiedades**.
    
3. En **Propiedades de CSAdministrator**, haga clic en la pestaña **Miembros**.
    
4. En la pestaña Miembros, haga clic en **Agregar**. En **Seleccionar usuarios, contactos, equipos, cuentas de servicio o grupos**, busque **Escribir los nombres de objeto para seleccionar**. Escriba el nombre o los nombres de usuario, o bien el nombre o los nombres de grupo que desee agregar al grupo CSAdministrators. Haga clic en **Aceptar**.
    
5. En la pestaña Miembros, confirme que estén los usuarios o los grupos que haya seleccionado. Haga clic en **Aceptar**.
    
> [!TIP]
> El panel Skype Empresarial Server control es una herramienta de control de acceso basada en roles. La pertenencia al grupo CsAdministrator proporciona a un usuario que usa el control total del Panel de control Skype Empresarial Server todas las funciones de configuración disponibles. Hay otros roles disponibles diseñados para funciones específicas. Los usuarios no tienen que estar habilitados para Skype Empresarial Server para poder ser miembros de los grupos de administración. 
  
Otros roles son:
  
- **CsArchiving:** Los miembros de este grupo pueden realizar todas las funciones de archivado, como configurar y administrar el rol servidor de archivado.
    
- **CsHelpDesk:** los miembros de este grupo pueden ver la configuración e implementar, incluidas las directivas y las propiedades de usuario. Asimismo, los miembros pueden llevar a cabo determinadas tareas de solución de problemas.
    
- **CsLocationAdministrator:** los miembros de este grupo son los que tienen el nivel más bajo de derechos asociados con la administración de 9-1-1 mejorado (E9-1-1). Pueden crear ubicaciones e identificadores de red de E9-1-1, y asociarlos en la implementación.
    
- **CsResponseGroupAdministrator:** los miembros pueden administrar y configurar el Servicio de grupo de respuesta.
    
- **CsServerAdministrator:** Los miembros pueden administrar, supervisar y solucionar problemas de todos los servidores que ejecutan Skype Empresarial Server.
    
- **CsUserAdministrator:** los miembros pueden administrar, habilitar y deshabilitar usuarios, y asignar directivas existentes a usuarios.
    
- **CsViewOnlyAdministrator:** Los miembros pueden ver la implementación y configuración de la información del servidor. Esta pertenencia permite a un miembro supervisar el estado de los servidores que ejecutan Skype Empresarial Server.
    
- **CsVoiceAdministrator:** Los miembros pueden crear, configurar y administrar la configuración relacionada con la voz en Skype Empresarial Server.
    
Para ayudar a conservar la seguridad y la integridad del control de acceso basado en roles, agregue usuarios a los grupos que definan qué rol desempeña el usuario en la administración de la Skype Empresarial Server implementación.
  

