---
title: Agregar almacén SQL Server de chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: Configure los almacenes de SQL Server que proporcionarán bases de datos para el servidor de chat persistente o el grupo de servidores de chat persistente.
ms.openlocfilehash: 3d6e5464cf435440cc7e7b1b29aa5a22ae2cbb0f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302283"
---
# <a name="add-persistent-chat-sql-server-store"></a>Agregar almacén SQL Server de chat persistente
 
Configure los almacenes de SQL Server que proporcionarán bases de datos para el servidor de chat persistente o el grupo de servidores de chat persistente.
  
 **Almacén de SQL Server**: Seleccione un SQL Server existente y, opcionalmente, una instancia para una conversación persistente.
  
Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para los datos persistentes del chat.
  
Seleccione la casilla habilitar el reflejo de la **tienda SQL Server** para configurar una base de datos de SQL Server y una instancia opcional que proporcione una base de datos espejada para los datos persistentes del chat.
  
Seleccione en la lista **reflejo de SQL Server** un SQL Server y una instancia opcional para actuar como SQL Server Mirror para el servidor SQL Server de chat persistente.
  
Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para el reflejo de SQL Server de chat persistente.
  
En la lista **Usar el testigo de creación de reflejo de SQL Server para habilitar la conmutación tras fallo automática**, seleccione un almacén de SQL Server que actúe como servidor testigo en casos de conmutación por error. El servidor testigo no refleja ni hospeda datos para los servidores de chat persistentes, pero garantiza que solo un SQL Server en una configuración duplicada es el servidor SQL activo en cualquier momento.
  
Haga clic en **nuevo** para definir un nuevo testigo de SQL Server opcionalmente una instancia para el testigo de reflejo de SQL Server de chat persistente.
  
Haga clic en **Atrás** para retroceder al cuadro de diálogo anterior de definición de grupo de servidores.
  
Haga clic en **siguiente** cuando haya terminado de escribir las opciones para la configuración de la tienda SQL Server de este grupo y continúe con la definición del grupo de servidores de chat persistente.
  
Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente **Definir nuevo grupo de chat persistente**.
  
Haga clic en **Ayuda** para obtener acceso a la ayuda contextual, como esta página.
  
## <a name="see-also"></a>Vea también

[Planificar el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Agregar un servidor de chat persistente a su topología de 2015 de Skype empresarial Server](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Conceptos básicos de topología de Skype Empresarial Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
