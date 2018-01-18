---
title: "Uso de los identificadores de conferencia de Audio dinámicos en su organización"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: e55e4bff-fb67-4389-8695-f03024baa9b6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Se está actualizando el servicio de conferencia de Audio para proporcionar cada Skype para reunión de negocios y Teams de Microsoft con identificadores de conferencia diferente. Identificadores de conferencia dinámicas suponen una mejora significativa sobre conferencia estática IDs, ya que proporcionan:"
ms.openlocfilehash: 0838014e8a88d5e27b6bd84838ea105b9f75025a
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="using-audio-conferencing-dynamic-ids-in-your-organization"></a><span data-ttu-id="52acd-104">Uso de los identificadores de conferencia de Audio dinámicos en su organización</span><span class="sxs-lookup"><span data-stu-id="52acd-104">Using Audio Conferencing dynamic IDs in your organization</span></span>

<span data-ttu-id="52acd-105">Se está actualizando el servicio de conferencia de Audio para proporcionar cada Skype para reunión de negocios y Teams de Microsoft con identificadores de conferencia diferente.</span><span class="sxs-lookup"><span data-stu-id="52acd-105">The Audio Conferencing service is being updated to provide each Skype for Business and Microsoft Teams meeting with different conference IDs.</span></span> <span data-ttu-id="52acd-106">Identificadores de conferencia dinámicas suponen una mejora significativa sobre conferencia estática IDs, ya que proporcionan:</span><span class="sxs-lookup"><span data-stu-id="52acd-106">Dynamic conference IDs are a significant improvement over static conference IDs, because they provide:</span></span>
  
- <span data-ttu-id="52acd-107">**Seguridad mejorada** La conferencia identificadores son únicos para cada Skype para reuniones de negocios o Teams de Microsoft y se generan cuando se programa la reunión.</span><span class="sxs-lookup"><span data-stu-id="52acd-107">**Enhanced security** The conference IDs are unique for each Skype for Business or Microsoft Teams meeting and are generated when the meeting is being scheduled.</span></span>
    
- <span data-ttu-id="52acd-108">**Una mejor experiencia para todo tipo de reuniones** Las reuniones de un único organizador reciben una información específica de acceso telefónico local para evitar que los participantes por teléfono de la reunión se mezclen con los participantes de otra cuando se programan una detrás de otra.</span><span class="sxs-lookup"><span data-stu-id="52acd-108">**A better experience for back-to-back and side-to-side meetings** Meetings for a single organizer are given specific dial-in information that prevents phone participants of one meeting from being mixed with participants of another one when they're scheduled next to each other.</span></span>
    
- <span data-ttu-id="52acd-109">**Una transición constante** Cuando a su organización se le habilita un identificador de conferencia dinámico, todas las reuniones que ya se hayan programado con un identificador estático de conferencia seguirán funcionando.</span><span class="sxs-lookup"><span data-stu-id="52acd-109">**A seamless transition** When your organization is enabled for dynamic conference IDs, all the meetings that have been already scheduled in your organization with static conference IDs will continue to work.</span></span>
    
> [!TIP]
> <span data-ttu-id="52acd-110">IDs dinámicas sólo están disponibles para los usuarios que están habilitados para ** conferencias de Audio ** y establecer como su proveedor de conferencia de audio de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="52acd-110">Dynamic IDs are only available to users who are enabled for ** Audio Conferencing** and have Microsoft set as their audio conferencing provider.</span></span> <span data-ttu-id="52acd-111">Puede [Asignar Microsoft como proveedor de conferencia de audio](assign-microsoft-as-the-audio-conferencing-provider.md) para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="52acd-111">You can [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md) for your users.</span></span>
  
## <a name="what-changes-will-the-users-in-my-organization-see"></a><span data-ttu-id="52acd-112">¿Qué cambios verán los usuarios de mi organización?</span><span class="sxs-lookup"><span data-stu-id="52acd-112">What changes will the users in my organization see?</span></span>

<span data-ttu-id="52acd-113">Después de IDs de conferencia dinámico se han habilitado para su organización, cualquier nuevo Skype para negocios o Teams Microsoft reunión que se programa por usuarios de la organización que están habilitados para conferencias de Audio tendrá conferencia identificadores que será diferente de la Id. de conferencia estática que tenían antes.</span><span class="sxs-lookup"><span data-stu-id="52acd-113">After dynamic conference IDs have been enabled for your organization, any new Skype for Business or Microsoft Teams meeting that is scheduled by users in your organization who are enabled for Audio Conferencing will have conference IDs that will be different from the static conference ID they had before.</span></span> <span data-ttu-id="52acd-114">Organizadores que habían estática identificadores de conferencia antes necesitan recordar a los usuarios unirse a sus reuniones que necesitan ahora para utilizar un nuevo ID de conferencia en la invitación de la reunión antes de que puedan unirse a él.</span><span class="sxs-lookup"><span data-stu-id="52acd-114">Organizers who had static conference IDs before need to remind the users joining their meetings that they now need to use a new conference ID in the meeting's invite before they can join it.</span></span>
  
> [!NOTE]
> <span data-ttu-id="52acd-115">Reuniones que estaban programadas por un usuario con identificadores de conferencia estática antes de que la organización se habilitó para conferencia dinámica que continuarán identificadores tengan los identificadores de conferencia estática, por lo que continúan programar reuniones sin ningún impacto.</span><span class="sxs-lookup"><span data-stu-id="52acd-115">Meetings that were scheduled by a user with static conference IDs before the organization was enabled for dynamic conference IDs will continue to have the static conference IDs, so they'll continue to schedule meetings without any impact.</span></span> 
  
<span data-ttu-id="52acd-116">Estos ejemplos muestran la nueva experiencia de dos Skype para reuniones de negocios que han sido clasificados por el mismo usuario pero ahora tendrán dos identificadores de conferencia diferente:</span><span class="sxs-lookup"><span data-stu-id="52acd-116">These examples show you the new experience for two Skype for Business meetings that have been organized by the same user but will both now have two different conference IDs:</span></span> 
  
 <span data-ttu-id="52acd-117">La **reunión 1** se ha programado de 9:00 a 10:00 y su id. de conferencia es 93907123:</span><span class="sxs-lookup"><span data-stu-id="52acd-117">**Meeting #1** has been scheduled from 9:00 AM to 10:00 AM and it has 93907123 as its conference ID:</span></span>
  
![First Dynamic Conference ID.](../images/997b2473-7645-46df-9774-95eb070c2239.png)
  
 <span data-ttu-id="52acd-119">El mismo usuario ha programado la **reunión 2** de 10:00 a 11:00 y su id. de conferencia es 16353789:</span><span class="sxs-lookup"><span data-stu-id="52acd-119">**Meeting #2** has been scheduled by the same user from 10:00 AM to 11:00 AM and it has 16353789 as its conference ID:</span></span>
  
![Second Dynamic Conference IDs](../images/e1eecc76-812b-426c-90e8-80e9f6f4ad31.png)
  
## <a name="related-topics"></a><span data-ttu-id="52acd-121">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="52acd-121">Related topics</span></span>

- [<span data-ttu-id="52acd-122">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="52acd-122">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- <span data-ttu-id="52acd-123">La conferencia de acceso telefónico local o también denominada conferencia RTC no está disponible para toda la organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="52acd-123">[Set up Audio Conferencing for Skype for Business and Microsoft Teams](set-up-audio-conferencing.md)</span></span>
    
- <span data-ttu-id="52acd-124">Puede obtener más información en [Conferencias de acceso telefónico en Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="52acd-124">[Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span></span>
    

