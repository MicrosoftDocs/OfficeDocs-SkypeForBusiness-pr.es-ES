---
title: Implementar el servidor de chat persistente en Skype Empresarial Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8373c93b-92a7-4932-bc1f-00fc08955426
description: 'Resumen: Lea este tema para obtener información sobre cómo implementar el servidor de chat persistente de Skype empresarial Server 2015.'
ms.openlocfilehash: 06cc51ccbbab193e749c2f919102d7d38fde3f56
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273899"
---
# <a name="deploy-persistent-chat-server-in-skype-for-business-server-2015"></a>Implementar el servidor de chat persistente en Skype Empresarial Server 2015
 
**Resumen:** Lea este tema para obtener información sobre cómo implementar el servidor de chat persistente de Skype empresarial Server 2015.
  
Para implementar un servidor de chat persistente, haga lo siguiente: 
  
- Use el generador de topología para definir o importar y posteriormente publicar su topología y los componentes que desea implementar.
    
- Preparar el entorno para implementar componentes de servidor de chat persistentes
    
- Instalar y configurar componentes de servidor de chat persistentes para la implementación
    
Antes de implementar un servidor de chat persistente, debe leer [plan para el servidor de chat persistente en Skype empresarial server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md). Los temas sobre la planeación describen los requisitos de hardware y software, las topologías posibles y los escenarios de combinación. 
  
> [!NOTE] 
> Chat persistente está disponible en Skype empresarial Server 2015, pero ya no es compatible con Skype empresarial Server 2019. La misma funcionalidad está disponible en Teams. Para obtener más información, consulte Cómo desplazarse [de Skype empresarial a Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams). Si necesita usar una conversación persistente, puede elegir entre migrar los usuarios que tienen esta funcionalidad a teams o continuar usando Skype empresarial Server 2015. 

## <a name="deployment-checklist"></a>Lista de comprobación de la implementación

Puede implementar un servidor de chat persistente después de implementar su Topología inicial, incluido al menos un grupo de servidores front-end de Skype empresarial Server o un solo servidor de Skype empresarial Standard Edition. La lista de comprobación de la implementación describe los pasos básicos necesarios para implementar el servidor de chat persistente y proporciona vínculos para obtener más información.
  
**Proceso de implementación del servidor de chat persistente**

|**Tarea**|**Pasos**|**Roles y pertenencias a grupos necesarios**|**Temas relacionados**|
|:-----|:-----|:-----|:-----|
|**Instalar los requisitos previos de hardware y software** <br/> | En un hardware que cumpla los requisitos del sistema, instale los siguientes elementos: <br/>  En los servidores front-end del servidor de chat persistente: <br/>  Un sistema operativo que cumpla los requisitos del sistema <br/>  Requisitos previos de software para equipos con Skype empresarial Server <br/>  En el servidor que hospedará la base de datos del servidor de chat persistente: <br/>  Una versión compatible de SQL Server <br/>  Si se requiere el cumplimiento del servidor de chat persistente: <br/>  SQL Server en el servidor que hospedará la base de datos de cumplimiento del servidor de chat persistente <br/> |Cualquier usuario que pertenezca al grupo de administradores locales.  <br/> |[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) <br/> [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) <br/> [Requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md) <br/> |
|**Crear la topología interna adecuada para admitir el servidor de chat persistente (y, opcionalmente, el cumplimiento persistente de la conversación)** <br/> | Ejecute el generador de topología para agregar un grupo de servidores de chat persistente a su topología: <br/>  Agregar componentes de servidor de chat persistentes a la topología <br/>  Crear una base de datos de SQL Server para el almacén de servidor de chat persistente (y una copia de seguridad de SQL Server para recuperación ante desastres) <br/>  Definir un nuevo almacenamiento de archivos de Skype empresarial o usar un almacén de archivos existente de Skype empresarial para los archivos del servidor de chat persistentes <br/>  Asociar el grupo de servidores de Skype empresarial que puede enrutar solicitudes a este grupo de servidores de chat persistente <br/>  Si se necesita el cumplimiento del chat persistente: <br/>  Agregar almacén de cumplimiento persistente de chat <br/>  Haga clic en la casilla definición del grupo de servidores de chat persistente para habilitar el cumplimiento. <br/>  Publique la topología. <br/>  Si instala el servidor de chat persistente en Standard Edition, el nombre de dominio completo (FQDN) del grupo de servidores de chat persistente debe coincidir con el servidor Standard Edition y las bases de datos de SQL Server se colocan en la instancia de SQL Server Express en el estándar Servidor de edición <br/> |Para definir una topología, una cuenta que pertenezca al grupo de usuarios locales.  <br/> Para publicar la topología, una cuenta que sea miembro del grupo administradores del dominio y del grupo RTCUniversalServerAdmins, y el usuario también debe tener permisos de control total (lectura/escritura/modificar) en el almacenamiento de archivos de Skype empresarial para archivos del servidor de chat persistentes el generador de topología puede configurar las DACL necesarias).  <br/> |[Crear y publicar una nueva topología en Skype Empresarial Server 2015](../../deploy/install/create-and-publish-new-topology.md) <br/> [Agregar un servidor de chat persistente a su topología de 2015 de Skype empresarial Server](add-persistent-chat-server.md) <br/> |
|**Implementar el servidor de chat persistente** <br/> | Ejecute el programa de instalación de Skype empresarial Server en todos los equipos que ejecuten el servidor de chat persistente. La configuración del servidor de chat persistente está integrada en el Asistente para la implementación de Skype empresarial Server que proporciona las siguientes instrucciones: <br/>  Implemente el almacén de administración local. <br/>  Instalar servicios de chat persistentes <br/>  Solicite y asigne los certificados. <br/>  Ejecute e inicie los servicios. <br/> |Cualquier usuario que pertenezca al grupo de administradores locales.  <br/> |[Implementar el servidor de chat persistente en Skype Empresarial Server 2015](deploy-persistent-chat-server.md) <br/> |
|**Crear un administrador de chat persistente** <br/> |Agregue usuarios al grupo de seguridad CsPersistentChatAdministrator.  <br/> |Cualquier usuario que pertenezca al grupo de administradores de dominio.  <br/> |[Crear un administrador de chat persistente en Skype Empresarial Server 2015](create-a-persistent-chat-administrator.md) <br/> |
|**Configurar el servidor de chat persistente** <br/> | Configure usuarios: <br/>  El usuario debe estar habilitado por la Directiva para tener acceso al servidor de chat persistente. De manera predeterminada, la directiva está desactivada para todos los usuarios, y se puede definir en el ámbito global, de sitio, de grupo o de usuario. <br/>  Defina la configuración <br/> |El usuario necesita pertenecer al grupo CsPersistentChatAdministrator. Para cambiar la directiva, es preciso que el usuario sea miembro de CsUserAdministrator, como mínimo.  <br/> |[Administrar el servidor de chat persistente en Skype Empresarial Server 2015](../../manage/persistent-chat/persistent-chat.md) <br/> |
   

