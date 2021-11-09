---
title: Agregar almacén de SQL Server de copia de seguridad del chat persistente
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatBackupSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 106698e4-ce73-4a34-8fc7-e9d3208a17dc
description: Configure los almacenes de SQL Server copia de seguridad que proporcionarán bases de datos de copia de seguridad para el servidor de chat persistente o el grupo de servidores de chat persistente.
ms.openlocfilehash: 038e8aff6c905ae60c7f5ed8a1e704cf7961d5dc
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863907"
---
# <a name="add-persistent-chat-backup-sql-server-store"></a>Agregar almacén de la instancia de copia de seguridad de SQL Server del chat persistente
 
Configure los almacenes de SQL Server copia de seguridad que proporcionarán bases de datos de copia de seguridad para el servidor de chat persistente o el grupo de servidores de chat persistente.
  
 **SQL Server de almacenamiento:** seleccione una SQL Server existente y, opcionalmente, una instancia para chat persistente.
  
Haga **clic en** Nuevo para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para los datos de copia de seguridad de chat persistente.
  
Active la **casilla Habilitar SQL Server** creación de reflejos del almacén para configurar una base de datos SQL Server y una instancia opcional que proporcionará una base de datos reflejada para los datos de copia de seguridad de chat persistente.
  
Seleccione en la lista Creación de **SQL Server** almacenar una instancia SQL Server y opcional para que actúe como el reflejo de SQL Server para la copia de seguridad de chat persistente SQL Server.
  
Haga **clic en** Nuevo para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para la creación de reflejos SQL Server chat persistente.
  
En la lista **Utilizar el testigo de creación de reflejo SQL Server para garantizar la conmutación automática por error** seleccione un SQL Server que actuará como servidor testigo en casos de conmutación por error. El servidor testigo no refleja ni hospeda los datos de los servidores de chat persistente, pero garantiza que solo un SQL Server en una configuración reflejada sea el servidor activo SQL Server en cualquier momento.
  
Haga **clic en** Nuevo para definir un nuevo SQL Server testigo opcionalmente una instancia para la copia de seguridad de chat persistente SQL Server testigo de creación de reflejo.
  
Haga clic en **Atrás** para retroceder al diálogo de definición de grupo de servidores anterior.
  
Haga **clic en** Siguiente después de haber terminado de especificar las opciones para la configuración del almacén SQL Server copia de seguridad de este grupo y para continuar con la definición del grupo de servidores de chat persistente.
  
Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente **Definir nuevo grupo de chat persistente**.
  
Haga clic en **Ayuda** para acceder a la ayuda contextual, como esta página.
  
## <a name="see-also"></a>Consulte también

[Planear el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Requisitos del servidor para Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
