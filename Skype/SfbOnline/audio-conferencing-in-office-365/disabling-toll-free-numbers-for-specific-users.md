---
title: Desactivación de números de teléfono gratuitos para usuarios específicos
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: Los administradores pueden controlar cómo los organizadores pueden usar números de teléfono gratuitos para sus reuniones.
ms.openlocfilehash: 0d2b4d16d6475587dd85223e0a88f64562664429
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2018
---
# <a name="disabling-toll-free-numbers-for-specific-users"></a>Desactivación de números de teléfono gratuitos para usuarios específicos

Si su organización tiene números gratuitos en su Microsoft Audio Conferencing Bridge, puede permitir o impedir su uso en las reuniones de organizadores específicos.  

De forma predeterminada, todos los usuarios de su organización están habilitados para el uso de números de teléfono gratuitos, lo que significa que esos números, si está disponible, pueden utilizarse por los participantes para unirse a sus reuniones. Si no es el comportamiento deseado de algunos usuarios de su organización, puede evitar que usuarios específicos utilizando esos números en sus reuniones a través de un control de habilitación número gratuito. 

Cuando los números gratuitos están deshabilitados para el organizador de una determinada: 
 - Ya no se incluirán un número gratuito en su o invita su reunión. 
 - Ya no se mostrarán en la página "Buscar un número local" que se hace referencia en su números gratuitos o invita su reunión. 
 - Los participantes no pueden participar en la reunión del organizador determinado si marcar cualquier número gratuito de la organización. 
 - Se programará automáticamente todas las reuniones del organizador y se quitará el número gratuito de ellos.  

    > [!IMPORTANT]
    > Esto volverá a enviar todas las invitaciones de correo electrónico del organizador a todos los participantes de las reuniones. 

 - Los participantes pueden continuar unirse a reuniones del organizador con números de teléfono. 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Desactivación de números de teléfono gratuitos para usuarios específicos 

**Utilizando los equipos de Microsoft y Skype para el centro de administración de negocios**

1. En la exploración de la izquierda, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En la parte superior de la página, haga clic en **Editar**.

3. Haga clic en el menú situado junto a **Los puentes de conferencia**y, a continuación, haga clic en **Editar** en la lista desplegable.

4. En el panel de **proveedor de puente de conferencia** , desactive **Permitir utilizando números gratuitos en el puente de conferencia de la organización para unirse a las reuniones de este usuario**. 

5. Haga clic en **Aplicar.** 

Puede usar el Centro de administración de Skype Empresarial o Windows PowerShell para habilitar o deshabilitar el envío de correos electrónicos a los usuarios.

1. En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio** > **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles. 

2. En el panel de acciones, haga clic en **Editar**. 

3. Desactive **Permitir mediante números de teléfono gratuitos para unirse a las reuniones de este usuario**. 
 
4. Haga clic en **Guardar**. 
 
**Uso de PowerShell**  

Puede utilizar el parámetro AllowTollFreeDialIn del cmdlet Set-CsOnlineDialInConferencingUser para habilitar o deshabilitar este control. Por ejemplo: 

 - Conjunto CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false
