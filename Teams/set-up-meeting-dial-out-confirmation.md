---
title: Configurar la confirmación de llamada de salida de la reunión para los usuarios en Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
ms.reviewer: oscarr
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo configurar Teams solicitar una confirmación de acceso telefónico para evitar que los sistemas de correo de voz se conecten a reuniones cuando la persona llamada no pueda responder a la llamada.
ms.localizationpriority: medium
ms.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9db8d3882ea7d05b1bc3600682c0c803040b4c10
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055660"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Configurar la confirmación de acceso telefónico de reunión para los usuarios en Microsoft Teams

Las llamadas telefónicas de reunión y las llamadas llamarme son formas útiles de invitar a los participantes a unirse a una reunión y para que los participantes existentes se unan a una reunión con un teléfono móvil o tradicional. Sin embargo, cuando la persona llamada no puede responder a la llamada y un sistema de correo de voz responde a la llamada, el sistema de correo de voz está conectado a la reunión. Los participantes podrán escucharlo hasta que se quite de la reunión.

Para evitar que los sistemas de correo de voz se conecten a reuniones cuando se envía una llamada de salida a un número de teléfono y la persona llamada no puede responder a la llamada, puede configurar Teams para solicitar una confirmación a la persona llamada para que se una a la reunión. Si la persona llamada no puede responder a la llamada y un sistema de correo de voz responde a la llamada, el sistema de correo de voz no se conectará a la reunión porque no proporcionará una confirmación para unirse a ella.

Cuando esta capacidad está habilitada, las personas que reciben una llamada de salida o llamada de llamada deben confirmar que quieren unirse a la reunión presionando 1 en su teléfono móvil o tradicional o diciendo "Bien".

Para habilitar esta funcionalidad para todas las reuniones de su organización, establezca el parámetro del ```EnableDialOutJoinConfirmation``` cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) en ```true``` . Para establecer este parámetro, ejecute el siguiente comando:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Temas relacionados

- [Configure la característica llamarme para sus usuarios](set-up-the-call-me-feature-for-your-users.md)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
