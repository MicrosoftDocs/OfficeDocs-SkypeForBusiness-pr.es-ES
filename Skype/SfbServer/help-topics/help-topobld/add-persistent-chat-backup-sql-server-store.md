---
title: Agregar un almacén de SQL Server de copia de seguridad del chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: Configure los almacenes de SQL Server de copia de seguridad que proporcionarán bases de datos de copia de seguridad del servidor de chat persistente o del grupo de servidores de chat persistente.
ms.openlocfilehash: 0f8fe19d95adff9e2ac538600f3dcf5153c25afd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820712"
---
# <a name="add-persistent-chat-backup-sql-server-store"></a>Agregar un almacén de SQL Server de copia de seguridad del chat persistente
 
Configure los almacenes de SQL Server de copia de seguridad que proporcionarán bases de datos de copia de seguridad del servidor de chat persistente o del grupo de servidores de chat persistente.
  
 **Almacén de SQL Server**: Seleccione un SQL Server existente y, opcionalmente, una instancia para una conversación persistente.
  
Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para los datos de copia de seguridad de chat persistente.
  
Seleccione la casilla habilitar el reflejo de la **tienda SQL Server** para configurar una base de datos de SQL Server y una instancia opcional que proporcione una base de datos reflejada para los datos de copia de seguridad de la conversación persistente.
  
Seleccione en la lista **reflejo de SQL Server** un SQL Server y una instancia opcional para actuar como SQL Server Mirror para la copia de seguridad persistente de SQL Server.
  
Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para el reflejo de SQL Server de chat persistente.
  
En la lista **Usar el testigo de creación de reflejo de SQL Server para habilitar la conmutación tras fallo automática**, seleccione un almacén de SQL Server que actúe como servidor testigo en casos de conmutación por error. El servidor testigo no refleja ni hospeda datos para los servidores de chat persistentes, pero garantiza que solo un SQL Server en una configuración duplicada es el servidor SQL activo en cualquier momento.
  
Haga clic en **nuevo** para definir un nuevo testigo de SQL Server, opcionalmente, una instancia de la copia de seguridad persistente del testigo de reflejo de SQL Server.
  
Haga clic en **Atrás** para retroceder al cuadro de diálogo anterior de definición de grupo de servidores.
  
Haga clic en **siguiente** cuando haya terminado de escribir las opciones para la configuración de la copia de seguridad de la tienda SQL Server y continuar con la definición del grupo de servidores de chat persistente.
  
Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente **Definir nuevo grupo de chat persistente**.
  
Haga clic en **Ayuda** para obtener acceso a la ayuda contextual, como esta página.
  
## <a name="see-also"></a>Vea también

[Planificar el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
