---
title: Introducción a las plantillas de Teams para pequeñas y medianas empresas
author: kenwith
ms.author: kenwith
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.reviewer: lavenkat
description: Introducción a las plantillas de Teams para pequeñas y medianas empresas
ms.openlocfilehash: d9e626dad9bbdde655448d0a2052c394fff2ffb7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36242969"
---
# <a name="get-started-with-teams-templates-for-small-and-medium-businesses"></a><span data-ttu-id="cb41c-103">Introducción a las plantillas de Teams para pequeñas y medianas empresas</span><span class="sxs-lookup"><span data-stu-id="cb41c-103">Get started with Teams templates for Small and Medium Businesses</span></span>

<span data-ttu-id="cb41c-104">Las plantillas de Microsoft Teams le permiten crear equipos de forma rápida y sencilla proporcionando una plantilla predefinida de configuración, canales y aplicaciones preinstaladas.</span><span class="sxs-lookup"><span data-stu-id="cb41c-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="cb41c-105">Para las pequeñas y medianas empresas, las plantillas pueden ser especialmente eficaces, ya que ayudan a los administradores a implementar rápidamente Teams en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="cb41c-105">For small and medium businesses, templates can be especially powerful, as they help administrators to quickly deploy Teams across their organization.</span></span> <span data-ttu-id="cb41c-106">Las plantillas también ayudan a orientar a los usuarios y a comenzar a usar Teams de manera eficaz.</span><span class="sxs-lookup"><span data-stu-id="cb41c-106">Templates also help orient users and get started with using Teams effectively.</span></span> <span data-ttu-id="cb41c-107">Este artículo le interesa si es responsable de planear, implementar y administrar varios equipos en la organización.</span><span class="sxs-lookup"><span data-stu-id="cb41c-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your organization.</span></span>

<span data-ttu-id="cb41c-108">Actualmente ofrecemos tres plantillas de SMB de primera parte que puede aprovechar para diversas situaciones.</span><span class="sxs-lookup"><span data-stu-id="cb41c-108">We currently offer three first party SMB templates that you can leverage for a variety of situations.</span></span> <span data-ttu-id="cb41c-109">Todas las plantillas crearán equipos *privados* .</span><span class="sxs-lookup"><span data-stu-id="cb41c-109">All templates will create *Private* Teams.</span></span> <span data-ttu-id="cb41c-110">Una vez que haya creado los equipos y estén listos para su organización, puede establecer la privacidad en *toda* la organización o *pública*, según corresponda.</span><span class="sxs-lookup"><span data-stu-id="cb41c-110">Once you have created the Teams and are ready to roll-out to your organization, you can set the privacy to *Org-Wide* or *Public*, as appropriate.</span></span> <span data-ttu-id="cb41c-111">Para obtener más información sobre las plantillas de equipo en general, consulte [Introducción a las plantillas](get-started-with-teams-templates.md)de Teams.</span><span class="sxs-lookup"><span data-stu-id="cb41c-111">To learn more about team templates in general, please see [Get started with Teams templates](get-started-with-teams-templates.md).</span></span>

## <a name="company-wide-template"></a><span data-ttu-id="cb41c-112">Plantilla de toda la empresa</span><span class="sxs-lookup"><span data-stu-id="cb41c-112">Company-Wide template</span></span>
<span data-ttu-id="cb41c-113">La plantilla para toda la empresa está destinada a la comunicación y la colaboración que son relevantes para toda la empresa.</span><span class="sxs-lookup"><span data-stu-id="cb41c-113">The Company-Wide template is meant for communication and collaboration that are relevant for the entire company.</span></span> <span data-ttu-id="cb41c-114">Puede usar el canal general para anuncios de toda la empresa, noticias de la industria o publicaciones ejecutivas.</span><span class="sxs-lookup"><span data-stu-id="cb41c-114">You can use the General channel for company-wide announcements, industry news or executive posts.</span></span> <span data-ttu-id="cb41c-115">El canal de recursos humanos es un buen lugar para consolidar todas las actividades relacionadas con recursos humanos, como las publicaciones de trabajo, la incorporación de nuevos empleados, la formación y el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="cb41c-115">The Human Resources channel is a great place to consolidate all HR-related activities like job posts, new employee onboarding, training and development.</span></span> <span data-ttu-id="cb41c-116">El canal de material variado proporciona una plataforma social para todas las publicaciones de forma aleatoria y divertida.</span><span class="sxs-lookup"><span data-stu-id="cb41c-116">The Fun Stuff channel provides a social platform for all random and fun posts.</span></span>

| <span data-ttu-id="cb41c-117">Tipo de plantilla base</span><span class="sxs-lookup"><span data-stu-id="cb41c-117">Base template type</span></span>  | <span data-ttu-id="cb41c-118">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="cb41c-118">baseTemplateId</span></span> | <span data-ttu-id="cb41c-119">Propiedades que vienen con esta plantilla base</span><span class="sxs-lookup"><span data-stu-id="cb41c-119">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="cb41c-120">Pequeñas</span><span class="sxs-lookup"><span data-stu-id="cb41c-120">SMB -</span></span> <br><span data-ttu-id="cb41c-121">Toda la empresa</span><span class="sxs-lookup"><span data-stu-id="cb41c-121">Company-wide</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessOrgWide')`| <span data-ttu-id="cb41c-122">Canales</span><span class="sxs-lookup"><span data-stu-id="cb41c-122">Channels</span></span> <ul><li><span data-ttu-id="cb41c-123">General\*</span><span class="sxs-lookup"><span data-stu-id="cb41c-123">General\*</span></span></li><li><span data-ttu-id="cb41c-124">Recursos humanos\*</span><span class="sxs-lookup"><span data-stu-id="cb41c-124">Human Resources\*</span></span></li><li><span data-ttu-id="cb41c-125">Cosas divertidas\*</span><span class="sxs-lookup"><span data-stu-id="cb41c-125">Fun Stuff\*</span></span></li></ul><br> <span data-ttu-id="cb41c-126">Aplicaciones</span><span class="sxs-lookup"><span data-stu-id="cb41c-126">Apps</span></span><ul><li><span data-ttu-id="cb41c-127">Portal de empresa (sitio web anclado al canal de **recursos humanos** )</span><span class="sxs-lookup"><span data-stu-id="cb41c-127">Company Portal (Website pinned to the **Human Resources** channel)</span></span> </li> </UL><br><span data-ttu-id="cb41c-128">Propiedades del equipo</span><span class="sxs-lookup"><span data-stu-id="cb41c-128">Team properties</span></span> <ul><li><span data-ttu-id="cb41c-129">Visibilidad del equipo establecida en privado</span><span class="sxs-lookup"><span data-stu-id="cb41c-129">Team visibility set to Private</span></span></li></ul> |

<span data-ttu-id="cb41c-130">\* Canales favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="cb41c-130">\*Auto-favorited channels</span></span> 

<span data-ttu-id="cb41c-131">Para crear el equipo de toda la empresa mediante la toma de valores predeterminados de la plantilla predefinida, proporcione la representación JSON del objeto de equipo en el cuerpo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="cb41c-131">To create the Company-Wide team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="cb41c-132">Para obtener más información sobre cómo implementar las plantillas de Teams, vea el [artículo de Microsoft Graph sobre la creación de un equipo](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="cb41c-132">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="cb41c-133">Solicitud</span><span class="sxs-lookup"><span data-stu-id="cb41c-133">Request</span></span> 
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

## <a name="executive-team-template"></a><span data-ttu-id="cb41c-134">Plantilla de equipo ejecutivo</span><span class="sxs-lookup"><span data-stu-id="cb41c-134">Executive Team template</span></span>

<span data-ttu-id="cb41c-135">La plantilla del equipo ejecutivo es ideal para crear un equipo para que los ejecutivos de la empresa puedan comunicarse y colaborar en iniciativas de la empresa, como prioridades anuales, presupuestos fiscales, iniciativas estratégicas, clientes principales, etc. Esta plantilla viene con un canal *privado* para invitar a determinados usuarios a determinados temas.</span><span class="sxs-lookup"><span data-stu-id="cb41c-135">The Executive Team template is ideal for creating a team for company executives to communicate and collaborate on company initiatives like annual priorities, fiscal budgets, strategic initiatives, top clients, etc. This template comes with a *Private* channel to invite select users for specific topics.</span></span>

| <span data-ttu-id="cb41c-136">Tipo de plantilla base</span><span class="sxs-lookup"><span data-stu-id="cb41c-136">Base template type</span></span>  | <span data-ttu-id="cb41c-137">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="cb41c-137">baseTemplateId</span></span> | <span data-ttu-id="cb41c-138">Propiedades que vienen con esta plantilla base</span><span class="sxs-lookup"><span data-stu-id="cb41c-138">Properties that come with this base template</span></span> |
| :------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="cb41c-139">Pequeñas</span><span class="sxs-lookup"><span data-stu-id="cb41c-139">SMB -</span></span> <br><span data-ttu-id="cb41c-140">Equipo ejecutivos</span><span class="sxs-lookup"><span data-stu-id="cb41c-140">Executives Team</span></span> | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessExecutive')` | <span data-ttu-id="cb41c-141">Canales</span><span class="sxs-lookup"><span data-stu-id="cb41c-141">Channels</span></span> <ul><li><span data-ttu-id="cb41c-142">General\*</span><span class="sxs-lookup"><span data-stu-id="cb41c-142">General\*</span></span></li><li><span data-ttu-id="cb41c-143">Empresa\*</span><span class="sxs-lookup"><span data-stu-id="cb41c-143">Private \*</span></span></li></ul> <span data-ttu-id="cb41c-144">Aplicaciones</span><span class="sxs-lookup"><span data-stu-id="cb41c-144">Apps</span></span><ul><li><span data-ttu-id="cb41c-145">OneNote (anclado al canal **privado** )</span><span class="sxs-lookup"><span data-stu-id="cb41c-145">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="cb41c-146">Planner (anclado al canal **privado** )</span><span class="sxs-lookup"><span data-stu-id="cb41c-146">Planner (pinned to the **Private** channel)</span></span> </li></ul><br><span data-ttu-id="cb41c-147">Propiedades del equipo</span><span class="sxs-lookup"><span data-stu-id="cb41c-147">Team properties</span></span> <ul><li><span data-ttu-id="cb41c-148">Visibilidad del equipo establecida en privado</span><span class="sxs-lookup"><span data-stu-id="cb41c-148">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="cb41c-149">\* Canales favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="cb41c-149">\*Auto-favorited channels</span></span><br>

<span data-ttu-id="cb41c-150">Para crear el equipo de ejecutivos adoptando de forma predeterminada las plantillas predefinidas, proporcione la representación JSON del objeto de equipo en el cuerpo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="cb41c-150">To create the Executives team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="cb41c-151">Para obtener más información sobre cómo implementar las plantillas de Teams, vea el [artículo de Microsoft Graph sobre la creación de un equipo](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="cb41c-151">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="cb41c-152">Solicitud</span><span class="sxs-lookup"><span data-stu-id="cb41c-152">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessExecutive')",
    "displayName": "Executive",
    "description": "All posts, announcements and daily collaboration and communication for the company’s leadership team.",
    "visibility": "Private"
}
```

## <a name="departmental-team-template"></a><span data-ttu-id="cb41c-153">Plantilla de equipo departamental</span><span class="sxs-lookup"><span data-stu-id="cb41c-153">Departmental Team template</span></span>

<span data-ttu-id="cb41c-154">La plantilla de equipo departamental se puede usar para crear un equipo para departamentos individuales o para proyectos.</span><span class="sxs-lookup"><span data-stu-id="cb41c-154">The Departmental team template can be used for creating a team for individual departments or for projects.</span></span> <span data-ttu-id="cb41c-155">La plantilla del equipo de finanzas es ideal para todas las publicaciones, anuncios y colaboración y comunicación diaria dentro de los miembros del equipo de Finanzas (y miembros del equipo ejecutivo según corresponda).</span><span class="sxs-lookup"><span data-stu-id="cb41c-155">The Finance team template is ideal for all posts, announcements and daily collaboration and communication within the Finance team members (and executive team members as appropriate).</span></span> <span data-ttu-id="cb41c-156">La plantilla viene con un canal *privado* para invitar a determinados usuarios a determinados temas.</span><span class="sxs-lookup"><span data-stu-id="cb41c-156">The template comes with a *Private* channel to invite select users for specific topics.</span></span> <span data-ttu-id="cb41c-157">También proporcionamos la siguiente secuencia de comandos para el equipo de finanzas, que se puede usar para ampliar la plantilla a otros departamentos o proyectos específicos agregando, eliminando o editando a su gusto.</span><span class="sxs-lookup"><span data-stu-id="cb41c-157">We also provide the script below for the Finance team which can be used to extend the template to additional departments or specific projects by adding, deleting from or editing to your liking.</span></span> <span data-ttu-id="cb41c-158">Por ejemplo, si tiene un departamento de *marketing* , el script puede adaptarse cambiando el nombre del equipo de Finance \*\* a *marketing* para crear un nuevo equipo de marketing</span><span class="sxs-lookup"><span data-stu-id="cb41c-158">For example, if you have a *Marketing* department, then the script can be adapted by renaming the team from *Finance* to *Marketing* to create a new Marketing team</span></span>

| <span data-ttu-id="cb41c-159">Tipo de plantilla base</span><span class="sxs-lookup"><span data-stu-id="cb41c-159">Base template type</span></span> | <span data-ttu-id="cb41c-160">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="cb41c-160">baseTemplateId</span></span> | <span data-ttu-id="cb41c-161">Propiedades que vienen con esta plantilla base</span><span class="sxs-lookup"><span data-stu-id="cb41c-161">Properties that come with this base template</span></span> |
|:------------------ | :-------------- | :----------------------------------------------------- | 
| <span data-ttu-id="cb41c-162">Pequeñas</span><span class="sxs-lookup"><span data-stu-id="cb41c-162">SMB -</span></span> <br><span data-ttu-id="cb41c-163">Finanzas</span><span class="sxs-lookup"><span data-stu-id="cb41c-163">Finance</span></span>  | `https://graph.microsoft.com/beta/`<br>` teamsTemplates('SmallBusinessFinance')`| <span data-ttu-id="cb41c-164">Canales</span><span class="sxs-lookup"><span data-stu-id="cb41c-164">Channels</span></span> <ul><li><span data-ttu-id="cb41c-165">General\*</span><span class="sxs-lookup"><span data-stu-id="cb41c-165">General\*</span></span></li><li><span data-ttu-id="cb41c-166">Empresa\*</span><span class="sxs-lookup"><span data-stu-id="cb41c-166">Private \*</span></span></li></ul><br> <span data-ttu-id="cb41c-167">Aplicaciones</span><span class="sxs-lookup"><span data-stu-id="cb41c-167">Apps</span></span><ul><li><span data-ttu-id="cb41c-168">OneNote (anclado al canal **privado** )</span><span class="sxs-lookup"><span data-stu-id="cb41c-168">OneNote (pinned to the **Private** channel)</span></span></li> <li><span data-ttu-id="cb41c-169">Planner (anclado al canal **privado** )</span><span class="sxs-lookup"><span data-stu-id="cb41c-169">Planner (pinned to the **Private** channel)</span></span> </li> </ul><br><span data-ttu-id="cb41c-170">Propiedades del equipo</span><span class="sxs-lookup"><span data-stu-id="cb41c-170">Team properties</span></span> <ul><li><span data-ttu-id="cb41c-171">Visibilidad del equipo establecida en privado</span><span class="sxs-lookup"><span data-stu-id="cb41c-171">Team visibility set to Private</span></span></li></ul> | 

<span data-ttu-id="cb41c-172">\* Canales favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="cb41c-172">\*Auto-favorited channels</span></span>

<span data-ttu-id="cb41c-173">Para crear el equipo de finanzas adoptando los valores predeterminados de la plantilla predefinida, proporcione la representación JSON del objeto de equipo en el cuerpo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="cb41c-173">To create the Finance team by taking defaults from the pre-defined template, supply the JSON representation of the team object in the request body.</span></span> <span data-ttu-id="cb41c-174">Para obtener más información sobre cómo implementar las plantillas de Teams, vea el [artículo de Microsoft Graph sobre la creación de un equipo](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="cb41c-174">To learn more about how to deploy Teams templates, see the Microsoft Graph [article on creating a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

#### <a name="request"></a><span data-ttu-id="cb41c-175">Solicitud</span><span class="sxs-lookup"><span data-stu-id="cb41c-175">Request</span></span> 
```http 
POST https://graph.microsoft.com/beta/teams 
Content-Type: application/json 
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('SmallBusinessFinance')",
    "displayName": "Finance",
    "description": "All posts, announcements and daily collaboration and communication within the Finance team members (and exec team members as appropriate).",
    "visibility": "Private"
}
``

### Example: Finance Team template extension script

``` Powershell
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

## <a name="related-topics"></a><span data-ttu-id="cb41c-176">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="cb41c-176">Related topics</span></span>

- [<span data-ttu-id="cb41c-177">Introducción a las plantillas de Teams</span><span class="sxs-lookup"><span data-stu-id="cb41c-177">Get started with Teams templates</span></span>](get-started-with-teams-templates.md)
- <span data-ttu-id="cb41c-178">[Crear equipo](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (en versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="cb41c-178">[Create team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in preview)</span></span>

