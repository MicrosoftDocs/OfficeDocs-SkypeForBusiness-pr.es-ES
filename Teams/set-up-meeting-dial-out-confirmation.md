---
title: Configurar la confirmación de llamada de salida de la reunión para los usuarios en Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo configurar Teams solicitar una confirmación de acceso telefónico para evitar que los sistemas de correo de voz se conecten a reuniones cuando la persona llamada no pueda responder a la llamada.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4bfa15bdb0e58066d085aa852f671c6d89ff1b90
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117098"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Configurar la confirmación de acceso telefónico de reunión para los usuarios en Microsoft Teams

Los accesos telefónicos a reuniones y las llamadas llamarme son formas muy útiles de invitar a los participantes a unirse a una reunión y para que los participantes existentes se unan a una reunión con un teléfono móvil o tradicional. Sin embargo, cuando la persona llamada no puede responder a la llamada y un sistema de correo de voz responde a la llamada, el sistema de correo de voz está conectado a la reunión y los participantes podrán escucharla hasta que se quite de la reunión.

Para evitar que los sistemas de correo de voz se conecten a reuniones cuando se envía una llamada de salida a un número de teléfono y la persona llamada no puede responder a la llamada, puede configurar Teams para solicitar una confirmación a la persona llamada para que se una a la reunión. Si la persona llamada no puede responder a la llamada y un sistema de correo de voz responde a la llamada, el sistema de correo de voz no se conectará a la reunión porque no proporcionará una confirmación para unirse a ella.

Cuando esta funcionalidad está habilitada, las personas que reciben una llamada de salida o llamada llamarme deben confirmar que quieren unirse a la reunión presionando 1 en su teléfono móvil o tradicional.

Para habilitar esta funcionalidad para todas las reuniones de su organización, establezca el parámetro del ```EnableDialOutJoinConfirmation``` cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) en ```true``` . Para ello, ejecute el siguiente comando:

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Temas relacionados

- [Configure la característica llamarme para sus usuarios](set-up-the-call-me-feature-for-your-users.md)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)