---
title: Agregar almacén de SQL Server de copia de seguridad de cumplimiento del chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: Configure los almacenes de SQL Server de cumplimiento de copias de seguridad que proporcionarán bases de datos de copia de seguridad para el servidor de chat persistente o el servidor de chat persistente que los almacenes de SQL Server.
ms.openlocfilehash: 457874f87266453939c75cdef50d30231d8610bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277709"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>Agregar almacén de SQL Server de copia de seguridad de cumplimiento del chat persistente
 
Configure los almacenes de SQL Server de cumplimiento de copias de seguridad que proporcionarán bases de datos de copia de seguridad para el servidor de chat persistente o el servidor de chat persistente que los almacenes de SQL Server.
  
 **Almacén de SQL Server**: Seleccione un SQL Server existente y, opcionalmente, una instancia para una conversación persistente.
  
Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para los datos de cumplimiento de la copia de seguridad de chat persistente.
  
Seleccione la casilla habilitar el reflejo de la **tienda SQL Server** para configurar una base de datos de SQL Server y una instancia opcional que proporcione una base de datos reflejada para los datos de cumplimiento de la copia de seguridad de la conversación persistente.
  
Seleccione en la lista **reflejo de SQL Server** un SQL Server y una instancia opcional para actuar como el reflejo de SQL Server para el servidor SQL de cumplimiento de la copia de seguridad de chat persistente.
  
Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para el reflejo de SQL Server de chat persistente.
  
En la lista **Usar el testigo de creación de reflejo de SQL Server para habilitar la conmutación tras fallo automática**, seleccione un almacén de SQL Server que actúe como servidor testigo en casos de conmutación por error. El servidor testigo no refleja ni hospeda datos para los servidores de chat persistentes, pero garantiza que solo un SQL Server en una configuración duplicada es el servidor SQL activo en cualquier momento.
  
Haga clic en **nuevo** para definir un nuevo testigo de SQL Server opcionalmente una instancia de la copia de seguridad persistente testigo de reflejo de SQL Server.
  
Haga clic en **Atrás** para retroceder al cuadro de diálogo anterior de definición de grupo de servidores.
  
Haga clic en **siguiente** cuando haya terminado de escribir las opciones para la configuración de la copia de seguridad de la tienda SQL Server y continuar con la definición del grupo de servidores de chat persistente.
  
Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente **Definir nuevo grupo de chat persistente**.
  
Haga clic en **Ayuda** para obtener acceso a la ayuda contextual, como esta página.
  
## <a name="see-also"></a>Vea también

[Planificar el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configurar el servicio de cumplimiento para el servidor de chat persistente en Skype Empresarial Server 2015](../../manage/persistent-chat/configure-compliance.md)
  
[Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
