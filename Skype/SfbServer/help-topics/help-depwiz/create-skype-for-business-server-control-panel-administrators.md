---
title: Crear administradores del Panel de control de Skype Empresarial Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
description: 'Para conceder acceso a Skype empresarial Server 2015, haga lo siguiente:'
ms.openlocfilehash: f5300f9d3bf63e9deea103eb09e5a705953761d8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823754"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a>Crear administradores del Panel de control de Skype Empresarial Server
 
Para conceder acceso a Skype empresarial Server 2015, haga lo siguiente:
  
1. Inicie sesión como miembro del grupo Admins. del dominio o del grupo RTCUniversalServerAdmins.
    
2. Abra **Usuarios y equipos de Active Directory**, expanda el dominio, haga clic con el botón secundario en el contenedor **Usuarios** y, a continuación, haga clic en **Propiedades**.
    
3. En **Propiedades de CSAdministrator**, haga clic en la pestaña **Miembros**.
    
4. En la pestaña Miembros, haga clic en **Agregar**. En **Seleccionar usuarios, contactos, equipos, cuentas de servicio o grupos**, busque **Escribir los nombres de objeto para seleccionar**. Escriba el nombre o los nombres de usuario, o bien el nombre o los nombres de grupo que desee agregar al grupo CSAdministrators. Haga clic en **Aceptar**.
    
5. En la pestaña Miembros, confirme que estén los usuarios o los grupos que haya seleccionado. Haga clic en **Aceptar**.
    
> [!TIP]
> El panel de control de Skype empresarial Server es una herramienta de control de acceso basada en roles. La pertenencia al grupo CsAdministrator ofrece a un usuario que usa el control total del panel de control de Skype empresarial Server para todas las funciones de configuración disponibles. Hay otros roles disponibles diseñados para funciones específicas. Los usuarios no tienen que estar habilitados para Skype empresarial Server a fin de que se hagan miembros de los grupos de administración. 
  
Otros roles son:
  
- **CsArchiving:** Los miembros de este grupo pueden realizar todas las funciones de archivado, como la configuración y la administración del rol de servidor de archivado.
    
- **CsHelpDesk:** los miembros de este grupo pueden ver la configuración e implementar, incluidas las directivas y las propiedades de usuario. Asimismo, los miembros pueden llevar a cabo determinadas tareas de solución de problemas.
    
- **CsLocationAdministrator:** los miembros de este grupo son los que tienen el nivel más bajo de derechos asociados con la administración de 9-1-1 mejorado (E9-1-1). Pueden crear ubicaciones e identificadores de red de E9-1-1, y asociarlos en la implementación.
    
- **CsResponseGroupAdministrator:** los miembros pueden administrar y configurar el Servicio de grupo de respuesta.
    
- **CsServerAdministrator:** Los miembros pueden administrar, supervisar y solucionar problemas en todos los servidores que ejecutan Skype empresarial Server.
    
- **CsUserAdministrator:** los miembros pueden administrar, habilitar y deshabilitar usuarios, y asignar directivas existentes a usuarios.
    
- **CsViewOnlyAdministrator:** Los miembros pueden ver la implementación y la configuración de la información del servidor. Esta pertenencia permite a un miembro supervisar el estado de los servidores que ejecutan Skype empresarial Server 2015.
    
- **CsVoiceAdministrator:** Los miembros pueden crear, configurar y administrar la configuración relacionada con la voz en Skype empresarial Server.
    
Para ayudar a retener la seguridad y la integridad de control de acceso basada en roles, agregue usuarios a los grupos que definen qué función realiza el usuario en la administración de la implementación de Skype empresarial Server.
  

