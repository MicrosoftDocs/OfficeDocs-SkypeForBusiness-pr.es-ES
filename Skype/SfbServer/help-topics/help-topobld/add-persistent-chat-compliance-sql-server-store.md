---
title: Agregar almacén SQL Server de cumplimiento del chat persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddPersistentChatComplianceStorePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9771b53-e19a-4a12-bf01-24bae6f7e482
description: Configure los almacenes de cumplimiento de SQL Server que proporcionarán bases de datos para el servidor de chat persistente o la característica de cumplimiento del servidor de chat persistente.
ms.openlocfilehash: 64697fbe9783bbdf356a28882f7cf53e7e96ef94
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698075"
---
# <a name="add-persistent-chat-compliance-sql-server-store"></a>Agregar almacén SQL Server de cumplimiento del chat persistente
 
Configure los almacenes de cumplimiento de SQL Server que proporcionarán bases de datos para el servidor de chat persistente o la característica de cumplimiento del servidor de chat persistente.
  
 **Almacén de SQL Server**: Seleccione un SQL Server existente y, opcionalmente, una instancia para una conversación persistente.
  
Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para los datos de cumplimiento de la conversación persistente.
  
Seleccione la casilla habilitar el reflejo de la **tienda SQL Server** para configurar una base de datos de SQL Server y una instancia opcional que proporcione una base de datos reflejada para los datos de cumplimiento de la conversación.
  
Seleccione en la lista **reflejo de SQL Server** un SQL Server y una instancia opcional para actuar como SQL Server Mirror para el servidor SQL Server de cumplimiento persistente.
  
Haga clic en **nuevo** para definir un nuevo SQL Server y, opcionalmente, una nueva instancia para el reflejo de SQL Server de chat persistente.
  
En la lista **Usar el testigo de creación de reflejo de SQL Server para habilitar la conmutación tras fallo automática**, seleccione un almacén de SQL Server que actúe como servidor testigo en casos de conmutación por error. El servidor testigo no refleja ni hospeda datos para los servidores de chat persistentes, pero garantiza que solo un SQL Server en una configuración duplicada es el servidor SQL activo en cualquier momento.
  
Haga clic en **nuevo** para definir un nuevo testigo de SQL Server, opcionalmente, una instancia del testigo de reflejo de SQL Server de cumplimiento persistente.
  
Haga clic en **Atrás** para retroceder al cuadro de diálogo anterior de definición de grupo de servidores.
  
Haga clic en **siguiente** cuando haya terminado de escribir las opciones para la configuración de la copia de seguridad de la tienda SQL Server y continuar con la definición del grupo de servidores de chat persistente.
  
Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente **Definir nuevo grupo de chat persistente**.
  
Haga clic en **Ayuda** para obtener acceso a la ayuda contextual, como esta página.
  
## <a name="see-also"></a>Vea también

[Planificar el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)
  
[Requisitos de hardware y software para el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/hardware-and-software-requirements.md)
  
[Configurar el servicio de cumplimiento para el servidor de chat persistente en Skype Empresarial Server 2015](../../manage/persistent-chat/configure-compliance.md)
