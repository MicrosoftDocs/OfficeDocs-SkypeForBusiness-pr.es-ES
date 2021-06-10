---
title: Crear un equipo con plantillas de atención sanitaria
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
description: Use plantillas de equipo en el centro de administración o con Microsoft Graph para crear equipos de forma rápida y sencilla proporcionando una plantilla predefinida de configuración, canales y aplicaciones.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: f90ddfa9682c7000c4698977c51a39c9631ff9b1
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684357"
---
# <a name="use-a-healthcare-team-templates"></a><span data-ttu-id="6d13b-103">Usar plantillas de equipo de atención sanitaria</span><span class="sxs-lookup"><span data-stu-id="6d13b-103">Use a healthcare team templates</span></span>

<span data-ttu-id="6d13b-104">Las plantillas le permiten crear equipos de forma rápida y sencilla proporcionando una plantilla predefinida de configuración, canales y aplicaciones preinstaladas.</span><span class="sxs-lookup"><span data-stu-id="6d13b-104">Templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="6d13b-105">Para las organizaciones sanitarias, las plantillas pueden ser especialmente eficaces, ya que proporcionan estructura para que los usuarios se orienten con la manera de usar de forma eficaz Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6d13b-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Microsoft Teams.</span></span> <span data-ttu-id="6d13b-106">Las plantillas también permiten a los administradores implementar equipos coherentes en todas las organizaciones.</span><span class="sxs-lookup"><span data-stu-id="6d13b-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="6d13b-107">Este artículo les ayudará si es el responsable de planear, implementar y administrar varios equipos en toda la organización sanitaria.</span><span class="sxs-lookup"><span data-stu-id="6d13b-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="6d13b-108">Elija un método para crear equipos con las plantillas de atención sanitaria del equipo:</span><span class="sxs-lookup"><span data-stu-id="6d13b-108">Choose a method for creating teams with the team healthcare templates:</span></span>

| <span data-ttu-id="6d13b-109">Quién</span><span class="sxs-lookup"><span data-stu-id="6d13b-109">Who</span></span> | <span data-ttu-id="6d13b-110">Método de uso:</span><span class="sxs-lookup"><span data-stu-id="6d13b-110">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="6d13b-111">Administradores y profesionales de TI</span><span class="sxs-lookup"><span data-stu-id="6d13b-111">Admins and IT Professionals</span></span> | <span data-ttu-id="6d13b-112">[Use el centro Teams administración para](#use-the-team-templates-in-the-admin-center) crear equipos basados en las plantillas de equipo de salud.</span><span class="sxs-lookup"><span data-stu-id="6d13b-112">[Use the Teams admin center](#use-the-team-templates-in-the-admin-center) to create teams based on the healthcare team templates.</span></span>|
| <span data-ttu-id="6d13b-113">Desarrolladores e integradores de sistemas</span><span class="sxs-lookup"><span data-stu-id="6d13b-113">Developers and systems integrators</span></span> | <span data-ttu-id="6d13b-114">[Use microsoft Graph](#use-the-team-templates-with-the-microsoft-graph) para crear un equipo basado en las plantillas de equipo de salud.</span><span class="sxs-lookup"><span data-stu-id="6d13b-114">[Use the Microsoft Graph](#use-the-team-templates-with-the-microsoft-graph) to create a team based on the healthcare team templates.</span></span> |

## <a name="use-the-team-templates-in-the-admin-center"></a><span data-ttu-id="6d13b-115">Usar las plantillas de equipo en el Centro de administración</span><span class="sxs-lookup"><span data-stu-id="6d13b-115">Use the team templates in the admin center</span></span>

<span data-ttu-id="6d13b-116">Microsoft Teams administradores pueden usar el Teams de administración para crear equipos con las plantillas de equipo.</span><span class="sxs-lookup"><span data-stu-id="6d13b-116">Microsoft Teams admins can use the Teams admin center to create teams with the team templates.</span></span> <span data-ttu-id="6d13b-117">Actualmente ofrecemos dos plantillas propias para la atención sanitaria que puede usar en varias situaciones.</span><span class="sxs-lookup"><span data-stu-id="6d13b-117">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="6d13b-118">Para obtener más información sobre las plantillas de equipo en general, vea Introducción a las plantillas [de equipo en el Centro de administración.](../../get-started-with-teams-templates-in-the-admin-console.md)</span><span class="sxs-lookup"><span data-stu-id="6d13b-118">To learn more about team templates in general, see [Get started with team templates in the admin center](../../get-started-with-teams-templates-in-the-admin-console.md).</span></span>

### <a name="collaborate-on-patient-care"></a><span data-ttu-id="6d13b-119">Colaborar en la atención al paciente</span><span class="sxs-lookup"><span data-stu-id="6d13b-119">Collaborate on patient care</span></span>

 <span data-ttu-id="6d13b-120">Simplifique la comunicación y la colaboración sanitaria en una sala, dispensario o departamento.</span><span class="sxs-lookup"><span data-stu-id="6d13b-120">Streamline healthcare communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="6d13b-121">La plantilla puede usarse para facilitar la gestión de los pacientes y las necesidades operativas de una sala.</span><span class="sxs-lookup"><span data-stu-id="6d13b-121">The template can be used to facilitate patient management and operational needs of a ward.</span></span>

| <span data-ttu-id="6d13b-122">Tipo de plantilla base</span><span class="sxs-lookup"><span data-stu-id="6d13b-122">Base template type</span></span> |<span data-ttu-id="6d13b-123">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="6d13b-123">baseTemplateId</span></span>| <span data-ttu-id="6d13b-124">Propiedades que vienen con esta plantilla base</span><span class="sxs-lookup"><span data-stu-id="6d13b-124">Properties that come with this base template</span></span> |
| ------------------ |---|----------------------------------------------------- |
| <span data-ttu-id="6d13b-125">Colaborar en la atención al paciente</span><span class="sxs-lookup"><span data-stu-id="6d13b-125">Collaborate on patient care</span></span> |`healthcareWard` | <span data-ttu-id="6d13b-126">Canales:</span><span class="sxs-lookup"><span data-stu-id="6d13b-126">Channels:</span></span><ul><li><span data-ttu-id="6d13b-127">General</span><span class="sxs-lookup"><span data-stu-id="6d13b-127">General</span></span></li><li><span data-ttu-id="6d13b-128">Anuncios</span><span class="sxs-lookup"><span data-stu-id="6d13b-128">Announcements</span></span></li><li><span data-ttu-id="6d13b-129">Reuniones</span><span class="sxs-lookup"><span data-stu-id="6d13b-129">Huddles</span></span></li><li><span data-ttu-id="6d13b-130">Rondas</span><span class="sxs-lookup"><span data-stu-id="6d13b-130">Rounds</span></span></li><li><span data-ttu-id="6d13b-131">Personal</span><span class="sxs-lookup"><span data-stu-id="6d13b-131">Staffing</span></span></li><li><span data-ttu-id="6d13b-132">Aprendizaje</span><span class="sxs-lookup"><span data-stu-id="6d13b-132">Training</span></span></li></ul> <span data-ttu-id="6d13b-133">Aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="6d13b-133">Apps:</span></span> <ul><li><span data-ttu-id="6d13b-134">Wiki</span><span class="sxs-lookup"><span data-stu-id="6d13b-134">Wiki</span></span></li><li><span data-ttu-id="6d13b-135">Listas</span><span class="sxs-lookup"><span data-stu-id="6d13b-135">Lists</span></span></li></ul>|
||||

### <a name="hospital"></a><span data-ttu-id="6d13b-136">Hospital</span><span class="sxs-lookup"><span data-stu-id="6d13b-136">Hospital</span></span>

<span data-ttu-id="6d13b-137">Simplifique la comunicación y la colaboración entre varias salas, dispensario y departamentos dentro de un hospital.</span><span class="sxs-lookup"><span data-stu-id="6d13b-137">Streamline communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="6d13b-138">Esta plantilla incluye un conjunto de canales base para operaciones en los hospitales y puede ampliarse para incluir especialidades, según necesario.</span><span class="sxs-lookup"><span data-stu-id="6d13b-138">This template includes a set of base channels for hospital operations, and can be self-extended to include specialties, ad-hoc.</span></span>

| <span data-ttu-id="6d13b-139">Tipo de plantilla base</span><span class="sxs-lookup"><span data-stu-id="6d13b-139">Base template type</span></span> |<span data-ttu-id="6d13b-140">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="6d13b-140">baseTemplateId</span></span> | <span data-ttu-id="6d13b-141">Propiedades que vienen con esta plantilla base</span><span class="sxs-lookup"><span data-stu-id="6d13b-141">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="6d13b-142">Hospital</span><span class="sxs-lookup"><span data-stu-id="6d13b-142">Hospital</span></span>|`healthcareHospital`|<span data-ttu-id="6d13b-143">Canales:</span><span class="sxs-lookup"><span data-stu-id="6d13b-143">Channels:</span></span> <ul><li><span data-ttu-id="6d13b-144">General</span><span class="sxs-lookup"><span data-stu-id="6d13b-144">General</span></span></li><li><span data-ttu-id="6d13b-145">Anuncios</span><span class="sxs-lookup"><span data-stu-id="6d13b-145">Announcements</span></span></li><li><span data-ttu-id="6d13b-146">Cumplimiento</span><span class="sxs-lookup"><span data-stu-id="6d13b-146">Compliance</span></span></li><li><span data-ttu-id="6d13b-147">Custodia</span><span class="sxs-lookup"><span data-stu-id="6d13b-147">Custodial</span></span></li><li><span data-ttu-id="6d13b-148">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="6d13b-148">Human resources</span></span></li><li><span data-ttu-id="6d13b-149">Farmacia</span><span class="sxs-lookup"><span data-stu-id="6d13b-149">Pharmacy</span></span></li></ul> <span data-ttu-id="6d13b-150">Aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="6d13b-150">Apps:</span></span> <ul><li><span data-ttu-id="6d13b-151">Wiki</span><span class="sxs-lookup"><span data-stu-id="6d13b-151">Wiki</span></span></li><li><span data-ttu-id="6d13b-152">Listas</span><span class="sxs-lookup"><span data-stu-id="6d13b-152">Lists</span></span> </li></ul>|
||||


## <a name="use-the-team-templates-with-the-microsoft-graph"></a><span data-ttu-id="6d13b-153">Use las plantillas de equipo con microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="6d13b-153">Use the team templates with the Microsoft Graph</span></span>

<span data-ttu-id="6d13b-154">Los desarrolladores pueden usar el Graph Microsoft para crear equipos con las plantillas de equipo.</span><span class="sxs-lookup"><span data-stu-id="6d13b-154">Developers can use the Microsoft Graph to create teams with the team templates.</span></span> <span data-ttu-id="6d13b-155">Actualmente ofrecemos dos plantillas propias para la atención sanitaria que puede usar en varias situaciones.</span><span class="sxs-lookup"><span data-stu-id="6d13b-155">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="6d13b-156">Para obtener más información sobre las plantillas de equipo en general, vea Introducción [a las plantillas de equipo.](../../get-started-with-teams-templates.md)</span><span class="sxs-lookup"><span data-stu-id="6d13b-156">To learn more about team templates in general, see [Get started with team templates](../../get-started-with-teams-templates.md).</span></span> <span data-ttu-id="6d13b-157">Y para obtener información acerca de las plantillas de equipo y Graph microsoft, vea información general Microsoft Teams [API](/graph/teams-concept-overview?view=graph-rest-1.0) y [teamsTemplate tipo de recurso.](/graph/api/resources/teamstemplate?view=graph-rest-1.0)</span><span class="sxs-lookup"><span data-stu-id="6d13b-157">And for information about team templates and the Microsoft Graph, see [Microsoft Teams API overview](/graph/teams-concept-overview?view=graph-rest-1.0) and [teamsTemplate resource type](/graph/api/resources/teamstemplate?view=graph-rest-1.0).</span></span>

### <a name="ward-template"></a><span data-ttu-id="6d13b-158">Plantilla de sala</span><span class="sxs-lookup"><span data-stu-id="6d13b-158">Ward template</span></span>

<span data-ttu-id="6d13b-159">La plantilla de sala está pensada para la comunicación y la colaboración dentro de una sala, dispensario o departamento.</span><span class="sxs-lookup"><span data-stu-id="6d13b-159">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="6d13b-160">La plantilla puede usarse para facilitar la gestión de los pacientes, así como las necesidades operativas de una sala.</span><span class="sxs-lookup"><span data-stu-id="6d13b-160">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="6d13b-161">Por ejemplo, los anuncios de salas pueden publicarse en el canal *Anuncios* y los turnos pueden publicarse en el canal *Personal*.</span><span class="sxs-lookup"><span data-stu-id="6d13b-161">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="6d13b-162">Si quiere simplificar sus operaciones de sala, esta plantilla es la adecuada.</span><span class="sxs-lookup"><span data-stu-id="6d13b-162">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="6d13b-163">Tipo de plantilla base</span><span class="sxs-lookup"><span data-stu-id="6d13b-163">Base Template Type</span></span> |<span data-ttu-id="6d13b-164">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="6d13b-164">baseTemplateId</span></span> |<span data-ttu-id="6d13b-165">Canales de plantilla de línea base</span><span class="sxs-lookup"><span data-stu-id="6d13b-165">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="6d13b-166">Atención sanitaria: sala</span><span class="sxs-lookup"><span data-stu-id="6d13b-166">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="6d13b-167">Anuncios\*</span><span class="sxs-lookup"><span data-stu-id="6d13b-167">Announcements\*</span></span> <br> <span data-ttu-id="6d13b-168">Reuniones\*</span><span class="sxs-lookup"><span data-stu-id="6d13b-168">Huddles\*</span></span> <br> <span data-ttu-id="6d13b-169">Rondas\*</span><span class="sxs-lookup"><span data-stu-id="6d13b-169">Rounds\*</span></span> <br> <span data-ttu-id="6d13b-170">Personal\*</span><span class="sxs-lookup"><span data-stu-id="6d13b-170">Staffing\*</span></span> <br> <span data-ttu-id="6d13b-171">Aprendizaje\*</span><span class="sxs-lookup"><span data-stu-id="6d13b-171">Training\*</span></span> |
|     | |         |

<span data-ttu-id="6d13b-172">\* Marcado automáticamente como favorito</span><span class="sxs-lookup"><span data-stu-id="6d13b-172">\* Auto-favorited</span></span>

### <a name="hospital-template"></a><span data-ttu-id="6d13b-173">Plantilla de hospital</span><span class="sxs-lookup"><span data-stu-id="6d13b-173">Hospital template</span></span>

<span data-ttu-id="6d13b-174">La plantilla de hospital está pensada para la comunicación y la colaboración entre varias salas, dispensarios y departamentos dentro un hospital.</span><span class="sxs-lookup"><span data-stu-id="6d13b-174">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="6d13b-175">En esta plantilla se incluyen varios canales operativos, como *Anuncios*, *Custodia* y *Farmacia*, pero también le proporcionamos un script a continuación que amplía la plantilla con departamentos adicionales o canales de especialidades que puede agregar, eliminar o editar a su gusto.</span><span class="sxs-lookup"><span data-stu-id="6d13b-175">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="6d13b-176">Por ejemplo, si tiene un departamento de *Endocrinología*, pero no necesita un canal para *Oftalmología*, el script puede adaptarse para incluir un canal de *Endocrinología* y quitar el canal de *Oftalmología*.</span><span class="sxs-lookup"><span data-stu-id="6d13b-176">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="6d13b-177">Para evitar la saturación de notificaciones, recomendamos que estos canales de especialidades o basados en salas no se marquen como favoritos automáticamente.</span><span class="sxs-lookup"><span data-stu-id="6d13b-177">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="6d13b-178">Los usuarios suelen marcar como favoritos los canales que encuentran relevantes.</span><span class="sxs-lookup"><span data-stu-id="6d13b-178">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="6d13b-179">Tipo de plantilla base</span><span class="sxs-lookup"><span data-stu-id="6d13b-179">Base Template Type</span></span> |<span data-ttu-id="6d13b-180">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="6d13b-180">baseTemplateId</span></span> |<span data-ttu-id="6d13b-181">Canales de plantilla de línea base</span><span class="sxs-lookup"><span data-stu-id="6d13b-181">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="6d13b-182">atención sanitaria: hospital</span><span class="sxs-lookup"><span data-stu-id="6d13b-182">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="6d13b-183">Anuncios\*</span><span class="sxs-lookup"><span data-stu-id="6d13b-183">Announcements\*</span></span> <br> <span data-ttu-id="6d13b-184">Cumplimiento\*</span><span class="sxs-lookup"><span data-stu-id="6d13b-184">Compliance\*</span></span> <br> <span data-ttu-id="6d13b-185">Custodia</span><span class="sxs-lookup"><span data-stu-id="6d13b-185">Custodial</span></span> <br> <span data-ttu-id="6d13b-186">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="6d13b-186">Human Resources</span></span> <br> <span data-ttu-id="6d13b-187">Farmacia</span><span class="sxs-lookup"><span data-stu-id="6d13b-187">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="6d13b-188">\* Marcado automáticamente como favorito</span><span class="sxs-lookup"><span data-stu-id="6d13b-188">\* Auto-favorited</span></span> 

### <a name="how-to-use-first-party-templates"></a><span data-ttu-id="6d13b-189">Cómo usar plantillas de terceros</span><span class="sxs-lookup"><span data-stu-id="6d13b-189">How to use first-party templates</span></span>

<span data-ttu-id="6d13b-190">Para usar estas plantillas, simplemente cambie la propiedad "template@odata.bind" en el cuerpo de la solicitud de "estándar" a los TemplateID anteriores.</span><span class="sxs-lookup"><span data-stu-id="6d13b-190">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="6d13b-191">Para obtener más información sobre cómo implementar plantillas de equipo, vea el artículo de Microsoft Graph sobre cómo [crear un equipo.](/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="6d13b-191">For more information on how to deploy team templates, see the Microsoft Graph article on how to [create a Team](/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="6d13b-192">Los canales de la plantilla se crearán automáticamente en la pestaña General.</span><span class="sxs-lookup"><span data-stu-id="6d13b-192">The channels in the template will automatically be created under the General Tab.</span></span>

#### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="6d13b-193">Ejemplo: script de extensión de plantilla de hospital</span><span class="sxs-lookup"><span data-stu-id="6d13b-193">Example: Hospital template extension script</span></span>

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

### <a name="related-topics"></a><span data-ttu-id="6d13b-194">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="6d13b-194">Related topics</span></span>

[<span data-ttu-id="6d13b-195">Introducción a las plantillas de equipo</span><span class="sxs-lookup"><span data-stu-id="6d13b-195">Get started with team templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="6d13b-196">Introducción al equipo de organizaciones sanitarias</span><span class="sxs-lookup"><span data-stu-id="6d13b-196">Get started with team for Healthcare organizations</span></span>](teams-in-hc.md)