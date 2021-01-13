---
title: Agregar almacén de SQL Server de copia de seguridad de cumplimiento del chat persistente
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatBackupComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 358b74bd-a97d-4f28-9bed-af633ea0099e
description: Configure los almacenes de cumplimiento de SQL Server copia de seguridad que proporcionarán bases de datos de copia de seguridad para los almacenes de cumplimiento del servidor de chat persistente o del servidor SQL Server chat persistente.
ms.openlocfilehash: 9b380091978d62294c6ea16ffa8586b9f8d9d322
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818720"
---
# <a name="add-persistent-chat-compliance-backup-sql-server-store"></a>Agregar almacén de instancia de copia de seguridad de SQL Server del chat persistente
 
Configure los almacenes de cumplimiento de SQL Server copia de seguridad que proporcionarán bases de datos de copia de seguridad para los almacenes de cumplimiento del servidor de chat persistente o del servidor SQL Server chat persistente.
  
 **SQL Server almacén:** seleccione una instancia SQL Server existente y, opcionalmente, una instancia para chat persistente.
  
Haga **clic en** Nuevo para definir una nueva SQL Server y, opcionalmente, una nueva instancia para los datos de cumplimiento de copia de seguridad de chat persistente.
  
Active la casilla Habilitar creación de **reflejos** del almacén de SQL Server para configurar una base de datos de SQL Server y una instancia opcional que proporcionará una base de datos reflejada para los datos de cumplimiento de copia de seguridad de chat persistente.
  
Seleccione en la lista Creación de **reflejos SQL Server** almacenar una instancia SQL Server y opcional para que actúe como el reflejo de SQL Server para el servidor de cumplimiento de copia de seguridad de chat persistente SQL Server.
  
Haga **clic** en Nuevo para definir una nueva SQL Server y, opcionalmente, una nueva instancia para la creación de reflejos SQL Server chat persistente.
  
En la lista **Utilizar el testigo de creación de reflejo SQL Server para garantizar la conmutación automática por error** seleccione un SQL Server que actuará como servidor testigo en casos de conmutación por error. El servidor testigo no refleja ni hospeda datos para los servidores de chat persistente, pero garantiza que solo un SQL Server en una configuración reflejada sea el servidor activo SQL Server en cualquier momento.
  
Haga **clic en** Nuevo para definir un nuevo testigo SQL Server, opcionalmente, una instancia para el testigo de cumplimiento de copia de seguridad de chat persistente SQL Server reflejo.
  
Haga clic en **Atrás** para retroceder al diálogo de definición de grupo de servidores anterior.
  
Haga **clic en** Siguiente una vez que haya terminado de especificar las opciones para la configuración del almacén de copia de seguridad SQL Server grupo de servidores y para continuar con la definición del grupo de servidores de chat persistente.
  
Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente **Definir nuevo grupo de chat persistente**.
  
Haga clic en **Ayuda** para acceder a la ayuda contextual, como esta página.
  
## <a name="see-also"></a>Ver también

[Planear el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Requisitos del servidor para Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configurar el servicio de cumplimiento para el servidor de chat persistente en Skype Empresarial Server 2015](../../manage/persistent-chat/configure-compliance.md)
  
[Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype Empresarial Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
