---
title: Implementar el servidor de chat persistente en Skype Empresarial Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: 'Resumen: Leer este tema para aprender a implementar Skype para Business Server 2015 persistente Chat Server.'
ms.openlocfilehash: c2dedae876c61f84d672f8cf457e1b6c4baeff43
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>Implementar el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para aprender a implementar Skype para Business Server 2015 persistente Chat Server.
  
Para implementar el servidor de charla persistente, usted: 
  
- Utilice el generador de topología para definir, o importar y publicar posteriormente la topología y los componentes que desea implementar
    
- Preparar el entorno para implementar los componentes de servidor de charla persistente
    
- Instalar y configurar componentes de servidor de charla persistente para su implementación
    
Antes de implementar el servidor de charla persistente, debe leer [Planear persistente Server Chat de Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Los temas sobre la planeación describen los requisitos de hardware y software, las topologías posibles y los escenarios de combinación. 
  
## <a name="deployment-checklist"></a>Lista de comprobación de la implementación

Puede implementar el servidor de charla persistente después de implementar su topología inicial, incluyendo al menos un Skype para el grupo de negocio de servidor Front-End o un Skype para servidor Standard Edition de negocio. La lista de comprobación de implementación describe los pasos básicos necesarios para implementar el servidor de charla persistente y proporciona vínculos para obtener más detalles.
  
**Proceso de implementación del servidor de charla persistente**

|**Tarea**|**Pasos**|**Funciones requeridas y pertenencias a grupos**|**Temas relacionados**|
|:-----|:-----|:-----|:-----|
|**Instalar los requisitos previos de hardware y software** <br/> | En un hardware que cumpla los requisitos del sistema, instale los siguientes elementos: <br/>  En el modo persistente Chat servidores Front-End: <br/>  Un sistema operativo que cumpla los requisitos del sistema <br/>  Requisitos previos de software para equipos que ejecutan Skype para Business Server <br/>  En el servidor que alojará la base de datos del servidor de charla persistente: <br/>  Una versión compatible de SQL Server <br/>  Si se requiere cumplimiento de servidor de charla persistente: <br/>  SQL Server en el servidor que alojará la base de datos de servidor de charla persistente cumplimiento <br/> |Cualquier usuario que pertenezca al grupo de administradores locales.  <br/> |[Requisitos del servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Requisitos ambientales para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Requisitos de hardware y software para el servidor de Chat persistente en Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**Crear la topología interna adecuada para admitir el servidor de Chat persistente (y opcionalmente, cumplimiento de Chat persistentes)** <br/> | Ejecutar el generador de topología para agregar un grupo de servidores de charla persistente a la topología: <br/>  Agregar componentes de servidor de charla persistente a la topología <br/>  Crear una base de datos de SQL Server para el almacén del servidor de Chat persistentes (y una copia de seguridad de SQL Server para recuperación ante desastres) <br/>  Definir un nuevo Skype para el almacén de archivos de Business o utilizar una existente Skype para el almacén de archivos de Business para archivos del servidor de Chat persistentes <br/>  Asociar el Skype para el grupo de Business Server puede enrutar las solicitudes a este grupo de servidores de charla persistente <br/>  Si se necesita el cumplimiento del chat persistente: <br/>  Agregar el almacén persistente de cumplimiento de normas de Chat <br/>  Haga clic en la casilla de verificación servidor de Chat persistente definición de grupo para permitir el cumplimiento <br/>  Publique la topología. <br/>  Si instala al servidor de charla persistente en Standard Edition, el nombre de dominio completo (FQDN) del grupo de servidores de charla persistente debe coincidir con el servidor Standard Edition, y las bases de datos de SQL Server están ubicados en la instancia de SQL Server Express en el estándar Server Edition <br/> |Para definir una topología, una cuenta que pertenezca al grupo de usuarios locales.  <br/> Para publicar la topología, una cuenta que sea miembro del grupo Administradores de dominio y grupo RTCUniversalServerAdmins y el usuario debe también tiene permisos control total (lectura/escritura/modificación) en el Skype para el almacén de archivos de negocio para archivos del servidor de Chat persistentes (tan el generador de topología puede configurar las DACL necesarias).  <br/> |[Crear y publicar la nueva topología en Skype para Business Server 2015](../../deploy/install/create-and-publish-new-topology.md) <br/> [Agregar servidor de Chat persistentes a su Skype para la topología de servidor de negocios 2015](add-persistent-chat-server.md) <br/> |
|**Implementar servidor de Chat persistentes** <br/> | Ejecutar el Skype para el programa de instalación de Business Server en todos los equipos que ejecutan el servidor de charla persistente. La instalación del servidor de Chat persistentes se integra en el Skype para el Asistente de implementación de servidores empresariales que proporciona las siguientes instrucciones: <br/>  Implemente el almacén de administración local. <br/>  Instalar los servicios de Chat persistentes <br/>  Solicite y asigne los certificados. <br/>  Ejecute e inicie los servicios. <br/> |Cualquier usuario que pertenezca al grupo de administradores locales.  <br/> |[Implementar servidor de charla persistente en Skype para Business Server 2015](deploy-persistent-chat-server.md) <br/> |
|**Crear un administrador de Chat persistentes** <br/> |Agregue usuarios al grupo de seguridad CsPersistentChatAdministrator.  <br/> |Cualquier usuario que pertenezca al grupo de administradores de dominio.  <br/> |[Crear un administrador de charla persistente en Skype para Business Server 2015](create-a-persistent-chat-administrator.md) <br/> |
|**Configurar el servidor de charla persistente** <br/> | Configure usuarios: <br/>  Usuario debe estar habilitada por la directiva para tener acceso a servidor de Chat persistente. De manera predeterminada, la directiva está desactivada para todos los usuarios, y se puede definir en el ámbito global, de sitio, de grupo o de usuario. <br/>  Defina la configuración <br/> |El usuario necesita pertenecer al grupo CsPersistentChatAdministrator. Para cambiar la directiva, es preciso que el usuario sea miembro de CsUserAdministrator, como mínimo.  <br/> |[Administrar servidor de charla persistente en Skype para Business Server 2015](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

