---
title: Deshabilitar los números gratuitos para usuarios específicos de Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Los administradores pueden controlar cómo los organizadores pueden usar los números gratuitos para sus reuniones.
ms.openlocfilehash: 42323afd397612c3cdc0549bdcc33b16cfdae9ea
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41695685"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a>Deshabilitar los números gratuitos para usuarios específicos de Skype for Business Online
 
> [!Note]
> Para obtener información acerca de deshabilitar los números gratuitos para los usuarios de Teams, vea [Deshabilitar los números gratuitos para usuarios específicos de Teams](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).

Si su organización tiene números gratuitos en su puente de Audioconferencia de Microsoft, puede permitir o impedir su uso en las reuniones de organizadores específicos.  

By default, all users in your organization are enabled for using toll-free numbers, meaning that those numbers, if available, can be used by participants to join their meetings. If this is not the desired behavior for some users in your organization, you can restrict specific users from using those numbers in their meetings via a toll-free number enablement control. 

Cuando se deshabilitan los números gratuitos para un organizador determinado: 
 - Ya no se incluirá un número de teléfono gratuito en sus invitaciones a reuniones. 
 - Los números gratuitos ya no se mostrarán en la página "Encontrar un número local" a la que se hace referencia en sus invitaciones a reuniones. 
 - Los participantes no podrán unirse a la reunión del organizador determinado si llaman a cualquier número de teléfono gratuito de la organización. 
 - Se volverán a programar automáticamente todas las reuniones del organizador y el número de teléfono gratuito se quitará de ellas.  

    > [!IMPORTANT]
    > Esto hará que se vuelvan a enviar todas las invitaciones de correo electrónico del organizador a todos los participantes de las reuniones. 

 - Los participantes pueden continuar uniéndose a reuniones del organizador utilizando números de teléfono de pago. 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Deshabilitar los números gratuitos para usuarios específicos 

Desde el **centro de administración de Microsoft Teams**:

1. En el navegación de la izquierda, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. Junto a **audioconferencia**, haga clic en **Editar**.

3. Set **incluye números gratuitos en las convocatorias de reunión de este usuario** como **deshabilitado**. 

4. Haga clic en **Guardar.** 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
**Usar PowerShell**  

Puede usar el parámetro AllowTollFreeDialIn del cmdlet Set-CsOnlineDialInConferencingUser para habilitar o deshabilitar este control. Por ejemplo: 

- Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false
