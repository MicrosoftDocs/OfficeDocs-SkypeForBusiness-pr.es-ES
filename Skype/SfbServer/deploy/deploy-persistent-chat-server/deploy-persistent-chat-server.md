---
title: Implementar el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: 'Resumen: lea este tema para obtener información sobre cómo implementar el servidor de chat persistente de Skype Empresarial Server 2015.'
ms.openlocfilehash: 60dbabc84e278f6add3b7de408787f4969a164a7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830480"
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>Implementar el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información sobre cómo implementar el servidor de chat persistente de Skype Empresarial Server 2015.
  
Para implementar el servidor de chat persistente, haga lo siguiente: 
  
- Usar el Generador de topologías para definir o importar y, posteriormente, publicar la topología y los componentes que desea implementar
    
- Preparar el entorno para implementar componentes del servidor de chat persistente
    
- Instalar y configurar componentes del servidor de chat persistente para la implementación
    
Antes de implementar el servidor de chat persistente, debe leer [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). En los temas de planeación se describen los requisitos de hardware y software, las topologías posibles y los escenarios de colocación. 
  
> [!NOTE] 
> El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no es compatible con Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte [Introducción a la actualización de Microsoft Teams.](/microsoftteams/upgrade-start-here) Si necesita usar el chat persistente, puede migrar usuarios que requieran esta funcionalidad a Teams o seguir usando Skype Empresarial Server 2015. 

## <a name="deployment-checklist"></a>Lista de comprobación de implementación

Puede implementar el servidor de chat persistente después de implementar la topología inicial, incluido al menos un grupo de servidores front-end de Skype Empresarial Server o un servidor Standard Edition de Skype Empresarial. La lista de comprobación de implementación describe los pasos básicos necesarios para implementar el servidor de chat persistente y proporciona vínculos para obtener más información.
  
**Proceso de implementación del servidor de chat persistente**

|**Task**|**Pasos**|**Roles y pertenencias a grupos necesarios**|**Temas relacionados**|
|:-----|:-----|:-----|:-----|
|**Instalar los requisitos previos de hardware y software** <br/> | En un hardware que cumpla los requisitos del sistema, instale los siguientes elementos: <br/>  En los servidores front-end del servidor de chat persistente: <br/>  Un sistema operativo que cumpla los requisitos del sistema <br/>  Requisitos previos de software para equipos que ejecutan Skype Empresarial Server <br/>  En el servidor que hospedará la base de datos del servidor de chat persistente: <br/>  Una versión compatible de SQL Server <br/>  Si se requiere el cumplimiento del servidor de chat persistente: <br/>  SQL Server en el servidor que hospedará la base de datos de cumplimiento del servidor de chat persistente <br/> |Cualquier usuario que pertenezca al grupo de administradores locales.  <br/> |[Requisitos del servidor para Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Requisitos del entorno para Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**Crear la topología interna adecuada para admitir el servidor de chat persistente (y, opcionalmente, el cumplimiento de chat persistente)** <br/> | Ejecute topology Builder para agregar un grupo de servidores de chat persistente a la topología: <br/>  Agregar componentes del servidor de chat persistente a la topología <br/>  Crear una base SQL Server de datos para el almacén del servidor de chat persistente (y una copia de seguridad SQL Server para la recuperación ante desastres) <br/>  Definir un nuevo almacén de archivos de Skype Empresarial o usar un almacén de archivos de Skype Empresarial existente para archivos de servidor de chat persistente <br/>  Asociar el grupo de Skype Empresarial Server que puede enrutar las solicitudes a este grupo de servidores de chat persistente <br/>  Si se requiere cumplimiento de chat persistente: <br/>  Agregar almacén de cumplimiento de chat persistente <br/>  Haga clic en la casilla definición del grupo de servidores de chat persistente para habilitar el cumplimiento <br/>  Publique la topología. <br/>  Si instala el servidor de chat persistente en Standard Edition, el nombre de dominio completo (FQDN) del grupo de servidores de chat persistente debe coincidir con el servidor Standard Edition y las bases de datos de SQL Server se instalan en la instancia de SQL Server Express en el servidor Standard Edition <br/> |Para definir una topología, una cuenta que pertenezca al grupo de usuarios locales.  <br/> Para publicar la topología, una cuenta que sea miembro del grupo Administradores de dominio y del grupo RTCUniversalServerAdmins, y el usuario también debe tener permisos de control total (lectura/escritura/modificación) en el almacén de archivos de Skype Empresarial para los archivos del servidor de chat persistente (de modo que topology Builder pueda configurar las DACL necesarias).  <br/> |[Crear y publicar una topología nueva en Skype Empresarial Server 2015](../../deploy/install/create-and-publish-new-topology.md) <br/> [Agregar un servidor de chat persistente a la topología de Skype Empresarial Server 2015](add-persistent-chat-server.md) <br/> |
|**Implementar el servidor de chat persistente** <br/> | Ejecute el programa de instalación de Skype Empresarial Server en todos los equipos que ejecutan el servidor de chat persistente. La configuración del servidor de chat persistente está integrada en el Asistente para la implementación de Skype Empresarial Server que proporciona las siguientes instrucciones: <br/>  Implemente el almacén de administración local <br/>  Instalar servicios de chat persistente <br/>  Solicite y asigne certificados <br/>  Ejecute e inicie los servicios <br/> |Cualquier usuario que pertenezca al grupo de administradores locales.  <br/> |[Implementar el servidor de chat persistente en Skype Empresarial Server 2015](deploy-persistent-chat-server.md) <br/> |
|**Crear un administrador de chat persistente** <br/> |Agregue usuarios al grupo de seguridad CsPersistentChatAdministrator.  <br/> |Cualquier usuario que pertenezca al grupo de administradores de dominio.  <br/> |[Crear un administrador de chat persistente en Skype Empresarial Server 2015](create-a-persistent-chat-administrator.md) <br/> |
|**Configuración del servidor de chat persistente** <br/> | Configure usuarios: <br/>  El usuario debe estar habilitado por la directiva para tener acceso al servidor de chat persistente. De manera predeterminada, la directiva está desactivada para todos los usuarios, y se puede definir en el ámbito global, de sitio, de grupo o de usuario. <br/>  Defina la configuración <br/> |El usuario debe pertenecer al grupo CsPersistentChatAdministrator. Para cambiar la directiva, el usuario ser miembro de CsUserAdministrator, como mínimo.  <br/> |[Administrar el servidor de chat persistente en Skype Empresarial Server 2015](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

