---
title: Agregar almacén SQL Server de chat persistente
ms.reviewer: ''
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
description: Configurar los almacenes de SQL Server que proporcionarán bases de datos para el servidor de Chat persistente o grupo de servidores de Chat persistente.
ms.openlocfilehash: 856c74db37ef99243e024b0c044b20d095ca6ba6
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899564"
---
# <a name="add-persistent-chat-sql-server-store"></a>Agregar almacén SQL Server de chat persistente
 
Configurar los almacenes de SQL Server que proporcionarán bases de datos para el servidor de Chat persistente o grupo de servidores de Chat persistente.
  
 **Almacén de SQL Server**: seleccione un SQL Server existente y, opcionalmente, una instancia de Chat persistente.
  
Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para los datos de Chat persistente.
  
Seleccione la casilla de verificación de **la creación de reflejo de almacén de habilitar SQL Server** para configurar una base de datos de SQL Server y una instancia opcional que proporcionará una base de datos reflejada para los datos de Chat persistente.
  
Seleccione en la lista **almacén de SQL Server de reflejo** un SQL Server y una instancia opcional para que actúen como reflejo de SQL Server para el servidor SQL de Chat persistente.
  
Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para el servidor SQL de Chat persistente la creación de reflejo.
  
En la lista **Usar el testigo de creación de reflejo de SQL Server para habilitar la conmutación tras fallo automática**, seleccione un almacén de SQL Server que actúe como servidor testigo en casos de conmutación por error. El servidor testigo realiza datos no reflejado o de host para los servidores de Chat persistente, pero garantiza que un solo servidor de SQL en una configuración duplicada es el servidor SQL activo en cualquier momento.
  
Haga clic en **nuevo** para definir un nuevo testigo de SQL Server y, opcionalmente, una instancia para el SQL servidor de Chat persistente testigo de reflejo.
  
Haga clic en **Atrás** para retroceder al cuadro de diálogo anterior de definición de grupo de servidores.
  
Haga clic en **siguiente** cuando haya terminado de introducir las opciones de configuración del almacén de SQL Server de este grupo de servidores y para continuar con la definición de grupo de servidores de servidor de Chat persistente.
  
Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente **Definir nuevo grupo de chat persistente**.
  
Haga clic en **Ayuda** para obtener acceso a la ayuda contextual, como esta página.
  
## <a name="see-also"></a>Consulte también

[Planificar el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Agregar servidor de Chat persistente a su Skype para topología empresarial Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)
  
[Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
