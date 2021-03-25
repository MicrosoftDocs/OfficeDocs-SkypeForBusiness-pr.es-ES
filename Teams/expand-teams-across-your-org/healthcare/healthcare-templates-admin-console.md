---
title: Crear un equipo con plantillas de Teams para la atención sanitaria
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Use plantillas de Microsoft Teams en el Centro de administración o con Microsoft Graph para crear equipos de forma rápida y sencilla proporcionando una plantilla predefinida de configuración, canales y aplicaciones.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 13b85818101e1c3d42ae6dc715274ac23453e178
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117878"
---
# <a name="create-a-team-using-teams-healthcare-templates"></a><span data-ttu-id="d5135-103">Crear un equipo con plantillas de Teams para la atención sanitaria</span><span class="sxs-lookup"><span data-stu-id="d5135-103">Create a team using Teams healthcare templates</span></span>

<span data-ttu-id="d5135-104">Las plantillas de Microsoft Teams le permiten crear equipos de forma rápida y sencilla al proporcionar una plantilla predefinida de configuración, canales y aplicaciones preinstaladas.</span><span class="sxs-lookup"><span data-stu-id="d5135-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="d5135-105">Para las organizaciones sanitarias, las plantillas pueden ser especialmente eficaces, ya que proporcionan una estructura para que los usuarios se orienten sobre cómo usar Teams de forma eficaz.</span><span class="sxs-lookup"><span data-stu-id="d5135-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams.</span></span> <span data-ttu-id="d5135-106">Las plantillas también permiten a los administradores implementar equipos coherentes en todas las organizaciones.</span><span class="sxs-lookup"><span data-stu-id="d5135-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="d5135-107">Este artículo les ayudará si es el responsable de planear, implementar y administrar varios equipos en toda la organización sanitaria.</span><span class="sxs-lookup"><span data-stu-id="d5135-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="d5135-108">Elija un método para crear equipos con las plantillas de Teams para la atención sanitaria:</span><span class="sxs-lookup"><span data-stu-id="d5135-108">Choose a method for creating teams with the Teams healthcare templates:</span></span>

| <span data-ttu-id="d5135-109">Quién</span><span class="sxs-lookup"><span data-stu-id="d5135-109">Who</span></span> | <span data-ttu-id="d5135-110">Método de uso:</span><span class="sxs-lookup"><span data-stu-id="d5135-110">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="d5135-111">Administradores y profesionales de TI</span><span class="sxs-lookup"><span data-stu-id="d5135-111">Admins and IT Professionals</span></span> | <span data-ttu-id="d5135-112">[Use el Centro de administración de Teams](#use-the-teams-templates-in-the-teams-admin-center) para crear equipos basados en las plantillas de Teams para la atención sanitaria.</span><span class="sxs-lookup"><span data-stu-id="d5135-112">[Use the Teams admin center](#use-the-teams-templates-in-the-teams-admin-center) to create teams based on the healthcare Teams templates.</span></span>|
| <span data-ttu-id="d5135-113">Desarrolladores e integradores de sistemas</span><span class="sxs-lookup"><span data-stu-id="d5135-113">Developers and systems integrators</span></span> | <span data-ttu-id="d5135-114">[Use Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) crear equipos basados en las plantillas de Teams para la atención sanitaria.</span><span class="sxs-lookup"><span data-stu-id="d5135-114">[Use the Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) to create teams based on the healthcare Teams templates.</span></span> |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a><span data-ttu-id="d5135-115">Usar las plantillas de Teams en el Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="d5135-115">Use the Teams templates in the Teams admin center</span></span>

<span data-ttu-id="d5135-116">Los administradores de Microsoft Teams pueden usar el Centro de administración de Teams para crear equipos con las plantillas de Teams.</span><span class="sxs-lookup"><span data-stu-id="d5135-116">Microsoft Teams admins can use the Teams admin center to create teams with the Teams templates.</span></span> <span data-ttu-id="d5135-117">Actualmente ofrecemos dos plantillas propias para la atención sanitaria que puede usar en varias situaciones.</span><span class="sxs-lookup"><span data-stu-id="d5135-117">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="d5135-118">Para obtener más información sobre las plantillas de equipo en general, vea [Introducción a las plantillas de Teams en el Centro de administración](../../get-started-with-teams-templates-in-the-admin-console.md).</span><span class="sxs-lookup"><span data-stu-id="d5135-118">To learn more about team templates in general, see [Get started with Teams templates in the admin center](../../get-started-with-teams-templates-in-the-admin-console.md).</span></span>

### <a name="collaborate-on-patient-care"></a><span data-ttu-id="d5135-119">Colaborar en la atención al paciente</span><span class="sxs-lookup"><span data-stu-id="d5135-119">Collaborate on patient care</span></span>

 <span data-ttu-id="d5135-120">Simplifique la comunicación y la colaboración sanitaria en una sala, dispensario o departamento.</span><span class="sxs-lookup"><span data-stu-id="d5135-120">Streamline healthcare communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="d5135-121">La plantilla puede usarse para facilitar la gestión de los pacientes y las necesidades operativas de una sala.</span><span class="sxs-lookup"><span data-stu-id="d5135-121">The template can be used to facilitate patient management and operational needs of a ward.</span></span>

| <span data-ttu-id="d5135-122">Tipo de plantilla base</span><span class="sxs-lookup"><span data-stu-id="d5135-122">Base template type</span></span> |<span data-ttu-id="d5135-123">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="d5135-123">baseTemplateId</span></span>| <span data-ttu-id="d5135-124">Propiedades que vienen con esta plantilla base</span><span class="sxs-lookup"><span data-stu-id="d5135-124">Properties that come with this base template</span></span> |
| ------------------ |---|----------------------------------------------------- |
| <span data-ttu-id="d5135-125">Colaborar en la atención al paciente</span><span class="sxs-lookup"><span data-stu-id="d5135-125">Collaborate on patient care</span></span> |`healthcareWard` | <span data-ttu-id="d5135-126">Canales:</span><span class="sxs-lookup"><span data-stu-id="d5135-126">Channels:</span></span><ul><li><span data-ttu-id="d5135-127">General</span><span class="sxs-lookup"><span data-stu-id="d5135-127">General</span></span></li><li><span data-ttu-id="d5135-128">Anuncios</span><span class="sxs-lookup"><span data-stu-id="d5135-128">Announcements</span></span></li><li><span data-ttu-id="d5135-129">Reuniones</span><span class="sxs-lookup"><span data-stu-id="d5135-129">Huddles</span></span></li><li><span data-ttu-id="d5135-130">Rondas</span><span class="sxs-lookup"><span data-stu-id="d5135-130">Rounds</span></span></li><li><span data-ttu-id="d5135-131">Personal</span><span class="sxs-lookup"><span data-stu-id="d5135-131">Staffing</span></span></li><li><span data-ttu-id="d5135-132">Aprendizaje</span><span class="sxs-lookup"><span data-stu-id="d5135-132">Training</span></span></li></ul> <span data-ttu-id="d5135-133">Aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="d5135-133">Apps:</span></span> <ul><li><span data-ttu-id="d5135-134">Wiki</span><span class="sxs-lookup"><span data-stu-id="d5135-134">Wiki</span></span></li><li><span data-ttu-id="d5135-135">Listas</span><span class="sxs-lookup"><span data-stu-id="d5135-135">Lists</span></span></li></ul>|
||||

### <a name="hospital"></a><span data-ttu-id="d5135-136">Hospital</span><span class="sxs-lookup"><span data-stu-id="d5135-136">Hospital</span></span>

<span data-ttu-id="d5135-137">Simplifique la comunicación y la colaboración entre varias salas, dispensario y departamentos dentro de un hospital.</span><span class="sxs-lookup"><span data-stu-id="d5135-137">Streamline communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="d5135-138">Esta plantilla incluye un conjunto de canales base para operaciones en los hospitales y puede ampliarse para incluir especialidades, según necesario.</span><span class="sxs-lookup"><span data-stu-id="d5135-138">This template includes a set of base channels for hospital operations, and can be self-extended to include specialties, ad-hoc.</span></span>

| <span data-ttu-id="d5135-139">Tipo de plantilla base</span><span class="sxs-lookup"><span data-stu-id="d5135-139">Base template type</span></span> |<span data-ttu-id="d5135-140">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="d5135-140">baseTemplateId</span></span> | <span data-ttu-id="d5135-141">Propiedades que vienen con esta plantilla base</span><span class="sxs-lookup"><span data-stu-id="d5135-141">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="d5135-142">Hospital</span><span class="sxs-lookup"><span data-stu-id="d5135-142">Hospital</span></span>|`healthcareHospital`|<span data-ttu-id="d5135-143">Canales:</span><span class="sxs-lookup"><span data-stu-id="d5135-143">Channels:</span></span> <ul><li><span data-ttu-id="d5135-144">General</span><span class="sxs-lookup"><span data-stu-id="d5135-144">General</span></span></li><li><span data-ttu-id="d5135-145">Anuncios</span><span class="sxs-lookup"><span data-stu-id="d5135-145">Announcements</span></span></li><li><span data-ttu-id="d5135-146">Cumplimiento</span><span class="sxs-lookup"><span data-stu-id="d5135-146">Compliance</span></span></li><li><span data-ttu-id="d5135-147">Custodia</span><span class="sxs-lookup"><span data-stu-id="d5135-147">Custodial</span></span></li><li><span data-ttu-id="d5135-148">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="d5135-148">Human resources</span></span></li><li><span data-ttu-id="d5135-149">Farmacia</span><span class="sxs-lookup"><span data-stu-id="d5135-149">Pharmacy</span></span></li></ul> <span data-ttu-id="d5135-150">Aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="d5135-150">Apps:</span></span> <ul><li><span data-ttu-id="d5135-151">Wiki</span><span class="sxs-lookup"><span data-stu-id="d5135-151">Wiki</span></span></li><li><span data-ttu-id="d5135-152">Listas</span><span class="sxs-lookup"><span data-stu-id="d5135-152">Lists</span></span> </li></ul>|
||||


## <a name="use-the-teams-templates-with-the-microsoft-graph"></a><span data-ttu-id="d5135-153">Usar las plantillas de Teams con Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="d5135-153">Use the Teams templates with the Microsoft Graph</span></span>

<span data-ttu-id="d5135-154">Los desarrolladores pueden usar Microsoft Graph para crear equipos con las plantillas de Teams.</span><span class="sxs-lookup"><span data-stu-id="d5135-154">Developers can use the Microsoft Graph to create teams with the Teams templates.</span></span> <span data-ttu-id="d5135-155">Actualmente ofrecemos dos plantillas propias para la atención sanitaria que puede usar en varias situaciones.</span><span class="sxs-lookup"><span data-stu-id="d5135-155">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="d5135-156">Para obtener más información sobre las plantillas de equipo en general, vea [Introducción a las plantillas de Teams](../../get-started-with-teams-templates.md).</span><span class="sxs-lookup"><span data-stu-id="d5135-156">To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span> <span data-ttu-id="d5135-157">Para obtener información sobre las plantillas de Teams y Microsoft Graph, vea [Información general de la API de Microsoft Teams](/graph/teams-concept-overview?view=graph-rest-1.0) y [Tipo de recurso teamsTemplate](/graph/api/resources/teamstemplate?view=graph-rest-1.0).</span><span class="sxs-lookup"><span data-stu-id="d5135-157">And for information about Teams templates and the Microsoft Graph, see [Microsoft Teams API overview](/graph/teams-concept-overview?view=graph-rest-1.0) and [teamsTemplate resource type](/graph/api/resources/teamstemplate?view=graph-rest-1.0).</span></span>

### <a name="ward-template"></a><span data-ttu-id="d5135-158">Plantilla de sala</span><span class="sxs-lookup"><span data-stu-id="d5135-158">Ward template</span></span>

<span data-ttu-id="d5135-159">La plantilla de sala está pensada para la comunicación y la colaboración dentro de una sala, dispensario o departamento.</span><span class="sxs-lookup"><span data-stu-id="d5135-159">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="d5135-160">La plantilla puede usarse para facilitar la gestión de los pacientes, así como las necesidades operativas de una sala.</span><span class="sxs-lookup"><span data-stu-id="d5135-160">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="d5135-161">Por ejemplo, los anuncios de salas pueden publicarse en el canal *Anuncios* y los turnos pueden publicarse en el canal *Personal*.</span><span class="sxs-lookup"><span data-stu-id="d5135-161">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="d5135-162">Si quiere simplificar sus operaciones de sala, esta plantilla es la adecuada.</span><span class="sxs-lookup"><span data-stu-id="d5135-162">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="d5135-163">Tipo de plantilla base</span><span class="sxs-lookup"><span data-stu-id="d5135-163">Base Template Type</span></span> |<span data-ttu-id="d5135-164">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="d5135-164">baseTemplateId</span></span> |<span data-ttu-id="d5135-165">Canales de plantilla de línea base</span><span class="sxs-lookup"><span data-stu-id="d5135-165">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="d5135-166">Atención sanitaria: sala</span><span class="sxs-lookup"><span data-stu-id="d5135-166">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="d5135-167">Anuncios\*</span><span class="sxs-lookup"><span data-stu-id="d5135-167">Announcements\*</span></span> <br> <span data-ttu-id="d5135-168">Reuniones\*</span><span class="sxs-lookup"><span data-stu-id="d5135-168">Huddles\*</span></span> <br> <span data-ttu-id="d5135-169">Rondas\*</span><span class="sxs-lookup"><span data-stu-id="d5135-169">Rounds\*</span></span> <br> <span data-ttu-id="d5135-170">Personal\*</span><span class="sxs-lookup"><span data-stu-id="d5135-170">Staffing\*</span></span> <br> <span data-ttu-id="d5135-171">Aprendizaje\*</span><span class="sxs-lookup"><span data-stu-id="d5135-171">Training\*</span></span> |
|     | |         |

<span data-ttu-id="d5135-172">\* Marcado automáticamente como favorito</span><span class="sxs-lookup"><span data-stu-id="d5135-172">\* Auto-favorited</span></span>

### <a name="hospital-template"></a><span data-ttu-id="d5135-173">Plantilla de hospital</span><span class="sxs-lookup"><span data-stu-id="d5135-173">Hospital template</span></span>

<span data-ttu-id="d5135-174">La plantilla de hospital está pensada para la comunicación y la colaboración entre varias salas, dispensarios y departamentos dentro un hospital.</span><span class="sxs-lookup"><span data-stu-id="d5135-174">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="d5135-175">En esta plantilla se incluyen varios canales operativos, como *Anuncios*, *Custodia* y *Farmacia*, pero también le proporcionamos un script a continuación que amplía la plantilla con departamentos adicionales o canales de especialidades que puede agregar, eliminar o editar a su gusto.</span><span class="sxs-lookup"><span data-stu-id="d5135-175">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="d5135-176">Por ejemplo, si tiene un departamento de *Endocrinología*, pero no necesita un canal para *Oftalmología*, el script puede adaptarse para incluir un canal de *Endocrinología* y quitar el canal de *Oftalmología*.</span><span class="sxs-lookup"><span data-stu-id="d5135-176">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="d5135-177">Para evitar la saturación de notificaciones, recomendamos que estos canales de especialidades o basados en salas no se marquen como favoritos automáticamente.</span><span class="sxs-lookup"><span data-stu-id="d5135-177">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="d5135-178">Los usuarios suelen marcar como favoritos los canales que encuentran relevantes.</span><span class="sxs-lookup"><span data-stu-id="d5135-178">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="d5135-179">Tipo de plantilla base</span><span class="sxs-lookup"><span data-stu-id="d5135-179">Base Template Type</span></span> |<span data-ttu-id="d5135-180">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="d5135-180">baseTemplateId</span></span> |<span data-ttu-id="d5135-181">Canales de plantilla de línea base</span><span class="sxs-lookup"><span data-stu-id="d5135-181">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="d5135-182">atención sanitaria: hospital</span><span class="sxs-lookup"><span data-stu-id="d5135-182">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="d5135-183">Anuncios\*</span><span class="sxs-lookup"><span data-stu-id="d5135-183">Announcements\*</span></span> <br> <span data-ttu-id="d5135-184">Cumplimiento\*</span><span class="sxs-lookup"><span data-stu-id="d5135-184">Compliance\*</span></span> <br> <span data-ttu-id="d5135-185">Custodia</span><span class="sxs-lookup"><span data-stu-id="d5135-185">Custodial</span></span> <br> <span data-ttu-id="d5135-186">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="d5135-186">Human Resources</span></span> <br> <span data-ttu-id="d5135-187">Farmacia</span><span class="sxs-lookup"><span data-stu-id="d5135-187">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="d5135-188">\* Marcado automáticamente como favorito</span><span class="sxs-lookup"><span data-stu-id="d5135-188">\* Auto-favorited</span></span> 

### <a name="how-to-use-first-party-templates"></a><span data-ttu-id="d5135-189">Cómo usar plantillas de terceros</span><span class="sxs-lookup"><span data-stu-id="d5135-189">How to use first-party templates</span></span>

<span data-ttu-id="d5135-190">Para usar estas plantillas, simplemente cambie la propiedad "template@odata.bind" en el cuerpo de la solicitud de "estándar" a los TemplateID anteriores.</span><span class="sxs-lookup"><span data-stu-id="d5135-190">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="d5135-191">Para obtener más información sobre cómo implementar plantillas de Teams, vea el artículo de Microsoft Graph sobre cómo [crear un equipo](/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="d5135-191">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="d5135-192">Los canales de la plantilla se crearán automáticamente en la pestaña General.</span><span class="sxs-lookup"><span data-stu-id="d5135-192">The channels in the template will automatically be created under the General Tab.</span></span>

#### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="d5135-193">Ejemplo: script de extensión de plantilla de hospital</span><span class="sxs-lookup"><span data-stu-id="d5135-193">Example: Hospital template extension script</span></span>

``` Powershell
{ 
          "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('healthcareHospital')",
          "DisplayName": "Contoso Hospital",
          "Description": "Team for all staff in Contoso Hospital",
          "Channels": [
            {
              "displayName": "Ambulatory",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Anesthesiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Cardiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "CCU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ear, Nose, and Throat",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Emergency Care",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Family Medicine",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Gynecology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "ICU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Mother-Baby",
              "IsFavoriteByDefault": false
            }, 
            {
              "displayName": "Neonatal",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Neurology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Oncology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Ophthalmology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "PACU",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Psychiatric",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Radiology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Rehabilitation",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Surgical",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Urology",
              "IsFavoriteByDefault": false
            },
            {
              "displayName": "Women's Health",
              "IsFavoriteByDefault": false
            }
          ],
          "Apps": [
            {
              "Id": "1542629c-01b3-4a6d-8f76-1938b779e48d"
            }
          ]
          }

```

### <a name="related-topics"></a><span data-ttu-id="d5135-194">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d5135-194">Related topics</span></span>

[<span data-ttu-id="d5135-195">Introducción a las plantillas de Teams</span><span class="sxs-lookup"><span data-stu-id="d5135-195">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="d5135-196">Introducción a Teams para organizaciones sanitarias</span><span class="sxs-lookup"><span data-stu-id="d5135-196">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)