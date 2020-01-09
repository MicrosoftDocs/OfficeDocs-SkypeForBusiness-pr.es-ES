---
title: Administrar la detección de equipos privados en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: shpoddar
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
description: Obtenga información sobre cómo controlar si los usuarios de Microsoft Teams pueden descubrir los equipos privados mediante sugerencias de la galería de equipos y resultados de la búsqueda.
ms.openlocfilehash: e2e0ec956b40ff5e84bb29874c0dc567edefd034
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992015"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a><span data-ttu-id="dbfb9-103">Administrar la detección de equipos privados en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dbfb9-103">Manage discovery of private teams in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="dbfb9-104">Los administradores y los propietarios del equipo pueden controlar si los usuarios de Microsoft Teams pueden descubrir equipos privados de su organización.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-104">Admins and team owners can control whether private teams can be discovered by Microsoft Teams users in your organization.</span></span> <span data-ttu-id="dbfb9-105">Cuando se detecta un equipo privado, se muestra en los resultados de la búsqueda y se incluye en las sugerencias de la galería de equipo junto con los equipos públicos de Teams.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-105">When a private team is discoverable, it shows up in search results and is included in suggestions in the team gallery alongside public teams in Teams.</span></span> <span data-ttu-id="dbfb9-106">Esto facilita que los usuarios busquen y encuentren a los equipos privados a los que desean unirse.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-106">This makes it easy for users to search for and find the private teams that they want to join.</span></span> <span data-ttu-id="dbfb9-107">Los usuarios pueden solicitar unirse a un equipo privado y un propietario del equipo puede aprobar o denegar la solicitud.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-107">Users can request to join a private team, and a team owner can then approve or deny the request.</span></span>

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a><span data-ttu-id="dbfb9-108">Información general sobre los equipos públicos, los equipos privados y el descubrimiento en Teams</span><span class="sxs-lookup"><span data-stu-id="dbfb9-108">Overview of public teams, private teams, and discovery in Teams</span></span>

<span data-ttu-id="dbfb9-109">La mayoría de las organizaciones tienen los siguientes tipos de equipos: equipos públicos, equipos privados que se pueden descubrir y equipos privados que no se pueden descubrir.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-109">Most organizations have the following kinds of teams: public teams, discoverable private teams, and non-discoverable private teams.</span></span>

![Captura de pantalla de la galería de equipos](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a><span data-ttu-id="dbfb9-111">Equipos públicos</span><span class="sxs-lookup"><span data-stu-id="dbfb9-111">Public teams</span></span>

<span data-ttu-id="dbfb9-112">Los equipos públicos están disponibles para que todos los usuarios de su organización se unan.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-112">Public teams are available for all users in your organization to join.</span></span> <span data-ttu-id="dbfb9-113">Los equipos públicos están visibles para todos los usuarios de la galería de equipos y los usuarios pueden unirse a un equipo público sin tener que obtener la aprobación del propietario del equipo.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-113">Public teams are visible to everyone in the teams gallery, and users can join a public team without having to get approval from the team owner.</span></span> <span data-ttu-id="dbfb9-114">Entre los ejemplos de equipos públicos se incluye un equipo para debatir noticias sobre tecnología, un equipo para obtener comentarios sobre sus productos y un equipo para que los usuarios carpooling trabajar.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-114">Examples of public teams include a team to discuss technology news, a team to get feedback for your products, and a team for people carpooling to work.</span></span>

### <a name="discoverable-private-teams"></a><span data-ttu-id="dbfb9-115">Equipos privados que se pueden descubrir</span><span class="sxs-lookup"><span data-stu-id="dbfb9-115">Discoverable private teams</span></span>

<span data-ttu-id="dbfb9-116">Los equipos privados que se pueden descubrir solo se pueden unir cuando el propietario del equipo les agregue usuarios.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-116">Discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="dbfb9-117">Cuando hace que un equipo privado sea reconocible, el equipo está incluido en la lista de equipos sugeridos y resultados de la búsqueda de la galería de equipos.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-117">When you make a private team discoverable, the team is included in the list of suggested teams and search results in the teams gallery.</span></span> <span data-ttu-id="dbfb9-118">Use equipos privados detectables para los proyectos y grupos de su organización que conozcan todos los usuarios y donde sea necesario controlar el acceso a las conversaciones y los archivos del equipo.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-118">Use discoverable private teams for projects and groups in your organization that everyone is aware of and where access to conversations and files in the team need to be controlled.</span></span> <span data-ttu-id="dbfb9-119">Los ejemplos incluyen un equipo para el Departamento de recursos humanos, un equipo para todos los administradores de su organización y un equipo para un administrador y sus subordinados directos.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-119">Examples include a team for your HR department, a team for all managers in your organization, and a team for a manager and their direct reports.</span></span>

### <a name="non-discoverable-private-teams"></a><span data-ttu-id="dbfb9-120">Equipos privados no exportadas</span><span class="sxs-lookup"><span data-stu-id="dbfb9-120">Non-discoverable private teams</span></span>

<span data-ttu-id="dbfb9-121">Los equipos privados no detectables solo se pueden unir cuando el propietario del equipo les agregue usuarios.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-121">Non-discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="dbfb9-122">Cuando hace que un equipo privado no sea reconocible, se oculta de la lista de equipos sugeridos y se ha eliminado de los resultados de la búsqueda en la galería de equipos.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-122">When you make a private team not discoverable, it's hidden from the list of suggested teams and removed from search results in the teams gallery.</span></span> <span data-ttu-id="dbfb9-123">Use equipos no exportadas para colaborar en temas confidenciales y muy confidenciales.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-123">Use non-discoverable teams to collaborate on sensitive and highly confidential topics.</span></span> <span data-ttu-id="dbfb9-124">Algunos ejemplos incluyen un equipo para discutir una próxima adquisición y un equipo para discutir un cambio en la dirección estratégica de su organización.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-124">Examples include a team to discuss an upcoming acquisition and a team to discuss a change in your organization's strategic direction.</span></span>

## <a name="set-whether-new-private-teams-are-discoverable"></a><span data-ttu-id="dbfb9-125">Establecer si los nuevos equipos privados se pueden descubrir</span><span class="sxs-lookup"><span data-stu-id="dbfb9-125">Set whether new private teams are discoverable</span></span>

<span data-ttu-id="dbfb9-126">Cuando un propietario de equipo crea un equipo privado, puede elegir que sea reconocible configurando la configuración de detección del equipo.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-126">When a team owner creates a private team, they can choose to make it discoverable by configuring the team's discovery setting.</span></span> <span data-ttu-id="dbfb9-127">De forma predeterminada, los nuevos equipos privados se pueden buscar y descubrir.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-127">By default, new private teams are searchable and discoverable.</span></span> <span data-ttu-id="dbfb9-128">Si el propietario del equipo no desea que el equipo privado se muestre en los resultados de búsqueda y las sugerencias, el propietario puede desactivar la configuración seleccionando **Cambiar configuración** junto a **este equipo es buscable y reconocible**.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-128">If the team owner doesn't want the private team to show up in search results and suggestions, the owner can turn off the setting by selecting **Change setting** next to **This team is searchable and discoverable**.</span></span>

![Captura de pantalla de la configuración de detección para nuevos equipos privados](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a><span data-ttu-id="dbfb9-130">Establecer si los equipos privados existentes se pueden descubrir</span><span class="sxs-lookup"><span data-stu-id="dbfb9-130">Set whether existing private teams are discoverable</span></span>

<span data-ttu-id="dbfb9-131">Los propietarios de equipo pueden establecer la configuración de detección de un equipo privado existente directamente en la configuración del equipo y los administradores pueden hacerlo con PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-131">Team owners can set the discovery setting for an existing private team directly in the team settings and admins can do so by using PowerShell.</span></span>

### <a name="in-team-settings"></a><span data-ttu-id="dbfb9-132">En la configuración del equipo</span><span class="sxs-lookup"><span data-stu-id="dbfb9-132">In team settings</span></span>

<span data-ttu-id="dbfb9-133">En Teams, vaya al equipo privado, haga clic en **más opciones** > **administrar equipo**.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-133">In Teams, go to the private team, click **More options** > **Manage team**.</span></span> <span data-ttu-id="dbfb9-134">En la pestaña **configuración** , expanda descubrimiento de equipo y, a continuación, Active o desactive la casilla **de verificación Activar** el **descubrimiento**.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-134">On the **Settings** tab, expand **Team discovery**, and then clear or select the **Turn on discoverability** check box.</span></span>

![Captura de pantalla de la configuración de detección para equipos privados existentes](media/private-team-discovery-existing-team.png)

### <a name="using-powershell"></a><span data-ttu-id="dbfb9-136">Usar PowerShell</span><span class="sxs-lookup"><span data-stu-id="dbfb9-136">Using PowerShell</span></span>

<span data-ttu-id="dbfb9-137">Use el cmdlet **[set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps)** para desactivar o activar la configuración de detección de un equipo privado existente.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-137">Use the **[Set-Team](https://docs.microsoft.com/powershell/module/teams/set-team?view=teams-ps)** cmdlet to turn off or turn on the discovery setting for an existing private team.</span></span> <span data-ttu-id="dbfb9-138">Este es un ejemplo de cómo hacer que un equipo sea reconocible:</span><span class="sxs-lookup"><span data-stu-id="dbfb9-138">Here's an example of how to make a team discoverable:</span></span>
```PowerShell
    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInTeamsSearchAndSuggestions $true
```
<span data-ttu-id="dbfb9-139">Puede usar este cmdlet en un script para establecer la configuración de detección de equipos privados existentes en masa.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-139">You can use this cmdlet in a script to set the discovery setting of existing private teams in bulk.</span></span>

## <a name="set-whether-users-can-discover-private-teams"></a><span data-ttu-id="dbfb9-140">Establecer si los usuarios pueden descubrir equipos privados</span><span class="sxs-lookup"><span data-stu-id="dbfb9-140">Set whether users can discover private teams</span></span>

<span data-ttu-id="dbfb9-141">Como administrador, también puede controlar los usuarios de su organización que pueden detectar equipos privados en los resultados de búsqueda y sugerencias de Teams.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-141">As an admin, you can also control which users in your organization are allowed to discover private teams in search results and suggestions in Teams.</span></span> <span data-ttu-id="dbfb9-142">Cree una directiva con el cmdlet **[New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)** y, a continuación, asigne la Directiva a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-142">Create a policy by using the **[New-CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)** cmdlet, and then assign the policy to users.</span></span>
 
<span data-ttu-id="dbfb9-143">Establezca el parámetro **AllowPrivateTeamDiscovery** en **true** para permitir que los usuarios a los que se les asigne la Directiva vean equipos privados que se pueden descubrir en resultados y sugerencias de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-143">Set the **AllowPrivateTeamDiscovery** parameter to **true** to allow users who are assigned the policy to see discoverable private teams in search results and suggestions.</span></span> <span data-ttu-id="dbfb9-144">Al establecer el parámetro **AllowPrivateTeamDiscovery** en **false** , se quitan todos los equipos privados detectables de los resultados de búsqueda y sugerencias para los usuarios que tienen asignada la Directiva.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-144">Setting the **AllowPrivateTeamDiscovery** parameter to **false** removes all discoverable private teams from search results and suggestions for users who are assigned the policy.</span></span>

<span data-ttu-id="dbfb9-145">De forma predeterminada, **AllowPrivateTeamDiscovery** se establece en **true** para todos los usuarios de una organización.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-145">By default, **AllowPrivateTeamDiscovery** is set to **true** for all users in an organization.</span></span>

<span data-ttu-id="dbfb9-146">En este ejemplo, creamos una directiva denominada VendorPolicy que impide que los usuarios descubran equipos privados que se hacen detectables y, a continuación, asignamos la Directiva a un usuario denominado vendoruser1.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-146">In this example, we create a policy named VendorPolicy that prevents users from discovering any private teams that are made discoverable, and then we assign the policy to a user named vendoruser1.</span></span>
```PowerShell
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy
```

> [!NOTE]
> <span data-ttu-id="dbfb9-147">Los equipos privados que no se pueden detectar nunca se muestran en los resultados de la búsqueda ni en las sugerencias, independientemente de la configuración de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-147">Private teams that are not discoverable are never shown in search results and suggestions, regardless of the policy setting.</span></span> <span data-ttu-id="dbfb9-148">Por ejemplo, si desactiva la configuración de descubrimiento para un equipo privado, los usuarios no podrán descubrir el equipo, aunque el parámetro **AllowPrivateTeamDiscovery** se establezca en **verdadero** en la configuración de directiva para esos usuarios.</span><span class="sxs-lookup"><span data-stu-id="dbfb9-148">For example, if you turn off the discovery setting for a private team, users are unable to discover the team, even though  the **AllowPrivateTeamDiscovery** parameter is set to **true** in the policy setting for those users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="dbfb9-149">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="dbfb9-149">Related topics</span></span>
- [<span data-ttu-id="dbfb9-150">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="dbfb9-150">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
