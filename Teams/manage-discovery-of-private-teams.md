---
title: Administrar la detección de los equipos privados en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 4/25/2019
ms.reviewer: shpoddar
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo controlar si los equipos privados se pueden detectar los usuarios de Microsoft Teams a través de sugerencias en el equipo galería y resultados de búsqueda.
ms.openlocfilehash: 70d5b81bba719a9e6cc6a51d38d58fd309e07a3b
ms.sourcegitcommit: 9329d740a2060f9c055c5c0c03107a9268c0df5b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2019
ms.locfileid: "33262773"
---
# <a name="manage-discovery-of-private-teams-in-microsoft-teams"></a><span data-ttu-id="2d96f-103">Administrar la detección de los equipos privados en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2d96f-103">Manage discovery of private teams in Microsoft Teams</span></span>

<span data-ttu-id="2d96f-104">Los propietarios de los administradores y del equipo pueden controlar si se pueden detectar los equipos privados por los usuarios de Microsoft Teams en su organización.</span><span class="sxs-lookup"><span data-stu-id="2d96f-104">Admins and team owners can control whether private teams can be discovered by Microsoft Teams users in your organization.</span></span> <span data-ttu-id="2d96f-105">Una vez que se pueda detectar un equipo privado, se muestra en los resultados de búsqueda y se incluye en sugerencias en la Galería de equipo junto con los equipos públicos en los equipos.</span><span class="sxs-lookup"><span data-stu-id="2d96f-105">When a private team is discoverable, it shows up in search results and is included in suggestions in the team gallery alongside public teams in Teams.</span></span> <span data-ttu-id="2d96f-106">Esto facilita a los usuarios a buscar y encontrar los equipos privados que deseen unirse a.</span><span class="sxs-lookup"><span data-stu-id="2d96f-106">This makes it easy for users to search for and find the private teams that they want to join.</span></span> <span data-ttu-id="2d96f-107">Los usuarios pueden solicitar para unirse a un equipo privado que el propietario de un equipo, a continuación, puede aprobar o denegar.</span><span class="sxs-lookup"><span data-stu-id="2d96f-107">Users can request to join a private team which a team owner can then approve or deny.</span></span>

## <a name="overview-of-public-teams-private-teams-and-discovery-in-teams"></a><span data-ttu-id="2d96f-108">Información general de los equipos públicos, los equipos privados y detección en los equipos</span><span class="sxs-lookup"><span data-stu-id="2d96f-108">Overview of public teams, private teams, and discovery in Teams</span></span>

<span data-ttu-id="2d96f-109">La mayoría de las organizaciones tienen los siguientes tipos de equipos - equipos públicos, que se pueda detectar equipos privados y equipos privados no detectable.</span><span class="sxs-lookup"><span data-stu-id="2d96f-109">Most organizations have the following kinds of teams - public teams, discoverable private teams, and non-discoverable private teams.</span></span>

![Galería de equipo](media/private-team-discovery-team-gallery.png)

### <a name="public-teams"></a><span data-ttu-id="2d96f-111">Equipos públicos</span><span class="sxs-lookup"><span data-stu-id="2d96f-111">Public teams</span></span>

<span data-ttu-id="2d96f-112">Están disponibles para todos los usuarios de la organización para unirse a los equipos públicos.</span><span class="sxs-lookup"><span data-stu-id="2d96f-112">Public teams are available for all users in your organization to join.</span></span> <span data-ttu-id="2d96f-113">Los equipos públicos están visibles para todos los usuarios en la Galería de los equipos y los usuarios pueden unirse a un equipo público sin necesidad de obtener la aprobación del propietario del equipo.</span><span class="sxs-lookup"><span data-stu-id="2d96f-113">Public teams are visible to everyone in the teams gallery and users can join a public team without having to get approval from the team owner.</span></span> <span data-ttu-id="2d96f-114">Algunos ejemplos de los equipos públicos son un equipo para discutir noticias en tecnología, un equipo para obtener comentarios dogfood para sus productos y un equipo para molesta de personas para que funcione.</span><span class="sxs-lookup"><span data-stu-id="2d96f-114">Examples of public teams include a team to discuss news in technology, a team to get dogfood feedback for your products, and a team for people carpooling to work.</span></span>

### <a name="discoverable-private-teams"></a><span data-ttu-id="2d96f-115">Equipos privados que se pueda detectar</span><span class="sxs-lookup"><span data-stu-id="2d96f-115">Discoverable private teams</span></span>

<span data-ttu-id="2d96f-116">Sólo se pueden unir los equipos privados que se pueda detectar cuando el propietario del equipo agrega a los usuarios a ellos.</span><span class="sxs-lookup"><span data-stu-id="2d96f-116">Discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="2d96f-117">Cuando realiza un equipo privado que se pueda detectar, el equipo se incluye en la lista de los equipos sugeridos y los resultados de búsqueda en la Galería de los equipos.</span><span class="sxs-lookup"><span data-stu-id="2d96f-117">When you make a private team discoverable, the team is included in the list of suggested teams and search results in the teams gallery.</span></span> <span data-ttu-id="2d96f-118">Use que se pueda detectar equipos privados para proyectos y grupos de la organización que todos los usuarios es consciente de y donde el acceso a las conversaciones y los archivos en el equipo deben controlarse.</span><span class="sxs-lookup"><span data-stu-id="2d96f-118">Use discoverable private teams for projects and groups in your organization that everyone is aware of and where access to conversations and files in the team need to be controlled.</span></span> <span data-ttu-id="2d96f-119">Algunos ejemplos son un equipo para el departamento de recursos humanos, un equipo para todos los administradores de la organización y un equipo de un administrador y sus subordinados directos.</span><span class="sxs-lookup"><span data-stu-id="2d96f-119">Examples include a team for your HR department, a team for all managers at your organization, and a team for a manager and their direct reports.</span></span>

### <a name="non-discoverable-private-teams"></a><span data-ttu-id="2d96f-120">Equipos privados que no se pueda detectar</span><span class="sxs-lookup"><span data-stu-id="2d96f-120">Non-discoverable private teams</span></span>

<span data-ttu-id="2d96f-121">Sólo se pueden unir los equipos privados que no se pueda detectar cuando el propietario del equipo agrega a los usuarios a ellos.</span><span class="sxs-lookup"><span data-stu-id="2d96f-121">Non-discoverable private teams can only be joined when the team owner adds users to them.</span></span> <span data-ttu-id="2d96f-122">Cuando realiza no puede detectar un equipo privado, tiene oculto de la lista de los equipos sugeridas y se quitan los resultados de búsqueda en la Galería de los equipos.</span><span class="sxs-lookup"><span data-stu-id="2d96f-122">When you make a private team not discoverable, it's hidden from the list of suggested teams and removed from search results in the teams gallery.</span></span> <span data-ttu-id="2d96f-123">Uso de los equipos que no sean reconocibles para colaborar en los temas importantes y altamente confidenciales.</span><span class="sxs-lookup"><span data-stu-id="2d96f-123">Use non-discoverable teams to collaborate on sensitive and highly confidential topics.</span></span> <span data-ttu-id="2d96f-124">Algunos ejemplos son un equipo para discutir una adquisición próxima y un equipo para discutir un cambio en la dirección estratégica de su organización.</span><span class="sxs-lookup"><span data-stu-id="2d96f-124">Examples include a team to discuss an upcoming acquisition and a team to discuss a change in your organization's strategic direction.</span></span>

## <a name="set-whether-new-private-teams-are-discoverable"></a><span data-ttu-id="2d96f-125">Establecer si se puede detectar nuevos equipos privados</span><span class="sxs-lookup"><span data-stu-id="2d96f-125">Set whether new private teams are discoverable</span></span>

<span data-ttu-id="2d96f-126">Cuando el propietario de un equipo, crea un equipo privado, pueden elegir para que se pueda detectar mediante la configuración de detección del grupo.</span><span class="sxs-lookup"><span data-stu-id="2d96f-126">When a team owner creates a private team, they can choose to make it discoverable by configuring the team's discovery setting.</span></span> <span data-ttu-id="2d96f-127">De forma predeterminada, los equipos privados nuevo son que admite búsquedas y que se pueda detectar.</span><span class="sxs-lookup"><span data-stu-id="2d96f-127">By default, new private teams are searchable and discoverable.</span></span> <span data-ttu-id="2d96f-128">Si el propietario del equipo no desea que el equipo privado aparezca en los resultados de búsqueda y sugerencias, puede activar desactiva la opción seleccionando **Cambiar configuración** junto a **este equipo es que admite búsquedas y que se pueda detectar**.</span><span class="sxs-lookup"><span data-stu-id="2d96f-128">If the team owner doesn't want the private team to show up in search results and suggestions, they can turn off the setting by selecting **Change setting** next to **This team is searchable and discoverable**.</span></span>

![configuración de detección para nuevos equipos privados](media/private-team-discovery-new-team.png)

## <a name="set-whether-existing-private-teams-are-discoverable"></a><span data-ttu-id="2d96f-130">Establecer si se puede detectar los equipos privados existentes</span><span class="sxs-lookup"><span data-stu-id="2d96f-130">Set whether existing private teams are discoverable</span></span>

<span data-ttu-id="2d96f-131">Los propietarios de equipo pueden establecer la configuración de detección de un equipo privado existente directamente en la configuración del equipo y los administradores pueden hacerlo mediante el uso de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2d96f-131">Team owners can set the discovery setting for an existing private team directly in the team settings and admins can do so by using PowerShell.</span></span>

### <a name="in-team-settings"></a><span data-ttu-id="2d96f-132">En configuración del equipo</span><span class="sxs-lookup"><span data-stu-id="2d96f-132">In team settings</span></span>

<span data-ttu-id="2d96f-133">En los equipos, vaya al equipo privado, haga clic en **más ˙˙˙ opciones** > **Administrar equipo**.</span><span class="sxs-lookup"><span data-stu-id="2d96f-133">In Teams, go to the private team, click **More options ˙˙˙** > **Manage team**.</span></span> <span data-ttu-id="2d96f-134">En la ficha **configuración** , expanda la **detección de equipo**y, a continuación, desactive o Active la casilla de verificación **activar la detectabilidad** .</span><span class="sxs-lookup"><span data-stu-id="2d96f-134">On the **Settings** tab, expand **Team discovery**, and then clear or select the **Turn on discoverability** check box.</span></span>

![configuración de detección de equipos privados existentes](media/private-team-discovery-existing-team.png)

### <a name="using-powershell"></a><span data-ttu-id="2d96f-136">Uso de PowerShell</span><span class="sxs-lookup"><span data-stu-id="2d96f-136">Using PowerShell</span></span>

<span data-ttu-id="2d96f-137">Use el cmdlet **Set-equipo** para activar o desactivar la opción de detección de un equipo privado existente.</span><span class="sxs-lookup"><span data-stu-id="2d96f-137">Use the **Set-Team** cmdlet to turn off or turn on the discovery setting for an existing private team.</span></span> <span data-ttu-id="2d96f-138">Este es un ejemplo de cómo hacer que un equipo que se pueda detectar:</span><span class="sxs-lookup"><span data-stu-id="2d96f-138">Here's an example of how to make a team discoverable:</span></span>

    Set-Team -GroupId 0abc123d-e4f5-67gh-i890-jk1m2n345o6p -ShowInSearchAndSuggestions $true
<span data-ttu-id="2d96f-139">Puede usar este cmdlet en una secuencia de comandos para establecer la configuración de detección de equipos privados existentes de forma masiva.</span><span class="sxs-lookup"><span data-stu-id="2d96f-139">You can use this cmdlet in a script to set the discovery setting of existing private teams in bulk.</span></span>

## <a name="set-whether-users-can-discover-private-teams"></a><span data-ttu-id="2d96f-140">Establecer si los usuarios pueden detectar los equipos privados</span><span class="sxs-lookup"><span data-stu-id="2d96f-140">Set whether users can discover private teams</span></span>

<span data-ttu-id="2d96f-141">Como administrador, también puede controlar qué usuarios de la organización se permiten detectar equipos privados en los resultados de búsqueda y sugerencias en los equipos.</span><span class="sxs-lookup"><span data-stu-id="2d96f-141">As an admin, you can also control which users in your organization are allowed to discover private teams in search results and suggestions in Teams.</span></span> <span data-ttu-id="2d96f-142">Crear una directiva con el cmdlet **New-CsTeamsChannelsPolicy** y, a continuación, asigne la directiva a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2d96f-142">Create a policy by using the **New-CsTeamsChannelsPolicy** cmdlet, and then assign the policy to users.</span></span>
 
<span data-ttu-id="2d96f-143">Establezca el parámetro **AllowPrivateTeamDiscovery** en **true** para permitir que a los usuarios que tienen asignados la directiva para ver que se pueda detectar equipos privados en los resultados de búsqueda y sugerencias.</span><span class="sxs-lookup"><span data-stu-id="2d96f-143">Set the **AllowPrivateTeamDiscovery** parameter to **true** to allow users who are assigned the policy to see discoverable private teams in search results and suggestions.</span></span> <span data-ttu-id="2d96f-144">Si el parámetro **AllowPrivateTeamDiscovery** se establece en **false** , quita todos los equipos privados detectable de los resultados de búsqueda y sugerencias para los usuarios que tienen asignadas la directiva.</span><span class="sxs-lookup"><span data-stu-id="2d96f-144">Setting the **AllowPrivateTeamDiscovery** parameter to **false** removes all discoverable private teams from search results and suggestions for users who are assigned the policy.</span></span>

<span data-ttu-id="2d96f-145">De forma predeterminada, **AllowPrivateTeamDiscovery** se establece en **true** para todos los usuarios de una organización.</span><span class="sxs-lookup"><span data-stu-id="2d96f-145">By default, **AllowPrivateTeamDiscovery** is set to **true** for all users in an organization.</span></span>

<span data-ttu-id="2d96f-146">En este ejemplo, se crea una directiva denominada VendorPolicy que impide que los usuarios descubrir cualquier equipos privados que se realizan puede detectar y, a continuación, se asigne la directiva a un usuario denominado vendoruser1.</span><span class="sxs-lookup"><span data-stu-id="2d96f-146">In this example, we create a policy named VendorPolicy that prevents users from discovering any private teams that are made discoverable, and then we assign the policy to a user named vendoruser1.</span></span> 
   
     New-CsTeamsChannelsPolicy -Identity VendorPolicy -AllowPrivateTeamDiscovery $false
     Grant-CsTeamsChannelsPolicy -Identity vendoruser1@company.com -PolicyName VendorPolicy

> [!NOTE]
> <span data-ttu-id="2d96f-147">Los equipos privados que no se pueden descubrir nunca se muestran en los resultados de búsqueda y sugerencias, independientemente de la configuración de directiva.</span><span class="sxs-lookup"><span data-stu-id="2d96f-147">Private teams that are not discoverable are never shown in search results and suggestions, regardless of the policy setting.</span></span> <span data-ttu-id="2d96f-148">Por ejemplo, si desactiva la configuración de detección de un equipo privado, los usuarios son no se puede detectar el equipo, aunque el parámetro **AllowPrivateTeamDiscovery** se establece en **true** en la configuración de directiva para esos usuarios.</span><span class="sxs-lookup"><span data-stu-id="2d96f-148">For example, if you turn off the discovery setting for a private team, users are unable to discover the team, even though  the **AllowPrivateTeamDiscovery** parameter is set to **true** in the policy setting for those users.</span></span>

## <a name="related-topics"></a><span data-ttu-id="2d96f-149">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="2d96f-149">Related topics</span></span>
- [<span data-ttu-id="2d96f-150">Descripción de PowerShell para Teams</span><span class="sxs-lookup"><span data-stu-id="2d96f-150">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)