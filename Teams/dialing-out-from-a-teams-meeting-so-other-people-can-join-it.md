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
description: Los organizadores de reuniones pueden aprender a llamar con la aplicación Teams para permitir que otras personas se unan a la misma reunión con sus teléfonos.
ms.openlocfilehash: 575ed18bd3dbd404dba947c0c4556d52e0653200
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788764"
---
# <a name="dialing-out-from-a-microsoft-teams-meeting-so-other-people-can-join-it"></a><span data-ttu-id="76a4f-103">Llamar desde una reunión de Microsoft Teams para que otras personas puedan unirse</span><span class="sxs-lookup"><span data-stu-id="76a4f-103">Dialing out from a Microsoft Teams meeting so other people can join it</span></span>

<span data-ttu-id="76a4f-104">Como organizador de la reunión, puede llamar con la aplicación Teams para permitir que otras personas se unan a la misma reunión con sus teléfonos.</span><span class="sxs-lookup"><span data-stu-id="76a4f-104">As the meeting organizer, you can dial out using the Teams app to let other people join the same meeting using their phones.</span></span>

<span data-ttu-id="76a4f-105">Cuando llame a alguien, se recomienda que lo haga con sus números de teléfono completos (incluido el código de país o región - formato E.164).</span><span class="sxs-lookup"><span data-stu-id="76a4f-105">When you dial out to someone, we recommend that you do so using their full phone numbers (including the country/region code - E.164 format).</span></span>
  
  <span data-ttu-id="76a4f-106">Ten en cuenta que:</span><span class="sxs-lookup"><span data-stu-id="76a4f-106">Please note that:</span></span>

- <span data-ttu-id="76a4f-107">Puede llamar solo si se une a una reunión con Teams.</span><span class="sxs-lookup"><span data-stu-id="76a4f-107">You can dial out only if you join a meeting using Teams.</span></span>
- <span data-ttu-id="76a4f-108">Al organizador de la reunión se le ha habilitado para la audioconferencia, O, en caso de que no se asigne ninguna licencia de audioconferencia, podrá realizar llamadas a la red telefónica conmutada pública a través de planes de llamadas en línea o enrutamiento directo.</span><span class="sxs-lookup"><span data-stu-id="76a4f-108">The meeting organizer, has been enabled for audio conferencing, OR, in the case no audio conferencing license is assigned, is allowed to make calls to the public switched telephone network via online calling plans or direct routing.</span></span>
- <span data-ttu-id="76a4f-109">Al organizador de la reunión [se le concede una directiva de llamada de](https://docs.microsoft.com/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps) salida en línea que habilita la llamada desde la conferencia habilitada</span><span class="sxs-lookup"><span data-stu-id="76a4f-109">The meeting organizer is [Granted an online dial out policy that enables dial out from conferencing enabled](https://docs.microsoft.com/powershell/module/skype/grant-csdialoutpolicy?view=skype-ps)</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="76a4f-110">Esta es la manera de llamar al trabajo:</span><span class="sxs-lookup"><span data-stu-id="76a4f-110">Here's how to get dial out to work:</span></span>

 <span data-ttu-id="76a4f-111">**Paso 1:** En la reunión, use la captura de pantalla **Agregar personas** de la opción del botón Agregar personas para llamar a un número ![ de ](media/add-people-button.png) teléfono.</span><span class="sxs-lookup"><span data-stu-id="76a4f-111">**Step 1:** In the meeting, use the **Add people** ![Screenshot of the Add people button](media/add-people-button.png) option to dial out to a phone number.</span></span>
 <span data-ttu-id="76a4f-112">**Paso 2:** Escriba el número de teléfono completo, incluido el código de país o región, en el cuadro Invitar **a alguien o marque un número.**</span><span class="sxs-lookup"><span data-stu-id="76a4f-112">**Step 2:** Enter the full phone number, including the country/region code in the **Invite someone or dial a number** box.</span></span>
  
![Captura de pantalla del cuadro Invitar a alguien o marcar un número](media/invite-someone-box.png)
    
## <a name="supported-countries-and-regions"></a><span data-ttu-id="76a4f-114">Países y regiones admitidas</span><span class="sxs-lookup"><span data-stu-id="76a4f-114">Supported countries and regions</span></span>

<span data-ttu-id="76a4f-115">Dial-out is only available to some countries/regions.</span><span class="sxs-lookup"><span data-stu-id="76a4f-115">Dial-out is only available to some countries/regions.</span></span> <span data-ttu-id="76a4f-116">Para ver la lista completa, consulte Disponibilidad del país y la región para planes de [audioconferencia y llamadas.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="76a4f-116">For complete list, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span>

## <a name="allow-users-to-dial-in"></a><span data-ttu-id="76a4f-117">Permitir que los usuarios llamen</span><span class="sxs-lookup"><span data-stu-id="76a4f-117">Allow users to dial in</span></span>

<span data-ttu-id="76a4f-118">Si busca instrucciones sobre cómo permitir que los usuarios llamen a una reunión de Teams, consulte Números de teléfono para [Audioconferencia en Microsoft Teams.](phone-numbers-for-audio-conferencing-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="76a4f-118">If you are looking for instructions on how to let your users dial in to a Teams meeting, please see [Phone numbers for Audio Conferencing in Microsoft Teams](phone-numbers-for-audio-conferencing-in-teams.md).</span></span>

## <a name="want-to-know-more-about-audio-conferencing"></a><span data-ttu-id="76a4f-119">¿Desea saber más sobre las conferencias de acceso telefónico local?</span><span class="sxs-lookup"><span data-stu-id="76a4f-119">Want to know more about audio conferencing?</span></span>

[<span data-ttu-id="76a4f-120">Probar o comprar Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="76a4f-120">Try or purchase Audio Conferencing</span></span>](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
    
[<span data-ttu-id="76a4f-121">Licencias complementarias de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="76a4f-121">Microsoft Teams add-on licensing</span></span>](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
