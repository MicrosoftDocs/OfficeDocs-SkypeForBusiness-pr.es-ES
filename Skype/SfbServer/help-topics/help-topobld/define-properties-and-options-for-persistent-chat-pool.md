---
title: Definir propiedades y opciones para grupo de servidores de chat persistente
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
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Las opciones para el servidor de chat persistente o el grupo de servidores de chat persistente se configuran definiendo las siguientes propiedades:'
ms.openlocfilehash: acc80c76e79364be730ec56a2b64e5dcd001f661
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818430"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>Definir propiedades y opciones para grupo de servidores de chat persistente
 
Las opciones para el servidor de chat persistente o el grupo de servidores de chat persistente se configuran definiendo las siguientes propiedades:
  
 **Nombre para mostrar del** grupo de chat persistente: una propiedad necesaria que define un nombre descriptivo que se mostrará para este servidor de chat persistente o grupo de servidores de chat persistente.
  
 **Puerto de chat persistente:** una propiedad necesaria que definirá el número de puerto en el que escuchará este servidor de chat persistente o grupo de servidores de chat persistente.
  
 **Habilitar cumplimiento:** active la casilla si tiene previsto implementar la base de datos y la característica opcional de cumplimiento de chat persistente.
  
 **Use** almacenes de SQL Server de copia de seguridad para habilitar la recuperación ante desastres: active esta casilla si tiene previsto implementar e implementar la recuperación ante desastres de los almacenes de SQL Server de chat persistente de un conjunto de almacenes de copia de seguridad configurado en otro SQL Server. Para obtener más información, consulte Configurar la alta disponibilidad y la recuperación ante desastres para el servidor de [chat persistente en Skype Empresarial Server 2015.](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
  
> [!NOTE]
> Esta opción solamente está disponible para grupos de servidores con varios servidores. 
  
 **Use este grupo de \<site that this server or pool is being configured in\> servidores como** predeterminado para el sitio: active esta casilla si será el servidor de chat persistente predeterminado o el grupo de servidores de chat persistente para el sitio. Debe tener un servidor de chat persistente o pol predeterminado por sitio.
  
> [!NOTE]
> Si la topología incluye varios sitios también aparecerá una casilla de verificación para **Usar este grupo de servidores como predeterminado para todos los sitios**.
  
Haga clic en **Atrás** para retroceder al diálogo de definición de grupo de servidores anterior.
  
Haga **clic en** Siguiente una vez que haya terminado de especificar las opciones para que este grupo continúe con la definición del grupo de servidores de chat persistente.
  
Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente **Definir nuevo grupo de chat persistente**.
  
Haga clic en **Ayuda** para acceder a la ayuda contextual, como esta página.
  
## <a name="see-also"></a>Ver también

[Planear el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Agregar un servidor de chat persistente a la topología de Skype Empresarial Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
