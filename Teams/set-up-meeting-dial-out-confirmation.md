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
description: Aprenda a configurar Teams para solicitar una confirmación de llamada para evitar que los sistemas de correo de voz se conecten a las reuniones cuando la persona llamada no pueda responder a la llamada.
localization_priority: Normal
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 37d68eb90e42b57ff76d352ea2c856e6904a9308
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806150"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Configurar la confirmación de llamada de salida de la reunión para los usuarios en Microsoft Teams

Las llamadas a las llamadas y las llamadas a las reuniones son formas muy útiles de invitar a participantes a unirse a una reunión y para que los participantes existentes se unan a una reunión con un teléfono móvil o tradicional. Sin embargo, cuando la persona llamada no puede responder a la llamada y el sistema de correo de voz responde a la llamada, el sistema de correo de voz está conectado a la reunión y los participantes podrán escucharla hasta que se quite de la reunión.

Para evitar que los sistemas de correo de voz se conecten a las reuniones cuando se envía una llamada a un número de teléfono y la persona llamada no puede responder a la llamada, puede configurar Teams para solicitar una confirmación a la persona llamada para que se una a la reunión. Si la persona llamada no puede responder a la llamada y la llamada se responde con un sistema de correo de voz, el sistema de correo de voz no se conectará a la reunión porque no proporcionará una confirmación para unirse a ella.

Cuando esta función está habilitada, las personas que reciben una llamada o una llamada llamarme deben confirmar que desean unirse a la reunión pulsando 1 en su teléfono móvil o tradicional.

Para habilitar esta función para todas las reuniones de su organización, establezca el parámetro del ```EnableDialOutJoinConfirmation``` cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) en ```true``` . Para ello, ejecute el siguiente comando:

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Temas relacionados

- [Configure la característica llamarme para sus usuarios](set-up-the-call-me-feature-for-your-users.md)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)