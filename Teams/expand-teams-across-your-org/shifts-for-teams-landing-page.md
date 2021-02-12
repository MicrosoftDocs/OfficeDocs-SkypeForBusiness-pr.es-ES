---
title: Turnos para Teams
description: Obtenga las instrucciones de administración que necesita para configurar y administrar Turnos, la herramienta de administración de programación, en Teams.
ms.topic: conceptual
author: cichur
ms.author: v-cichur
audience: admin
manager: serdars
f1.keywords:
- NOCSH
ms.date: 03/29/2019
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: f699b60bddba6bcf5ffa884760540e5c20378f81
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909224"
---
# <a name="shifts-for-teams"></a><span data-ttu-id="6eeca-103">Turnos para Teams</span><span class="sxs-lookup"><span data-stu-id="6eeca-103">Shifts for Teams</span></span>

<span data-ttu-id="6eeca-104">Teams proporciona a los frontline workers de su organización las herramientas que necesitan para comunicarse y colaborar de forma eficaz.</span><span class="sxs-lookup"><span data-stu-id="6eeca-104">Teams gives Frontline Workers in your organization the tools they need to communicate and collaborate effectively.</span></span> <span data-ttu-id="6eeca-105">Este artículo le muestra cómo configurar y administrar.</span><span class="sxs-lookup"><span data-stu-id="6eeca-105">This article shows you how to set up and manage.</span></span> <span data-ttu-id="6eeca-106">Turnos y usar la herramienta de administración de programación en Teams.</span><span class="sxs-lookup"><span data-stu-id="6eeca-106">Shifts and use the schedule management tool in Teams.</span></span>

### <a name="set-up-and-manage-shifts-for-your-organization"></a><span data-ttu-id="6eeca-107">Configurar y administrar turnos para su organización</span><span class="sxs-lookup"><span data-stu-id="6eeca-107">Set up and manage Shifts for your organization</span></span>

|               |               |               |               |
| ------------- | ------------- | ------------- | ------------- |
|![task-checklist-planning-teams](../media/task-checklist-planning-teams-small.svg) | <span data-ttu-id="6eeca-109">**[Administrar Turnos en su organización](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams)**</span><span class="sxs-lookup"><span data-stu-id="6eeca-109">**[Manage Shifts in your organization](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams)**</span></span> |![diseño](../media/Help-small.svg)  | <span data-ttu-id="6eeca-111">**[Ayuda de turnos para los trabajadores de primera línea](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Specific_apps)**</span><span class="sxs-lookup"><span data-stu-id="6eeca-111">**[Shifts Help for Frontline Workers](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Specific_apps)**</span></span> |

### <a name="shifts-extensions"></a><span data-ttu-id="6eeca-112">Extensiones de turnos</span><span class="sxs-lookup"><span data-stu-id="6eeca-112">Shifts extensions</span></span>

|               |               |
| ------------- | ------------- |
| ![api](../media/api-small.svg) | <span data-ttu-id="6eeca-114">**[API de Shift Graph](/graph/api/resources/shift?view=graph-rest-1.0)** Las API de Shifts Graph le permiten integrar datos de Turnos con sistemas de administración de recursos externos.</span><span class="sxs-lookup"><span data-stu-id="6eeca-114">**[Shift Graph APIs](/graph/api/resources/shift?view=graph-rest-1.0)** Shifts Graph APIs allow you to integrate Shifts data with external workforce management systems.</span></span> <span data-ttu-id="6eeca-115">Tendrá la flexibilidad de crear experiencias de Turnos personalizadas en el back-end, a la vez que ofrece a los usuarios una experiencia completa y front-end en Teams.</span><span class="sxs-lookup"><span data-stu-id="6eeca-115">You'll have the flexibility to build custom Shifts experiences in the back end, while giving users a rich, front-end experience in Teams.</span></span>             |
| ![api](../media/api-small.svg) | <span data-ttu-id="6eeca-117">**[Integraciones de administración de recursos](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)** Si usa sistemas de administración de recursos de terceros, como Kronos y JDA, para programación, hora y asistencia, puede integrar directamente con Turnos a través de API y SDK de Graph Turnos con integraciones de código abierto.</span><span class="sxs-lookup"><span data-stu-id="6eeca-117">**[Workforce management integrations](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)** If you're using third-party workforce management systems, such as Kronos and JDA, for scheduling, time, and attendance, you can integrate directly with Shifts through Shifts Graph APIs and SDK with open source integrations.</span></span> |
| ![api](../media/process-flow-teams-small.svg) | <span data-ttu-id="6eeca-119">**[Turnos + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Turnos + Power Automate le permite tomar información de Turnos, crear flujos de trabajo personalizados con otras aplicaciones y realizar operaciones a escala.</span><span class="sxs-lookup"><span data-stu-id="6eeca-119">**[Shifts + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Shifts + Power Automate lets you take info from Shifts and create custom workflows with other apps and perform operations at scale.</span></span> <span data-ttu-id="6eeca-120">Automatice los procesos clave con poco o ningún código.</span><span class="sxs-lookup"><span data-stu-id="6eeca-120">Automate key processes with little to no code.</span></span> <span data-ttu-id="6eeca-121">Los desencadenadores y las plantillas admiten una variedad de escenarios, como habilitar las aprobaciones automáticas para las solicitudes de turno cuando no es necesaria la aprobación de un director.</span><span class="sxs-lookup"><span data-stu-id="6eeca-121">The triggers and templates support a variety of scenarios such as enabling auto-approvals for shift requests when a manager’s approval isn't needed.</span></span> |

## <a name="featured-training"></a><span data-ttu-id="6eeca-122">Aprendizaje destacado</span><span class="sxs-lookup"><span data-stu-id="6eeca-122">Featured training</span></span>

|               |               |               |               |               |               |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| ![arrow-right-2-teams](../media/arrow-right-2-teams-small.svg)  |  [<span data-ttu-id="6eeca-124">Vídeo: ¿Qué es Turnos?</span><span class="sxs-lookup"><span data-stu-id="6eeca-124">Video: What is Shifts?</span></span>](https://support.office.com/article/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821) |![reloj-equipos](../media/clock-teams-small.svg)  |  [<span data-ttu-id="6eeca-126">Vídeo: ¿Qué es Turnos?</span><span class="sxs-lookup"><span data-stu-id="6eeca-126">Video: What is Shifts?</span></span>](https://support.office.com/article/create-a-shifts-schedule-2b94ca38-36db-4a1c-8fee-f8f0fec9a984) |![blocks-teams](../media/blocks-teams-small.svg)  |  [<span data-ttu-id="6eeca-128">Vídeo: Administrar una programación de Turnos</span><span class="sxs-lookup"><span data-stu-id="6eeca-128">Video: Manage a Shifts schedule</span></span>](https://support.office.com/article/manage-a-shifts-schedule-63acda7b-ea39-441a-b1c6-c404a72e79f7) |
