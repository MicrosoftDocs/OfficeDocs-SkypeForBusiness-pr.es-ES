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
description: Configurar el cumplimiento de normas de servidor de Chat persistente que almacenes de SQL Server o almacenes de SQL Server de cumplimiento de copia de seguridad que proporcionará bases de datos de copia de seguridad para el servidor de Chat persistente.
ms.openlocfilehash: c84123946ffa22e3db4000f6e431539b48f6e735
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "19503322"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>Agregar almacén de SQL Server de copia de seguridad de cumplimiento del chat persistente
 
Configurar el cumplimiento de normas de servidor de Chat persistente que almacenes de SQL Server o almacenes de SQL Server de cumplimiento de copia de seguridad que proporcionará bases de datos de copia de seguridad para el servidor de Chat persistente.
  
 **Almacén de SQL Server**: seleccione un SQL Server existente y, opcionalmente, una instancia de Chat persistente.
  
Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para los datos de copia de seguridad de cumplimiento de Chat persistente.
  
Seleccione la casilla de verificación de **la creación de reflejo de almacén de habilitar SQL Server** para configurar una base de datos de SQL Server y una instancia opcional que proporcionará una base de datos reflejada para los datos de copia de seguridad de cumplimiento de Chat persistente.
  
Seleccione en la lista **almacén de SQL Server de reflejo** un SQL Server y una instancia opcional para actuar como el reflejo de SQL Server para la copia de seguridad cumplimiento de Chat persistente SQL Server.
  
Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para el servidor SQL de Chat persistente la creación de reflejo.
  
En la lista **Usar el testigo de creación de reflejo de SQL Server para habilitar la conmutación tras fallo automática**, seleccione un almacén de SQL Server que actúe como servidor testigo en casos de conmutación por error. El servidor testigo realiza datos no reflejado o de host para los servidores de Chat persistente, pero garantiza que un solo servidor de SQL en una configuración duplicada es el servidor SQL activo en cualquier momento.
  
Haga clic en **nuevo** para definir un nuevo testigo de SQL Server y, opcionalmente, una instancia de la copia de seguridad cumplimiento de Chat persistente testigo de reflejo de SQL Server.
  
Haga clic en **Atrás** para retroceder al cuadro de diálogo anterior de definición de grupo de servidores.
  
Haga clic en **siguiente** cuando haya terminado de introducir las opciones de configuración de almacén de SQL Server copia de seguridad de este grupo de servidores y para continuar con la definición de grupo de servidores de servidor de Chat persistente.
  
Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente **Definir nuevo grupo de chat persistente**.
  
Haga clic en **Ayuda** para obtener acceso a la ayuda contextual, como esta página.
  
## <a name="see-also"></a>Vea también

[Planificar el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configurar el servicio de cumplimiento para el servidor de chat persistente en Skype Empresarial Server 2015](../../manage/persistent-chat/configure-compliance.md)
  
[Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)