---
title: Caso práctico de Teams voice Contoso
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
ms.openlocfilehash: f58f3518202fd836ff962374e8f3b3a00ab71817
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786113"
---
# <a name="contoso-case-study-audio-conferencing"></a><span data-ttu-id="22c68-103">Caso práctico Contoso: Audioconferencia</span><span class="sxs-lookup"><span data-stu-id="22c68-103">Contoso case study: Audio Conferencing</span></span>

<span data-ttu-id="22c68-104">Para comprender qué es la audioconferencia, qué cuesta, disponibilidad y cómo funciona Contoso revisó &mdash; &mdash; Audioconferencia en Office [365.](deploy-audio-conferencing-teams-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="22c68-104">To gain an understanding of audio conferencing&mdash;what it is, what it costs, availability, and how it works&mdash;Contoso reviewed [Audio Conferencing in Office 365](deploy-audio-conferencing-teams-landing-page.md).</span></span> 

## <a name="overview"></a><span data-ttu-id="22c68-105">Información general</span><span class="sxs-lookup"><span data-stu-id="22c68-105">Overview</span></span> 

<span data-ttu-id="22c68-106">Para las audioconferencias, Contoso usó números de teléfono conocidos dentro de la organización, así como externamente.</span><span class="sxs-lookup"><span data-stu-id="22c68-106">For audio conferencing, Contoso used phone numbers that are well known within the organization as well as externally.</span></span> <span data-ttu-id="22c68-107">Como Contoso quería mantener estos números siempre que fuera posible, revisaba la información sobre cómo asignar números de teléfono dedicados y compartidos al puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="22c68-107">Because Contoso wanted to maintain these numbers where possible, they reviewed the information on assigning dedicated and shared phone numbers to the audio conferencing bridge.</span></span> 

<span data-ttu-id="22c68-108">Basándose en su investigación, Contoso tomó las siguientes decisiones:</span><span class="sxs-lookup"><span data-stu-id="22c68-108">Based on their research, Contoso made the following decisions:</span></span> 

- <span data-ttu-id="22c68-109">Solo un segmento del número de usuarios que hospedan llamadas de audioconferencia de forma periódica recibirán licencias de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="22c68-109">Only a segment of the population that regularly host audio conferencing calls would receive Audio Conferencing licenses.</span></span> 

- <span data-ttu-id="22c68-110">Contoso usaría números de teléfono dedicados y portabilidad de sus números existentes para usarlos con Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="22c68-110">Contoso would use dedicated phone numbers and port their existing numbers for use with Audio Conferencing.</span></span>   

<span data-ttu-id="22c68-111">Como los usuarios de Contoso usaban Skype Empresarial y todos los buzones de los usuarios residen en línea, muchos usuarios tienen reuniones existentes programadas.</span><span class="sxs-lookup"><span data-stu-id="22c68-111">Because Contoso users were using Skype for Business and all users' mailboxes reside online, many users have existing meetings scheduled.</span></span> <span data-ttu-id="22c68-112">Contoso leyó Usar el servicio de migración de reuniones [(MMS)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) para saber que las reuniones existentes se actualizan automáticamente para Contoso cuando cambian el usuario final al modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="22c68-112">Contoso read [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) to learn that existing meetings are updated automatically for Contoso when they change the end user to TeamsOnly mode.</span></span>  


## <a name="configuration"></a><span data-ttu-id="22c68-113">Configuración</span><span class="sxs-lookup"><span data-stu-id="22c68-113">Configuration</span></span>

<span data-ttu-id="22c68-114">Los números de teléfono asociados a las audioconferencias se conocen como números de servicio en Sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="22c68-114">Phone numbers that are associated with audio conferencing are referred to as service numbers within Phone System.</span></span> 

- <span data-ttu-id="22c68-115">Para ubicaciones con planes de llamadas, para portabilidad de sus números de teléfono existentes de su operador de telefonía a Office 365, Contoso ha seguido los pasos indicados en Obtener números [de teléfono de servicio.](getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="22c68-115">For locations using Calling Plans, to port their existing phone numbers from their phone carrier to Office 365, Contoso followed the steps in [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

- <span data-ttu-id="22c68-116">Para asignar la licencia de Audioconferencia al usuario final en el piloto técnico, el administrador de Contoso siguió los pasos de Administrar la configuración de [Audioconferencia para su organización.](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="22c68-116">To assign the Audio Conferencing license to the end user in the technical pilot, the Contoso administrator followed the steps in [Manage the Audio Conferencing settings for your organization](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).</span></span> 

- <span data-ttu-id="22c68-117">Para la migración y el piloto empresarial, Contoso usó licencias basadas en grupos siguiendo los pasos de Asignar licencias a usuarios por pertenencia a grupos [en Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span><span class="sxs-lookup"><span data-stu-id="22c68-117">For the business pilot and migration, Contoso used group-based licensing by following the steps in [Assign licenses to users by group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

 

 