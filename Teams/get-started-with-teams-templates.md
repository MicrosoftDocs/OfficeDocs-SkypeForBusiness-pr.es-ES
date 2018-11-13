---
title: Introducción a las plantillas de equipos
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/12/2018
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
ms.openlocfilehash: 7850ad245eebee96b6852e7f0cc57a35adcca9f7
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295010"
---
# <a name="get-started-with-teams-templates"></a><span data-ttu-id="c7c30-103">Introducción a las plantillas de equipos</span><span class="sxs-lookup"><span data-stu-id="c7c30-103">Get started with Teams templates</span></span> 

<span data-ttu-id="c7c30-104">Plantillas de equipo son predefinidas definiciones de estructura de un equipo diseñado alrededor de un proyecto o necesidad empresarial.</span><span class="sxs-lookup"><span data-stu-id="c7c30-104">Team templates are pre-built definitions of a team's structure designed around a business need or project.</span></span> <span data-ttu-id="c7c30-105">Puede usar las plantillas de equipo para crear rápidamente los espacios de colaboración con los canales para diferentes temas y preinstalación de aplicaciones que se van a extraer en servicios y contenido de misión crítica.</span><span class="sxs-lookup"><span data-stu-id="c7c30-105">You can use team templates to quickly create rich collaboration spaces with channels for different topics and preinstall apps to pull in mission-critical content and services.</span></span> <span data-ttu-id="c7c30-106">Plantillas de equipo proporcionan una estructura de equipo predefinidos que puede ayudarle a crear fácilmente los equipos coherentes en toda la organización.</span><span class="sxs-lookup"><span data-stu-id="c7c30-106">Team templates provide a predefined team structure that can help you easily create consistent teams across your organization.</span></span> 

<span data-ttu-id="c7c30-107">En este artículo, se explican las propiedades que pueden definirse en plantillas, qué plantilla base son tipos, y cómo puede usar algunas solicitudes para crear un equipo a partir de una plantilla de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="c7c30-107">In this article, we'll explain the properties that can be defined in templates, what base template types are, and how you can use a few sample requests to create a team from a template.</span></span>
 
<span data-ttu-id="c7c30-108">En este artículo es para usted si es:</span><span class="sxs-lookup"><span data-stu-id="c7c30-108">This article is for you if you're:</span></span>

<span data-ttu-id="c7c30-109">• Responsable de la planeación, implementación y administración de varios equipos a través de su desarrollador de • una organización ¿está buscando para crear un equipo con predefinidos canales y aplicaciones mediante programación</span><span class="sxs-lookup"><span data-stu-id="c7c30-109">•   Responsible for planning, deploying, and managing multiple teams across your organization •   A developer looking to create a team with predefined channels and apps programmatically</span></span>

## <a name="team-template-capabilities"></a><span data-ttu-id="c7c30-110">Capacidades de la plantilla de equipo</span><span class="sxs-lookup"><span data-stu-id="c7c30-110">Team template capabilities</span></span>

<span data-ttu-id="c7c30-111">Mayoría de las propiedades en un equipo se incluyen y compatible con las plantillas.</span><span class="sxs-lookup"><span data-stu-id="c7c30-111">Most properties in a team are included and supported by templates.</span></span> <span data-ttu-id="c7c30-112">Sin embargo, hay algunas propiedades y características que actualmente no son compatibles.</span><span class="sxs-lookup"><span data-stu-id="c7c30-112">However, there are a few properties and features that are currently not supported.</span></span> <span data-ttu-id="c7c30-113">En la siguiente tabla proporciona un resumen rápido de lo que se incluye y qué no se incluye en las plantillas de equipos.</span><span class="sxs-lookup"><span data-stu-id="c7c30-113">The following table provides a quick summary of what's included and what's not included in Teams templates.</span></span>

| <span data-ttu-id="c7c30-114">**Propiedades de equipo compatibles con las plantillas de equipos**</span><span class="sxs-lookup"><span data-stu-id="c7c30-114">**Team properties supported by Teams templates**</span></span> | <span data-ttu-id="c7c30-115">**Propiedades de equipo aún no admitidas por las plantillas de equipos**</span><span class="sxs-lookup"><span data-stu-id="c7c30-115">**Team properties not yet supported by Teams templates**</span></span> |
| ------------------------------------------------ | -------------------------------------------------------- |
| <span data-ttu-id="c7c30-116">Tipo de plantilla de base</span><span class="sxs-lookup"><span data-stu-id="c7c30-116">Base template type</span></span> | <span data-ttu-id="c7c30-117">Miembros del equipo</span><span class="sxs-lookup"><span data-stu-id="c7c30-117">Team membership</span></span> |
| <span data-ttu-id="c7c30-118">Nombre del equipo</span><span class="sxs-lookup"><span data-stu-id="c7c30-118">Team name</span></span> | <span data-ttu-id="c7c30-119">Imagen del equipo</span><span class="sxs-lookup"><span data-stu-id="c7c30-119">Team picture</span></span> |
| <span data-ttu-id="c7c30-120">Descripción de equipo</span><span class="sxs-lookup"><span data-stu-id="c7c30-120">Team description</span></span> | <span data-ttu-id="c7c30-121">Configuración de canal (por ejemplo, auto-favorito y privacidad)</span><span class="sxs-lookup"><span data-stu-id="c7c30-121">Channel settings (for example, auto-favorite and privacy)</span></span> |
| <span data-ttu-id="c7c30-122">Visibilidad de equipo (pública o privada)</span><span class="sxs-lookup"><span data-stu-id="c7c30-122">Team visibility (public or private)</span></span> | <span data-ttu-id="c7c30-123">Conectores</span><span class="sxs-lookup"><span data-stu-id="c7c30-123">Connectors</span></span> |
| <span data-ttu-id="c7c30-124">Configuración del equipo (por ejemplo, miembro, invitado, @ menciones)</span><span class="sxs-lookup"><span data-stu-id="c7c30-124">Team settings (for example, member, guest, @ mentions)</span></span> | <span data-ttu-id="c7c30-125">Los archivos y contenido</span><span class="sxs-lookup"><span data-stu-id="c7c30-125">Files and content</span></span> |
| <span data-ttu-id="c7c30-126">Canal de favorito de automático</span><span class="sxs-lookup"><span data-stu-id="c7c30-126">Auto-favorite channel</span></span> | |
| <span data-ttu-id="c7c30-127">Aplicación instalada</span><span class="sxs-lookup"><span data-stu-id="c7c30-127">Installed app</span></span> | |
| <span data-ttu-id="c7c30-128">Fichas ancladas</span><span class="sxs-lookup"><span data-stu-id="c7c30-128">Pinned tabs</span></span> | | 

> [!NOTE]
> <span data-ttu-id="c7c30-129">Se podrá ser agregar más capacidades de plantilla en futuras versiones de Microsoft Teams, por lo que vuelva a consultar para la información más actualizada sobre propiedades compatibles con.</span><span class="sxs-lookup"><span data-stu-id="c7c30-129">We'll be adding more template capabilities in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.</span></span>

## <a name="what-are-base-template-types"></a><span data-ttu-id="c7c30-130">¿Qué son los tipos de plantilla base?</span><span class="sxs-lookup"><span data-stu-id="c7c30-130">What are base template types?</span></span>

<span data-ttu-id="c7c30-131">Tipos de plantilla de base son plantillas especiales que Microsoft ha creado para sectores específicos.</span><span class="sxs-lookup"><span data-stu-id="c7c30-131">Base template types are special templates that Microsoft created for specific industries.</span></span> <span data-ttu-id="c7c30-132">Estas plantillas bases a menudo contienen propietarias aplicaciones que no están disponibles en las propiedades de almacenamiento y de grupo que no se admite aún individualmente en las plantillas de equipos.</span><span class="sxs-lookup"><span data-stu-id="c7c30-132">These base templates often contain proprietary apps that aren't available in the store and team properties not yet supported individually in Teams templates.</span></span>

<span data-ttu-id="c7c30-133">Una vez que se define un tipo de plantilla base, puede ampliar o reemplazar estas plantillas especiales con propiedades adicionales que le gustaría usar para especificar.</span><span class="sxs-lookup"><span data-stu-id="c7c30-133">Once a base template type is defined, you can extend or override these special templates with additional properties that you'd like to specify.</span></span> <span data-ttu-id="c7c30-134">Sin embargo, algunos tipos de plantilla base contienen las propiedades que no se puede reemplazar.</span><span class="sxs-lookup"><span data-stu-id="c7c30-134">However, some base template types contain properties that can't be overridden.</span></span> 

<span data-ttu-id="c7c30-135">De forma predeterminada, la plantilla base se establece en **estándar** que no contiene propiedades especiales ni aplicaciones adicionales de su propiedad.</span><span class="sxs-lookup"><span data-stu-id="c7c30-135">By default the base template is set to **Standard** which doesn't contain any additional proprietary apps or special properties.</span></span> <span data-ttu-id="c7c30-136">A continuación está disponible la lista actual de tipos de plantillas de base.</span><span class="sxs-lookup"><span data-stu-id="c7c30-136">Below is the current list of base templates types available.</span></span>

| <span data-ttu-id="c7c30-137">Tipo de plantilla de base</span><span class="sxs-lookup"><span data-stu-id="c7c30-137">Base template type</span></span> | <span data-ttu-id="c7c30-138">baseTemplateId</span><span class="sxs-lookup"><span data-stu-id="c7c30-138">baseTemplateId</span></span> | <span data-ttu-id="c7c30-139">Aplicaciones propietario de plantilla de base y las propiedades especiales</span><span class="sxs-lookup"><span data-stu-id="c7c30-139">Base template proprietary apps and special properties</span></span> |
| ------------------ | -------------- | ----------------------------------------------------- |
| <span data-ttu-id="c7c30-140">Standard</span><span class="sxs-lookup"><span data-stu-id="c7c30-140">Standard</span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json) | <span data-ttu-id="c7c30-141">No hay aplicaciones adicionales y propiedades</span><span class="sxs-lookup"><span data-stu-id="c7c30-141">No additional apps and properties</span></span> |
| <span data-ttu-id="c7c30-142">Healthcare - coordinación de la atención</span><span class="sxs-lookup"><span data-stu-id="c7c30-142">Healthcare - care coordination</span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-CC.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-CC.json#) | <span data-ttu-id="c7c30-143">Aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="c7c30-143">Apps:</span></span><br/> <span data-ttu-id="c7c30-144">-Aplicación de los pacientes (anclado a la ficha **General** )</span><span class="sxs-lookup"><span data-stu-id="c7c30-144">- Patients app (pinned to the **General** tab)</span></span><br/> <br/><span data-ttu-id="c7c30-145">Canales de entrada:</span><span class="sxs-lookup"><span data-stu-id="c7c30-145">Channels:</span></span> <br/> <span data-ttu-id="c7c30-146">-Anuncios</span><span class="sxs-lookup"><span data-stu-id="c7c30-146">- Announcements</span></span><br/> <span data-ttu-id="c7c30-147">-Diabetes</span><span class="sxs-lookup"><span data-stu-id="c7c30-147">- Diabetes</span></span><br/> <span data-ttu-id="c7c30-148">-Cardiovascular</span><span class="sxs-lookup"><span data-stu-id="c7c30-148">- Cardiovascular</span></span><br/> <span data-ttu-id="c7c30-149">-Diplomadas</span><span class="sxs-lookup"><span data-stu-id="c7c30-149">- Registered nurses</span></span> |
| <span data-ttu-id="c7c30-150">Healthcare - proceso ponerse a trabajar</span><span class="sxs-lookup"><span data-stu-id="c7c30-150">Healthcare - process huddle</span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-PH.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Healthcare-PH.json#) | <span data-ttu-id="c7c30-151">Canales de entrada:</span><span class="sxs-lookup"><span data-stu-id="c7c30-151">Channels:</span></span><br/> <span data-ttu-id="c7c30-152">-Evitables muertes</span><span class="sxs-lookup"><span data-stu-id="c7c30-152">- Avoidable deaths</span></span><br/> <span data-ttu-id="c7c30-153">-Revisión de mortalidad</span><span class="sxs-lookup"><span data-stu-id="c7c30-153">- Mortality review</span></span> <br/> <span data-ttu-id="c7c30-154">-Impidiendo que se divide</span><span class="sxs-lookup"><span data-stu-id="c7c30-154">- Preventing falls</span></span> <br/> <span data-ttu-id="c7c30-155">-Planes de sepsis</span><span class="sxs-lookup"><span data-stu-id="c7c30-155">- Sepsis plans</span></span> |
| <span data-ttu-id="c7c30-156">Educación - clase equipo<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c7c30-156">Education - Class team<sup>1</sup></span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-CT.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-CT.json#) | <span data-ttu-id="c7c30-157">Aplicaciones:</span><span class="sxs-lookup"><span data-stu-id="c7c30-157">Apps:</span></span><br/> <span data-ttu-id="c7c30-158">-Bloc de notas de OneNote clase (anclado a la ficha **General** )</span><span class="sxs-lookup"><span data-stu-id="c7c30-158">- OneNote Class Notebook (pinned to the **General** tab)</span></span> <br/> <span data-ttu-id="c7c30-159">-App asignaciones (anclado a la ficha **General** )</span><span class="sxs-lookup"><span data-stu-id="c7c30-159">- Assignments app (pinned to the **General** tab)</span></span> <br/><br/> <span data-ttu-id="c7c30-160">Propiedades de equipo</span><span class="sxs-lookup"><span data-stu-id="c7c30-160">Team properties</span></span> <br/> <span data-ttu-id="c7c30-161">-Visibilidad equipo establecida en **HiddenMembership** (no se puede reemplazar)</span><span class="sxs-lookup"><span data-stu-id="c7c30-161">- Team visibility set to **HiddenMembership** (cannot be overridden)</span></span> |
| <span data-ttu-id="c7c30-162">Equipo de personal de educación -<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c7c30-162">Education - Staff team<sup>1</sup></span></span> | [https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-ST.json#](https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Education-ST.json#) | <span data-ttu-id="c7c30-163">Aplicaciones</span><span class="sxs-lookup"><span data-stu-id="c7c30-163">Apps</span></span><br/> <span data-ttu-id="c7c30-164">-Bloc de notas de OneNote personal (anclado a la ficha **General** )</span><span class="sxs-lookup"><span data-stu-id="c7c30-164">- OneNote Staff Notebook (pinned to the **General** tab)</span></span> |

<span data-ttu-id="c7c30-165">Publicación de <sup>1</sup> de octubre de 2018 las últimas</span><span class="sxs-lookup"><span data-stu-id="c7c30-165"><sup>1</sup> Publication in late October, 2018</span></span>

> [!NOTE]
> <span data-ttu-id="c7c30-166">Agregaremos más plantilla base de tipos de en futuras versiones de Microsoft Teams, por lo que verificación atrás para la información más actualizada sobre admite propiedades.</span><span class="sxs-lookup"><span data-stu-id="c7c30-166">We'll be adding more base template types in future releases of Microsoft Teams, so check back for the most up-to-date information on supported properties.</span></span>

## <a name="examples"></a><span data-ttu-id="c7c30-167">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c7c30-167">Examples</span></span> 

<span data-ttu-id="c7c30-168">Puede iniciar la creación de un equipo a través de la plantilla mediante la instalación de [Microsoft Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/overview).</span><span class="sxs-lookup"><span data-stu-id="c7c30-168">You can start creating a team via template by installing [Microsoft Graph](https://developer.microsoft.com/en-us/graph/docs/concepts/overview).</span></span>

### <a name="create-a-team-from-a-template"></a><span data-ttu-id="c7c30-169">Crear un equipo a partir de una plantilla</span><span class="sxs-lookup"><span data-stu-id="c7c30-169">Create a team from a template</span></span>

#### <a name="requests"></a><span data-ttu-id="c7c30-170">Solicitudes</span><span class="sxs-lookup"><span data-stu-id="c7c30-170">Requests</span></span>

<span data-ttu-id="c7c30-171">**Solicitud para crear un equipo con la plantilla de base estándar**</span><span class="sxs-lookup"><span data-stu-id="c7c30-171">**Request to create a team with the standard base template**</span></span>

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
    
    "teamDisplayName": "My Sample Team",
    "teamDescription": "My Sample Team’s Description",
}

~~~

<span data-ttu-id="c7c30-172">**Para crear un equipo con un canal extra y no permitir a los miembros de eliminar los canales de solicitudes**</span><span class="sxs-lookup"><span data-stu-id="c7c30-172">**Request to create a team with an extra channel and disallow members from deleting channels**</span></span>

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
    
    "teamDisplayName": "My Sample Team",
    "teamDescription": "My Sample Team’s Description",
    "channels": [
        {
            "displayName": "Interns",
            "autoFavorite": false
        }
    ],
    "memberSettings": {
        "allowDeleteChannels": false,
    }
}

~~~

<span data-ttu-id="c7c30-173">**Solicitud para crear un equipo con todas las propiedades compatibles**</span><span class="sxs-lookup"><span data-stu-id="c7c30-173">**Request to create a team with all supported properties**</span></span>

~~~
POST   /teams
Authorization: Bearer <TOKEN>
Content-Type: application/json
{
    "baseTemplateId": "https://teams.microsoft.com/templates/schemas/1.0/TeamTemplate.Standard.json",
    "schemaVersion": "1.0",
 
    "teamType": "Healthcare_CareCoordination",
    "visibility": "Private",
    "teamDisplayName": "My Care Team",
    "teamDescription": "My Care Team’s description",
 
    "channels": [
        {
            "displayName": "General  ",
            "autoFavorite": true,
            "tabs": [
                   {
                       "appId": "0d820ecd-def2-4297-adad-78056cde7c78",
                       "tabDisplayName": "Intranet”
                   }
               ]
        },
        {
            "displayName": "Announcements",
            "autoFavorite": true
        },
        {
            "displayName": "Diabetes",
            "autoFavorite": true
        },
        {
            "displayName": "Cardiovascular",
            "autoFavorite": true
        },
        {
            "displayName": "Registered Nurses",
            "autoFavorite": true
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
 
      "messagingSettings": {
        "allowUserEditMessages": true,
        "allowUserDeleteMessages": true,
        "allowOwnerDeleteMessages": true,
        "allowTeamMentions": true,
        "allowChannelMentions": true
      },
 
      "funSettings": {
        "allowGiphy": true,
        "giphyContentRating": "moderate",
        "allowStickersAndMemes": true,
        "allowCustomMemes": true
      }
 
 
    "installedApplications": [
      {
        "id": "0d820ecd-def2-4297-adad-78056cde7c78"
      }
    ]
}
~~~

#### <a name="response"></a><span data-ttu-id="c7c30-174">Respuesta</span><span class="sxs-lookup"><span data-stu-id="c7c30-174">Response</span></span>

~~~
HTTP/1.1 202 Accepted
Content-Type: application/json
Location: /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
{
    "workflowId": "c953c202-7b44-4a63-aa33-364fcb2d65aa",
    "statusUri": "https://<apihostandpath>/workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa"
}
~~~

### <a name="get-status"></a><span data-ttu-id="c7c30-175">Obtener el estado</span><span class="sxs-lookup"><span data-stu-id="c7c30-175">Get status</span></span>

#### <a name="request"></a><span data-ttu-id="c7c30-176">Solicitud</span><span class="sxs-lookup"><span data-stu-id="c7c30-176">Request</span></span>

~~~
GET   /workflow/status/c953c202-7b44-4a63-aa33-364fcb2d65aa
Authorization: Bearer <TOKEN>
~~~

#### <a name="response"></a><span data-ttu-id="c7c30-177">Respuesta</span><span class="sxs-lookup"><span data-stu-id="c7c30-177">Response</span></span>

~~~
HTTP/1.1 200 OK
Content-Type: application/json
{
    "status": "[InProgress|Completed|Cancelled|Failed]"
}
~~~

## <a name="related-topics"></a><span data-ttu-id="c7c30-178">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c7c30-178">Related topics</span></span>

- <span data-ttu-id="c7c30-179">[Crear equipo](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/team_put_teams) (en la vista previa)</span><span class="sxs-lookup"><span data-stu-id="c7c30-179">[Create team](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/team_put_teams) (in preview)</span></span>
- [<span data-ttu-id="c7c30-180">Nuevo equipo</span><span class="sxs-lookup"><span data-stu-id="c7c30-180">New-Team</span></span>](https://docs.microsoft.com/en-us/powershell/module/teams/New-Team?view=teams-ps)
- [<span data-ttu-id="c7c30-181">Formación de administradores para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c7c30-181">Admin training for Microsoft Teams</span></span>](itadmin-readiness.md)