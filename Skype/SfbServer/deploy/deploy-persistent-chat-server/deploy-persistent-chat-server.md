---
title: Implementar el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: 'Resumen: Lea este tema para obtener información sobre cómo implementar Skype for Business Server 2015 Persistent Chat Server.'
ms.openlocfilehash: 2b88d20437a85c9a634bf8a156a3dcec214c60fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894468"
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>Implementar el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información sobre cómo implementar Skype for Business Server 2015 Persistent Chat Server.
  
Para implementar el servidor de Chat persistente,: 
  
- Usar el generador de topología para definir, o importar y posteriormente publicar su topología y los componentes que se van a implementar
    
- Preparar el entorno para implementar componentes de servidor de Chat persistente
    
- Instalar y configurar componentes de servidor de Chat persistente para la implementación
    
Antes de implementar servidores de Chat persistente, debe leer [Plan for Persistent Chat Server in Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Los temas sobre la planeación describen los requisitos de hardware y software, las topologías posibles y los escenarios de combinación. 
  
> [!NOTE] 
> Chat persistente está disponible en Skype para Business Server 2015, pero ya no se admite en Skype para Business Server 2019. La misma funcionalidad está disponible en los equipos. Para obtener más información, vea [viaje de Skype para la empresa a los equipos de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si necesita usar chat en grupo, las opciones son para migrar los usuarios que requieren esta funcionalidad a los equipos, o para continuar usando Skype para Business Server 2015. 

## <a name="deployment-checklist"></a>Lista de comprobación de la implementación

Puede implementar servidor de Chat persistente después de implementar su topología inicial, incluidos al menos un Skype para grupo de negocio de servidor Front-End o un Skype para servidor Standard Edition de negocio. La lista de comprobación de implementación describe los pasos básicos necesarios para implementar el servidor de Chat persistente y proporciona vínculos para obtener más detalles.
  
**Proceso de implementación del servidor de Chat en grupo**

|**Tarea**|**Pasos**|**Roles y pertenencias a grupos necesarios**|**Temas relacionados**|
|:-----|:-----|:-----|:-----|
|**Instalar los requisitos previos de hardware y software** <br/> | En un hardware que cumpla los requisitos del sistema, instale los siguientes elementos: <br/>  En el Persistent Chat servidores Front-End de servidor: <br/>  Un sistema operativo que cumpla los requisitos del sistema <br/>  Requisitos previos de software para equipos que ejecutan Skype para Business Server <br/>  En el servidor que se va a hospedar la base de datos del servidor de Chat persistente: <br/>  Una versión compatible de SQL Server <br/>  Si es necesario cumplimiento del servidor de Chat persistente: <br/>  SQL Server en el servidor que se va a hospedar la base de datos de cumplimiento del servidor de Chat persistente <br/> |Cualquier usuario que pertenezca al grupo de administradores locales.  <br/> |[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**Crear la topología interna adecuada para admitir el servidor de Chat persistente (y opcionalmente, cumplimiento de Chat persistente)** <br/> | Ejecute el generador de topología para agregar un grupo de servidores de Chat persistente a la topología: <br/>  Agregar componentes de servidor de Chat persistente a la topología <br/>  Crear una base de datos de SQL Server para el almacén del servidor de Chat persistente (y una copia de seguridad de SQL Server para la recuperación ante desastres) <br/>  Definir un nuevo Skype para almacén de archivos de negocio o usar un Skype existente para el almacén de archivos de negocio para los archivos del servidor de Chat persistente <br/>  Asociar el Skype para grupo de servidores de negocio que puede enrutar solicitudes a este grupo de servidores de servidor de Chat persistente <br/>  Si se necesita el cumplimiento del chat persistente: <br/>  Agregar almacén de cumplimiento de normas de Chat persistente <br/>  Haga clic en la casilla de verificación servidor de Chat persistente definición de grupo para habilitar el cumplimiento <br/>  Publique la topología. <br/>  Si instala el servidor de Chat persistente en Standard Edition, el nombre de dominio completo (FQDN) del grupo de servidores de Chat persistente debe coincidir con el servidor Standard Edition, y las bases de datos de SQL Server se instalan en la instancia de SQL Server Express en el estándar Server Edition <br/> |Para definir una topología, una cuenta que pertenezca al grupo de usuarios locales.  <br/> Para publicar la topología, una cuenta que sea miembro del grupo Administradores del dominio y grupo RTCUniversalServerAdmins y el usuario también debe tener permisos de control total (lectura/escritura/modificar) en el Skype para almacén de archivos de negocio para los archivos del servidor de Chat persistente (es así que el generador de topología puede configurar las DACL necesarias).  <br/> |[Crear y publicar una nueva topología en Skype Empresarial Server 2015](../../deploy/install/create-and-publish-new-topology.md) <br/> [Agregar servidor de Chat persistente a su Skype para topología empresarial Server 2015](add-persistent-chat-server.md) <br/> |
|**Implementar el servidor de chat persistente** <br/> | Ejecute el Skype para el programa de instalación de Business Server en todos los equipos que ejecutan el servidor de Chat persistente. El programa de instalación de servidor de Chat persistente está integrado en el Skype para el Asistente para la implementación de servidor de negocio que proporciona las siguientes instrucciones: <br/>  Implemente el almacén de administración local. <br/>  Instalar servicios de Chat persistente <br/>  Solicite y asigne los certificados. <br/>  Ejecute e inicie los servicios. <br/> |Cualquier usuario que pertenezca al grupo de administradores locales.  <br/> |[Implementar el servidor de chat persistente en Skype Empresarial Server 2015](deploy-persistent-chat-server.md) <br/> |
|**Crear un administrador de chat persistente** <br/> |Agregue usuarios al grupo de seguridad CsPersistentChatAdministrator.  <br/> |Cualquier usuario que pertenezca al grupo de administradores de dominio.  <br/> |[Crear un administrador de chat persistente en Skype Empresarial Server 2015](create-a-persistent-chat-administrator.md) <br/> |
|**Configurar el servidor de chat persistente** <br/> | Configure usuarios: <br/>  El usuario tiene a habilitarse mediante la directiva de acceso al servidor de Chat persistente. De manera predeterminada, la directiva está desactivada para todos los usuarios, y se puede definir en el ámbito global, de sitio, de grupo o de usuario. <br/>  Defina la configuración <br/> |El usuario necesita pertenecer al grupo CsPersistentChatAdministrator. Para cambiar la directiva, es preciso que el usuario sea miembro de CsUserAdministrator, como mínimo.  <br/> |[Administrar el servidor de chat persistente en Skype Empresarial Server 2015](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

