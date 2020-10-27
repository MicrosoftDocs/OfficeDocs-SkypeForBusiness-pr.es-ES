---
title: Plantillas para organizaciones de salud
author: serdarsoysal
ms.author: serdars
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Use las plantillas de Microsoft Teams con Microsoft Graph para crear equipos de forma rápida y sencilla proporcionando una plantilla predefinida de configuración, canales y aplicaciones.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 63376c68d8267aaa49b4bdf4033d5ebfaa0a446f
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766703"
---
# <a name="get-started-with-teams-templates-for-healthcare-organizations"></a><span data-ttu-id="8987d-103">Introducción a las plantillas de Teams para organizaciones de sanidad</span><span class="sxs-lookup"><span data-stu-id="8987d-103">Get started with Teams templates for healthcare organizations</span></span>

<span data-ttu-id="8987d-104">Las plantillas de Microsoft Teams le permiten crear equipos de forma rápida y sencilla proporcionando una plantilla predefinida de configuración, canales y aplicaciones preinstaladas.</span><span class="sxs-lookup"><span data-stu-id="8987d-104">Microsoft Teams templates allow you to quickly and easily create teams by providing a predefined template of settings, channels, and pre-installed apps.</span></span>

<span data-ttu-id="8987d-105">Para las organizaciones de salud, las plantillas pueden ser especialmente eficaces, puesto que proporcionan una estructura para que los usuarios se orienten con el uso eficaz de Teams.</span><span class="sxs-lookup"><span data-stu-id="8987d-105">For healthcare organizations, templates can be especially powerful, as they provide structure for users to become oriented with how to effectively use Teams.</span></span> <span data-ttu-id="8987d-106">Las plantillas también permiten a los administradores implementar equipos coherentes en sus organizaciones.</span><span class="sxs-lookup"><span data-stu-id="8987d-106">Templates also allow administrators to deploy consistent teams across their organizations.</span></span> <span data-ttu-id="8987d-107">Este artículo le interesa si es responsable de planear, implementar y administrar varios equipos en la organización de la salud.</span><span class="sxs-lookup"><span data-stu-id="8987d-107">This article is for you if you're responsible for planning, deploying, and managing multiple teams across your healthcare organization.</span></span>

<span data-ttu-id="8987d-108">Actualmente ofrecemos dos plantillas de atención médica de origen que puede usar para una gran variedad de situaciones.</span><span class="sxs-lookup"><span data-stu-id="8987d-108">We currently offer two first-party healthcare templates that you can use for a variety of situations.</span></span> <span data-ttu-id="8987d-109">Para obtener más información sobre las plantillas de equipo en general, consulte [Introducción a las plantillas](../../get-started-with-teams-templates.md)de Teams.</span><span class="sxs-lookup"><span data-stu-id="8987d-109">To learn more about team templates in general, see [Get started with Teams templates](../../get-started-with-teams-templates.md).</span></span>

## <a name="ward-template"></a><span data-ttu-id="8987d-110">Plantilla en adelante</span><span class="sxs-lookup"><span data-stu-id="8987d-110">Ward template</span></span>

<span data-ttu-id="8987d-111">La plantilla en adelante está pensada para la comunicación y la colaboración dentro de un interior, un conjunto Pod o un departamento.</span><span class="sxs-lookup"><span data-stu-id="8987d-111">The ward template is meant for communication and collaboration within a ward, pod, or department.</span></span> <span data-ttu-id="8987d-112">La plantilla se puede usar para facilitar la administración de pacientes, así como las necesidades operacionales de un mismo.</span><span class="sxs-lookup"><span data-stu-id="8987d-112">The template can be used to facilitate patient management, as well as the operational needs of a ward.</span></span> <span data-ttu-id="8987d-113">Por ejemplo, los anuncios en adelante se pueden publicar en el canal de *anuncios* y los turnos se pueden administrar en el *personal* .</span><span class="sxs-lookup"><span data-stu-id="8987d-113">For example, ward announcements can be posted in the *Announcements* channel and shifts can be managed in *Staffing* .</span></span> <span data-ttu-id="8987d-114">Si está buscando simplificar sus operaciones en el exterior, esta plantilla es para usted.</span><span class="sxs-lookup"><span data-stu-id="8987d-114">If you're looking to streamline your ward operations, then this template is for you.</span></span>

|<span data-ttu-id="8987d-115">Tipo de plantilla base</span><span class="sxs-lookup"><span data-stu-id="8987d-115">Base Template Type</span></span> |<span data-ttu-id="8987d-116">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="8987d-116">baseTemplateId</span></span> |<span data-ttu-id="8987d-117">Canales de plantillas de línea base</span><span class="sxs-lookup"><span data-stu-id="8987d-117">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="8987d-118">Atención médica en adelante</span><span class="sxs-lookup"><span data-stu-id="8987d-118">Healthcare - Ward</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareWard')`   | <span data-ttu-id="8987d-119">Anuncios\*</span><span class="sxs-lookup"><span data-stu-id="8987d-119">Announcements\*</span></span> <br> <span data-ttu-id="8987d-120">Huddles\*</span><span class="sxs-lookup"><span data-stu-id="8987d-120">Huddles\*</span></span> <br> <span data-ttu-id="8987d-121">Hacia\*</span><span class="sxs-lookup"><span data-stu-id="8987d-121">Rounds\*</span></span> <br> <span data-ttu-id="8987d-122">Personal\*</span><span class="sxs-lookup"><span data-stu-id="8987d-122">Staffing\*</span></span> <br> <span data-ttu-id="8987d-123">Aprendizaje\*</span><span class="sxs-lookup"><span data-stu-id="8987d-123">Training\*</span></span> |
|     | |         |

<span data-ttu-id="8987d-124">\* Con favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="8987d-124">\* Auto-favorited</span></span>

## <a name="hospital-template"></a><span data-ttu-id="8987d-125">Plantilla de hospital</span><span class="sxs-lookup"><span data-stu-id="8987d-125">Hospital template</span></span>

<span data-ttu-id="8987d-126">La plantilla del hospital está pensada para la comunicación y la colaboración entre varios departamentos, pods y otros departamentos dentro de un hospital.</span><span class="sxs-lookup"><span data-stu-id="8987d-126">The hospital template is meant for communication and collaboration between multiple wards, pods, and departments within a hospital.</span></span> <span data-ttu-id="8987d-127">En esta plantilla se incluyen varios canales operativos, entre los que se incluyen *anuncios* , personalización de la *asistencia* y *farmacia* , pero también ofrecemos una secuencia de comandos a continuación que extiende la plantilla con una variedad de canales adicionales centrados en el servicio o que puede Agregar, eliminar o editar a su gusto.</span><span class="sxs-lookup"><span data-stu-id="8987d-127">Included in this template are several operational channels including *Announcements* , *Custodial* , and *Pharmacy* , but we also provide a script below which extends the template with a variety of additional department or specialty-centric channels that you can add to, delete from, or edit to your liking.</span></span> <span data-ttu-id="8987d-128">Por ejemplo, si tiene un departamento de *Endocrinology* , pero no necesita un canal para *Ophthalmology* , la secuencia de comandos puede adaptarse para incluir un canal de *Endocrinology* y quitar el canal *Ophthalmology* .</span><span class="sxs-lookup"><span data-stu-id="8987d-128">For example, if you have an *Endocrinology* department, but don't need a channel for *Ophthalmology* , then the script can be adapted to include an *Endocrinology* channel and remove the *Ophthalmology* channel.</span></span> <span data-ttu-id="8987d-129">Le recomendamos que estos canales de especialidad o modelos en el exterior no se hayan preferido de forma automática para evitar la saturación de las notificaciones.</span><span class="sxs-lookup"><span data-stu-id="8987d-129">We recommend that these specialty or ward-modeled channels not be auto-favorited to avoid notification saturation.</span></span> <span data-ttu-id="8987d-130">Por lo general, los usuarios tienen los canales que encuentran relevantes.</span><span class="sxs-lookup"><span data-stu-id="8987d-130">Users generally favorite any channels that they find relevant.</span></span>

|<span data-ttu-id="8987d-131">Tipo de plantilla base</span><span class="sxs-lookup"><span data-stu-id="8987d-131">Base Template Type</span></span> |<span data-ttu-id="8987d-132">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="8987d-132">baseTemplateId</span></span> |<span data-ttu-id="8987d-133">Canales de plantillas de línea base</span><span class="sxs-lookup"><span data-stu-id="8987d-133">Baseline Template channels</span></span>|
|:--- |:---|:---|
|<span data-ttu-id="8987d-134">Asistencia sanitaria-Hospital</span><span class="sxs-lookup"><span data-stu-id="8987d-134">Healthcare - Hospital</span></span> | `https://graph.microsoft.com/beta/`<br>`teamsTemplates('healthcareHospital')`   | <span data-ttu-id="8987d-135">Anuncios\*</span><span class="sxs-lookup"><span data-stu-id="8987d-135">Announcements\*</span></span> <br> <span data-ttu-id="8987d-136">Cumplimiento\*</span><span class="sxs-lookup"><span data-stu-id="8987d-136">Compliance\*</span></span> <br> <span data-ttu-id="8987d-137">Private</span><span class="sxs-lookup"><span data-stu-id="8987d-137">Custodial</span></span> <br> <span data-ttu-id="8987d-138">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="8987d-138">Human Resources</span></span> <br> <span data-ttu-id="8987d-139">Pertenecie</span><span class="sxs-lookup"><span data-stu-id="8987d-139">Pharmacy</span></span> |
| | |  |

<span data-ttu-id="8987d-140">\* Con favoritos automáticos</span><span class="sxs-lookup"><span data-stu-id="8987d-140">\* Auto-favorited</span></span> 

## <a name="how-to-use-first-party-templates"></a><span data-ttu-id="8987d-141">Cómo usar las plantillas de origen</span><span class="sxs-lookup"><span data-stu-id="8987d-141">How to use first-party templates</span></span>

<span data-ttu-id="8987d-142">Para usar estas plantillas, simplemente cambie la propiedad ' template@odata. bind ' en el cuerpo de la solicitud de ' Standard ' a la TemplateIDs anterior.</span><span class="sxs-lookup"><span data-stu-id="8987d-142">To use these templates, simply change the 'template@odata.bind' property in the request body from 'standard' to the TemplateIDs above.</span></span>  <span data-ttu-id="8987d-143">Para obtener más información sobre cómo implementar las plantillas de Teams, vea el artículo de Microsoft Graph sobre cómo [crear un equipo](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="8987d-143">For more information on how to deploy Teams templates, see the Microsoft Graph article on how to [create a Team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

> [!NOTE]
> <span data-ttu-id="8987d-144">Los canales de la plantilla se crearán automáticamente en la ficha General.</span><span class="sxs-lookup"><span data-stu-id="8987d-144">The channels in the template will automatically be created under the General Tab.</span></span>

### <a name="example-hospital-template-extension-script"></a><span data-ttu-id="8987d-145">Ejemplo: script de extensión de plantilla de hospital</span><span class="sxs-lookup"><span data-stu-id="8987d-145">Example: Hospital template extension script</span></span>

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

## <a name="related-topics"></a><span data-ttu-id="8987d-146">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="8987d-146">Related topics</span></span>

[<span data-ttu-id="8987d-147">Introducción a las plantillas de Teams</span><span class="sxs-lookup"><span data-stu-id="8987d-147">Get started with Teams templates</span></span>](../../get-started-with-teams-templates.md)

[<span data-ttu-id="8987d-148">Introducción a Teams para organizaciones sanitarias</span><span class="sxs-lookup"><span data-stu-id="8987d-148">Get started with Teams for Healthcare organizations</span></span>](teams-in-hc.md)

[<span data-ttu-id="8987d-149">Introducción a las plantillas de Teams en la consola de administración</span><span class="sxs-lookup"><span data-stu-id="8987d-149">Get started with Teams templates in the admin console</span></span>](../../get-started-with-teams-templates-in-the-admin-console.md)
