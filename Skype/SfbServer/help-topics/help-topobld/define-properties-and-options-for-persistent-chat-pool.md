---
title: Definir propiedades y opciones para grupo de servidores de chat persistente
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddPersistentChatOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f4914a44-2113-48f1-8299-4645fc7011b6
description: 'Configurar opciones para el servidor de charla persistente o el grupo de servidores de charla persistente mediante la definición de las propiedades siguientes:'
ms.openlocfilehash: 445e84b4be0567b63b9a56a7bc130e584a826430
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>Definir propiedades y opciones para grupo de servidores de chat persistente
 
Configurar opciones para el servidor de charla persistente o el grupo de servidores de charla persistente mediante la definición de las propiedades siguientes:
  
 **Nombre para mostrar del grupo de servidores de charla persistente**: una propiedad necesaria que define un nombre de usuario descriptivo que se mostrará para este servidor de Chat persistentes o el grupo de servidores de charla persistente.
  
 **Puerto de Chat persistentes**: una propiedad requiere que se defina el puerto número que este servidor de Chat persistentes o grupo persistente Chat Server escuchará en.
  
 **Permitir el cumplimiento**: Active la casilla de verificación si piensa implementar y la función opcional de conformidad Chat persistente y la base de datos.
  
 **Utilice copia de seguridad de SQL Server almacena para permitir una recuperación ante desastres**: seleccione esta casilla si va a implementar y la recuperación de desastres de la persistente de SQL Server de Chat se almacena en un conjunto de copia de seguridad configurado de almacenes en otro SQL Server. Para obtener información detallada, vea [configurar alta disponibilidad y recuperación ante desastres para el servidor de charla persistente en Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).
  
> [!NOTE]
> Esta opción solamente está disponible para grupos de servidores con varios servidores. 
  
 **Utilizar este grupo como predeterminado para el sitio \<sitio está configurado en este servidor o grupo de\>**: Active esta casilla si va a ser el predeterminado del servidor de charla persistente o grupo de servidor de charla persistente para el sitio. Debe tener un servidor de Chat persistentes predeterminado o pol por sitio.
  
> [!NOTE]
> Si la topología incluye varios sitios, también aparecerá una casilla **Usar este grupo como predeterminado para todos los sitios**.
  
Haga clic en **Atrás** para retroceder al cuadro de diálogo anterior de definición del grupo de servidores.
  
Haga clic en **siguiente** cuando haya terminado de especificar las opciones para este grupo continuar con la definición de grupo del servidor de Chat persistentes.
  
Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente **Definir el nuevo grupo de chat persistente**.
  
Haga clic en **Ayuda** para obtener acceso a la ayuda contextual, como esta página.
  
## <a name="see-also"></a>Vea también

#### 

[Plan para el servidor de charla persistente en Skype para Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Agregar servidor de Chat persistentes a su Skype para la topología de servidor de negocios 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)

