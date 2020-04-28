---
title: Deshabilitar los números gratuitos para usuarios específicos de Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Obtenga información sobre cómo controlar la forma en que los organizadores pueden usar números gratuitos para sus reuniones de puente de audioconferencia.
ms.openlocfilehash: 517ffea6a15cd625320f33e3eb4911f4a250d51d
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904575"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>Deshabilitar los números gratuitos para usuarios específicos de Teams

Si su organización tiene números gratuitos en su puente de Audioconferencia de Microsoft, puede permitir o impedir su uso en las reuniones de organizadores específicos.  

De forma predeterminada, todos los usuarios de su organización están habilitados para el uso de los números gratuitos, lo que significa que dichos números, si están disponible, se pueden usar por los participantes para unirse a sus reuniones. Si no es el comportamiento deseado para algunos usuarios de su organización, puede restringir a usuarios específicos el uso de dichos números en sus reuniones a través de un control de habilitación de los números gratuitos. 

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

2. Junto a **Audioconferencia**, haga clic en **Editar**.

3. Set **incluye números gratuitos en las convocatorias de reunión de este usuario** como **deshabilitado**. 

4. Haga clic en **Guardar**. 

 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
 
**Uso de PowerShell**  

Vea la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.
