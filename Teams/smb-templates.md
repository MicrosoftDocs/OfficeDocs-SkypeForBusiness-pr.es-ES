---
title: Teams plantillas para pequeñas y medianas empresas creadas con Microsoft Graph
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: Use Microsoft Teams plantillas predefinidas integradas en Microsoft Graph crear equipos para pequeñas y medianas empresas de forma rápida y sencilla.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e3d29dca0bbdbd7b3487ac1738b84396a3d41117
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116998"
---
# <a name="teams-templates-built-in-microsoft-graph-for-small-and-medium-businesses"></a><span data-ttu-id="514db-103">Teams plantillas integradas en Microsoft Graph para pequeñas y medianas empresas</span><span class="sxs-lookup"><span data-stu-id="514db-103">Teams templates built in Microsoft Graph for Small and Medium Businesses</span></span>

<span data-ttu-id="514db-104">Las plantillas de Microsoft Teams le permiten crear equipos de forma rápida y sencilla al proporcionar una plantilla predefinida de configuración, canales y aplicaciones preinstaladas.</span><span class="sxs-lookup"><span data-stu-id="514db-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="514db-105">Para pequeñas y medianas empresas, las plantillas pueden ser especialmente eficaces, ya que ayudan a los administradores a implementar rápidamente Teams toda su organización.</span><span class="sxs-lookup"><span data-stu-id="514db-105">For small and medium businesses, templates can be especially powerful, as they help administrators to quickly deploy Teams across their organization.</span></span> <span data-ttu-id="514db-106">Las plantillas también ayudan a orientar a los usuarios y a empezar a usar Teams eficaz.</span><span class="sxs-lookup"><span data-stu-id="514db-106">Templates also help orient users and get started with using Teams effectively.</span></span> <span data-ttu-id="514db-107">Este artículo es para usted si es responsable de planear, implementar y administrar varios equipos en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="514db-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your organization.</span></span>

<span data-ttu-id="514db-108">Actualmente ofrecemos tres plantillas SMB de primer nivel que puede aprovechar para una variedad de situaciones.</span><span class="sxs-lookup"><span data-stu-id="514db-108">We currently offer three first-party SMB templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="514db-109">Todas las plantillas crearán *Teams.*</span><span class="sxs-lookup"><span data-stu-id="514db-109">All templates will create *Private* Teams.</span></span> <span data-ttu-id="514db-110">Una vez que haya creado el Teams y esté listo para su organización, puede establecer la privacidad en *Org-Wide* o *Public*, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="514db-110">Once you have created the Teams and are ready to roll out to your organization, you can set the privacy to *Org-Wide* or *Public*, as appropriate.</span></span> <span data-ttu-id="514db-111">Para obtener más información sobre las plantillas de equipo en general, vea [Introducción a las plantillas de Teams](get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="514db-111">To learn more about team templates in general, see [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="company-wide-template"></a><span data-ttu-id="514db-112">Company-Wide plantilla</span><span class="sxs-lookup"><span data-stu-id="514db-112">Company-Wide template</span></span>
<span data-ttu-id="514db-113">La Company-Wide está pensada para la comunicación y la colaboración que son relevantes para toda la empresa.</span><span class="sxs-lookup"><span data-stu-id="514db-113">The Company-Wide template is meant for communication and collaboration that are relevant for the entire company.</span></span> <span data-ttu-id="514db-114">Puede usar el canal General para anuncios de toda la empresa, noticias del sector o publicaciones ejecutivas.</span><span class="sxs-lookup"><span data-stu-id="514db-114">You can use the General channel for company-wide announcements, industry news or executive posts.</span></span> <span data-ttu-id="514db-115">El canal recursos humanos es un excelente lugar para consolidar todas las actividades relacionadas con recursos humanos, como puestos de trabajo, incorporación de nuevos empleados, formación y desarrollo.</span><span class="sxs-lookup"><span data-stu-id="514db-115">The Human Resources channel is a great place to consolidate all HR-related activities like job posts, new employee onboarding, training, and development.</span></span> <span data-ttu-id="514db-116">El canal Cosas divertidas proporciona una plataforma social para todas las publicaciones aleatorias y divertidas.</span><span class="sxs-lookup"><span data-stu-id="514db-116">The Fun Stuff channel provides a social platform for all random and fun posts.</span></span>

| <span data-ttu-id="514db-117">Tipo de plantilla base</span><span class="sxs-lookup"><span data-stu-id="514db-117">Base template type</span></span>  | <span data-ttu-id="514db-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="514db-118">baseTemplateId</span></span> | <span data-ttu-id="514db-119">Propiedades que vienen con esta plantilla base</span><span class="sxs-lookup"><span data-stu-id="514db-119">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="514db-120">SMB -</span><span class="sxs-lookup"><span data-stu-id="514db-120">SMB -</span></span> <br><span data-ttu-id="514db-121">Toda la empresa</span><span class="sxs-lookup"><span data-stu-id="514db-121">Company-wide</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| <span data-ttu-id="514db-122">Canales</span><span class="sxs-lookup"><span data-stu-id="514db-122">Channels</span></span> <ul><li><span data-ttu-id="514db-123">General\*</span><span class="sxs-lookup"><span data-stu-id="514db-123">General\*</span></span></li><li><span data-ttu-id="514db-124">Recursos humanos\*</span><span class="sxs-lookup"><span data-stu-id="514db-124">Human Resources\*</span></span></li><li><span data-ttu-id="514db-125">Cosas divertidas\*</span><span class="sxs-lookup"><span data-stu-id="514db-125">Fun Stuff\*</span></span></li></ul><br> <span data-ttu-id="514db-126">Aplicaciones</span><span class="sxs-lookup"><span data-stu-id="514db-126">Apps</span></span><ul><li><span data-ttu-id="514db-127">Portal de empresa (sitio web anclado al **canal de Recursos** humanos)</span><span class="sxs-lookup"><span data-stu-id="514db-127">Company Portal (Website pinned to the **Human Resources** channel)</span></span> </li> </UL><br><span data-ttu-id="514db-128">Propiedades del equipo</span><span class="sxs-lookup"><span data-stu-id="514db-128">Team properties</span></span> <ul><li><span data-ttu-id="514db-129">Visibilidad de equipo establecida en Privado</span><span class="sxs-lookup"><span data-stu-id="514db-129">Team visibility set to Private</span></span></li></ul> |

<span data-ttu-id="514db-130">\*Canales auto favoritos</span><span class="sxs-lookup"><span data-stu-id="514db-130">\*Auto-favorited channels</span></span> 

<span data-ttu-id="514db-131">Para crear el Company-Wide de trabajo tomando valores predeterminados de la plantilla predefinida, proporcione la representación JSON del objeto de grupo en el cuerpo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="514db-131">To create the Company-Wide team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="514db-132">Para obtener más información sobre cómo implementar Teams plantillas, vea el artículo de Microsoft Graph [sobre cómo crear un equipo.](/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="514db-132">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="514db-133">Solicitud</span><span class="sxs-lookup"><span data-stu-id="514db-133">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessOrgWide')",
    "displayName": "Org-wide",
    "description": "All posts that are relevant for entire company (e.g. Company-wide announcements, Exec posts, employee poll/feedback).",
    "visibility": "Private"
}
```

## <a name="executive-team-template"></a><span data-ttu-id="514db-134">Plantilla de equipo ejecutivo</span><span class="sxs-lookup"><span data-stu-id="514db-134">Executive Team template</span></span>

<span data-ttu-id="514db-135">La plantilla de equipo ejecutivo es ideal para crear un equipo para que los ejecutivos de la compañía se comuniquen y colaboren en iniciativas de la empresa como prioridades anuales, presupuestos fiscales, iniciativas estratégicas y clientes principales.</span><span class="sxs-lookup"><span data-stu-id="514db-135">The Executive Team template is ideal for creating a team for company executives to communicate and collaborate on company initiatives like annual priorities, fiscal budgets, strategic initiatives, and top clients.</span></span> <span data-ttu-id="514db-136">Esta plantilla incluye un *canal privado* para invitar a usuarios seleccionados a temas específicos.</span><span class="sxs-lookup"><span data-stu-id="514db-136">This template comes with a *Private* channel to invite select users for specific topics.</span></span>

| <span data-ttu-id="514db-137">Tipo de plantilla base</span><span class="sxs-lookup"><span data-stu-id="514db-137">Base template type</span></span>  | <span data-ttu-id="514db-138">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="514db-138">baseTemplateId</span></span> | <span data-ttu-id="514db-139">Propiedades que vienen con esta plantilla base</span><span class="sxs-lookup"><span data-stu-id="514db-139">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="514db-140">SMB -</span><span class="sxs-lookup"><span data-stu-id="514db-140">SMB -</span></span> <br><span data-ttu-id="514db-141">Equipo de ejecutivos</span><span class="sxs-lookup"><span data-stu-id="514db-141">Executives Team</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | <span data-ttu-id="514db-142">Canales</span><span class="sxs-lookup"><span data-stu-id="514db-142">Channels</span></span> <ul><li><span data-ttu-id="514db-143">General\*</span><span class="sxs-lookup"><span data-stu-id="514db-143">General\*</span></span></li><li><span data-ttu-id="514db-144">Privado \*</span><span class="sxs-lookup"><span data-stu-id="514db-144">Private \*</span></span></li></ul> <span data-ttu-id="514db-145">Aplicaciones</span><span class="sxs-lookup"><span data-stu-id="514db-145">Apps</span></span><ul><li><span data-ttu-id="514db-146">OneNote (anclado al **canal** privado)</span><span class="sxs-lookup"><span data-stu-id="514db-146">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="514db-147">Planner (anclado al **canal** privado)</span><span class="sxs-lookup"><span data-stu-id="514db-147">Planner (pinned to the **Private** channel)</span></span> </li></ul><br><span data-ttu-id="514db-148">Propiedades del equipo</span><span class="sxs-lookup"><span data-stu-id="514db-148">Team properties</span></span> <ul><li><span data-ttu-id="514db-149">Visibilidad de equipo establecida en Privado</span><span class="sxs-lookup"><span data-stu-id="514db-149">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="514db-150">\*Canales auto favoritos</span><span class="sxs-lookup"><span data-stu-id="514db-150">\*Auto-favorited channels</span></span><br>

<span data-ttu-id="514db-151">Para crear el equipo ejecutivo tomando valores predeterminados de la plantilla predefinida, proporcione la representación JSON del objeto de equipo en el cuerpo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="514db-151">To create the Executives team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="514db-152">Para obtener más información sobre cómo implementar Teams plantillas, vea el artículo de Microsoft Graph [sobre cómo crear un equipo.](/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="514db-152">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="514db-153">Solicitud</span><span class="sxs-lookup"><span data-stu-id="514db-153">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessExecutive')",
    "displayName": "Executive",
    "description": "All posts, announcements and daily collaboration and communication for the company's leadership team.",
    "visibility": "Private"
}
```

## <a name="departmental-team-template"></a><span data-ttu-id="514db-154">Plantilla de equipo departamental</span><span class="sxs-lookup"><span data-stu-id="514db-154">Departmental Team template</span></span>

<span data-ttu-id="514db-155">La plantilla de equipo departamental se puede usar para crear un equipo para departamentos individuales o para proyectos.</span><span class="sxs-lookup"><span data-stu-id="514db-155">The Departmental team template can be used for creating a team for individual departments or for projects.</span></span> <span data-ttu-id="514db-156">La plantilla de equipo finanzas es ideal para todas las publicaciones, anuncios y colaboración y comunicación diarias dentro de los miembros del equipo de Finanzas y los miembros del equipo ejecutivo según corresponda.</span><span class="sxs-lookup"><span data-stu-id="514db-156">The Finance team template is ideal for all posts, announcements, and daily collaboration and communication within the Finance team members and executive team members as appropriate.</span></span> <span data-ttu-id="514db-157">La plantilla viene con un *canal privado* para invitar a usuarios seleccionados a temas específicos.</span><span class="sxs-lookup"><span data-stu-id="514db-157">The template comes with a *Private* channel to invite select users for specific topics.</span></span> <span data-ttu-id="514db-158">También proporcionamos el script siguiente para el equipo de Finanzas que se puede usar para extender la plantilla a departamentos adicionales o proyectos específicos agregando, eliminando o editando a su gusto.</span><span class="sxs-lookup"><span data-stu-id="514db-158">We also provide the script below for the Finance team that can be used to extend the template to additional departments or specific projects by adding, deleting from, or editing to your liking.</span></span> <span data-ttu-id="514db-159">Por ejemplo, si tiene un departamento de *marketing,* el script se  puede adaptar si cambia el nombre del equipo de Finanzas a *Marketing* para crear un nuevo equipo de marketing</span><span class="sxs-lookup"><span data-stu-id="514db-159">For example, if you have a *Marketing* department, then the script can be adapted by renaming the team from *Finance* to *Marketing* to create a new Marketing team</span></span>

| <span data-ttu-id="514db-160">Tipo de plantilla base</span><span class="sxs-lookup"><span data-stu-id="514db-160">Base template type</span></span> | <span data-ttu-id="514db-161">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="514db-161">baseTemplateId</span></span> | <span data-ttu-id="514db-162">Propiedades que vienen con esta plantilla base</span><span class="sxs-lookup"><span data-stu-id="514db-162">Properties that come with this base template</span></span> |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="514db-163">SMB -</span><span class="sxs-lookup"><span data-stu-id="514db-163">SMB -</span></span> <br><span data-ttu-id="514db-164">Finanzas</span><span class="sxs-lookup"><span data-stu-id="514db-164">Finance</span></span>  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| <span data-ttu-id="514db-165">Canales</span><span class="sxs-lookup"><span data-stu-id="514db-165">Channels</span></span> <ul><li><span data-ttu-id="514db-166">General\*</span><span class="sxs-lookup"><span data-stu-id="514db-166">General\*</span></span></li><li><span data-ttu-id="514db-167">Privado \*</span><span class="sxs-lookup"><span data-stu-id="514db-167">Private \*</span></span></li></ul><br> <span data-ttu-id="514db-168">Aplicaciones</span><span class="sxs-lookup"><span data-stu-id="514db-168">Apps</span></span><ul><li><span data-ttu-id="514db-169">OneNote (anclado al **canal** privado)</span><span class="sxs-lookup"><span data-stu-id="514db-169">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="514db-170">Planner (anclado al **canal** privado)</span><span class="sxs-lookup"><span data-stu-id="514db-170">Planner (pinned to the **Private** channel)</span></span> </li> </ul><br><span data-ttu-id="514db-171">Propiedades del equipo</span><span class="sxs-lookup"><span data-stu-id="514db-171">Team properties</span></span> <ul><li><span data-ttu-id="514db-172">Visibilidad de equipo establecida en Privado</span><span class="sxs-lookup"><span data-stu-id="514db-172">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="514db-173">\*Canales auto favoritos</span><span class="sxs-lookup"><span data-stu-id="514db-173">\*Auto-favorited channels</span></span>

<span data-ttu-id="514db-174">Para crear el equipo de Finanzas tomando valores predeterminados de la plantilla predefinida, proporcione la representación JSON del objeto de equipo en el cuerpo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="514db-174">To create the Finance team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="514db-175">Para obtener más información sobre cómo implementar Teams plantillas, vea el artículo de Microsoft Graph [sobre cómo crear un equipo.](/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="514db-175">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="514db-176">Solicitud</span><span class="sxs-lookup"><span data-stu-id="514db-176">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessFinance')",
    "displayName": "Finance",
    "description": "All posts, announcements and daily collaboration and communication within the Finance team members (and exec team members as appropriate).",
    "visibility": "Private"
}
```

### <a name="example-finance-team-template-extension-script"></a><span data-ttu-id="514db-177">Ejemplo: Script de extensión de plantilla del equipo de finanzas</span><span class="sxs-lookup"><span data-stu-id="514db-177">Example: Finance Team template extension script</span></span>

```powershell
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
  "displayName": "Finance",
  "description": "Finance Team",
  "channels": 
   [
        {
            "displayName": "Private",
            "isFavoriteByDefault": true,
            "description": "Invite a more select audience for specific topics.",
             "tabs": 
             [
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')",
                    "name": "OneNote"
                },
                {
                    "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')",
                    "name": "Planner"
                }
            ]
        }
    ],
    "memberSettings": 
    {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
       "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": 
    {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": 
    {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": 
    {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "discoverySettings": 
    {
        "showInTeamsSearchAndSuggestions": true
    },
    "installedApps": 
    [
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('0d820ecd-def2-4297-adad-78056cde7c78')"
        },
        {
            "teamsApp@odata.bind": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.planner')"
        }
    ]
}

```

## <a name="related-topics"></a><span data-ttu-id="514db-178">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="514db-178">Related topics</span></span>

- [<span data-ttu-id="514db-179">Introducción a las Teams en la consola de administración</span><span class="sxs-lookup"><span data-stu-id="514db-179">Get started with Teams templates in the admin console</span></span>](get-started-with-teams-templates-in-the-admin-console.md)
- [<span data-ttu-id="514db-180">Introducción a las plantillas de Teams</span><span class="sxs-lookup"><span data-stu-id="514db-180">Get started with Teams templates</span></span>](get-started-with-teams-templates.md)
- <span data-ttu-id="514db-181">[Crear equipo](/graph/api/team-post?view=graph-rest-beta) (en vista previa)</span><span class="sxs-lookup"><span data-stu-id="514db-181">[Create team](/graph/api/team-post?view=graph-rest-beta) (in preview)</span></span>