---
title: Deshabilitar a los números gratuitos para usuarios de equipos específicos
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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Los administradores pueden controlar cómo los organizadores pueden usar los números gratuitos para sus reuniones.
ms.openlocfilehash: 8fafe87823308035d2626d891ae12b72c2bcfeca
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23852160"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>Deshabilitar a los números gratuitos para usuarios de equipos específicos

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

1. En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En la parte superior de la página, haga clic en **Editar**.

3. Junto a **Conferencias de Audio**, haga clic en **Editar**.

4. Desactivar la opción de **incluir los números gratuitos en las convocatorias de reunión de este usuario**. 

5. Haga clic en **Guardar.** 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
**Uso de PowerShell**  

Vea la [referencia de PowerShell de los equipos de Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.
