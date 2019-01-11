---
title: Introducción a las plantillas de equipos
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 01/10/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: phecda louie
localization_priority: Normal
robots: NOINDEX, NOFOLLOW
search.appverid: MET150
description: Obtenga información sobre cómo usar las plantillas de equipos para crear un equipo con los canales de predefinidos.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: ead0a3dc9e27b90c49808bcece0aab39bf01f13a
ms.sourcegitcommit: 4c5b9e8c4bdb1187d610209d365680702d4372fd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/11/2019
ms.locfileid: "27801467"
---
# <a name="get-started-with-teams-templates"></a><span data-ttu-id="3ce26-103">Introducción a las plantillas de equipos</span><span class="sxs-lookup"><span data-stu-id="3ce26-103">Get started with Teams templates</span></span> 

<span data-ttu-id="3ce26-104">Las plantillas de equipos son predefinidas definiciones de estructura de un equipo diseñado alrededor de un proyecto o necesidad empresarial.</span><span class="sxs-lookup"><span data-stu-id="3ce26-104">Teams templates are pre-built definitions of a team's structure designed around a business need or project.</span></span> <span data-ttu-id="3ce26-105">Puede usar las plantillas de equipos para crear rápidamente los espacios de colaboración con los canales para diferentes temas y preinstalación de aplicaciones que se van a extraer en servicios y contenido de misión crítica.</span><span class="sxs-lookup"><span data-stu-id="3ce26-105">You can use Teams templates to quickly create rich collaboration spaces with channels for different topics and preinstall apps to pull in mission-critical content and services.</span></span> <span data-ttu-id="3ce26-106">Las plantillas de equipos proporcionan una estructura de equipo predefinidos que puede ayudarle a crear fácilmente los equipos coherentes en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="3ce26-106">Teams templates provide a predefined team structure that can help you easily create consistent teams across your organization.</span></span> 

<span data-ttu-id="3ce26-107">En este artículo, se explican las propiedades que pueden definirse en plantillas, qué plantilla base son tipos, y cómo puede usar algunas solicitudes para crear un equipo a partir de una plantilla de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3ce26-107">In this article, we'll explain the properties that can be defined in templates, what base template types are, and how you can use a few sample requests to create a team from a template.</span></span>
 
<span data-ttu-id="3ce26-108">En este artículo es para usted si es:</span><span class="sxs-lookup"><span data-stu-id="3ce26-108">This article is for you if you're:</span></span>

- <span data-ttu-id="3ce26-109">Responsable de la planeación, implementación y administración de varios equipos en toda la organización</span><span class="sxs-lookup"><span data-stu-id="3ce26-109">Responsible for planning, deploying, and managing multiple teams across your organization</span></span><br>
- <span data-ttu-id="3ce26-110">Un programador que deseen crear mediante programación un equipo con aplicaciones y canales predefinidos</span><span class="sxs-lookup"><span data-stu-id="3ce26-110">A developer wanting to programmatically create a team with predefined channels and apps</span></span> 

## <a name="teams-template-capabilities"></a><span data-ttu-id="3ce26-111">Capacidades de la plantilla de los equipos</span><span class="sxs-lookup"><span data-stu-id="3ce26-111">Teams template capabilities</span></span>

<span data-ttu-id="3ce26-112">Mayoría de las propiedades en un equipo se incluyen y compatible con las plantillas.</span><span class="sxs-lookup"><span data-stu-id="3ce26-112">Most properties in a team are included and supported by templates.</span></span> <span data-ttu-id="3ce26-113">Sin embargo, hay algunas propiedades y características que no son compatibles actualmente.</span><span class="sxs-lookup"><span data-stu-id="3ce26-113">But there are a few properties and features that are not currently supported.</span></span> <span data-ttu-id="3ce26-114">En la siguiente tabla proporciona un resumen rápido de lo que se incluye y qué no se incluye en las plantillas de equipos.</span><span class="sxs-lookup"><span data-stu-id="3ce26-114">The following table provides a quick summary of what's included and what's not included in Teams templates.</span></span>

| <span data-ttu-id="3ce26-115">**Propiedades de equipo compatibles con las plantillas de equipos**</span><span class="sxs-lookup"><span data-stu-id="3ce26-115">**Team properties supported by Teams templates**</span></span> | <span data-ttu-id="3ce26-116">**Propiedades de equipo aún no admitidas por las plantillas de equipos**</span><span class="sxs-lookup"><span data-stu-id="3ce26-116">**Team properties not yet supported by Teams templates**</span></span> |
| ------------------------------------------------ | -------------------------------------------------------- |
| <span data-ttu-id="3ce26-117">Tipo de plantilla de base</span><span class="sxs-lookup"><span data-stu-id="3ce26-117">Base template type</span></span> | <span data-ttu-id="3ce26-118">Miembros del equipo</span><span class="sxs-lookup"><span data-stu-id="3ce26-118">Team membership</span></span> |
| <span data-ttu-id="3ce26-119">Nombre del equipo</span><span class="sxs-lookup"><span data-stu-id="3ce26-119">Team name</span></span> | <span data-ttu-id="3ce26-120">Imagen del equipo</span><span class="sxs-lookup"><span data-stu-id="3ce26-120">Team picture</span></span> |
| <span data-ttu-id="3ce26-121">Descripción de equipo</span><span class="sxs-lookup"><span data-stu-id="3ce26-121">Team description</span></span> | <span data-ttu-id="3ce26-122">Opciones de canal</span><span class="sxs-lookup"><span data-stu-id="3ce26-122">Channel settings</span></span> |
| <span data-ttu-id="3ce26-123">Visibilidad de equipo (pública o privada)</span><span class="sxs-lookup"><span data-stu-id="3ce26-123">Team visibility (public or private)</span></span> | <span data-ttu-id="3ce26-124">Conectores</span><span class="sxs-lookup"><span data-stu-id="3ce26-124">Connectors</span></span> |
| <span data-ttu-id="3ce26-125">Configuración del equipo (por ejemplo, miembro, invitado, @ menciones)</span><span class="sxs-lookup"><span data-stu-id="3ce26-125">Team settings (for example, member, guest, @ mentions)</span></span> | <span data-ttu-id="3ce26-126">Los archivos y contenido</span><span class="sxs-lookup"><span data-stu-id="3ce26-126">Files and content</span></span> |
| <span data-ttu-id="3ce26-127">Canal de favorito de automático</span><span class="sxs-lookup"><span data-stu-id="3ce26-127">Auto-favorite channel</span></span> | |
| <span data-ttu-id="3ce26-128">Aplicación instalada</span><span class="sxs-lookup"><span data-stu-id="3ce26-128">Installed app</span></span> | |
| <span data-ttu-id="3ce26-129">Fichas ancladas</span><span class="sxs-lookup"><span data-stu-id="3ce26-129">Pinned tabs</span></span> | | 

> [!NOTE]
> <span data-ttu-id="3ce26-130">Se podrá ser agregar más capacidades de plantilla en futuras versiones de Microsoft Teams, por lo que vuelva a consultar para la información más actualizada sobre propiedades compatibles con.</span><span class="sxs-lookup"><span data-stu-id="3ce26-130">We'll be adding more template capabilities in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.</span></span>

## <a name="what-are-base-template-types"></a><span data-ttu-id="3ce26-131">¿Qué son los tipos de plantilla base?</span><span class="sxs-lookup"><span data-stu-id="3ce26-131">What are base template types?</span></span>

<span data-ttu-id="3ce26-132">Tipos de plantilla de base son plantillas especiales que Microsoft ha creado para sectores específicos.</span><span class="sxs-lookup"><span data-stu-id="3ce26-132">Base template types are special templates that Microsoft created for specific industries.</span></span> <span data-ttu-id="3ce26-133">Estas plantillas bases a menudo contienen propietarias aplicaciones que no están disponibles en las propiedades de almacenamiento y del equipo que no son compatibles todavía individualmente en las plantillas de equipos.</span><span class="sxs-lookup"><span data-stu-id="3ce26-133">These base templates often contain proprietary apps that aren't available in the store and team properties that are not yet supported individually in Teams templates.</span></span>

<span data-ttu-id="3ce26-134">Una vez que se define un tipo de plantilla base, puede ampliar o reemplazar estas plantillas especiales con propiedades adicionales que le gustaría usar para especificar.</span><span class="sxs-lookup"><span data-stu-id="3ce26-134">Once a base template type is defined, you can extend or override these special templates with additional properties that you'd like to specify.</span></span> <span data-ttu-id="3ce26-135">Pero algunos tipos de plantilla base contienen las propiedades que no se puede reemplazar.</span><span class="sxs-lookup"><span data-stu-id="3ce26-135">But some base template types contain properties that can't be overridden.</span></span> 

<span data-ttu-id="3ce26-136">De forma predeterminada, la plantilla base se establece en **estándar** que no contiene propiedades especiales ni aplicaciones adicionales de su propiedad.</span><span class="sxs-lookup"><span data-stu-id="3ce26-136">By default the base template is set to **Standard** which doesn't contain any additional proprietary apps or special properties.</span></span> <span data-ttu-id="3ce26-137">A continuación está disponible la lista actual de tipos de plantillas de base.</span><span class="sxs-lookup"><span data-stu-id="3ce26-137">Below is the current list of base templates types available.</span></span>

| <span data-ttu-id="3ce26-138">Tipo de plantilla de base</span><span class="sxs-lookup"><span data-stu-id="3ce26-138">Base template type</span></span> | <span data-ttu-id="3ce26-139">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="3ce26-139">baseTemplateId</span></span> | <span data-ttu-id="3ce26-140">Aplicaciones propietario de plantilla de base y las propiedades especiales</span><span class="sxs-lookup"><span data-stu-id="3ce26-140">Base template proprietary apps and special properties</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="3ce26-141">Standard</span><span class="sxs-lookup"><span data-stu-id="3ce26-141">Standard</span></span> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`standard` | <span data-ttu-id="3ce26-142">No hay aplicaciones adicionales y propiedades</span><span class="sxs-lookup"><span data-stu-id="3ce26-142">No additional apps and properties</span></span> |
| <span data-ttu-id="3ce26-143">Educación-</span><span class="sxs-lookup"><span data-stu-id="3ce26-143">Education -</span></span> <br><span data-ttu-id="3ce26-144">Clase equipo<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="3ce26-144">Class team<sup>1</sup></span></span> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationClass` | <span data-ttu-id="3ce26-145">Aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="3ce26-145">Apps:</span></span><ul><li><span data-ttu-id="3ce26-146">Bloc de notas de OneNote clase (anclado a la ficha **General** )</span><span class="sxs-lookup"><span data-stu-id="3ce26-146">OneNote Class Notebook (pinned to the **General** tab)</span></span> </li><li><span data-ttu-id="3ce26-147">Aplicación de las asignaciones (anclado a la ficha **General** )</span><span class="sxs-lookup"><span data-stu-id="3ce26-147">Assignments app (pinned to the **General** tab)</span></span></li></ul> <span data-ttu-id="3ce26-148">Propiedades de equipo:</span><span class="sxs-lookup"><span data-stu-id="3ce26-148">Team properties:</span></span><ul><li><span data-ttu-id="3ce26-149">Visibilidad de equipo se establece en **HiddenMembership** (no se puede reemplazar)</span><span class="sxs-lookup"><span data-stu-id="3ce26-149">Team visibility set to **HiddenMembership** (cannot be overridden)</span></span></li></ul> |
| <span data-ttu-id="3ce26-150">Educación-</span><span class="sxs-lookup"><span data-stu-id="3ce26-150">Education -</span></span><br><span data-ttu-id="3ce26-151">Personal de grupo<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="3ce26-151">Staff team<sup>1</sup></span></span> | `https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationStaff` | <span data-ttu-id="3ce26-152">Aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="3ce26-152">Apps:</span></span><ul><li><span data-ttu-id="3ce26-153">Bloc de notas de OneNote personal (anclado a la ficha **General** )</span><span class="sxs-lookup"><span data-stu-id="3ce26-153">OneNote Staff Notebook (pinned to the **General** tab)</span></span></li></ul> |
|<span data-ttu-id="3ce26-154">Educación-</span><span class="sxs-lookup"><span data-stu-id="3ce26-154">Education -</span></span><br><span data-ttu-id="3ce26-155">Equipo PLC</span><span class="sxs-lookup"><span data-stu-id="3ce26-155">PLC team</span></span> |`https://graph.microsoft.com/beta/teamsTemplates/`<br>`educationProfessionalLearningCommunity` | <span data-ttu-id="3ce26-156">Aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="3ce26-156">Apps:</span></span><ul><li><span data-ttu-id="3ce26-157">Bloc de notas de OneNote PLC (anclado a la ficha **General** )</span><span class="sxs-lookup"><span data-stu-id="3ce26-157">OneNote PLC Notebook (pinned to the **General** tab)</span></span></ul></li>|
|||

<span data-ttu-id="3ce26-158">Publicación de <sup>1</sup> de octubre de 2018 las últimas</span><span class="sxs-lookup"><span data-stu-id="3ce26-158"><sup>1</sup> Publication in late October, 2018</span></span>

> [!NOTE]
> <span data-ttu-id="3ce26-159">Agregaremos más plantilla base de tipos de en futuras versiones de Microsoft Teams, por lo que verificación atrás para la información más actualizada sobre admite propiedades.</span><span class="sxs-lookup"><span data-stu-id="3ce26-159">We'll be adding more base template types in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.</span></span>

## <a name="examples"></a><span data-ttu-id="3ce26-160">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3ce26-160">Examples</span></span> 

<span data-ttu-id="3ce26-161">Puede empezar a usar una plantilla para crear un equipo mediante el uso de la [API de Microsoft Graph](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span><span class="sxs-lookup"><span data-stu-id="3ce26-161">You can start using a template to create a team by using the [Microsoft Graph API](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta).</span></span>

### <a name="create-a-team-from-a-template"></a><span data-ttu-id="3ce26-162">Crear un equipo a partir de una plantilla</span><span class="sxs-lookup"><span data-stu-id="3ce26-162">Create a team from a template</span></span>

#### <a name="requests"></a><span data-ttu-id="3ce26-163">Solicitudes</span><span class="sxs-lookup"><span data-stu-id="3ce26-163">Requests</span></span>

<span data-ttu-id="3ce26-164">**Solicitud para crear un equipo con la plantilla de base estándar**</span><span class="sxs-lookup"><span data-stu-id="3ce26-164">**Request to create a team with the standard base template**</span></span>

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates/standard",
  "displayName": "Sample Team",
  "description": "Sample Team’s Description"
}

~~~

<span data-ttu-id="3ce26-165">**Para crear un equipo con un canal extra y no permitir a los miembros de eliminar los canales de solicitudes**</span><span class="sxs-lookup"><span data-stu-id="3ce26-165">**Request to create a team with an extra channel and disallow members from deleting channels**</span></span>

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
  "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates/standard",
  "displayName": "My Sample Team",
  "description": "My Sample Team’s Description",
  "channels": [
    {
        "displayName": "Random",
        "isFavoriteByDefault": true
    }
              ],
    "memberSettings": {
        "allowDeleteChannels": false
    }
}

~~~

<span data-ttu-id="3ce26-166">**Solicitud para crear un equipo con todas las propiedades compatibles**</span><span class="sxs-lookup"><span data-stu-id="3ce26-166">**Request to create a team with all supported properties**</span></span>

~~~
POST /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "template@odata.bind": "https://graph.microsoft.com/beta/teamsTemplates('standard')",
    "visibility": "Private",
    "displayName": "Sample Engineering Team",
    "description": "This is a sample engineering team, used to showcase the range of properties 
supported by this API",
    "channels": [
        {
            "displayName": "Announcements 📢",
            "isFavoriteByDefault": true,
            "description": "This is a sample announcements channel that is favorited by default. Use this 
channel to make important team, product, and service announcements."
        },
        {
            "displayName": "Training 🏋️",
            "isFavoriteByDefault": true,
            "description": "This is a sample training channel that is favorited by default and contains an 
example of pinned website and YouTube tabs.",
            "tabs": [
                {
                    "teamsApp@odata.bind":
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.web')",
                   "name": "A Pinned Website",
                    "configuration": {
                        "contentUrl": "https://docs.microsoft.com/en-us/microsoftteams/microsoft-teams"
                    }
                },
                {
                    "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.youtube')",
                    "name": "A Pinned YouTube Video",
                    "configuration": {
                        "contentUrl": "https://tabs.teams.microsoft.com/Youtube/Home/YoutubeTab?
videoId=X8krAMdGvCQ",
                        "websiteUrl": "https://www.youtube.com/watch?v=X8krAMdGvCQ"
                    }
                }
            ]
        },
        {
"displayName": "Planning 📅 ",
            "description": "This is a sample of a channel that is not favorited by default, these channels 
will appear in the more channels overflow menu.",
            "isFavoriteByDefault": false
        },
        {
            "displayName": "Issues and Feedback 🐞",
            "description": "This is a sample of a channel that is not favorited by default, these channels 
will appear in the more channels overflow menu."
        }
    ],
    "memberSettings": {
        "allowCreateUpdateChannels": true,
        "allowDeleteChannels": true,
        "allowAddRemoveApps": true,
        "allowCreateUpdateRemoveTabs": true,
        "allowCreateUpdateRemoveConnectors": true
    },
    "guestSettings": {
        "allowCreateUpdateChannels": false,
        "allowDeleteChannels": false
    },
    "funSettings": {
        "allowGiphy": true,
        "giphyContentRating": "Moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
    },
    "messagingSettings": {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
    },
    "installedApps": [
        {
            "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('com.microsoft.teamspace.tab.vsts')"
        },
        {
            "teamsApp@odata.bind": 
"https://graph.microsoft.com/v1.0/appCatalogs/teamsApps('1542629c-01b3-4a6d-8f76-1938b779e48d')"
        }
    ]
}
~~~

### <a name="get-status"></a><span data-ttu-id="3ce26-167">Obtener el estado</span><span class="sxs-lookup"><span data-stu-id="3ce26-167">Get status</span></span>

#### <a name="request"></a><span data-ttu-id="3ce26-168">Solicitud</span><span class="sxs-lookup"><span data-stu-id="3ce26-168">Request</span></span>

~~~
GET   /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
Authorization: Bearer <TOKEN>
~~~

#### <a name="response"></a><span data-ttu-id="3ce26-169">Respuesta</span><span class="sxs-lookup"><span data-stu-id="3ce26-169">Response</span></span>

~~~
HTTP/1.1 200 OK
Content-Type: application/json
{
    "status": "[InProgress|Completed|Cancelled|Failed]"
}
~~~

## <a name="related-topics"></a><span data-ttu-id="3ce26-170">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="3ce26-170">Related topics</span></span>

- <span data-ttu-id="3ce26-171">[Crear equipo](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (en la vista previa)</span><span class="sxs-lookup"><span data-stu-id="3ce26-171">[Create team](https://docs.microsoft.com/graph/api/team-post?view=graph-rest-beta) (in preview)</span></span>
- [<span data-ttu-id="3ce26-172">Nuevo equipo</span><span class="sxs-lookup"><span data-stu-id="3ce26-172">New-Team</span></span>](https://docs.microsoft.com/powershell/module/teams/New-Team?view=teams-ps)
- [<span data-ttu-id="3ce26-173">Formación de administradores para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3ce26-173">Admin training for Microsoft Teams</span></span>](itadmin-readiness.md)