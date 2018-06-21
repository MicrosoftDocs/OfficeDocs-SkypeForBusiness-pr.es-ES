---
title: Clientes móviles crear o editar la configuración de notificaciones de inserción
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
description: Las notificaciones de inserción y el centro de enrutamiento de notificaciones de inserción (PNCH) son dos partes esenciales de la característica de movilidad. La notificación de inserción es el proceso por el cual un mensaje se envía al PNCH. El mensaje se mantiene allí hasta que puede enviarse al cliente móvil o hasta que el tiempo de espera se agota.
ms.openlocfilehash: 6b5aa62b7b89729ef80e215302744dd02f444731
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/21/2018
ms.locfileid: "19988484"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a>Cliente móvil: Crear o editar configuración de notificaciones de inserción
 
Las notificaciones de inserción y el centro de enrutamiento de notificaciones de inserción (PNCH) son dos partes esenciales de la característica de movilidad. La notificación de inserción es el proceso por el cual un mensaje se envía al PNCH. El mensaje se mantiene allí hasta que puede enviarse al cliente móvil o hasta que el tiempo de espera se agota. 
  
> [!NOTE]
> El período de tiempo se define en el centro de enrutamiento de notificaciones de inserción y ni el usuario ni el administrador de la implementación pueden configurarlo. 
  
Haga lo siguiente para habilitar las notificaciones de inserción:
  
1. **Ámbito:** tenga en cuenta el ámbito de esta directiva. Puede ser **Global** (se aplica a todos los usuarios de la implementación) o **Sitio** (solo para usuarios asignados a servidores hospedados en el sitio especificado).
    
    > [!IMPORTANT]
    > La configuración de directiva que se aplica en un nivel de directiva puede invalidar la configuración que se aplica en otro nivel de directiva. La precedencia de directiva es esta: la directiva de usuario (de mayor influencia) invalida una directiva de sitio, y una directiva de sitio invalida una directiva global (de menor influencia). Esto significa que, cuanto más cercana es la configuración de directiva al objeto al que la directiva afecta, mayor es la influencia que ejerce sobre el objeto. 
  
2. Seleccione qué servicios de notificación de inserción desea habilitar activando la casilla correspondiente:
    
  - **Notificación de inserción de habilitar Microsoft** habilitará la notificación de inserción a la de PNCH basada en la nube para Windows Phone con la Skype para la aplicación empresarial
    
  - **Notificación de inserción de Apple habilitar** habilitará la notificación de inserción para PNCH de Apple para dispositivos que ejecutan iOS de Apple (por ejemplo, iPhone, iPad) y usan el Skype para la aplicación empresarial
    
3. Una vez editada la directiva, haga clic en **Confirmar** para guardar los cambios. Si prefiere eliminar los cambios realizados, seleccione **Cancelar**. No se guardará ningún cambio en la directiva.
    

