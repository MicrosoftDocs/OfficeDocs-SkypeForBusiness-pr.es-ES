---
title: Agregar almacén SQL Server de chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8e6064a-8127-4c25-8685-06f49d8bbfce
description: Configure los almacenes de SQL Server que proporcionarán bases de datos para el servidor de chat persistente o el grupo de servidores de chat persistente.
ms.openlocfilehash: 2771b63063e155973cd711c4b80f06dee46e1865
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216331"
---
# <a name="add-persistent-chat-sql-server-store"></a>Agregar almacén SQL Server de chat persistente
 
Configure los almacenes de SQL Server que proporcionarán bases de datos para el servidor de chat persistente o el grupo de servidores de chat persistente.
  
 **Almacén de SQL Server**: Seleccione un SQL Server existente y, opcionalmente, una instancia para chat persistente.
  
Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para los datos del chat persistente.
  
Active la casilla **Habilitar la creación de reflejos del almacén de SQL Server** para configurar una base de datos de SQL Server y una instancia opcional que proporcionará una base de datos reflejada para los datos del chat persistente.
  
Seleccione en la lista **reflejo de SQL** Server el almacén de SQL Server y una instancia opcional que actúe como el reflejo de SQL Server para el servidor SQL Server de chat persistente.
  
Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para la creación de reflejo de SQL Server de chat persistente.
  
En la lista **Utilizar el testigo de creación de reflejo SQL Server para garantizar la conmutación automática por error** seleccione un SQL Server que actuará como servidor testigo en casos de conmutación por error. El servidor testigo no refleja ni hospeda datos para los servidores de chat persistente, pero garantiza que sólo un SQL Server en una configuración reflejada es el servidor SQL Server activo en cualquier momento.
  
Haga clic en **nuevo** para definir un nuevo testigo de SQL Server opcionalmente una instancia para el testigo de creación de reflejo de SQL Server de chat persistente.
  
Haga clic en **Atrás** para retroceder al diálogo de definición de grupo de servidores anterior.
  
Haga clic en **siguiente** cuando haya terminado de introducir las opciones para la configuración del almacén de SQL Server de este grupo de servidores y continúe con la definición del grupo de servidores de chat persistente.
  
Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente **Definir nuevo grupo de chat persistente**.
  
Haga clic en **Ayuda** para acceder a la ayuda contextual, como esta página.
  
## <a name="see-also"></a>Vea también

[Planeación del servidor de chat persistente en Skype empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Agregar un servidor de chat persistente a la topología de Skype empresarial Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Requisitos de hardware y software para el servidor de chat persistente en Skype empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Requisitos de servidor para Skype empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Aspectos básicos de la topología de Skype empresarial Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype empresarial Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
