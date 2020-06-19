---
title: Caso práctico de voz de Contoso
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
description: Estudio de casos de voz de Teams para la corporación multinacional
appliesto:
- Microsoft Teams
ms.openlocfilehash: f58f3518202fd836ff962374e8f3b3a00ab71817
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786113"
---
# <a name="contoso-case-study-audio-conferencing"></a><span data-ttu-id="15900-103">Caso práctico de Contoso: audioconferencia</span><span class="sxs-lookup"><span data-stu-id="15900-103">Contoso case study: Audio Conferencing</span></span>

<span data-ttu-id="15900-104">Para comprender las conferencias de audio &mdash; Qué es, lo que cuesta, la disponibilidad y cómo funciona la &mdash; [Conferencia de audio revisada de Contoso en Office 365](deploy-audio-conferencing-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="15900-104">To gain an understanding of audio conferencing&mdash;what it is, what it costs, availability, and how it works&mdash;Contoso reviewed [Audio Conferencing in Office 365](deploy-audio-conferencing-teams-landing-page.md).</span></span> 

## <a name="overview"></a><span data-ttu-id="15900-105">Información general</span><span class="sxs-lookup"><span data-stu-id="15900-105">Overview</span></span> 

<span data-ttu-id="15900-106">En el caso de las conferencias de audio, contoso usó números de teléfono que son bien conocidos dentro de la organización y externamente.</span><span class="sxs-lookup"><span data-stu-id="15900-106">For audio conferencing, Contoso used phone numbers that are well known within the organization as well as externally.</span></span> <span data-ttu-id="15900-107">Debido a que contoso deseaba mantener estos números siempre que sea posible, revisaron la información sobre la asignación de números de teléfono dedicados y compartidos al puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="15900-107">Because Contoso wanted to maintain these numbers where possible, they reviewed the information on assigning dedicated and shared phone numbers to the audio conferencing bridge.</span></span> 

<span data-ttu-id="15900-108">En función de su investigación, contoso ha tomado las siguientes decisiones:</span><span class="sxs-lookup"><span data-stu-id="15900-108">Based on their research, Contoso made the following decisions:</span></span> 

- <span data-ttu-id="15900-109">Solo un segmento de la población que normalmente aloja las llamadas de las conferencias de audio recibiría licencias de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="15900-109">Only a segment of the population that regularly host audio conferencing calls would receive Audio Conferencing licenses.</span></span> 

- <span data-ttu-id="15900-110">Contoso usaría números de teléfono dedicados y trasladará los números existentes para usar con las conferencias de audio.</span><span class="sxs-lookup"><span data-stu-id="15900-110">Contoso would use dedicated phone numbers and port their existing numbers for use with Audio Conferencing.</span></span>   

<span data-ttu-id="15900-111">Como los usuarios de Contoso usaban Skype empresarial y todos los buzones de los usuarios se encuentran en línea, muchos usuarios tienen programada una reunión.</span><span class="sxs-lookup"><span data-stu-id="15900-111">Because Contoso users were using Skype for Business and all users' mailboxes reside online, many users have existing meetings scheduled.</span></span> <span data-ttu-id="15900-112">Contoso lea [con el servicio de migración de reuniones (MMS)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) para saber que las reuniones existentes se actualizan automáticamente en Contoso cuando cambian el usuario final al modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="15900-112">Contoso read [Using the Meeting Migration Service (MMS)](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) to learn that existing meetings are updated automatically for Contoso when they change the end user to TeamsOnly mode.</span></span>  


## <a name="configuration"></a><span data-ttu-id="15900-113">Configuración</span><span class="sxs-lookup"><span data-stu-id="15900-113">Configuration</span></span>

<span data-ttu-id="15900-114">Los números de teléfono asociados a las conferencias de audio se conocen como números de servicio en el sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="15900-114">Phone numbers that are associated with audio conferencing are referred to as service numbers within Phone System.</span></span> 

- <span data-ttu-id="15900-115">Para las ubicaciones que usan planes de llamadas, para trasladar sus números de teléfono existentes desde su operador telefónico a Office 365, contoso siguió los pasos de [obtener números de teléfono de servicio](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="15900-115">For locations using Calling Plans, to port their existing phone numbers from their phone carrier to Office 365, Contoso followed the steps in [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

- <span data-ttu-id="15900-116">Para asignar la licencia de audioconferencia al usuario final en el piloto técnico, el administrador de Contoso siguió los pasos de [administrar la configuración de la audioconferencia para su organización](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="15900-116">To assign the Audio Conferencing license to the end user in the technical pilot, the Contoso administrator followed the steps in [Manage the Audio Conferencing settings for your organization](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md).</span></span> 

- <span data-ttu-id="15900-117">Para el piloto y la migración de empresas, contoso usó las licencias basadas en grupos siguiendo los pasos de [asignar licencias a usuarios por pertenencia a grupos en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="15900-117">For the business pilot and migration, Contoso used group-based licensing by following the steps in [Assign licenses to users by group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

 

 