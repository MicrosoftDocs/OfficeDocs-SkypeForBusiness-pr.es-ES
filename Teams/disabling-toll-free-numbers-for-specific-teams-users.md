---
title: Deshabilitar los números gratuitos para usuarios específicos de Teams
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Obtenga información sobre cómo controlar cómo los organizadores pueden usar números gratuitos para sus reuniones del puente de audioconferencia.
ms.openlocfilehash: 6d841a48381609a019a1749095aac4a95901a7c4
ms.sourcegitcommit: 296fbefe0481c0b8b94aee925118474375cdf138
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2022
ms.locfileid: "65016632"
---
# <a name="disabling-toll-free-numbers-for-specific-teams-users"></a>Deshabilitar los números gratuitos para usuarios específicos de Teams

Si su organización tiene números gratuitos en su puente de Audioconferencia de Microsoft, puede permitir o impedir su uso en las reuniones de organizadores específicos.  

De forma predeterminada, todos los usuarios de su organización están habilitados para el uso de los números gratuitos, lo que significa que dichos números, si están disponible, se pueden usar por los participantes para unirse a sus reuniones. Si no es el comportamiento deseado para algunos usuarios de su organización, puede restringir a usuarios específicos el uso de dichos números en sus reuniones a través de un control de habilitación de los números gratuitos.

Cuando se deshabilitan los números gratuitos para un organizador determinado:

- Ya no se incluirá un número de teléfono gratuito en sus invitaciones a reuniones.
- Los números gratuitos ya no se mostrarán en la página "Encontrar un número local" a la que se hace referencia en sus invitaciones a reuniones.
- Los participantes no podrán unirse a la reunión del organizador determinado si llaman a cualquier número de teléfono gratuito de la organización.
- Los participantes pueden continuar uniéndose a reuniones del organizador utilizando números de teléfono de pago.

## <a name="disabling-toll-free-numbers-for-specific-users"></a>Deshabilitar los números gratuitos para usuarios específicos

Puede deshabilitar los números gratuitos para usuarios específicos cambiando la configuración *de AllowTollFreeDialIn* a **Desactivado** dentro de *TeamsAudioConferencingPolicy* asignado a esos usuarios. Una vez desactivadas las nuevas reuniones creadas por dichos usuarios, no se incluirá ningún número gratuito. [La configuración de la directiva de audioconferencia para números de pago y gratuitos](audio-conferencing-toll-free-numbers-policy.md) tiene más información.

> [!IMPORTANT]
> Las reuniones periódicas antiguas y programadas anteriormente pueden seguir mostrando números gratuitos y los participantes no podrán unirse a dichas reuniones con un número gratuito. Puede volver a programar todas las reuniones antiguas y periódicas para estos usuarios y quitarles números gratuitos con MMS.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
