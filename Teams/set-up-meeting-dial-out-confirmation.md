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
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a><span data-ttu-id="6dad6-103">Configurar la confirmación de acceso telefónico de reunión para los usuarios en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6dad6-103">Set up meeting dial-out confirmation for your users in Microsoft Teams</span></span>

<span data-ttu-id="6dad6-104">Los accesos telefónicos a reuniones y las llamadas llamarme son formas muy útiles de invitar a los participantes a unirse a una reunión y para que los participantes existentes se unan a una reunión con un teléfono móvil o tradicional.</span><span class="sxs-lookup"><span data-stu-id="6dad6-104">Meeting dial outs and Call me calls are very useful ways to invite participants to join a meeting and for existing participants to join a meeting using a traditional or mobile phone.</span></span> <span data-ttu-id="6dad6-105">Sin embargo, cuando la persona llamada no puede responder a la llamada y un sistema de correo de voz responde a la llamada, el sistema de correo de voz está conectado a la reunión y los participantes podrán escucharla hasta que se quite de la reunión.</span><span class="sxs-lookup"><span data-stu-id="6dad6-105">However, when the called person is unable to answer the call and the call is answered by a voicemail system, the voicemail system is connected to the meeting and participants will be able to listen to it until it’s removed from the meeting.</span></span>

<span data-ttu-id="6dad6-106">Para evitar que los sistemas de correo de voz se conecten a reuniones cuando se envía una llamada de salida a un número de teléfono y la persona llamada no puede responder a la llamada, puede configurar Teams para solicitar una confirmación a la persona llamada para que se una a la reunión.</span><span class="sxs-lookup"><span data-stu-id="6dad6-106">To prevent voicemail systems from connecting to meetings when a meeting dial out is sent to a phone number and the called person is unable to answer the call, you can set up Teams to request a confirmation from the called person for them to join the meeting.</span></span> <span data-ttu-id="6dad6-107">Si la persona llamada no puede responder a la llamada y un sistema de correo de voz responde a la llamada, el sistema de correo de voz no se conectará a la reunión porque no proporcionará una confirmación para unirse a ella.</span><span class="sxs-lookup"><span data-stu-id="6dad6-107">If the called person can’t answer the call and the call is answered by a voicemail system, the voicemail system won‘t be connected to the meeting because it won’t provide a confirmation to join it.</span></span>

<span data-ttu-id="6dad6-108">Cuando esta funcionalidad está habilitada, las personas que reciben una llamada de salida o llamada llamarme deben confirmar que quieren unirse a la reunión presionando 1 en su teléfono móvil o tradicional.</span><span class="sxs-lookup"><span data-stu-id="6dad6-108">When this capability is enabled, people that receive a dial out or Call me call must confirm that they want to join the meeting by pressing 1 on their traditional or mobile phone.</span></span>

<span data-ttu-id="6dad6-109">Para habilitar esta funcionalidad para todas las reuniones de su organización, establezca el parámetro del ```EnableDialOutJoinConfirmation``` cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) en ```true``` .</span><span class="sxs-lookup"><span data-stu-id="6dad6-109">To enable this capability for all meetings in your organization, set the ```EnableDialOutJoinConfirmation``` parameter of the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to ```true```.</span></span> <span data-ttu-id="6dad6-110">Para ello, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="6dad6-110">To do this, run the following command:</span></span>

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a><span data-ttu-id="6dad6-111">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="6dad6-111">Related topics</span></span>

- [<span data-ttu-id="6dad6-112">Configure la característica llamarme para sus usuarios</span><span class="sxs-lookup"><span data-stu-id="6dad6-112">Set up the Call me feature for your users</span></span>](set-up-the-call-me-feature-for-your-users.md)
- [<span data-ttu-id="6dad6-113">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="6dad6-113">Teams PowerShell overview</span></span>](teams-powershell-overview.md)