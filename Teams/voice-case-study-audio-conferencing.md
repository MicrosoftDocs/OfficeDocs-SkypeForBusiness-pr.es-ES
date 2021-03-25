---
title: Caso práctico de Contoso de voz de Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Caso práctico de voz de Teams para una corporación multinacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: 085c9994bc2522d1ab56abc1670113e22d35f642
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121308"
---
# <a name="contoso-case-study-audio-conferencing"></a><span data-ttu-id="42c84-103">Caso práctico de Contoso: Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="42c84-103">Contoso case study: Audio Conferencing</span></span>

<span data-ttu-id="42c84-104">Para comprender lo que es la audioconferencia, lo que cuesta, la disponibilidad y cómo funciona Contoso revisó &mdash; &mdash; Audioconferencia en Office [365.](deploy-audio-conferencing-teams-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="42c84-104">To gain an understanding of audio conferencing&mdash;what it is, what it costs, availability, and how it works&mdash;Contoso reviewed [Audio Conferencing in Office 365](deploy-audio-conferencing-teams-landing-page.md).</span></span> 

## <a name="overview"></a><span data-ttu-id="42c84-105">Información general</span><span class="sxs-lookup"><span data-stu-id="42c84-105">Overview</span></span> 

<span data-ttu-id="42c84-106">Para las audioconferencias, Contoso usó números de teléfono bien conocidos dentro de la organización, así como de forma externa.</span><span class="sxs-lookup"><span data-stu-id="42c84-106">For audio conferencing, Contoso used phone numbers that are well known within the organization as well as externally.</span></span> <span data-ttu-id="42c84-107">Como Contoso quería mantener estos números siempre que fuera posible, revisaron la información sobre cómo asignar números de teléfono dedicados y compartidos al puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="42c84-107">Because Contoso wanted to maintain these numbers where possible, they reviewed the information on assigning dedicated and shared phone numbers to the audio conferencing bridge.</span></span> 

<span data-ttu-id="42c84-108">En función de su investigación, Contoso tomó las siguientes decisiones:</span><span class="sxs-lookup"><span data-stu-id="42c84-108">Based on their research, Contoso made the following decisions:</span></span> 

- <span data-ttu-id="42c84-109">Solo un segmento de la población que hospeda llamadas de audioconferencia periódicamente recibiría licencias de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="42c84-109">Only a segment of the population that regularly host audio conferencing calls would receive Audio Conferencing licenses.</span></span> 

- <span data-ttu-id="42c84-110">Contoso usaría números de teléfono dedicados y portabilidad de sus números existentes para usarlos con audioconferencias.</span><span class="sxs-lookup"><span data-stu-id="42c84-110">Contoso would use dedicated phone numbers and port their existing numbers for use with Audio Conferencing.</span></span>   

<span data-ttu-id="42c84-111">Como los usuarios de Contoso usaban Skype Empresarial y los buzones de todos los usuarios residen en línea, muchos usuarios tienen reuniones existentes programadas.</span><span class="sxs-lookup"><span data-stu-id="42c84-111">Because Contoso users were using Skype for Business and all users' mailboxes reside online, many users have existing meetings scheduled.</span></span> <span data-ttu-id="42c84-112">Contoso leyó Usar el servicio de migración de reuniones [(MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) para saber que las reuniones existentes se actualizan automáticamente para Contoso cuando cambian el usuario final al modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="42c84-112">Contoso read [Using the Meeting Migration Service (MMS)](/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fMicrosoftTeams%2ftoc.json) to learn that existing meetings are updated automatically for Contoso when they change the end user to TeamsOnly mode.</span></span>  


## <a name="configuration"></a><span data-ttu-id="42c84-113">Configuración</span><span class="sxs-lookup"><span data-stu-id="42c84-113">Configuration</span></span>

<span data-ttu-id="42c84-114">Los números de teléfono asociados a las audioconferencias se denominan números de servicio dentro del sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="42c84-114">Phone numbers that are associated with audio conferencing are referred to as service numbers within Phone System.</span></span> 

- <span data-ttu-id="42c84-115">Para ubicaciones que usan planes de llamadas, para portabilidad de sus números de teléfono existentes de su operador de teléfono a Office 365, Contoso siguió los pasos de Obtener números [de teléfono de servicio.](getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="42c84-115">For locations using Calling Plans, to port their existing phone numbers from their phone carrier to Office 365, Contoso followed the steps in [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

- <span data-ttu-id="42c84-116">Para asignar la licencia de Conferencias de audio al usuario final en el piloto técnico, el administrador de Contoso siguió los pasos descritos en Administrar la configuración de [audioconferencia de su organización.](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="42c84-116">To assign the Audio Conferencing license to the end user in the technical pilot, the Contoso administrator followed the steps in [Manage the Audio Conferencing settings for your organization](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).</span></span> 

- <span data-ttu-id="42c84-117">Para el piloto empresarial y la migración, Contoso usó licencias basadas en grupos siguiendo los pasos de Asignar licencias a usuarios por pertenencia a grupos [en Azure Active Directory.](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="42c84-117">For the business pilot and migration, Contoso used group-based licensing by following the steps in [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

 

