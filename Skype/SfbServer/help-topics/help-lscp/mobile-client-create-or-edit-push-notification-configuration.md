---
title: Configuración de creación o edición de notificaciones de inserción del cliente móvil
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientPushNotificationCfgEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb39af60-c999-42fb-9538-0bd87098f508
description: La notificación de inserción y el Centro de intercambio de notificaciones de inserción (PNCH) son dos partes clave de la característica de movilidad. La notificación de inserción es el proceso mediante el cual un mensaje se envía al PNCH. El mensaje se mantiene allí hasta que puede enviarse al cliente móvil o hasta que caduca el periodo de espera.
ms.openlocfilehash: 0cd2b17f764891dbb1ad89ada27f6be0b6246ba0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810890"
---
# <a name="mobile-client-create-or-edit-push-notification-configuration"></a>Cliente móvil: Crear o editar configuración de notificaciones de inserción
 
La notificación de inserción y el Centro de intercambio de notificaciones de inserción (PNCH) son dos partes clave de la característica de movilidad. La notificación de inserción es el proceso mediante el cual un mensaje se envía al PNCH. El mensaje se mantiene allí hasta que puede enviarse al cliente móvil o hasta que caduca el periodo de espera. 
  
> [!NOTE]
> El periodo de tiempo se define en el centro de enrutamiento de notificaciones de inserción y ni el usuario ni el administrador de su implementación pueden configurarlo. 
  
Para habilitar las notificaciones de inserción, haga lo siguiente:
  
1. **Ámbito:** Tenga en cuenta el ámbito de esta directiva. Puede ser **Global**, que se aplica a todos los usuarios de esta implementación, o **Sitio**, que solo son usuarios asignados a servidores locales en el sitio especificado.
    
    > [!IMPORTANT]
    > Las opciones de configuración de directiva que se aplican en un nivel de directiva pueden sobrescribir la configuración que se aplica en otro nivel de directiva. La prioridad de la directiva es: la directiva de usuario (más influencia) invalida una directiva de sitio y, a continuación, una directiva de sitio invalida una directiva global (menor influencia). Esto significa que cuanto más se aproxime la configuración de la directiva al objeto al que afecta la directiva, más influencia tendrá en el objeto. 
  
2. Seleccione qué servicios de notificación de inserción desea habilitar activando la casilla de:
    
   - **Habilitar la notificación de inserción de Microsoft** habilitará la notificación de inserción en el PNCH basado en la nube para Windows Phone con la aplicación skype empresarial
    
   - **Habilitar la** notificación de inserción de Apple habilitará la notificación de inserción al PNCH de Apple para dispositivos que ejecutan iOS de Apple (por ejemplo, iPhone, iPad) y usan la aplicación skype empresarial
    
3. Una vez editada la directiva, haga clic en **Confirmar** para guardar los cambios. Si necesita eliminar los cambios realizados, seleccione **Cancelar**. No se guardará ningún cambio en la directiva.
    

