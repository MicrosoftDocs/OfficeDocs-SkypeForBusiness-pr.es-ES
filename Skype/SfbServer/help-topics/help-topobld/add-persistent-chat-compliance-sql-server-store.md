---
title: Agregar almacén SQL Server de cumplimiento del chat persistente
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: Configure los almacenes de cumplimiento SQL Server que proporcionarán bases de datos para la característica de cumplimiento del servidor de chat persistente o del servidor de chat persistente.
ms.openlocfilehash: 9335165bf1aa59227fe1b29103bcad0860cda541
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2022
ms.locfileid: "62395702"
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a>Agregar almacén SQL Server de cumplimiento del chat persistente
 
Configure los almacenes de cumplimiento SQL Server que proporcionarán bases de datos para la característica de cumplimiento del servidor de chat persistente o del servidor de chat persistente.
  
 **SQL Server de almacenamiento**: seleccione una instancia SQL Server existente y, opcionalmente, una instancia para chat persistente.
  
Haga **clic en** Nuevo para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para los datos de cumplimiento de chat persistente.
  
Active la casilla **Habilitar SQL Server** reflejo del almacén para configurar una base de datos SQL Server y una instancia opcional que proporcionará una base de datos reflejada para los datos de cumplimiento de chat persistente.
  
Seleccione en la lista Creación **de SQL Server** almacenar una instancia SQL Server y opcional para que actúe como el reflejo SQL Server para el servidor de cumplimiento de chat persistente SQL Server.
  
Haga **clic en** Nuevo para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para la creación de reflejos SQL Server chat persistente.
  
En la lista **Utilizar el testigo de creación de reflejo SQL Server para garantizar la conmutación automática por error** seleccione un SQL Server que actuará como servidor testigo en casos de conmutación por error. El servidor testigo no refleja ni hospeda los datos de los servidores de chat persistente, pero garantiza que solo un SQL Server en una configuración reflejada sea el servidor activo SQL Server en cualquier momento.
  
Haga **clic en** Nuevo para definir un nuevo SQL Server testigo opcionalmente una instancia para el testigo de cumplimiento de chat persistente SQL Server reflejo.
  
Haga clic en **Atrás** para retroceder al diálogo de definición de grupo de servidores anterior.
  
Haga **clic en** Siguiente después de haber terminado de especificar las opciones para la configuración del almacén de SQL Server copia de seguridad de este grupo y para continuar con la definición del grupo de servidores de chat persistente.
  
Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente **Definir nuevo grupo de chat persistente**.
  
Haga clic en **Ayuda** para acceder a la ayuda contextual, como esta página.
  
## <a name="see-also"></a>Vea también

[Planear el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Requisitos del servidor para Skype Empresarial Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configurar el servicio de cumplimiento para el servidor de chat persistente en Skype Empresarial Server 2015](../../manage/persistent-chat/configure-compliance.md)
