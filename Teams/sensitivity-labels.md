---
title: Etiquetas de confidencialidad para Microsoft Teams
ms.author: mikeplum
author: cabailey
manager: laurawi
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
description: Obtenga información sobre cómo usar etiquetas de confidencialidad para proteger sus equipos en Microsoft Teams.
ms.openlocfilehash: 3b994bd7f1aa8fbc1fde13aaf49b195a1698695a
ms.sourcegitcommit: 5473b9fcd2bfe8adeb05a4a8d23e4350c7970fb6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49937532"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="701ab-103">Etiquetas de confidencialidad de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="701ab-103">Sensitivity labels for Microsoft Teams</span></span>

<span data-ttu-id="701ab-104">[Las etiquetas de](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) confidencialidad permiten a los administradores de Teams proteger y regular el acceso al contenido organizativo confidencial creado durante la colaboración dentro de los equipos.</span><span class="sxs-lookup"><span data-stu-id="701ab-104">[Sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) allow Teams admins to protect and regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="701ab-105">Después de configurar las etiquetas de confidencialidad con las directivas asociadas en el Centro de cumplimiento [de Microsoft,](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center)estas etiquetas se pueden aplicar a los equipos de su organización.</span><span class="sxs-lookup"><span data-stu-id="701ab-105">After you configure sensitivity labels with their associated policies in the [Microsoft compliance center](https://docs.microsoft.com/microsoft-365/compliance/go-to-the-securitycompliance-center), these labels can be applied to teams in your organization.</span></span>

<span data-ttu-id="701ab-106">Las etiquetas de confidencialidad no son compatibles actualmente para los clientes que usan SKU de Teams Educación.</span><span class="sxs-lookup"><span data-stu-id="701ab-106">Sensitivity labels are currently unsupported for customers using Teams Education SKUs.</span></span> <span data-ttu-id="701ab-107">Para obtener más información sobre las licencias, consulte la [descripción del servicio Microsoft Teams.](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)</span><span class="sxs-lookup"><span data-stu-id="701ab-107">To learn more about licensing, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="701ab-108">¿Cuál es la diferencia entre las etiquetas de confidencialidad y las etiquetas de clasificación de Teams?</span><span class="sxs-lookup"><span data-stu-id="701ab-108">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="701ab-109">Las etiquetas de confidencialidad son diferentes de las etiquetas de clasificación, también conocidas como clasificación de grupos de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="701ab-109">Sensitivity labels are different from classification labels, also known as Azure AD group classification.</span></span> <span data-ttu-id="701ab-110">Las etiquetas de clasificación son cadenas de texto que se pueden asociar con un grupo de Microsoft 365 pero que no tienen directivas reales asociadas.</span><span class="sxs-lookup"><span data-stu-id="701ab-110">Classification labels are text strings that can be associated with a Microsoft 365 group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="701ab-111">Las etiquetas de clasificación se usan como metadatos y, a continuación, se deben usar otros métodos, como herramientas internas y scripts, para aplicar directivas.</span><span class="sxs-lookup"><span data-stu-id="701ab-111">You use classification labels as metadata and then must use other methods such as internal tools and scripts, to enforce policies.</span></span>

<span data-ttu-id="701ab-112">La ventaja de usar etiquetas de confidencialidad es que sus directivas se aplican automáticamente de un extremo a otro mediante una combinación de la plataforma de Grupos de Microsoft 365, el centro de cumplimiento y los servicios de Teams.</span><span class="sxs-lookup"><span data-stu-id="701ab-112">The benefit of using sensitivity labels is that their policies are automatically enforced end-to-end through a combination of the Microsoft 365 Groups platform, the compliance center, and Teams services.</span></span> <span data-ttu-id="701ab-113">Las etiquetas de confidencialidad ofrecen una potente compatibilidad de infraestructura para proteger los datos confidenciales de su organización y garantizar el cumplimiento de las directivas internas o normativas.</span><span class="sxs-lookup"><span data-stu-id="701ab-113">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data and ensuring compliance with your internal policies or regulations.</span></span>

<span data-ttu-id="701ab-114">Si actualmente usa etiquetas de clasificación, consulte la siguiente documentación para obtener más información e instrucciones sobre cómo migrarlas a etiquetas de confidencialidad: clasificación de grupos de [Azure AD clásica.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)</span><span class="sxs-lookup"><span data-stu-id="701ab-114">If you currently use classification labels, see the following documentation for more information and instructions how to migrate them to sensitivity labels: [Classic Azure AD group classification](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).</span></span>

## <a name="example-scenarios-for-sensitivity-labels"></a><span data-ttu-id="701ab-115">Escenarios de ejemplo para etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="701ab-115">Example scenarios for sensitivity labels</span></span>

<span data-ttu-id="701ab-116">Escenarios de ejemplo para usar etiquetas de confidencialidad con Teams en su organización:</span><span class="sxs-lookup"><span data-stu-id="701ab-116">Example scenarios for how you can use sensitivity labels with Teams in your organization:</span></span>

- [<span data-ttu-id="701ab-117">Establecer el nivel de privacidad (público o privado) para los equipos</span><span class="sxs-lookup"><span data-stu-id="701ab-117">Set the privacy level (public or private) for teams</span></span>](#set-the-privacy-level-for-teams)
- [<span data-ttu-id="701ab-118">Controlar el acceso de invitados a los equipos</span><span class="sxs-lookup"><span data-stu-id="701ab-118">Control guest access to teams</span></span>](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a><span data-ttu-id="701ab-119">Establecer el nivel de privacidad para teams</span><span class="sxs-lookup"><span data-stu-id="701ab-119">Set the privacy level for teams</span></span>

<span data-ttu-id="701ab-120">Puede crear y configurar una etiqueta de confidencialidad que, cuando se aplique durante la creación de equipos, permita a los usuarios crear equipos con una configuración de privacidad específica (pública o privada).</span><span class="sxs-lookup"><span data-stu-id="701ab-120">You can create and configure a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="701ab-121">Por ejemplo, puede crear y publicar una etiqueta de confidencialidad denominada "Confidencial" que tenga la opción de privacidad de etiqueta configurada como **Privado.**</span><span class="sxs-lookup"><span data-stu-id="701ab-121">For example, you create and publish a sensitivity label named "Confidential" that has the label privacy option configured as **Private**.</span></span> <span data-ttu-id="701ab-122">Como resultado, cualquier equipo que se cree con esta etiqueta debe ser un equipo privado.</span><span class="sxs-lookup"><span data-stu-id="701ab-122">As a result, any team that's created with this label must be a private team.</span></span> 

<span data-ttu-id="701ab-123">Cuando un usuario crea un equipo  y selecciona la etiqueta Confidencial, la única opción de privacidad que está disponible para el usuario es **Privado.**</span><span class="sxs-lookup"><span data-stu-id="701ab-123">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="701ab-124">Otras opciones de privacidad, como Público y toda la organización, no están disponibles para que el usuario seleccione:</span><span class="sxs-lookup"><span data-stu-id="701ab-124">Other privacy options such as Public and Org-wide aren't available for the user to select:</span></span>

![Captura de pantalla de la etiqueta de confidencialidad confidencial](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="701ab-126">De forma similar, cree y publique una etiqueta de confidencialidad denominada "General" que tenga la opción de privacidad de etiqueta configurada como **Pública.**</span><span class="sxs-lookup"><span data-stu-id="701ab-126">Similarly, you create and publish a sensitivity label named "General" that has the label privacy option configured as **Public**.</span></span> <span data-ttu-id="701ab-127">Cuando un usuario crea un equipo, solo puede crear equipos públicos o para toda la organización al seleccionar esta etiqueta:</span><span class="sxs-lookup"><span data-stu-id="701ab-127">When a user creates a new team, they can only create public or org-wide teams when they select this label:</span></span>

![Captura de pantalla de la etiqueta de confidencialidad general](media/sensitivity-labels-general-example.png)

<span data-ttu-id="701ab-129">Cuando se crea un equipo, la etiqueta de confidencialidad está visible en la esquina superior derecha de los canales del equipo.</span><span class="sxs-lookup"><span data-stu-id="701ab-129">When a team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span>

![Captura de pantalla de la etiqueta de confidencialidad en el canal del equipo](media/sensitivity-labels-channel.png)

<span data-ttu-id="701ab-131">El propietario de un equipo puede cambiar la etiqueta de confidencialidad y la configuración de privacidad del equipo en cualquier momento si va al equipo y, a continuación, hace clic **en Editar equipo.**</span><span class="sxs-lookup"><span data-stu-id="701ab-131">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then click **Edit team**.</span></span>

![Captura de pantalla de la etiqueta de confidencialidad en las propiedades del equipo](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a><span data-ttu-id="701ab-133">Controlar el acceso de invitados a los equipos</span><span class="sxs-lookup"><span data-stu-id="701ab-133">Control guest access to teams</span></span>

<span data-ttu-id="701ab-134">Puede usar etiquetas de confidencialidad para controlar el acceso de invitados a sus equipos.</span><span class="sxs-lookup"><span data-stu-id="701ab-134">You can use sensitivity labels to control guest access to your teams.</span></span> <span data-ttu-id="701ab-135">Los equipos creados con una etiqueta que no permite el acceso de invitado solo están disponibles para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="701ab-135">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="701ab-136">Las personas de fuera de su organización no se pueden agregar al equipo.</span><span class="sxs-lookup"><span data-stu-id="701ab-136">People outside your organization can't be added to the team.</span></span>

## <a name="microsoft-teams-admin-center"></a><span data-ttu-id="701ab-137">Centro de administración de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="701ab-137">Microsoft Teams admin center</span></span>

<span data-ttu-id="701ab-138">Puede aplicar etiquetas de confidencialidad al crear o editar un equipo en el Centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="701ab-138">You can apply sensitivity labels when you create or edit a team in the Microsoft Teams admin center.</span></span> 

<span data-ttu-id="701ab-139">Las etiquetas de confidencialidad también  están visibles en las propiedades del equipo y en la columna Clasificación de la página Administrar equipos del Centro de administración de Microsoft Teams. </span><span class="sxs-lookup"><span data-stu-id="701ab-139">Sensitivity labels are also visible in team properties and in the **Classification** column on the **Manage teams** page of the Microsoft Teams admin center.</span></span>

## <a name="limitations"></a><span data-ttu-id="701ab-140">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="701ab-140">Limitations</span></span>

<span data-ttu-id="701ab-141">Antes de usar etiquetas de confidencialidad para Teams, tenga en cuenta las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="701ab-141">Before you use sensitivity labels for Teams, be aware of the following limitations:</span></span>

- <span data-ttu-id="701ab-142">**Los nombres de etiqueta principal no se muestran para las sublabelas**</span><span class="sxs-lookup"><span data-stu-id="701ab-142">**Parent label names aren't displayed for sublabels**</span></span>
    
    <span data-ttu-id="701ab-143">Teams admite subatiquetas, pero no muestra el nombre de la etiqueta principal.</span><span class="sxs-lookup"><span data-stu-id="701ab-143">Teams supports sublabels but doesn't display the name of the parent label.</span></span> <span data-ttu-id="701ab-144">Por ejemplo, **Confidencial** \\ **para todos los empleados** se muestra como **Todos los empleados.**</span><span class="sxs-lookup"><span data-stu-id="701ab-144">For example, **Confidential** \\ **All Employees** displays as **All Employees**.</span></span>

- <span data-ttu-id="701ab-145">**Las etiquetas de confidencialidad no son compatibles con las API de Teams Graph, los cmdlets de PowerShell y las plantillas**</span><span class="sxs-lookup"><span data-stu-id="701ab-145">**Sensitivity labels aren't supported by Teams Graph APIs, PowerShell cmdlets, and templates**</span></span>
    
    <span data-ttu-id="701ab-146">Los usuarios no podrán aplicar etiquetas de confidencialidad a los equipos que se crean directamente a través de las API de Teams Graph, los cmdlets de PowerShell de Teams y las plantillas de Teams.</span><span class="sxs-lookup"><span data-stu-id="701ab-146">Users won't be able to apply sensitivity labels on teams that are created directly through Teams Graph APIs, Teams PowerShell cmdlets, and Teams templates.</span></span>

- <span data-ttu-id="701ab-147">**Compatibilidad con canales privados**</span><span class="sxs-lookup"><span data-stu-id="701ab-147">**Support for private channels**</span></span>
    
    <span data-ttu-id="701ab-148">Los canales privados que se crean en un equipo heredan la etiqueta de confidencialidad que se aplicó en un equipo.</span><span class="sxs-lookup"><span data-stu-id="701ab-148">Private channels that are created in a team inherit the sensitivity label that was applied on a team.</span></span> <span data-ttu-id="701ab-149">La misma etiqueta se aplica automáticamente en la colección de sitios de SharePoint para el canal privado.</span><span class="sxs-lookup"><span data-stu-id="701ab-149">The same label is automatically applied on the SharePoint site collection for the private channel.</span></span>
    
    <span data-ttu-id="701ab-150">Sin embargo, si un usuario cambia directamente la etiqueta de confidencialidad en un sitio de SharePoint para un canal privado, ese cambio de etiqueta no se refleja en el cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="701ab-150">However, if a user directly changes the sensitivity label on a SharePoint site for a private channel, that label change isn't reflected in the Teams client.</span></span> <span data-ttu-id="701ab-151">En este escenario, los usuarios seguirán ven la etiqueta de confidencialidad original aplicada al equipo en el encabezado de canal privado.</span><span class="sxs-lookup"><span data-stu-id="701ab-151">In this scenario, users continue to see the original sensitivity label applied on the team in the private channel header.</span></span>

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a><span data-ttu-id="701ab-152">Cómo crear y configurar etiquetas de confidencialidad para Teams</span><span class="sxs-lookup"><span data-stu-id="701ab-152">How to create and configure sensitivity labels for Teams</span></span>

<span data-ttu-id="701ab-153">Use las instrucciones de la documentación de Microsoft 365 para crear y configurar etiquetas de confidencialidad para Teams:</span><span class="sxs-lookup"><span data-stu-id="701ab-153">Use the instructions from the Microsoft 365 documentation to create and configure sensitivity labels for Teams:</span></span> 

- <span data-ttu-id="701ab-154">[Use etiquetas de confidencialidad para proteger el contenido en Microsoft Teams, grupos de Microsoft 365 y sitios de SharePoint.](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)</span><span class="sxs-lookup"><span data-stu-id="701ab-154">[Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>
