---
title: Definir propiedades y opciones para grupo de servidores de chat persistente
ms.reviewer: ''
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
description: 'Configurar opciones para el servidor de Chat persistente o grupo de servidores de Chat persistente mediante la definición de las siguientes propiedades:'
ms.openlocfilehash: 380a1e34e041368d4520cd5c8ecea5b18284ef51
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226924"
---
# <a name="define-properties-and-options-for-persistent-chat-pool"></a>Definir propiedades y opciones para grupo de servidores de chat persistente
 
Configurar opciones para el servidor de Chat persistente o grupo de servidores de Chat persistente mediante la definición de las siguientes propiedades:
  
 **Nombre para mostrar del grupo de Chat persistente**: una propiedad obligatoria que define un nombre descriptivo que se mostrará para este servidor de Chat persistente o grupo de servidores de Chat persistente.
  
 **Puerto de Chat persistente**: una propiedad obligatoria que definirá el puerto de número que este servidor de Chat persistente o grupo de servidores de Chat persistente escuchará en.
  
 **Habilitar cumplimiento**: Active la casilla de verificación si tiene previsto implementar la característica de cumplimiento de normas de Chat persistente opcional y una base de datos.
  
 **Usar copia de seguridad de SQL Server almacena para habilitar la recuperación ante desastres**: seleccione esta casilla de verificación si tiene previsto implementar y la recuperación ante desastres de Persistent Chat SQL Server se almacena en un conjunto de copia de seguridad configurado de almacenes en otro servidor SQL Server. Para obtener información detallada, vea [Configure una alta disponibilidad y recuperación ante desastres para servidor de Chat persistente en Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).
  
> [!NOTE]
> Esta opción solamente está disponible para grupos de servidores con varios servidores. 
  
 **Utilizar este grupo de servidores como predeterminado para el sitio \<sitio que este servidor o grupo de servidores se configura en\>**: seleccione esta casilla de verificación si se trata de la predeterminada del servidor de Chat persistente o grupo de servidores de Chat persistente para el sitio. Debe tener un servidor de Chat persistente predeterminado o pol por sitio.
  
> [!NOTE]
> Si la topología incluye varios sitios, también aparecerá una casilla **Usar este grupo como predeterminado para todos los sitios**.
  
Haga clic en **Atrás** para retroceder al cuadro de diálogo anterior de definición del grupo de servidores.
  
Haga clic en **siguiente** cuando haya terminado de introducir las opciones de este grupo de servidores proceder con la definición de grupo de servidores de servidor de Chat persistente.
  
Haga clic en **Cancelar** para descartar todos los cambios y finalizar el asistente **Definir nuevo grupo de chat persistente**.
  
Haga clic en **Ayuda** para obtener acceso a la ayuda contextual, como esta página.
  
## <a name="see-also"></a>Vea también

[Planificar el servidor de chat persistente en Skype Empresarial Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Agregar servidor de Chat persistente a su Skype para topología empresarial Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
