---
title: Deshabilitar a los números gratuitos para Skype específico para los usuarios empresariales en línea
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
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Los administradores pueden controlar cómo los organizadores pueden usar los números gratuitos para sus reuniones.
ms.openlocfilehash: 1cd144af4f57b3c4ecb19de6c4aeea36f5d2baed
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490549"
---
# <a name="disabling-toll-free-numbers-for-specific-skype-for-business-online-users"></a>Deshabilitar a los números gratuitos para Skype específico para los usuarios empresariales en línea

> [!Note]
> Para obtener información acerca de los números deshabilitar libre de herramienta para los usuarios de los equipos, vea [Deshabilitar los números gratuitos para usuarios de equipos específicos](/MicrosoftTeams/disabling-toll-free-numbers-for-specific-teams-users).

Si su organización tiene los números gratuitos en su Bridge Conferencing de Audio de Microsoft, puede permitir o impedir su uso en las reuniones de los organizadores específicos.  

De forma predeterminada, todos los usuarios de su organización están habilitados para el uso de los números gratuitos, lo que significa que dichos números, si está disponible, se pueden usar por los participantes para unirse a sus reuniones. Si no es el comportamiento deseado para algunos usuarios de su organización, puede restringir usuarios específicos de uso de dichos números en sus reuniones a través de un control de habilitación de número gratuito. 

Cuando se deshabilitan los números gratuitos para el organizador de una determinada: 
 - Un número de teléfono gratuito ya no se incluirá en su o invita su reunión. 
 - Los números gratuitos ya no se mostrarán en la página "Encontrar un número local" en el que se hace referencia en su o invita su reunión. 
 - Los participantes no puedan unirse a la reunión del organizador determinado si marcado de cualquier número de teléfono gratuito de la organización. 
 - Se volverá a programar automáticamente todas las reuniones del organizador de la, y el número de teléfono gratuito se quitará de ellos.  

    > [!IMPORTANT]
    > Esto volverá a enviar todas las invitaciones de correo electrónico del organizador a todos los participantes de las reuniones. 

 - Los participantes pueden continuar unirse a reuniones del organizador utilizando números de teléfono de pago. 

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Deshabilitar a los números gratuitos para usuarios específicos 


1. En el **Skype para el centro de administración de negocio**, en el panel de navegación izquierdo, vaya a la **conferencia de Audio** > **a los usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles. 

2. En el panel de acciones, haga clic en **Editar**. 

3. Desactive **Permitir el uso de los números gratuitos para unirse a las reuniones de este usuario**. 
 
4. Haga clic en **Guardar**. 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
 
**Uso de PowerShell**  

Puede usar el parámetro AllowTollFreeDialIn del cmdlet Set-CsOnlineDialInConferencingUser para habilitar o deshabilitar este control. Por ejemplo: 

 - Set-CsOnlineDialInConferencingUser user@contoso.com – AllowTollFreeDialIn $false
