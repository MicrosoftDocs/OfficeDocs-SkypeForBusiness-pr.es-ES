---
title: Crear un equipo con las plantillas sanitarias de Teams
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
description: Use plantillas de Microsoft Teams en el centro de administración o con Microsoft Graph para crear equipos de forma rápida y sencilla proporcionando una plantilla predefinida de configuración, canales y aplicaciones.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b45c949b70aa2a299f2aafe54d81cdd8a1a6c0b5
ms.sourcegitcommit: 774c2fdc71df430674493c33b609523af3cbda4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/16/2021
ms.locfileid: "50260312"
---
# <a name="create-a-team-using-teams-healthcare-templates"></a><span data-ttu-id="32899-103">Crear un equipo con las plantillas sanitarias de Teams</span><span class="sxs-lookup"><span data-stu-id="32899-103">Create a team using Teams healthcare templates</span></span>

<span data-ttu-id="32899-104">Las plantillas de Microsoft Teams le permiten crear equipos de forma rápida y sencilla proporcionando una plantilla predefinida de configuración, canales y aplicaciones preinstaladas.</span><span class="sxs-lookup"><span data-stu-id="32899-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="32899-105">Para las organizaciones sanitarias, las plantillas pueden ser especialmente eficaces, ya que proporcionan una estructura para que los usuarios se orienten sobre cómo usar Teams de manera eficaz.</span><span class="sxs-lookup"><span data-stu-id="32899-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams.</span></span> <span data-ttu-id="32899-106">Las plantillas también permiten a los administradores implementar equipos coherentes en todas sus organizaciones.</span><span class="sxs-lookup"><span data-stu-id="32899-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="32899-107">Este artículo es para usted si es responsable de planear, implementar y administrar varios equipos en toda la organización sanitaria.</span><span class="sxs-lookup"><span data-stu-id="32899-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="32899-108">Elija un método para crear equipos con las plantillas sanitarias de Teams:</span><span class="sxs-lookup"><span data-stu-id="32899-108">Choose a method for creating teams with the Teams healthcare templates:</span></span>

| <span data-ttu-id="32899-109">Quién</span><span class="sxs-lookup"><span data-stu-id="32899-109">Who</span></span> | <span data-ttu-id="32899-110">Método para usar:</span><span class="sxs-lookup"><span data-stu-id="32899-110">Method to use:</span></span> |
| ---- | --------- |
| <span data-ttu-id="32899-111">Administradores y profesionales de TI</span><span class="sxs-lookup"><span data-stu-id="32899-111">Admins and IT Professionals</span></span> | <span data-ttu-id="32899-112">[Use el centro de administración de Teams](#use-the-teams-templates-in-the-teams-admin-center) para crear equipos basados en las plantillas de Teams para la salud.</span><span class="sxs-lookup"><span data-stu-id="32899-112">[Use the Teams admin center](#use-the-teams-templates-in-the-teams-admin-center) to create teams based on the healthcare Teams templates.</span></span>|
| <span data-ttu-id="32899-113">Desarrolladores e integradores de sistemas</span><span class="sxs-lookup"><span data-stu-id="32899-113">Developers and systems integrators</span></span> | <span data-ttu-id="32899-114">[Use Microsoft Graph para crear](#use-the-teams-templates-with-the-microsoft-graph) equipos basados en las plantillas de Teams para el ámbito sanitario.</span><span class="sxs-lookup"><span data-stu-id="32899-114">[Use the Microsoft Graph](#use-the-teams-templates-with-the-microsoft-graph) to create teams based on the healthcare Teams templates.</span></span> |

## <a name="use-the-teams-templates-in-the-teams-admin-center"></a><span data-ttu-id="32899-115">Usar las plantillas de Teams en el Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="32899-115">Use the Teams templates in the Teams admin center</span></span>

<span data-ttu-id="32899-116">Los administradores de Microsoft Teams pueden usar el Centro de administración de Teams para crear equipos con las plantillas de Teams.</span><span class="sxs-lookup"><span data-stu-id="32899-116">Microsoft Teams admins can use the Teams admin center to create teams with the Teams templates.</span></span> <span data-ttu-id="32899-117">Actualmente, ofrecemos dos plantillas sanitarias de terceros que puede usar para una variedad de situaciones.</span><span class="sxs-lookup"><span data-stu-id="32899-117">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="32899-118">Para obtener más información general sobre las plantillas de equipo, vea Introducción a [las plantillas de Teams en el Centro de administración.](../../get-started-with-teams-templates-in-the-admin-console.md)</span><span class="sxs-lookup"><span data-stu-id="32899-118">To learn more about team templates in general, see [Get started with Teams templates in the admin center](../../get-started-with-teams-templates-in-the-admin-console.md).</span></span>

### <a name="collaborate-on-patient-care"></a><span data-ttu-id="32899-119">Colaborar en la atención al paciente</span><span class="sxs-lookup"><span data-stu-id="32899-119">Collaborate on patient care</span></span>

 <span data-ttu-id="32899-120">Simplifiice la comunicación y la colaboración sanitaria en un departamento, una podio o un departamento.</span><span class="sxs-lookup"><span data-stu-id="32899-120">Streamline healthcare communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="32899-121">La plantilla se puede usar para facilitar la administración del paciente y las necesidades operativas de un centro de atención.</span><span class="sxs-lookup"><span data-stu-id="32899-121">The template can be used to facilitate patient management and operational needs of a ward.</span></span>

| <span data-ttu-id="32899-122">Tipo de plantilla base</span><span class="sxs-lookup"><span data-stu-id="32899-122">Base template type</span></span> |<span data-ttu-id="32899-123">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="32899-123">baseTemplateId</span></span>| <span data-ttu-id="32899-124">Propiedades que vienen con esta plantilla base</span><span class="sxs-lookup"><span data-stu-id="32899-124">Properties that come with this base template</span></span> |
| ------------------ |---|----------------------------------------------------- |
| <span data-ttu-id="32899-125">Colaborar en la atención al paciente</span><span class="sxs-lookup"><span data-stu-id="32899-125">Collaborate on patient care</span></span> |`healthcareWard` | <span data-ttu-id="32899-126">Canales:</span><span class="sxs-lookup"><span data-stu-id="32899-126">Channels:</span></span><ul><li><span data-ttu-id="32899-127">General</span><span class="sxs-lookup"><span data-stu-id="32899-127">General</span></span></li><li><span data-ttu-id="32899-128">Anuncios</span><span class="sxs-lookup"><span data-stu-id="32899-128">Announcements</span></span></li><li><span data-ttu-id="32899-129">Garabatos</span><span class="sxs-lookup"><span data-stu-id="32899-129">Huddles</span></span></li><li><span data-ttu-id="32899-130">Redondear</span><span class="sxs-lookup"><span data-stu-id="32899-130">Rounds</span></span></li><li><span data-ttu-id="32899-131">Empleados</span><span class="sxs-lookup"><span data-stu-id="32899-131">Staffing</span></span></li><li><span data-ttu-id="32899-132">Aprendizaje</span><span class="sxs-lookup"><span data-stu-id="32899-132">Training</span></span></li></ul> <span data-ttu-id="32899-133">Aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="32899-133">Apps:</span></span> <ul><li><span data-ttu-id="32899-134">Wiki</span><span class="sxs-lookup"><span data-stu-id="32899-134">Wiki</span></span></li><li><span data-ttu-id="32899-135">Listas</span><span class="sxs-lookup"><span data-stu-id="32899-135">Lists</span></span></li></ul>|
||||

### <a name="hospital"></a><span data-ttu-id="32899-136">Hospital</span><span class="sxs-lookup"><span data-stu-id="32899-136">Hospital</span></span>

<span data-ttu-id="32899-137">Simplifiice la comunicación y la colaboración entre varios centros de investigación, podios y departamentos dentro de un hospital.</span><span class="sxs-lookup"><span data-stu-id="32899-137">Streamline communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="32899-138">Esta plantilla incluye un conjunto de canales base para operaciones hospitalarias y se puede ampliar para incluir especiales, ad hoc.</span><span class="sxs-lookup"><span data-stu-id="32899-138">This template includes a set of base channels for hospital operations, and can be self-extended to include specialties, ad-hoc.</span></span>

| <span data-ttu-id="32899-139">Tipo de plantilla base</span><span class="sxs-lookup"><span data-stu-id="32899-139">Base template type</span></span> |<span data-ttu-id="32899-140">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="32899-140">baseTemplateId</span></span> | <span data-ttu-id="32899-141">Propiedades que vienen con esta plantilla base</span><span class="sxs-lookup"><span data-stu-id="32899-141">Properties that come with this base template</span></span> |
| ------------------|-- |----------------------------------------------------- |
|<span data-ttu-id="32899-142">Hospital</span><span class="sxs-lookup"><span data-stu-id="32899-142">Hospital</span></span>|`healthcareHospital`|<span data-ttu-id="32899-143">Canales:</span><span class="sxs-lookup"><span data-stu-id="32899-143">Channels:</span></span> <ul><li><span data-ttu-id="32899-144">General</span><span class="sxs-lookup"><span data-stu-id="32899-144">General</span></span></li><li><span data-ttu-id="32899-145">Anuncios</span><span class="sxs-lookup"><span data-stu-id="32899-145">Announcements</span></span></li><li><span data-ttu-id="32899-146">Cumplimiento</span><span class="sxs-lookup"><span data-stu-id="32899-146">Compliance</span></span></li><li><span data-ttu-id="32899-147">Descúyal</span><span class="sxs-lookup"><span data-stu-id="32899-147">Custodial</span></span></li><li><span data-ttu-id="32899-148">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="32899-148">Human resources</span></span></li><li><span data-ttu-id="32899-149">Clínica</span><span class="sxs-lookup"><span data-stu-id="32899-149">Pharmacy</span></span></li></ul> <span data-ttu-id="32899-150">Aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="32899-150">Apps:</span></span> <ul><li><span data-ttu-id="32899-151">Wiki</span><span class="sxs-lookup"><span data-stu-id="32899-151">Wiki</span></span></li><li><span data-ttu-id="32899-152">Listas</span><span class="sxs-lookup"><span data-stu-id="32899-152">Lists</span></span> </li></ul>|
||||


## <a name="use-the-teams-templates-with-the-microsoft-graph"></a><span data-ttu-id="32899-153">Usar las plantillas de Teams con Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="32899-153">Use the Teams templates with the Microsoft Graph</span></span>

<span data-ttu-id="32899-154">Los desarrolladores pueden usar Microsoft Graph para crear equipos con las plantillas de Teams.</span><span class="sxs-lookup"><span data-stu-id="32899-154">Developers can use the Microsoft Graph to create teams with the Teams templates.</span></span> <span data-ttu-id="32899-155">Actualmente, ofrecemos dos plantillas sanitarias de terceros que puede usar para una variedad de situaciones.</span><span class="sxs-lookup"><span data-stu-id="32899-155">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="32899-156">Para obtener más información sobre las plantillas de equipo en general, vea [Introducción a las plantillas de Teams.](../../get-started-with-teams-templates.md)</span><span class="sxs-lookup"><span data-stu-id="32899-156">To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span> <span data-ttu-id="32899-157">Además, para obtener información sobre las plantillas de Teams y Microsoft Graph, vea información general sobre [la API](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0) de Microsoft Teams y [teamsTemplate tipo de recurso.](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0)</span><span class="sxs-lookup"><span data-stu-id="32899-157">And for information about Teams templates and the Microsoft Graph, see [Microsoft Teams API overview](https://docs.microsoft.com/graph/teams-concept-overview?view=graph-rest-1.0) and [teamsTemplate resource type](https://docs.microsoft.com/graph/api/resources/teamstemplate?view=graph-rest-1.0).</span></span>

### <a name="ward-template"></a><span data-ttu-id="32899-158">Plantilla de resalte</span><span class="sxs-lookup"><span data-stu-id="32899-158">Ward template</span></span>

<span data-ttu-id="32899-159">La plantilla del centro está pensada para la comunicación y la colaboración dentro de un departamento, una vaina o un departamento.</span><span class="sxs-lookup"><span data-stu-id="32899-159">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="32899-160">La plantilla se puede usar para facilitar la administración del paciente, así como las necesidades operativas de un centro de atención.</span><span class="sxs-lookup"><span data-stu-id="32899-160">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="32899-161">Por ejemplo, los anuncios del canal Anuncios se pueden publicar en el canal *Anuncios* y los turnos se pueden administrar en *Personal.*</span><span class="sxs-lookup"><span data-stu-id="32899-161">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing*.</span></span> <span data-ttu-id="32899-162">Si quiere simplificar las operaciones de sala, esta plantilla es la adecuada para usted.</span><span class="sxs-lookup"><span data-stu-id="32899-162">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="32899-163">Tipo de plantilla base</span><span class="sxs-lookup"><span data-stu-id="32899-163">Base Template Type</span></span> |<span data-ttu-id="32899-164">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="32899-164">baseTemplateId</span></span> |<span data-ttu-id="32899-165">Canales de plantilla de línea base</span><span class="sxs-lookup"><span data-stu-id="32899-165">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="32899-166">Salud - Centro de salud</span><span class="sxs-lookup"><span data-stu-id="32899-166">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="32899-167">Anuncios\*</span><span class="sxs-lookup"><span data-stu-id="32899-167">Announcements\*</span></span> <br> <span data-ttu-id="32899-168">Garabatos\*</span><span class="sxs-lookup"><span data-stu-id="32899-168">Huddles\*</span></span> <br> <span data-ttu-id="32899-169">Redondear\*</span><span class="sxs-lookup"><span data-stu-id="32899-169">Rounds\*</span></span> <br> <span data-ttu-id="32899-170">Empleados\*</span><span class="sxs-lookup"><span data-stu-id="32899-170">Staffing\*</span></span> <br> <span data-ttu-id="32899-171">Aprendizaje\*</span><span class="sxs-lookup"><span data-stu-id="32899-171">Training\*</span></span> |
|     | |         |

<span data-ttu-id="32899-172">\* Favorito automático</span><span class="sxs-lookup"><span data-stu-id="32899-172">\* Auto-favorited</span></span>

### <a name="hospital-template"></a><span data-ttu-id="32899-173">Plantilla hospital</span><span class="sxs-lookup"><span data-stu-id="32899-173">Hospital template</span></span>

<span data-ttu-id="32899-174">La plantilla hospitalaria está pensada para la comunicación y colaboración entre varios centros hospitalarios, podios y departamentos.</span><span class="sxs-lookup"><span data-stu-id="32899-174">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="32899-175">Esta plantilla incluye varios canales de operaciones, entre los que se incluyen *Anuncios,* *Limpiezal* y *Química,* pero a continuación le proporcionamos un script que amplía la plantilla con una variedad de canales adicionales centrados en el departamento o centrados en la atención que puede agregar, eliminar o editar a su gusto.</span><span class="sxs-lookup"><span data-stu-id="32899-175">Included in this template are several operational channels including *Announcements*, *Custodial*, and *Pharmacy*, but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="32899-176">Por ejemplo, si tiene un departamento de endocrinology, pero no necesita un canal para *la ophology,* el script puede adaptarse para incluir un canal de *endocrinology* y eliminar el canal de *Ophphology.* </span><span class="sxs-lookup"><span data-stu-id="32899-176">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology*, then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="32899-177">Se recomienda que estos canales especiales o modelo de canal no se agregó como favoritos automáticamente para evitar la saturación de notificaciones.</span><span class="sxs-lookup"><span data-stu-id="32899-177">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="32899-178">Por lo general, los usuarios son favoritos de los canales que les sean relevantes.</span><span class="sxs-lookup"><span data-stu-id="32899-178">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="32899-179">Tipo de plantilla base</span><span class="sxs-lookup"><span data-stu-id="32899-179">Base Template Type</span></span> |<span data-ttu-id="32899-180">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="32899-180">baseTemplateId</span></span> |<span data-ttu-id="32899-181">Canales de plantilla de línea base</span><span class="sxs-lookup"><span data-stu-id="32899-181">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="32899-182">Salud - Hospital</span><span class="sxs-lookup"><span data-stu-id="32899-182">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="32899-183">Anuncios\*</span><span class="sxs-lookup"><span data-stu-id="32899-183">Announcements\*</span></span> <br> <span data-ttu-id="32899-184">Cumplimiento\*</span><span class="sxs-lookup"><span data-stu-id="32899-184">Compliance\*</span></span> <br> <span data-ttu-id="32899-185">Descúyal</span><span class="sxs-lookup"><span data-stu-id="32899-185">Custodial</span></span> <br> <span data-ttu-id="32899-186">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="32899-186">Human Resources</span></span> <br> <span data-ttu-id="32899-187">Clínica</span><span class="sxs-lookup"><span data-stu-id="32899-187">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="32899-188">\* Favorito automático</span><span class="sxs-lookup"><span data-stu-id="32899-188">\* Auto-favorited</span></span> 

### <a name="how-to-use-first-party-templates"></a><span data-ttu-id="32899-189">Cómo usar plantillas de terceros</span><span class="sxs-lookup"><span data-stu-id="32899-189">How to use first-party templates</span></span>

<span data-ttu-id="32899-190">Para usar estas plantillas, simplemente cambie la propiedad "template@odata.bind" en el cuerpo de la solicitud de "estándar" a los templateIDs anteriores.</span><span class="sxs-lookup"><span data-stu-id="32899-190">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="32899-191">Para obtener más información sobre cómo implementar plantillas de Teams, vea el artículo de Microsoft Graph sobre cómo [crear un equipo.](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta)</span><span class="sxs-lookup"><span data-stu-id="32899-191">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="32899-192">Los canales de la plantilla se crearán automáticamente en la pestaña General.</span><span class="sxs-lookup"><span data-stu-id="32899-192">The channels in the template will automatically be created under the General Tab.</span></span>

#### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="32899-193">Ejemplo: Script de extensión de plantilla hospitalaria</span><span class="sxs-lookup"><span data-stu-id="32899-193">Example: Hospital template extension script</span></span>

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

### <a name="related-topics"></a><span data-ttu-id="32899-194">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="32899-194">Related topics</span></span>

[<span data-ttu-id="32899-195">Introducción a las plantillas de Teams</span><span class="sxs-lookup"><span data-stu-id="32899-195">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="32899-196">Introducción a Teams para organizaciones sanitarias</span><span class="sxs-lookup"><span data-stu-id="32899-196">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)
