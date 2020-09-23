---
title: Definir propiedades y opciones para grupo de servidores de chat persistente
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
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Para configurar las opciones del servidor de chat persistente o del grupo de servidores de chat persistente, defina las siguientes propiedades:'
ms.openlocfilehash: 8d3cef04d7089ffff640740bb048ca52cf7fd91e
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218551"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>Definir propiedades y opciones para grupo de servidores de chat persistente
 
Para configurar las opciones del servidor de chat persistente o del grupo de servidores de chat persistente, defina las siguientes propiedades:
  
 **Nombre para mostrar del grupo de chat persistente**: una propiedad obligatoria que define un nombre descriptivo de usuario que se mostrará para este servidor de chat persistente o grupo de servidores de chat persistente.
  
 **Puerto de chat persistente**: una propiedad necesaria que definirá el número de puerto en el que escuchará este servidor de chat persistente o el grupo de servidores de chat persistente.
  
 **Habilitar cumplimiento**: Active la casilla si tiene previsto implementar e implementar la base de datos y la característica de cumplimiento de chat persistente opcional.
  
 **Usar almacenes de SQL Server de copia de seguridad para habilitar la recuperación ante desastres**: Active esta casilla si va a implementar e implementar la recuperación ante desastres de los almacenes de SQL Server de chat persistente desde un conjunto de copias de seguridad configurado en otro servidor SQL Server. Para obtener más información, consulte [Configure High Availability and Disaster Recovery for persistent chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).
  
> [!NOTE]
> Esta opción solamente está disponible para grupos de servidores con varios servidores. 
  
 **Usar este grupo de servidores como predeterminado para \<site that this server or pool is being configured in\> el sitio **: Seleccione esta casilla si va a ser el servidor de chat persistente predeterminado o el grupo de servidores de chat persistente del sitio. Debe tener un servidor de chat persistente predeterminado o Pol por sitio.
  
> [!NOTE]
> Si la topología incluye varios sitios también aparecerá una casilla de verificación para **Usar este grupo de servidores como predeterminado para todos los sitios**.
  
Haga clic en **Atrás** para retroceder al diálogo de definición de grupo de servidores anterior.
  
Haga clic en **siguiente** cuando haya terminado de introducir las opciones de este grupo para continuar con la definición del grupo de servidores de chat persistente.
  
Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente **Definir nuevo grupo de chat persistente**.
  
Haga clic en **Ayuda** para acceder a la ayuda contextual, como esta página.
  
## <a name="see-also"></a>Vea también

[Planeación del servidor de chat persistente en Skype empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Agregar un servidor de chat persistente a la topología de Skype empresarial Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
