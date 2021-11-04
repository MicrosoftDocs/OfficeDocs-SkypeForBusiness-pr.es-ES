---
title: Implementar el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: 'Summary: Read this topic to learn how to deploy Skype Empresarial Server 2015 Persistent Chat Server.'
ms.openlocfilehash: 2fa97848809a05f87a700d71decd2c61be26bb70
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759012"
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>Implementar el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información sobre cómo implementar Skype Empresarial Server servidor de chat persistente de 2015.
  
Para implementar el servidor de chat persistente, debe: 
  
- Use el Generador de topologías para definir o importar y, posteriormente, publicar la topología y los componentes que desea implementar.
    
- Preparar el entorno para implementar componentes del servidor de chat persistente
    
- Instalar y configurar componentes del servidor de chat persistente para la implementación
    
Antes de implementar el servidor de chat persistente, debe leer [Plan for Persistent Chat Server in Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). En los temas de planeación se describen los requisitos de hardware y software, las topologías posibles y los escenarios de colocación. 
  
> [!NOTE] 
> El chat persistente está disponible en Skype Empresarial Server 2015, pero ya no se admite en Skype Empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, vea [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Si necesita usar el chat persistente, las opciones son migrar usuarios que requieren esta funcionalidad a Teams, o bien seguir usando Skype Empresarial Server 2015. 

## <a name="deployment-checklist"></a>Lista de comprobación de implementación

Puede implementar el servidor de chat persistente después de implementar la topología inicial, incluido al menos Skype Empresarial Server grupo de servidores front-end o un Skype Empresarial Standard Edition servidor. La lista de comprobación de implementación describe los pasos básicos necesarios para implementar el servidor de chat persistente y proporciona vínculos para obtener más detalles.
  
**Proceso de implementación del servidor de chat persistente**

|**Tarea**|**Pasos**|**Roles y pertenencias a grupos necesarios**|**Temas relacionados**|
|:-----|:-----|:-----|:-----|
|**Instalar los requisitos previos de hardware y software** <br/> | En un hardware que cumpla los requisitos del sistema, instale los siguientes elementos: <br/>  En los servidores front-end del servidor de chat persistente: <br/>  Un sistema operativo que cumpla los requisitos del sistema <br/>  Requisitos previos de software para equipos que ejecutan Skype Empresarial Server <br/>  En el servidor que hospedará la base de datos del servidor de chat persistente: <br/>  Una versión compatible de SQL Server <br/>  Si se requiere el cumplimiento del servidor de chat persistente: <br/>  SQL Server en el servidor que hospedará la base de datos de cumplimiento del servidor de chat persistente <br/> |Cualquier usuario que pertenezca al grupo de administradores locales.  <br/> |[Requisitos del servidor para Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Requisitos del entorno Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**Crear la topología interna adecuada para admitir el servidor de chat persistente (y, opcionalmente, el cumplimiento de chat persistente)** <br/> | Ejecute el Generador de topologías para agregar un grupo de servidores de chat persistente a la topología: <br/>  Agregar componentes del servidor de chat persistente a la topología <br/>  Crear una base SQL Server de datos para el almacén del servidor de chat persistente (y una copia de seguridad SQL Server para la recuperación ante desastres) <br/>  Definir un nuevo Skype Empresarial de archivos o usar un almacén de archivos de Skype Empresarial existente para archivos de servidor de chat persistente <br/>  Asociar el Skype Empresarial Server que puede enrutar las solicitudes a este grupo de servidores de chat persistente <br/>  Si se requiere el cumplimiento de chat persistente: <br/>  Agregar almacén de cumplimiento de chat persistente <br/>  Haga clic en la casilla definición del grupo de servidores de chat persistente para habilitar el cumplimiento <br/>  Publique la topología. <br/>  Si instala el servidor de chat persistente en Standard Edition, el nombre de dominio completo (FQDN) del grupo de servidores de servidor de chat persistente debe coincidir con el servidor Standard Edition y las bases de datos de SQL Server se instalan en la instancia de SQL Server Express en el servidor de Standard Edition <br/> |Para definir una topología, una cuenta que pertenezca al grupo de usuarios locales.  <br/> Para publicar la topología, una cuenta que sea miembro del grupo Administradores de dominio y del grupo RTCUniversalServerAdmins, y el usuario también debe tener permisos de control total (lectura/escritura/modificación) en el almacén de archivos de Skype Empresarial para archivos del servidor de chat persistente (de modo que el Generador de topologías pueda configurar las DACL necesarias).  <br/> |[Crear y publicar nueva topología en Skype Empresarial Server 2015](../../deploy/install/create-and-publish-new-topology.md) <br/> [Agregar servidor de chat persistente a la topología Skype Empresarial Server 2015](add-persistent-chat-server.md) <br/> |
|**Implementar el servidor de chat persistente** <br/> | Ejecute el Skype Empresarial Server en todos los equipos que ejecutan el servidor de chat persistente. La instalación del servidor de chat persistente está integrada en el asistente Skype Empresarial Server implementación de chat persistente que proporciona las siguientes instrucciones: <br/>  Implemente el almacén de administración local <br/>  Instalar servicios de chat persistente <br/>  Solicite y asigne certificados <br/>  Ejecute e inicie los servicios <br/> |Cualquier usuario que pertenezca al grupo de administradores locales.  <br/> |[Implementar el servidor de chat persistente en Skype Empresarial Server 2015](deploy-persistent-chat-server.md) <br/> |
|**Crear un administrador de chat persistente** <br/> |Agregue usuarios al grupo de seguridad CsPersistentChatAdministrator.  <br/> |Cualquier usuario que pertenezca al grupo de administradores de dominio.  <br/> |[Crear un administrador de chat persistente en Skype Empresarial Server 2015](create-a-persistent-chat-administrator.md) <br/> |
|**Configuración del servidor de chat persistente** <br/> | Configure usuarios: <br/>  La directiva debe habilitar al usuario para tener acceso al servidor de chat persistente. De manera predeterminada, la directiva está desactivada para todos los usuarios, y se puede definir en el ámbito global, de sitio, de grupo o de usuario. <br/>  Defina la configuración <br/> |El usuario debe pertenecer al grupo CsPersistentChatAdministrator. Para cambiar la directiva, el usuario ser miembro de CsUserAdministrator, como mínimo.  <br/> |[Administrar el servidor de chat persistente en Skype Empresarial Server 2015](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

