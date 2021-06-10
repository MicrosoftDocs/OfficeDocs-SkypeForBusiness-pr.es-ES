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
description: Obtenga información sobre cómo usar etiquetas de confidencialidad para proteger los equipos en Microsoft Teams.
ms.openlocfilehash: 461daf6e91f9ba276dceef1929601d1188563931
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593868"
---
# <a name="sensitivity-labels-for-microsoft-teams"></a><span data-ttu-id="16f28-103">Etiquetas de confidencialidad para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="16f28-103">Sensitivity labels for Microsoft Teams</span></span>

<span data-ttu-id="16f28-104">[Las etiquetas](/microsoft-365/compliance/sensitivity-labels) de confidencialidad Teams los administradores pueden proteger y regular el acceso al contenido organizativo confidencial creado durante la colaboración en equipos.</span><span class="sxs-lookup"><span data-stu-id="16f28-104">[Sensitivity labels](/microsoft-365/compliance/sensitivity-labels) allow Teams admins to protect and regulate access to sensitive organizational content created during collaboration within teams.</span></span> <span data-ttu-id="16f28-105">Después de configurar etiquetas de confidencialidad con sus directivas asociadas en el Centro de cumplimiento de [Microsoft,](/microsoft-365/compliance/go-to-the-securitycompliance-center)estas etiquetas se pueden aplicar a los equipos de su organización.</span><span class="sxs-lookup"><span data-stu-id="16f28-105">After you configure sensitivity labels with their associated policies in the [Microsoft compliance center](/microsoft-365/compliance/go-to-the-securitycompliance-center), these labels can be applied to teams in your organization.</span></span>

<span data-ttu-id="16f28-106">Actualmente, las etiquetas de confidencialidad no son compatibles en los equipos de clase para los clientes que usan Teams SKU de educación.</span><span class="sxs-lookup"><span data-stu-id="16f28-106">Sensitivity labels are currently unsupported in class teams for customers using Teams Education SKUs.</span></span> <span data-ttu-id="16f28-107">Para obtener más información sobre las licencias, [vea Microsoft Teams descripción del servicio](/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="16f28-107">To learn more about licensing, see [Microsoft Teams service description](/office365/servicedescriptions/teams-service-description).</span></span>

## <a name="whats-the-difference-between-sensitivity-labels-and-teams-classification-labels"></a><span data-ttu-id="16f28-108">¿Cuál es la diferencia entre las etiquetas de confidencialidad Teams etiquetas de clasificación?</span><span class="sxs-lookup"><span data-stu-id="16f28-108">What's the difference between sensitivity labels and Teams classification labels?</span></span>

<span data-ttu-id="16f28-109">Las etiquetas de confidencialidad son diferentes de las etiquetas de clasificación, también conocidas como clasificación de grupo de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="16f28-109">Sensitivity labels are different from classification labels, also known as Azure AD group classification.</span></span> <span data-ttu-id="16f28-110">Las etiquetas de clasificación son cadenas de texto que se pueden asociar a un grupo Microsoft 365 pero que no tienen ninguna directiva real asociada.</span><span class="sxs-lookup"><span data-stu-id="16f28-110">Classification labels are text strings that can be associated with a Microsoft 365 group but don't have any actual policies associated with them.</span></span> <span data-ttu-id="16f28-111">Use etiquetas de clasificación como metadatos y, a continuación, debe usar otros métodos, como herramientas internas y scripts, para aplicar directivas.</span><span class="sxs-lookup"><span data-stu-id="16f28-111">You use classification labels as metadata and then must use other methods such as internal tools and scripts, to enforce policies.</span></span>

<span data-ttu-id="16f28-112">La ventaja de usar etiquetas de confidencialidad es que sus directivas se aplican automáticamente de un extremo a otro a través de una combinación de la plataforma grupos de Microsoft 365, el centro de cumplimiento y Teams servicios.</span><span class="sxs-lookup"><span data-stu-id="16f28-112">The benefit of using sensitivity labels is that their policies are automatically enforced end-to-end through a combination of the Microsoft 365 Groups platform, the compliance center, and Teams services.</span></span> <span data-ttu-id="16f28-113">Las etiquetas de confidencialidad proporcionan un soporte de infraestructura eficaz para proteger los datos confidenciales de su organización y garantizar el cumplimiento de sus directivas internas o normativas.</span><span class="sxs-lookup"><span data-stu-id="16f28-113">Sensitivity labels provide powerful infrastructure support for securing your organization's sensitive data and ensuring compliance with your internal policies or regulations.</span></span>

<span data-ttu-id="16f28-114">Si actualmente usa etiquetas de clasificación, consulte la documentación siguiente para obtener más información e instrucciones sobre cómo migrarlas a etiquetas de confidencialidad: clasificación de grupo clásica [de Azure AD.](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification)</span><span class="sxs-lookup"><span data-stu-id="16f28-114">If you currently use classification labels, see the following documentation for more information and instructions how to migrate them to sensitivity labels: [Classic Azure AD group classification](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites#classic-azure-ad-group-classification).</span></span>

## <a name="example-scenarios-for-sensitivity-labels"></a><span data-ttu-id="16f28-115">Escenarios de ejemplo para etiquetas de confidencialidad</span><span class="sxs-lookup"><span data-stu-id="16f28-115">Example scenarios for sensitivity labels</span></span>

<span data-ttu-id="16f28-116">Escenarios de ejemplo para usar etiquetas de confidencialidad con Teams en su organización:</span><span class="sxs-lookup"><span data-stu-id="16f28-116">Example scenarios for how you can use sensitivity labels with Teams in your organization:</span></span>

- [<span data-ttu-id="16f28-117">Establecer el nivel de privacidad (público o privado) de los equipos</span><span class="sxs-lookup"><span data-stu-id="16f28-117">Set the privacy level (public or private) for teams</span></span>](#set-the-privacy-level-for-teams)
- [<span data-ttu-id="16f28-118">Controlar el acceso de invitado a los equipos</span><span class="sxs-lookup"><span data-stu-id="16f28-118">Control guest access to teams</span></span>](#control-guest-access-to-teams)

### <a name="set-the-privacy-level-for-teams"></a><span data-ttu-id="16f28-119">Establecer el nivel de privacidad de los equipos</span><span class="sxs-lookup"><span data-stu-id="16f28-119">Set the privacy level for teams</span></span>

<span data-ttu-id="16f28-120">Puede crear y configurar una etiqueta de confidencialidad que, cuando se aplica durante la creación de equipos, permite a los usuarios crear equipos con una configuración de privacidad específica (pública o privada).</span><span class="sxs-lookup"><span data-stu-id="16f28-120">You can create and configure a sensitivity label that, when applied during team creation, allows users to create teams with a specific privacy (public or private) setting.</span></span>

<span data-ttu-id="16f28-121">Por ejemplo, crea y publica una etiqueta de confidencialidad denominada "Confidencial" que tiene la opción de privacidad de etiqueta configurada como **Privado.**</span><span class="sxs-lookup"><span data-stu-id="16f28-121">For example, you create and publish a sensitivity label named "Confidential" that has the label privacy option configured as **Private**.</span></span> <span data-ttu-id="16f28-122">Como resultado, cualquier equipo que se cree con esta etiqueta debe ser un equipo privado.</span><span class="sxs-lookup"><span data-stu-id="16f28-122">As a result, any team that's created with this label must be a private team.</span></span> 

<span data-ttu-id="16f28-123">Cuando un usuario crea un equipo  y selecciona la etiqueta Confidencial, la única opción de privacidad disponible para el usuario es **Privado.**</span><span class="sxs-lookup"><span data-stu-id="16f28-123">When a user creates a new team and selects the **Confidential** label, the only privacy option that's available to the user is **Private**.</span></span> <span data-ttu-id="16f28-124">Otras opciones de privacidad como Público y Toda la organización no están disponibles para que el usuario seleccione:</span><span class="sxs-lookup"><span data-stu-id="16f28-124">Other privacy options such as Public and Org-wide aren't available for the user to select:</span></span>

![Captura de pantalla de la etiqueta confidencialidad](media/sensitivity-labels-confidential-example.png)

<span data-ttu-id="16f28-126">De forma similar, cree y publique una etiqueta de confidencialidad denominada "General" que tenga la opción de privacidad de etiqueta configurada como **Público.**</span><span class="sxs-lookup"><span data-stu-id="16f28-126">Similarly, you create and publish a sensitivity label named "General" that has the label privacy option configured as **Public**.</span></span> <span data-ttu-id="16f28-127">Cuando un usuario crea un equipo nuevo, solo puede crear equipos públicos o de toda la organización al seleccionar esta etiqueta:</span><span class="sxs-lookup"><span data-stu-id="16f28-127">When a user creates a new team, they can only create public or org-wide teams when they select this label:</span></span>

![Captura de pantalla de la etiqueta confidencialidad general](media/sensitivity-labels-general-example.png)

<span data-ttu-id="16f28-129">Cuando se crea el equipo, la etiqueta de confidencialidad está visible en la esquina superior derecha de los canales del equipo.</span><span class="sxs-lookup"><span data-stu-id="16f28-129">When the team is created, the sensitivity label is visible in the upper-right corner of channels in the team.</span></span> 

> [!NOTE]
> <span data-ttu-id="16f28-130">Si usa etiquetas jerárquicas de elementos primarios y secundarios como "Confidencial\Finanzas", solo se mostrará la etiqueta principal en el encabezado del canal.</span><span class="sxs-lookup"><span data-stu-id="16f28-130">If you are using hierarchical parent-child labels such as "Confidential\Finance", then only the parent label will be shown in the channel header.</span></span>

![Captura de pantalla de la etiqueta de confidencialidad en el canal de grupo](media/sensitivity-labels-channel.png)

<span data-ttu-id="16f28-132">El propietario de un equipo puede cambiar la etiqueta de confidencialidad y la configuración de privacidad del equipo en cualquier momento yendo al equipo y, a continuación, haga clic **en Editar equipo.**</span><span class="sxs-lookup"><span data-stu-id="16f28-132">A team owner can change the sensitivity label and the privacy setting of the team at any time by going to the team, and then click **Edit team**.</span></span>

![Captura de pantalla de etiqueta de confidencialidad en las propiedades del equipo](media/sensitivity-labels-edit-team.png)

### <a name="control-guest-access-to-teams"></a><span data-ttu-id="16f28-134">Controlar el acceso de invitado a los equipos</span><span class="sxs-lookup"><span data-stu-id="16f28-134">Control guest access to teams</span></span>

<span data-ttu-id="16f28-135">Puede usar etiquetas de confidencialidad para controlar el acceso de invitado a sus equipos.</span><span class="sxs-lookup"><span data-stu-id="16f28-135">You can use sensitivity labels to control guest access to your teams.</span></span> <span data-ttu-id="16f28-136">Teams creados con una etiqueta que no permite el acceso de invitado solo están disponibles para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="16f28-136">Teams created with a label that doesn't allow guest access are only available to users in your organization.</span></span> <span data-ttu-id="16f28-137">Las personas de fuera de su organización no se pueden agregar al equipo.</span><span class="sxs-lookup"><span data-stu-id="16f28-137">People outside your organization can't be added to the team.</span></span>

## <a name="microsoft-teams-admin-center"></a><span data-ttu-id="16f28-138">Microsoft Teams de administración</span><span class="sxs-lookup"><span data-stu-id="16f28-138">Microsoft Teams admin center</span></span>

<span data-ttu-id="16f28-139">Puede aplicar etiquetas de confidencialidad al crear o editar un equipo en el centro Microsoft Teams administración.</span><span class="sxs-lookup"><span data-stu-id="16f28-139">You can apply sensitivity labels when you create or edit a team in the Microsoft Teams admin center.</span></span> 

<span data-ttu-id="16f28-140">Las etiquetas de confidencialidad también  están visibles en las propiedades del equipo y en la columna Clasificación de la página Administrar equipos del centro Microsoft Teams administración. </span><span class="sxs-lookup"><span data-stu-id="16f28-140">Sensitivity labels are also visible in team properties and in the **Classification** column on the **Manage teams** page of the Microsoft Teams admin center.</span></span>

## <a name="limitations"></a><span data-ttu-id="16f28-141">Limitaciones</span><span class="sxs-lookup"><span data-stu-id="16f28-141">Limitations</span></span>

<span data-ttu-id="16f28-142">Antes de usar etiquetas de Teams, tenga en cuenta las siguientes limitaciones:</span><span class="sxs-lookup"><span data-stu-id="16f28-142">Before you use sensitivity labels for Teams, be aware of the following limitations:</span></span>

- <span data-ttu-id="16f28-143">**Los nombres de etiquetas primarias no se muestran para etiquetas subatiquetas**</span><span class="sxs-lookup"><span data-stu-id="16f28-143">**Parent label names aren't displayed for sublabels**</span></span>
    
    <span data-ttu-id="16f28-144">Teams admite subetiquetas, pero no muestra el nombre de la etiqueta principal.</span><span class="sxs-lookup"><span data-stu-id="16f28-144">Teams supports sublabels but doesn't display the name of the parent label.</span></span> <span data-ttu-id="16f28-145">Por ejemplo, **Confidencial** \\ **Todos los empleados** se muestra **como Todos los empleados.**</span><span class="sxs-lookup"><span data-stu-id="16f28-145">For example, **Confidential** \\ **All Employees** displays as **All Employees**.</span></span>

- <span data-ttu-id="16f28-146">**Las etiquetas de confidencialidad no son compatibles Teams Graph API, cmdlets de PowerShell y plantillas**</span><span class="sxs-lookup"><span data-stu-id="16f28-146">**Sensitivity labels aren't supported by Teams Graph APIs, PowerShell cmdlets, and templates**</span></span>
    
    <span data-ttu-id="16f28-147">Los usuarios no podrán especificar etiquetas de confidencialidad al crear equipos directamente a través de Teams Graph API, Teams cmdlets de PowerShell y Teams plantillas.</span><span class="sxs-lookup"><span data-stu-id="16f28-147">Users won't be able to specify sensitivity labels while creating teams directly through Teams Graph APIs, Teams PowerShell cmdlets, and Teams templates.</span></span> <span data-ttu-id="16f28-148">Sin embargo, los grupos Graph API y cmdlets de PowerShell permiten la creación de grupos con etiquetas.</span><span class="sxs-lookup"><span data-stu-id="16f28-148">However Modern Groups Graph APIs and PowerShell cmdlets do allow creation of groups with labels.</span></span> <span data-ttu-id="16f28-149">Para que los usuarios primero puedan crear grupos con etiquetas con grupos Graph API o cmdlets de PowerShell y, después, convertir estos grupos en Teams.</span><span class="sxs-lookup"><span data-stu-id="16f28-149">So users can first create Groups with labels using Groups Graph APIs or PowerShell cmdlets and then convert these Groups in to Teams.</span></span>

- <span data-ttu-id="16f28-150">**Compatibilidad con canales privados**</span><span class="sxs-lookup"><span data-stu-id="16f28-150">**Support for private channels**</span></span>
    
    <span data-ttu-id="16f28-151">Los canales privados que se crean en un equipo heredan la etiqueta de confidencialidad que se aplicó en un equipo.</span><span class="sxs-lookup"><span data-stu-id="16f28-151">Private channels that are created in a team inherit the sensitivity label that was applied on a team.</span></span> <span data-ttu-id="16f28-152">La misma etiqueta se aplica automáticamente en la SharePoint de sitios del canal privado.</span><span class="sxs-lookup"><span data-stu-id="16f28-152">The same label is automatically applied on the SharePoint site collection for the private channel.</span></span>
    
    <span data-ttu-id="16f28-153">Sin embargo, si un usuario cambia directamente la etiqueta de confidencialidad en un sitio de SharePoint para un canal privado, ese cambio de etiqueta no se refleja en el Teams cliente.</span><span class="sxs-lookup"><span data-stu-id="16f28-153">However, if a user directly changes the sensitivity label on a SharePoint site for a private channel, that label change isn't reflected in the Teams client.</span></span> <span data-ttu-id="16f28-154">En este escenario, los usuarios siguen ven la etiqueta de confidencialidad original aplicada en el equipo en el encabezado del canal privado.</span><span class="sxs-lookup"><span data-stu-id="16f28-154">In this scenario, users continue to see the original sensitivity label applied on the team in the private channel header.</span></span>

## <a name="how-to-create-and-configure-sensitivity-labels-for-teams"></a><span data-ttu-id="16f28-155">Cómo crear y configurar etiquetas de confidencialidad para Teams</span><span class="sxs-lookup"><span data-stu-id="16f28-155">How to create and configure sensitivity labels for Teams</span></span>

<span data-ttu-id="16f28-156">Use las instrucciones de la documentación Microsoft 365 para crear y configurar etiquetas de confidencialidad para Teams:</span><span class="sxs-lookup"><span data-stu-id="16f28-156">Use the instructions from the Microsoft 365 documentation to create and configure sensitivity labels for Teams:</span></span> 

- <span data-ttu-id="16f28-157">[Use etiquetas de confidencialidad para](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)proteger el contenido Microsoft Teams, Microsoft 365 grupos y SharePoint sitios .</span><span class="sxs-lookup"><span data-stu-id="16f28-157">[Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span>
