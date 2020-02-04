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
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Para configurar las opciones del servidor de chat persistente o del grupo de servidores de chat persistente, defina las siguientes propiedades:'
ms.openlocfilehash: 458e50ecc3ddd389a8e413e8f2dd368fc0f15369
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697555"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>Definir propiedades y opciones para grupo de servidores de chat persistente
 
Para configurar las opciones del servidor de chat persistente o del grupo de servidores de chat persistente, defina las siguientes propiedades:
  
 **Nombre para mostrar del grupo de chats persistentes**: una propiedad obligatoria que define un nombre descriptivo de usuario que se mostrará para este servidor de chat persistente o grupo de servidores de chat persistente.
  
 **Puerto de chat persistente**: propiedad necesaria que definirá el número de puerto en el que escuchará este servidor de chat persistente o el grupo de servidores de chat persistente.
  
 **Habilitar cumplimiento**: Active la casilla si tiene previsto implementar e implementar la característica de cumplimiento de la conversación persistente y la base de datos opcional.
  
 **Use la copia de seguridad de almacenes de SQL Server para habilitar la recuperación de desastres**: Seleccione esta casilla si desea implementar e implementar la recuperación de desastres de los almacenes de SQL Server de la conversación persistente desde un conjunto de almacenes de copia de seguridad configurado en otro servidor SQL Server. Para obtener más información, consulte [configurar la alta disponibilidad y la recuperación ante desastres para el servidor de chat persistente en Skype empresarial server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).
  
> [!NOTE]
> Esta opción solamente está disponible para grupos de servidores con varios servidores. 
  
 **Use este grupo como predeterminado para el sitio \<del sitio en el que se está configurando\>este servidor o grupo de**servidores: Active esta casilla si este es el servidor de chat persistente predeterminado o el grupo de servidores de chat persistente para el sitio. Debe tener un servidor de chat persistente predeterminado o Pol por sitio.
  
> [!NOTE]
> Si la topología incluye varios sitios, también aparecerá una casilla **Usar este grupo como predeterminado para todos los sitios**.
  
Haga clic en **Atrás** para retroceder al cuadro de diálogo anterior de definición del grupo de servidores.
  
Haga clic en **siguiente** cuando haya terminado de escribir las opciones de este grupo para continuar con la definición del grupo de servidores de chat persistente.
  
Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente **Definir nuevo grupo de chat persistente**.
  
Haga clic en **Ayuda** para obtener acceso a la ayuda contextual, como esta página.
  
## <a name="see-also"></a>Vea también

[Planificar el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Agregar un servidor de chat persistente a su topología de 2015 de Skype empresarial Server](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
