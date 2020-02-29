---
title: Configurar el acceso telefónico de la reunión-salida-confirmación para los usuarios en Microsoft Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo configurar Teams para solicitar una confirmación de aceptación de llamada para evitar que los sistemas de correo de voz se conecten a reuniones cuando la persona llamada no pueda responder a la llamada.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0a7d36d499ff7466fc1e0441bfd37bd7e6f863ae
ms.sourcegitcommit: 35de08b532eb7cf58c3221210c2b3b52f8aa047e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "42339482"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Configurar la confirmación de llamada de salida de la reunión para los usuarios de Microsoft Teams

Las llamadas de llamada y llamadas conmigo son formas muy útiles de invitar a participantes a unirse a una reunión y de que los participantes existentes se unan a una reunión con un teléfono tradicional o móvil. Sin embargo, cuando la persona que llama no pueda contestar la llamada y la llamada sea respondida por un sistema de buzón de voz, el sistema de buzón de voz se conecta a la reunión y los participantes podrán escucharla hasta que se quite de la reunión.

Para evitar que los sistemas de correo de voz se conecten a las reuniones cuando se envía una llamada telefónica a un número de teléfono y la persona a quien llama no puede responder a la llamada, puede configurar Teams para solicitar una confirmación de la persona a la que se ha llamado para que se unan a la reunión. Si la persona a la que se llama no puede responder a la llamada y un sistema de buzón de voz responde a la llamada, el sistema de correo de voz no se conectará a la reunión porque no le proporcionará una confirmación.

Cuando esta capacidad está habilitada, las personas que reciben una llamada de acceso telefónico o llamarme deben confirmar que desean unirse a la reunión pulsando 1 en su teléfono tradicional o móvil.

Para habilitar esta característica en todas las reuniones de su organización, establezca ```EnableDialOutJoinConfirmation``` el parámetro del cmdlet [set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) en ```true```. Para ello, ejecute el siguiente comando:

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Temas relacionados

- [Configure la característica llamarme para sus usuarios](set-up-the-call-me-feature-for-your-users.md)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)