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
description: Obtenga información sobre cómo configurar Teams para solicitar una confirmación de llamada de salida para evitar que los sistemas de correo de voz se conecten a las reuniones cuando la persona que llama no puede responder a la llamada.
ms.localizationpriority: medium
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: a74a02b8d6c0a11202676144ce2dba91618118c9
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271565"
---
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a>Configurar la confirmación de llamada de salida de la reunión para los usuarios en Microsoft Teams

Las llamadas de llamada de reunión y las llamadas de Llamarme son formas útiles de invitar a los participantes a unirse a una reunión y de que los participantes existentes se unan a una reunión con un teléfono móvil o tradicional. Sin embargo, cuando el autor de la llamada no puede responder a la llamada y la llamada se responde mediante un sistema de correo de voz, el sistema de correo de voz se conecta a la reunión. Los participantes podrán escucharlo hasta que se elimine de la reunión.

Para evitar que los sistemas de correo de voz se conecten a las reuniones cuando se envía una llamada de reunión a un número de teléfono y la persona a la que se llama no puede responder a la llamada, puede configurar Teams para que solicite una confirmación a la persona que llama para que se una a la reunión. Si la persona que llama no puede responder a la llamada y la llamada es contestada por un sistema de correo de voz, el sistema de correo de voz no se conectará a la reunión porque no proporcionará una confirmación para unirse a ella.

Cuando esta funcionalidad está habilitada, las personas que reciben una llamada telefónica o llamada Llamarme deben confirmar que quieren unirse a la reunión presionando 1 en su teléfono móvil o tradicional o diciendo "De acuerdo". La confirmación impedirá que el mensaje de correo de voz del usuario se una a la reunión.

Para habilitar esta funcionalidad para todas las reuniones de su organización, establezca el ```EnableDialOutJoinConfirmation``` parámetro del cmdlet ```true```[Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) en . Para establecer este parámetro, ejecute el siguiente comando:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a>Temas relacionados

- [Configure la característica llamarme para sus usuarios](set-up-the-call-me-feature-for-your-users.md)
- [Descripción de PowerShell para Teams](teams-powershell-overview.md)
