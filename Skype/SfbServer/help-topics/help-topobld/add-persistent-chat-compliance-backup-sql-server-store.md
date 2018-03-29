---
title: Agregar almacén de SQL Server de copia de seguridad de cumplimiento del chat persistente
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: Configurar la conformidad de copia de seguridad de SQL Server almacena que proporcionará las bases de datos de copia de seguridad para el servidor de charla persistente o cumplimiento de servidor de charla persistente de SQL Server almacena.
ms.openlocfilehash: 4e3a2bf034d5ab20c7352f2b6ef9c8a6a0c4befa
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>Agregar almacén de SQL Server de copia de seguridad de cumplimiento del chat persistente
 
Configurar la conformidad de copia de seguridad de SQL Server almacena que proporcionará las bases de datos de copia de seguridad para el servidor de charla persistente o cumplimiento de servidor de charla persistente de SQL Server almacena.
  
 **SQL Server almacenar**: seleccione una existente de SQL Server y, opcionalmente, una instancia de Chat persistentes.
  
Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia de los datos de copia de seguridad de cumplimiento de normas Chat persistente.
  
Seleccione la casilla de verificación **Habilitar SQL Server almacén espejado** para configurar una base de datos de SQL Server y una instancia opcional que proporcionará una base de datos reflejada para los datos de copia de seguridad de cumplimiento de normas Chat persistente.
  
Seleccione en la lista **almacén de creación de reflejos de SQL Server** un SQL Server y una instancia opcional para que actúe como la duplicación de SQL Server para la conformidad backup Chat persistentes de SQL Server.
  
Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para el espejado de SQL Server persistente de Chat.
  
En la lista **Usar el testigo de creación de reflejo de SQL Server para habilitar la conmutación tras fallo automática**, seleccione un almacén de SQL Server que actúe como servidor testigo en casos de conmutación por error. El servidor testigo no no datos espejo o host para los servidores de charla persistente, pero asegura que sólo uno de SQL Server en una configuración duplicada es el activo de SQL Server en cualquier momento.
  
Haga clic en **nuevo** para definir a un nuevo testigo de SQL Server, opcionalmente, una instancia para el cumplimiento backup Chat persistente testigo de creación de reflejos de SQL Server.
  
Haga clic en **Atrás** para retroceder al cuadro de diálogo anterior de definición del grupo de servidores.
  
Haga clic en **siguiente** cuando haya terminado de especificar las opciones de configuración del almacén de copia de seguridad de SQL Server de este grupo y continuar con la definición de grupo del servidor de Chat persistentes.
  
Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente **Definir el nuevo grupo de chat persistente**.
  
Haga clic en **Ayuda** para obtener acceso a la ayuda contextual, como esta página.
  
## <a name="see-also"></a>Vea también

#### 

[Plan para el servidor de charla persistente en Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Requisitos del servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Requisitos de hardware y software para el servidor de Chat persistente en Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configurar el servicio de cumplimiento de normas para el servidor de charla persistente en Skype para Business Server 2015](../../manage/persistent-chat/configure-compliance.md)
  
[Configurar alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)

