---
title: Llamar desde una reunión para que otras personas puedan unirse
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 3c2db9a5-3a19-4e19-b59e-8e5587f25d31
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
- seo-marvel-apr2020
description: Los organizadores de reuniones pueden obtener información sobre cómo marcar usando la aplicación de Teams para permitir que otras personas se unan a la misma reunión con sus teléfonos.
ms.openlocfilehash: f84f811d89847bfdf17f123abe9c2df88536bc76
ms.sourcegitcommit: 7a9c63ee790108eaa61950ce28ae8027311039d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662110"
---
# <a name="dialing-out-from-a-microsoft-teams-meeting-so-other-people-can-join-it"></a><span data-ttu-id="4bb7d-103">Llamar desde una reunión de Microsoft Teams para que otras personas puedan unirse</span><span class="sxs-lookup"><span data-stu-id="4bb7d-103">Dialing out from a Microsoft Teams meeting so other people can join it</span></span>

<span data-ttu-id="4bb7d-104">Como organizador de la reunión, puede marcar usando la aplicación de Teams para permitir que otras personas se unan a la misma reunión usando sus teléfonos.</span><span class="sxs-lookup"><span data-stu-id="4bb7d-104">As the meeting organizer, you can dial out using the Teams app to let other people join the same meeting using their phones.</span></span>

<span data-ttu-id="4bb7d-105">Cuando llames a alguien, te recomendamos que lo uses con sus números de teléfono completos (incluido el código de país o región, es decir, el formato E. 164).</span><span class="sxs-lookup"><span data-stu-id="4bb7d-105">When you dial out to someone, we recommend that you do so using their full phone numbers (including the country/region code - E.164 format).</span></span>
  
  <span data-ttu-id="4bb7d-106">Tenga en cuenta que:</span><span class="sxs-lookup"><span data-stu-id="4bb7d-106">Please note that:</span></span>

- <span data-ttu-id="4bb7d-107">Solo puede marcar si se une a una reunión con Teams.</span><span class="sxs-lookup"><span data-stu-id="4bb7d-107">You can dial out only if you join a meeting using Teams.</span></span>
- <span data-ttu-id="4bb7d-108">El organizador de la reunión, se ha habilitado para conferencias de audio o, en caso de que no se asigne ninguna licencia de audioconferencia, puede hacer llamadas a la red de telefonía pública conmutada a través de planes de llamadas en línea o enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="4bb7d-108">The meeting organizer, has been enabled for audio conferencing, OR, in the case no audio conferencing license is assigned, is allowed to make calls to the public switched telephone network via online calling plans or direct routing.</span></span>
- <span data-ttu-id="4bb7d-109">Al organizador de la reunión se le [concede una directiva de marcado en línea que permite hacer llamadas desde conferencias habilitadas](https://docs.microsoft.com/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="4bb7d-109">The meeting organizer is [Granted an online dial out policy that enables dial out from conferencing enabled](https://docs.microsoft.com/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps)</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="4bb7d-110">A continuación se explica cómo obtener acceso telefónico para trabajar:</span><span class="sxs-lookup"><span data-stu-id="4bb7d-110">Here's how to get dial out to work:</span></span>

 <span data-ttu-id="4bb7d-111">**Paso 1:** En la reunión, use la **Add people** ![ captura de pantalla agregar personas de la opción Agregar personas ](media/add-people-button.png) para llamar a un número de teléfono.</span><span class="sxs-lookup"><span data-stu-id="4bb7d-111">**Step 1:** In the meeting, use the **Add people** ![Screenshot of the Add people button](media/add-people-button.png) option to dial out to a phone number.</span></span>
 <span data-ttu-id="4bb7d-112">**Paso 2:** Escribe el número de teléfono completo, incluido el código de país o región en el cuadro **invitar a alguien o marcar un número** .</span><span class="sxs-lookup"><span data-stu-id="4bb7d-112">**Step 2:** Enter the full phone number, including the country/region code in the **Invite someone or dial a number** box.</span></span>
  
![Captura de pantalla del cuadro invitar a alguien o marcar un número](media/invite-someone-box.png)
    
## <a name="supported-countries-and-regions"></a><span data-ttu-id="4bb7d-114">Países y regiones admitidas</span><span class="sxs-lookup"><span data-stu-id="4bb7d-114">Supported countries and regions</span></span>

<span data-ttu-id="4bb7d-115">Dial-out is only available to some countries/regions.</span><span class="sxs-lookup"><span data-stu-id="4bb7d-115">Dial-out is only available to some countries/regions.</span></span> <span data-ttu-id="4bb7d-116">Para obtener una lista completa, consulte [disponibilidad de países y regiones para las conferencias de audio y los planes de llamadas](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="4bb7d-116">For complete list, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>

## <a name="allow-users-to-dial-in"></a><span data-ttu-id="4bb7d-117">Permitir a los usuarios marcar</span><span class="sxs-lookup"><span data-stu-id="4bb7d-117">Allow users to dial in</span></span>

<span data-ttu-id="4bb7d-118">Si está buscando instrucciones sobre cómo permitir que los usuarios llamen a una reunión de Teams, consulte [números de teléfono para audioconferencias en Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="4bb7d-118">If you are looking for instructions on how to let your users dial in to a Teams meeting, please see [Phone numbers for Audio Conferencing in Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md).</span></span>

## <a name="want-to-know-more-about-audio-conferencing"></a><span data-ttu-id="4bb7d-119">¿Desea saber más sobre las conferencias de acceso telefónico local?</span><span class="sxs-lookup"><span data-stu-id="4bb7d-119">Want to know more about audio conferencing?</span></span>

[<span data-ttu-id="4bb7d-120">Probar o comprar audioconferencia</span><span class="sxs-lookup"><span data-stu-id="4bb7d-120">Try or purchase Audio Conferencing</span></span>](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
    
[<span data-ttu-id="4bb7d-121">Licencias complementarias de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4bb7d-121">Microsoft Teams add-on licensing</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
