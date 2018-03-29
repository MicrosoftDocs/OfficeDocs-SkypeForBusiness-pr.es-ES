---
title: Agregar almacén SQL Server de chat persistente
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: Configurar los almacenes de SQL Server que proporcionan las bases de datos para el servidor de charla persistente o el grupo de servidores de charla persistente.
ms.openlocfilehash: 062092ff60fa30f7b8ac19725a12a3f62e1b9ec6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-persistent-chat-sql-server-store"></a>Agregar almacén SQL Server de chat persistente
 
Configurar los almacenes de SQL Server que proporcionan las bases de datos para el servidor de charla persistente o el grupo de servidores de charla persistente.
  
 **SQL Server almacenar**: seleccione una existente de SQL Server y, opcionalmente, una instancia de Chat persistentes.
  
Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia de los datos persistentes de charla.
  
Seleccione la casilla de verificación **Habilitar SQL Server almacén espejado** para configurar una base de datos de SQL Server y una instancia opcional que proporcionará una base de datos reflejada para los datos persistentes de charla.
  
Seleccione en la lista **almacén de creación de reflejos de SQL Server** un SQL Server y una instancia opcional para actuar como la duplicación de SQL Server para la persistente de SQL Server de Chat.
  
Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para el espejado de SQL Server persistente de Chat.
  
En la lista **Usar el testigo de creación de reflejo de SQL Server para habilitar la conmutación tras fallo automática**, seleccione un almacén de SQL Server que actúe como servidor testigo en casos de conmutación por error. El servidor testigo no no datos espejo o host para los servidores de charla persistente, pero asegura que sólo uno de SQL Server en una configuración duplicada es el activo de SQL Server en cualquier momento.
  
Haga clic en **nuevo** para definir a un testigo SQL Server nuevo, opcionalmente, una instancia de testigo de creación de reflejos de SQL Server de Chat persistentes.
  
Haga clic en **Atrás** para retroceder al cuadro de diálogo anterior de definición del grupo de servidores.
  
Haga clic en **siguiente** cuando haya terminado de especificar las opciones de configuración del almacén de la agrupación de SQL Server y continuar con la definición de grupo del servidor de Chat persistentes.
  
Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente **Definir el nuevo grupo de chat persistente**.
  
Haga clic en **Ayuda** para obtener acceso a la ayuda contextual, como esta página.
  
## <a name="see-also"></a>Vea también

#### 

[Plan para el servidor de charla persistente en Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Agregar servidor de Chat persistentes a su Skype para la topología de servidor de negocios 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Requisitos de hardware y software para el servidor de Chat persistente en Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Requisitos del servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Conceptos básicos de topología para Skype para Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[Configurar alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

