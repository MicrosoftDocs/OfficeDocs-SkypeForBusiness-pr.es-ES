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
# <a name="set-up-meeting-dial-out-confirmation-for-your-users-in-microsoft-teams"></a><span data-ttu-id="85fc2-103">Configurar la confirmación de llamada de salida de la reunión para los usuarios de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="85fc2-103">Set up meeting dial-out confirmation for your users in Microsoft Teams</span></span>

<span data-ttu-id="85fc2-104">Las llamadas de llamada y llamadas conmigo son formas muy útiles de invitar a participantes a unirse a una reunión y de que los participantes existentes se unan a una reunión con un teléfono tradicional o móvil.</span><span class="sxs-lookup"><span data-stu-id="85fc2-104">Meeting dial outs and Call me calls are very useful ways to invite participants to join a meeting and for existing participants to join a meeting using a traditional or mobile phone.</span></span> <span data-ttu-id="85fc2-105">Sin embargo, cuando la persona que llama no pueda contestar la llamada y la llamada sea respondida por un sistema de buzón de voz, el sistema de buzón de voz se conecta a la reunión y los participantes podrán escucharla hasta que se quite de la reunión.</span><span class="sxs-lookup"><span data-stu-id="85fc2-105">However, when the called person is unable to answer the call and the call is answered by a voicemail system, the voicemail system is connected to the meeting and participants will be able to listen to it until it’s removed from the meeting.</span></span>

<span data-ttu-id="85fc2-106">Para evitar que los sistemas de correo de voz se conecten a las reuniones cuando se envía una llamada telefónica a un número de teléfono y la persona a quien llama no puede responder a la llamada, puede configurar Teams para solicitar una confirmación de la persona a la que se ha llamado para que se unan a la reunión.</span><span class="sxs-lookup"><span data-stu-id="85fc2-106">To prevent voicemail systems from connecting to meetings when a meeting dial out is sent to a phone number and the called person is unable to answer the call, you can set up Teams to request a confirmation from the called person for them to join the meeting.</span></span> <span data-ttu-id="85fc2-107">Si la persona a la que se llama no puede responder a la llamada y un sistema de buzón de voz responde a la llamada, el sistema de correo de voz no se conectará a la reunión porque no le proporcionará una confirmación.</span><span class="sxs-lookup"><span data-stu-id="85fc2-107">If the called person can’t answer the call and the call is answered by a voicemail system, the voicemail system won‘t be connected to the meeting because it won’t provide a confirmation to join it.</span></span>

<span data-ttu-id="85fc2-108">Cuando esta capacidad está habilitada, las personas que reciben una llamada de acceso telefónico o llamarme deben confirmar que desean unirse a la reunión pulsando 1 en su teléfono tradicional o móvil.</span><span class="sxs-lookup"><span data-stu-id="85fc2-108">When this capability is enabled, people that receive a dial out or Call me call must confirm that they want to join the meeting by pressing 1 on their traditional or mobile phone.</span></span>

<span data-ttu-id="85fc2-109">Para habilitar esta característica en todas las reuniones de su organización, establezca ```EnableDialOutJoinConfirmation``` el parámetro del cmdlet [set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) en ```true```.</span><span class="sxs-lookup"><span data-stu-id="85fc2-109">To enable this capability for all meetings in your organization, set the ```EnableDialOutJoinConfirmation``` parameter of the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to ```true```.</span></span> <span data-ttu-id="85fc2-110">Para ello, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="85fc2-110">To do this, run the following command:</span></span>

```
Set-CsOnlineDialInConferencingTenantSettings -EnableDialOutJoinConfirmation $true
```

## <a name="related-topics"></a><span data-ttu-id="85fc2-111">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="85fc2-111">Related topics</span></span>

- [<span data-ttu-id="85fc2-112">Configure la característica llamarme para sus usuarios</span><span class="sxs-lookup"><span data-stu-id="85fc2-112">Set up the Call me feature for your users</span></span>](set-up-the-call-me-feature-for-your-users.md)
- [<span data-ttu-id="85fc2-113">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="85fc2-113">Teams PowerShell overview</span></span>](teams-powershell-overview.md)