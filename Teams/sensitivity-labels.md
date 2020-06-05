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
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo definir y usar etiquetas de confidencialidad en Microsoft Teams.
ms.openlocfilehash: 7f8eb7e0fa0d34ae21829a12011f094d8e9c9126
ms.sourcegitcommit: 2c23a8c5afc4a6b74c2c6d7487975a94fe99dc07
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "44562075"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="8880d-103">Etiquetas de confidencialidad para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8880d-103">Sensitivity labels for Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="8880d-104">Las [etiquetas de confidencialidad](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) permiten a los administradores de equipos regular el acceso a contenido de organización confidencial creado durante la colaboración dentro de Teams.</span><span class="sxs-lookup"><span data-stu-id="8880d-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="8880d-105">Puede definir las etiquetas de confidencialidad y las directivas asociadas en el [centro de cumplimiento de & de seguridad](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span><span class="sxs-lookup"><span data-stu-id="8880d-105">You can define sensitivity labels and their associated policies in the [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center).</span></span> <span data-ttu-id="8880d-106">Estas etiquetas y directivas se aplican automáticamente a los equipos de su organización.</span><span class="sxs-lookup"><span data-stu-id="8880d-106">These labels and policies are automatically applied to teams in your organization.</span></span>  

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="8880d-107">¿Cuál es la diferencia entre las etiquetas de confidencialidad y las etiquetas de clasificación de equipos?</span><span class="sxs-lookup"><span data-stu-id="8880d-107">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="8880d-108">Las etiquetas de confidencialidad son diferentes de las etiquetas de clasificación que requieren su creación con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8880d-108">Sensitivity labels are different from classification labels that require you to create them using PowerShell.</span></span> <span data-ttu-id="8880d-109">Las etiquetas de clasificación son cadenas de texto que se pueden asociar a un grupo pero que no tienen ninguna directiva real asociada.</span><span class="sxs-lookup"><span data-stu-id="8880d-109">Classification labels are text strings that can be associated with a group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="8880d-110">Use las etiquetas de clasificación como metadatos para aplicar manualmente las directivas a través de las herramientas y scripts internos.</span><span class="sxs-lookup"><span data-stu-id="8880d-110">You use classification labels as metadata to manually enforce policies through internal tools and scripts.</span></span>

<span data-ttu-id="8880d-111">Por otro lado, las etiquetas de confidencialidad y sus directivas se aplican de forma automática de principio a fin a través de una combinación de la plataforma de grupos, el centro de cumplimiento de & de seguridad y los servicios de Teams.</span><span class="sxs-lookup"><span data-stu-id="8880d-111">On the other hand, sensitivity labels and their policies are automatically enforced end-to-end through a combination of the Groups platform, Security & Compliance Center, and Teams services.</span></span> <span data-ttu-id="8880d-112">Las etiquetas de confidencialidad proporcionan una eficaz compatibilidad de infraestructura para proteger los datos confidenciales de su organización.</span><span class="sxs-lookup"><span data-stu-id="8880d-112">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data.</span></span>  

## <a name="create-manage-and-publish-sensitivity-labels-for-teams"></a><span data-ttu-id="8880d-113">Crear, administrar y publicar etiquetas de confidencialidad para equipos</span><span class="sxs-lookup"><span data-stu-id="8880d-113">Create, manage, and publish sensitivity labels for Teams</span></span>

<span data-ttu-id="8880d-114">Para obtener información sobre cómo habilitar, crear y publicar etiquetas de confidencialidad para equipos, consulte [usar etiquetas de confidencialidad con Microsoft Teams, grupos de microsoft 365 y sitios de SharePoint](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span><span class="sxs-lookup"><span data-stu-id="8880d-114">For how to enable, create, and publish sensitivity labels for Teams, see [Use sensitivity labels with Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>

>[!IMPORTANT]
><span data-ttu-id="8880d-115">Crear, actualizar y eliminar etiquetas de confidencialidad requieren una secuenciación cuidadosa con etiquetas de publicación para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8880d-115">Creating, updating and deleting sensitivity labels require careful sequencing with publishing labels to users.</span></span> <span data-ttu-id="8880d-116">Cualquier desviación en la secuencia puede dar lugar a errores de creación de equipo persistente para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8880d-116">Any deviation in the sequence can result in persistent team creation errors for all users.</span></span> <span data-ttu-id="8880d-117">Por lo tanto, es esencial que haga lo siguiente cuando <a href="#createpublishlabels">cree y publique etiquetas</a>, <a href="#modifydeletelabels">modifique y elimine etiquetas publicadas</a>y <a href="#manageerrors">administre errores de creación de equipos</a>.</span><span class="sxs-lookup"><span data-stu-id="8880d-117">Therefore, it's critical to do the following when you <a href="#createpublishlabels">create and publish labels</a>, <a href="#modifydeletelabels">modify and delete published labels</a>, and <a href="#manageerrors">manage team creation errors</a>.</span></span>

<span data-ttu-id="8880d-118">**Crear y publicar etiquetas** <a name="createpublishlabels"> </a></span><span class="sxs-lookup"><span data-stu-id="8880d-118">**Create and publish labels** <a name="createpublishlabels"> </a></span></span>

<span data-ttu-id="8880d-119">Cuando se crea una etiqueta y se publica en el centro de cumplimiento de seguridad &, la etiqueta puede tardar hasta 24 horas en verse en la interfaz de creación de equipos.</span><span class="sxs-lookup"><span data-stu-id="8880d-119">When a label is created and published in the Security & Compliance Center, it can take up to 24 hours for the label to become visible in the teams creation interface.</span></span> <span data-ttu-id="8880d-120">Realice los siguientes pasos para publicar la etiqueta de todos los usuarios del espacio empresarial:</span><span class="sxs-lookup"><span data-stu-id="8880d-120">Use the following steps to publish the label for all users in the tenant:</span></span>
1. <span data-ttu-id="8880d-121">Cree la etiqueta y publíquela para algunas cuentas de usuario seleccionadas en el inquilino.</span><span class="sxs-lookup"><span data-stu-id="8880d-121">Create the label and publish it for a few select user accounts in the tenant.</span></span>
2. <span data-ttu-id="8880d-122">Cuando se publique la etiqueta, espere 24 horas.</span><span class="sxs-lookup"><span data-stu-id="8880d-122">When the label is published, wait 24 hours.</span></span>
3. <span data-ttu-id="8880d-123">Después de 24 horas, intente crear un equipo con la etiqueta usando una de las cuentas de usuario que tengan acceso a la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="8880d-123">After 24 hours, try to create a team with the label using one of the user accounts that have access to the label.</span></span>
4. <span data-ttu-id="8880d-124">Si el equipo se creó correctamente en el paso 3, continúe y publique la etiqueta para el resto de usuarios del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="8880d-124">If the team successfully created in step 3, then go ahead and publish the label for the remaining users in the tenant.</span></span>

<span data-ttu-id="8880d-125">**Modificar y eliminar las etiquetas** <a name="modifydeletelabels"> </a> publicadas</span><span class="sxs-lookup"><span data-stu-id="8880d-125">**Modify and delete published labels** <a name="modifydeletelabels"> </a></span></span>

<span data-ttu-id="8880d-126">Eliminar o modificar la etiqueta mientras está asociada a directivas de confidencialidad puede dar lugar a errores en la creación del equipo en el inquilino.</span><span class="sxs-lookup"><span data-stu-id="8880d-126">Deleting or modifying the label while it's associated with sensitivity policies can result in team creation failures across the tenant.</span></span> <span data-ttu-id="8880d-127">Por lo tanto, antes de eliminar o modificar una etiqueta, primero debe desvincular la etiqueta de sus directivas asociadas.</span><span class="sxs-lookup"><span data-stu-id="8880d-127">Therefore, before you delete or modify a label, you must first disassociate the label from its associated policies.</span></span> <span data-ttu-id="8880d-128">Siga estos pasos</span><span class="sxs-lookup"><span data-stu-id="8880d-128">Use the following steps</span></span>  
<span data-ttu-id="8880d-129">para eliminar o modificar una etiqueta:</span><span class="sxs-lookup"><span data-stu-id="8880d-129">to delete or modify a label:</span></span>
1. <span data-ttu-id="8880d-130">Quite la etiqueta de todas las directivas que usan la etiqueta.</span><span class="sxs-lookup"><span data-stu-id="8880d-130">Remove the label from all policies that use the label.</span></span> <span data-ttu-id="8880d-131">También puede eliminar las directivas en sí.</span><span class="sxs-lookup"><span data-stu-id="8880d-131">Alternatively, you can also delete the policies themselves.</span></span>
2. <span data-ttu-id="8880d-132">Cuando se elimine la etiqueta de las directivas o se eliminen las directivas, espere 48 horas antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="8880d-132">When the label is removed from the policies or the policies themselves are deleted, wait 48 hours before proceeding further.</span></span>
3. <span data-ttu-id="8880d-133">Después de 48 horas, inicie la interfaz de creación de equipos y asegúrese de que la etiqueta ya no está visible para los usuarios del espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="8880d-133">After 48 hours, launch the team creation interface and ensure that the label is no longer visible for any user in the tenant.</span></span>
4. <span data-ttu-id="8880d-134">Ahora puede eliminar o modificar la etiqueta de forma segura.</span><span class="sxs-lookup"><span data-stu-id="8880d-134">Now you can safely delete or modify the label.</span></span>

<span data-ttu-id="8880d-135">**Administrar errores** <a name="manageerrors"> </a> de creación de equipos</span><span class="sxs-lookup"><span data-stu-id="8880d-135">**Manage team creation errors** <a name="manageerrors"> </a></span></span>

<span data-ttu-id="8880d-136">Si la creación del equipo comienza a fallar en cualquier momento durante la versión preliminar pública, tiene dos opciones:</span><span class="sxs-lookup"><span data-stu-id="8880d-136">If team creation begins to fail at any point during the public preview, you have two options:</span></span>
 - <span data-ttu-id="8880d-137">Asegúrese de que las etiquetas de confidencialidad no son obligatorias para ningún usuario durante la creación del equipo.</span><span class="sxs-lookup"><span data-stu-id="8880d-137">Ensure that sensitivity labels are not mandatory for any user during team creation.</span></span>
 - <span data-ttu-id="8880d-138">Desactive las etiquetas de confidencialidad usando los scripts en [habilitar esta vista previa](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview).</span><span class="sxs-lookup"><span data-stu-id="8880d-138">Turn off sensitivity labels using the scripts in [Enable this preview](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#enable-this-preview).</span></span>

<span data-ttu-id="8880d-139">Observe que la configuración EnableMIPLabels debe establecerse en falso de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="8880d-139">Note that the EnableMIPLabels setting must be set to false as follows:</span></span>

```console
$setting["EnableMIPLabels"] = "False"
```

## <a name="using-sensitivity-labels-with-teams"></a><span data-ttu-id="8880d-140">Usar etiquetas de confidencialidad con equipos</span><span class="sxs-lookup"><span data-stu-id="8880d-140">Using sensitivity labels with Teams</span></span>

<span data-ttu-id="8880d-141">A continuación se muestran algunos escenarios de ejemplo de cómo puede usar las etiquetas de confidencialidad con equipos de su organización.</span><span class="sxs-lookup"><span data-stu-id="8880d-141">Here are some example scenarios of how you can use sensitivity labels with Teams in your organization.</span></span>

### <a name="privacy-setting-of-teams"></a><span data-ttu-id="8880d-142">Configuración de privacidad de Teams</span><span class="sxs-lookup"><span data-stu-id="8880d-142">Privacy setting of teams</span></span>

<span data-ttu-id="8880d-143">Puede crear una etiqueta de confidencialidad que, cuando se aplique durante la creación del equipo, permita a los usuarios crear equipos con una configuración de privacidad (pública o privada) específica.</span><span class="sxs-lookup"><span data-stu-id="8880d-143">You can create a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="8880d-144">Por ejemplo, puede crear una etiqueta denominada "confidencial" en el centro de cumplimiento de & de seguridad y configurar Teams de modo que cualquier equipo que se cree con esta etiqueta debe ser un equipo privado.</span><span class="sxs-lookup"><span data-stu-id="8880d-144">For example, you create a label named “Confidential” in the Security & Compliance Center and you configure Teams so that any team that's created with this label must be a private team.</span></span> <span data-ttu-id="8880d-145">Cuando un usuario crea un nuevo equipo y selecciona la etiqueta **confidencial** , la única opción de privacidad que está disponible para el usuario es **privada**.</span><span class="sxs-lookup"><span data-stu-id="8880d-145">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="8880d-146">Otras opciones de privacidad, como público y toda la organización, están deshabilitadas para el usuario.</span><span class="sxs-lookup"><span data-stu-id="8880d-146">Other privacy options such as Public and Org-wide are disabled for the user.</span></span>

![Captura de pantalla de etiqueta confidencial confidencial](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="8880d-148">De forma similar, si el usuario selecciona **General** al crear un equipo nuevo, solo podrá crear equipos públicos o de toda la organización.</span><span class="sxs-lookup"><span data-stu-id="8880d-148">Similarly, if the user selects **General** when they create a new team, they can only create public or org-wide teams.</span></span>

![Captura de pantalla de etiqueta de confidencialidad general](media/sensitivity-labels-general-example.png)

<span data-ttu-id="8880d-150">Cuando se crea el equipo, la etiqueta de confidencialidad está visible en la esquina superior derecha de los canales del equipo.</span><span class="sxs-lookup"><span data-stu-id="8880d-150">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![Captura de pantalla de la etiqueta de confidencialidad en el canal de equipo](media/sensitivity-labels-channel.png)

<span data-ttu-id="8880d-152">El propietario de un equipo puede cambiar la etiqueta de confidencialidad y la configuración de privacidad del equipo en cualquier momento al ir al equipo y, a continuación, hacer clic en **Editar equipo**.</span><span class="sxs-lookup"><span data-stu-id="8880d-152">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then clicking **Edit team**.</span></span>

![Captura de pantalla de la etiqueta de confidencialidad en el canal de equipo](media/sensitivity-labels-edit-team.png)

### <a name="guest-access-to-teams"></a><span data-ttu-id="8880d-154">Acceso de invitado a equipos</span><span class="sxs-lookup"><span data-stu-id="8880d-154">Guest access to teams</span></span>

<span data-ttu-id="8880d-155">Puede especificar si un equipo creado con una etiqueta específica le permite el acceso de invitado.</span><span class="sxs-lookup"><span data-stu-id="8880d-155">You can specify whether a team created with a specific label allows guest access.</span></span> <span data-ttu-id="8880d-156">Los equipos creados con una etiqueta que no permite el acceso de invitados solo están disponibles para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="8880d-156">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="8880d-157">Las personas de fuera de su organización no se pueden agregar al equipo.</span><span class="sxs-lookup"><span data-stu-id="8880d-157">People outside your organization can't be added to the team.</span></span>

## <a name="known-issues"></a><span data-ttu-id="8880d-158">Problemas conocidos</span><span class="sxs-lookup"><span data-stu-id="8880d-158">Known issues</span></span>

<span data-ttu-id="8880d-159">**Compatibilidad con etiquetas de confidencialidad en el centro de administración de Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="8880d-159">**Support for sensitivity labels in the Microsoft Teams admin center**</span></span>

<span data-ttu-id="8880d-160">Actualmente, las etiquetas de confidencialidad no se admiten en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8880d-160">Currently, sensitivity labels are not supported in the Microsoft Teams admin center.</span></span> <span data-ttu-id="8880d-161">Si utiliza etiquetas de confidencialidad, no podrá establecer etiquetas de confidencialidad al crear o editar un equipo.</span><span class="sxs-lookup"><span data-stu-id="8880d-161">If you use sensitivity labels, you won't be able to set sensitivity labels when you create or edit a team.</span></span> <span data-ttu-id="8880d-162">Las etiquetas de confidencialidad tampoco están visibles en las propiedades del equipo y no se podrán ver en la columna **clasificación** del centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8880d-162">Sensitivity labels are also not visible in team properties and won't be visible in the **Classification** column in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="8880d-163">**Compatibilidad con etiquetas de confidencialidad en las API de Team Graph, plantillas y cmdlets de PowerShell**</span><span class="sxs-lookup"><span data-stu-id="8880d-163">**Support for sensitivity labels in Teams Graph APIs, Powershell cmdlets and templates**</span></span>

<span data-ttu-id="8880d-164">En la actualidad, los usuarios no podrán aplicar etiquetas de confidencialidad a los equipos que se crean directamente a través de las API de Graph, los cmdlets de PowerShell y las plantillas.</span><span class="sxs-lookup"><span data-stu-id="8880d-164">Currently, users won't be able to apply sensitivity labels on teams that are created directly through Graph APIs, Powershell cmdlets, and templates.</span></span>

<span data-ttu-id="8880d-165">**Compatibilidad con etiquetas de confidencialidad en SKU de los equipos EDU**</span><span class="sxs-lookup"><span data-stu-id="8880d-165">**Support for sensitivity labels in Teams EDU SKUs**</span></span>

<span data-ttu-id="8880d-166">Las etiquetas de confidencialidad actualmente no son compatibles con los clientes que usan las SKU de Educación de Teams.</span><span class="sxs-lookup"><span data-stu-id="8880d-166">Sensitivity labels are currently unsupported for customers using Teams Education SKUs.</span></span>

<span data-ttu-id="8880d-167">**Editar las etiquetas de confidencialidad directamente en una colección de sitios de SharePoint para canales privados**</span><span class="sxs-lookup"><span data-stu-id="8880d-167">**Editing sensitivity labels directly on a SharePoint site collection for private channels**</span></span>

<span data-ttu-id="8880d-168">Los canales privados que se crean en un equipo heredan la etiqueta de confidencialidad que se aplicó a un equipo.</span><span class="sxs-lookup"><span data-stu-id="8880d-168">Private channels that are created in a team inherit the sensitivity label which was applied on a team.</span></span> <span data-ttu-id="8880d-169">Además, la misma etiqueta se aplica automáticamente en la colección de sitios de SharePoint para el canal privado.</span><span class="sxs-lookup"><span data-stu-id="8880d-169">Furthermore, the same label is automatically applied on the SharePoint site collection for the private channel.</span></span>

<span data-ttu-id="8880d-170">Si un usuario actualiza directamente la etiqueta de confidencialidad en una colección de sitios de SharePoint para un canal privado, esa etiqueta no se actualiza en el cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="8880d-170">If a user directly updates the sensitivity label on a SharePoint site collection for a private channel, that label isn't updated in the Teams client.</span></span> <span data-ttu-id="8880d-171">En este caso, los usuarios seguirán viendo la etiqueta de confidencialidad aplicada a un equipo en el encabezado de canal privado.</span><span class="sxs-lookup"><span data-stu-id="8880d-171">In this scenario, users will continue to see the sensitivity label applied on a team in the private channel header.</span></span>

<span data-ttu-id="8880d-172">**Horas de propagación para los cambios aplicados a las etiquetas de confidencialidad fuera de la aplicación de Teams**</span><span class="sxs-lookup"><span data-stu-id="8880d-172">**Propagation times for changes applied to sensitivity labels outside the Teams app**</span></span>

<span data-ttu-id="8880d-173">Los cambios realizados en las etiquetas de confidencialidad fuera de la aplicación Teams pueden demorar hasta 24 horas en reflejarse en la aplicación de Teams.</span><span class="sxs-lookup"><span data-stu-id="8880d-173">Changes made to sensitivity labels outside the Teams app can take up to 24 hours to reflect in the Teams app.</span></span> <span data-ttu-id="8880d-174">Esto se aplica a los cambios realizados para habilitar o deshabilitar las etiquetas de un espacio empresarial, los cambios en los nombres de etiqueta, la configuración y las directivas.</span><span class="sxs-lookup"><span data-stu-id="8880d-174">This applies to any changes made to enable or disable labels for a tenant, changes to label names, settings, and policies.</span></span>

<span data-ttu-id="8880d-175">Además, cualquier cambio en una etiqueta realizada directamente a un grupo o una colección de sitios de SharePoint que respalda al equipo puede demorar hasta 24 horas en propagarse a la aplicación de Teams.</span><span class="sxs-lookup"><span data-stu-id="8880d-175">Additionally, any changes to a label made directly to a group or SharePoint site collection that backs the team can take up to 24 hours to propagate to the Teams app.</span></span>
