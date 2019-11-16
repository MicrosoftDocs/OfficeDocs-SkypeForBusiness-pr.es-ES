---
title: Etiquetas de confidencialidad para Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: abgupta
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo definir y usar etiquetas de confidencialidad en Microsoft Teams.
ms.openlocfilehash: 3a0c40a51653a525587a0662949a3fdd4e63faf4
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2019
ms.locfileid: "38653611"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="22169-103">Etiquetas de confidencialidad para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="22169-103">Sensitivity labels for Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="22169-104">Las [etiquetas de confidencialidad](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) permiten a los administradores de equipos regular el acceso a contenido de organización confidencial creado durante la colaboración dentro de Teams.</span><span class="sxs-lookup"><span data-stu-id="22169-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="22169-105">Puede definir las etiquetas de confidencialidad y las directivas asociadas en el [centro de cumplimiento de & de seguridad](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span><span class="sxs-lookup"><span data-stu-id="22169-105">You can define sensitivity labels and their associated policies in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span> <span data-ttu-id="22169-106">Estas etiquetas y directivas se aplican automáticamente a los equipos de su organización.</span><span class="sxs-lookup"><span data-stu-id="22169-106">These labels and policies are automatically applied to teams in your organization.</span></span>  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="22169-107">¿Cuál es la diferencia entre las etiquetas de confidencialidad y las etiquetas de clasificación de equipos?</span><span class="sxs-lookup"><span data-stu-id="22169-107">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="22169-108">Las etiquetas de confidencialidad son diferentes de las etiquetas de clasificación que requieren su creación con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="22169-108">Sensitivity labels are different from classification labels that require you to create them using PowerShell.</span></span> <span data-ttu-id="22169-109">Las etiquetas de clasificación son cadenas de texto que se pueden asociar a un grupo pero que no tienen ninguna directiva real asociada.</span><span class="sxs-lookup"><span data-stu-id="22169-109">Classification labels are text strings that can be associated with a group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="22169-110">Use las etiquetas de clasificación como metadatos para aplicar manualmente las directivas a través de las herramientas y scripts internos.</span><span class="sxs-lookup"><span data-stu-id="22169-110">You use classification labels as metadata to manually enforce policies through internal tools and scripts.</span></span>

<span data-ttu-id="22169-111">Por otro lado, las etiquetas de confidencialidad y sus directivas se aplican de forma automática de principio a fin a través de una combinación de la plataforma de grupos, el centro de cumplimiento de & de seguridad y los servicios de Teams.</span><span class="sxs-lookup"><span data-stu-id="22169-111">On the other hand, sensitivity labels and their policies are automatically enforced end-to-end through a combination of the Groups platform, Security & Compliance Center, and Teams services.</span></span> <span data-ttu-id="22169-112">Las etiquetas de confidencialidad proporcionan una eficaz compatibilidad de infraestructura para proteger los datos confidenciales de su organización.</span><span class="sxs-lookup"><span data-stu-id="22169-112">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data.</span></span>  

## <a name="create-and-publish-sensitivity-labels-for-teams"></a><span data-ttu-id="22169-113">Crear y publicar etiquetas de confidencialidad para equipos</span><span class="sxs-lookup"><span data-stu-id="22169-113">Create and publish sensitivity labels for Teams</span></span>

<span data-ttu-id="22169-114">Para obtener información sobre cómo habilitar, crear y publicar etiquetas de confidencialidad para equipos, consulte [usar etiquetas de confidencialidad con Microsoft Teams, grupos de Office 365 y sitios de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="22169-114">For how to enable, create, and publish sensitivity labels for Teams, see [Use sensitivity labels with Microsoft Teams, Office 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

## <a name="using-sensitivity-labels-with-teams"></a><span data-ttu-id="22169-115">Usar etiquetas de confidencialidad con equipos</span><span class="sxs-lookup"><span data-stu-id="22169-115">Using sensitivity labels with Teams</span></span>

<span data-ttu-id="22169-116">A continuación se muestran algunos escenarios de ejemplo de cómo puede usar las etiquetas de confidencialidad con equipos de su organización.</span><span class="sxs-lookup"><span data-stu-id="22169-116">Here are some example scenarios of how you can use sensitivity labels with Teams in your organization.</span></span>

### <a name="privacy-setting-of-teams"></a><span data-ttu-id="22169-117">Configuración de privacidad de Teams</span><span class="sxs-lookup"><span data-stu-id="22169-117">Privacy setting of teams</span></span>

<span data-ttu-id="22169-118">Puede crear una etiqueta de confidencialidad que, cuando se aplique durante la creación del equipo, permita a los usuarios crear equipos con una configuración de privacidad (pública o privada) específica.</span><span class="sxs-lookup"><span data-stu-id="22169-118">You can create a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="22169-119">Por ejemplo, puede crear una etiqueta denominada "confidencial" en el centro de cumplimiento de & de seguridad y configurar Teams de modo que cualquier equipo que se cree con esta etiqueta debe ser un equipo privado.</span><span class="sxs-lookup"><span data-stu-id="22169-119">For example, you create a label named “Confidential” in the Security & Compliance Center and you configure Teams so that any team that's created with this label must be a private team.</span></span> <span data-ttu-id="22169-120">Cuando un usuario crea un nuevo equipo y selecciona la etiqueta **confidencial** , la única opción de privacidad que está disponible para el usuario es **privada**.</span><span class="sxs-lookup"><span data-stu-id="22169-120">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="22169-121">Otras opciones de privacidad, como público y toda la organización, están deshabilitadas para el usuario.</span><span class="sxs-lookup"><span data-stu-id="22169-121">Other privacy options such as Public and Org-wide are disabled for the user.</span></span>

![Captura de pantalla de etiqueta confidencial confidencial](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="22169-123">De forma similar, si el usuario selecciona **General** al crear un equipo nuevo, solo podrá crear equipos públicos o de toda la organización.</span><span class="sxs-lookup"><span data-stu-id="22169-123">Similarly, if the user selects **General** when they create a new team, they can only create public or org-wide teams.</span></span>

![Captura de pantalla de etiqueta de confidencialidad general](media/sensitivity-labels-general-example.png)

<span data-ttu-id="22169-125">Cuando se crea el equipo, la etiqueta de confidencialidad está visible en la esquina superior derecha de los canales del equipo.</span><span class="sxs-lookup"><span data-stu-id="22169-125">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![Captura de pantalla de la etiqueta de confidencialidad en el canal de equipo](media/sensitivity-labels-channel.png)

<span data-ttu-id="22169-127">El propietario de un equipo puede cambiar la etiqueta de confidencialidad y la configuración de privacidad del equipo en cualquier momento al ir al equipo y, a continuación, hacer clic en **Editar equipo**.</span><span class="sxs-lookup"><span data-stu-id="22169-127">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then clicking **Edit team**.</span></span>

![Captura de pantalla de la etiqueta de confidencialidad en el canal de equipo](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a><span data-ttu-id="22169-129">Acceso de invitado a equipos</span><span class="sxs-lookup"><span data-stu-id="22169-129">Guest access to teams</span></span>

<span data-ttu-id="22169-130">Puede especificar si un equipo creado con una etiqueta específica le permite el acceso de invitado.</span><span class="sxs-lookup"><span data-stu-id="22169-130">You can specify whether a team created with a specific label allows guest access.</span></span> <span data-ttu-id="22169-131">Los equipos creados con una etiqueta que no permite el acceso de invitados solo están disponibles para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="22169-131">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="22169-132">Las personas de fuera de su organización no se pueden agregar al equipo.</span><span class="sxs-lookup"><span data-stu-id="22169-132">People outside your organization can't be added to the team.</span></span>

## <a name="known-issues"></a><span data-ttu-id="22169-133">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="22169-133">Known issues</span></span>

<span data-ttu-id="22169-134">**Compatibilidad con etiquetas de confidencialidad en el centro de administración de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="22169-134">**Support for sensitivity labels in the Microsoft Teams admin center**</span></span>

<span data-ttu-id="22169-135">Actualmente, las etiquetas de confidencialidad no se admiten en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="22169-135">Currently, sensitivity labels are not supported in the Microsoft Teams admin center.</span></span> <span data-ttu-id="22169-136">Si utiliza etiquetas de confidencialidad, no podrá establecer etiquetas de confidencialidad al crear o editar un equipo.</span><span class="sxs-lookup"><span data-stu-id="22169-136">If you use sensitivity labels, you won't be able to set sensitivity labels when you create or edit a team.</span></span> <span data-ttu-id="22169-137">Las etiquetas de confidencialidad tampoco están visibles en las propiedades del equipo y no se podrán ver en la columna **clasificación** del centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="22169-137">Sensitivity labels are also not visible in team properties and won't be visible in the **Classification** column in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="22169-138">**Compatibilidad con etiquetas de confidencialidad en las API de Team Graph, plantillas y cmdlets de PowerShell**</span><span class="sxs-lookup"><span data-stu-id="22169-138">**Support for sensitivity labels in Teams Graph APIs, Powershell cmdlets and templates**</span></span>

<span data-ttu-id="22169-139">En la actualidad, los usuarios no podrán aplicar etiquetas de confidencialidad a los equipos que se crean directamente a través de las API de Graph, los cmdlets de PowerShell y las plantillas.</span><span class="sxs-lookup"><span data-stu-id="22169-139">Currently, users won't be able to apply sensitivity labels on teams that are created directly through Graph APIs, Powershell cmdlets, and templates.</span></span>

<span data-ttu-id="22169-140">**Editar las etiquetas de confidencialidad directamente en una colección de sitios de SharePoint para canales privados**</span><span class="sxs-lookup"><span data-stu-id="22169-140">**Editing sensitivity labels directly on a SharePoint site collection for private channels**</span></span>

<span data-ttu-id="22169-141">Los canales privados que se crean en un equipo heredan la etiqueta de confidencialidad que se aplicó a un equipo.</span><span class="sxs-lookup"><span data-stu-id="22169-141">Private channels that are created in a team inherit the sensitivity label which was applied on a team.</span></span> <span data-ttu-id="22169-142">Además, la misma etiqueta se aplica automáticamente en la colección de sitios de SharePoint para el canal privado.</span><span class="sxs-lookup"><span data-stu-id="22169-142">Furthermore, the same label is automatically applied on the SharePoint site collection for the private channel.</span></span>

<span data-ttu-id="22169-143">Si un usuario actualiza directamente la etiqueta de confidencialidad en una colección de sitios de SharePoint para un canal privado, esa etiqueta no se actualiza en el cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="22169-143">If a user directly updates the sensitivity label on a SharePoint site collection for a private channel, that label isn't updated in the Teams client.</span></span> <span data-ttu-id="22169-144">En este caso, los usuarios seguirán viendo la etiqueta de confidencialidad aplicada a un equipo en el encabezado de canal privado.</span><span class="sxs-lookup"><span data-stu-id="22169-144">In this scenario, users will continue to see the sensitivity label applied on a team in the private channel header.</span></span>

<span data-ttu-id="22169-145">**Horas de propagación para los cambios aplicados a las etiquetas de confidencialidad fuera de la aplicación de Teams**</span><span class="sxs-lookup"><span data-stu-id="22169-145">**Propagation times for changes applied to sensitivity labels outside the Teams app**</span></span>

<span data-ttu-id="22169-146">Los cambios realizados en las etiquetas de confidencialidad fuera de la aplicación Teams pueden demorar hasta 24 horas en reflejarse en la aplicación de Teams.</span><span class="sxs-lookup"><span data-stu-id="22169-146">Changes made to sensitivity labels outside the Teams app can take up to 24 hours to reflect in the Teams app.</span></span> <span data-ttu-id="22169-147">Esto se aplica a los cambios realizados para habilitar o deshabilitar las etiquetas de un espacio empresarial, los cambios en los nombres de etiqueta, la configuración y las directivas.</span><span class="sxs-lookup"><span data-stu-id="22169-147">This applies to any changes made to enable or disable labels for a tenant, changes to label names, settings, and policies.</span></span>

<span data-ttu-id="22169-148">Además, cualquier cambio en una etiqueta realizada directamente a un grupo o una colección de sitios de SharePoint que respalda al equipo puede demorar hasta 24 horas en propagarse a la aplicación de Teams.</span><span class="sxs-lookup"><span data-stu-id="22169-148">Additionally, any changes to a label made directly to a group or SharePoint site collection that backs the team can take up to 24 hours to propagate to the Teams app.</span></span>