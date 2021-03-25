---
title: Información general sobre la pertenencia dinámica para los equipos
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga información sobre cómo Microsoft Teams admite equipos asociados con grupos de Microsoft 365 mediante la pertenencia dinámica.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a76600e8ca0a92b2d46e99bc26a857c969bd07e7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120772"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="df853-103">Información general sobre la pertenencia dinámica para los equipos</span><span class="sxs-lookup"><span data-stu-id="df853-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="df853-104">Microsoft Teams admite equipos asociados con grupos de Microsoft 365 mediante la *pertenencia dinámica.*</span><span class="sxs-lookup"><span data-stu-id="df853-104">Microsoft Teams supports teams associated with Microsoft 365 groups by using *dynamic membership*.</span></span> <span data-ttu-id="df853-105">La pertenencia dinámica permite definir la pertenencia a un equipo mediante una o más reglas que comprueban si hay determinados atributos de usuario en Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="df853-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="df853-106">Los usuarios se agregan o quitan automáticamente a los equipos correctos a medida que cambian los atributos de usuario o los usuarios se unen y abandonan el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="df853-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="df853-107">Con la pertenencia dinámica, puede configurar equipos para determinadas cohortes de usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="df853-107">With dynamic membership you can set up teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="df853-108">Entre los posibles escenarios se incluyen:</span><span class="sxs-lookup"><span data-stu-id="df853-108">Possible scenarios include:</span></span>
- <span data-ttu-id="df853-109">Un hospital puede crear equipos distintos para que enfermeras, médicos y cirujanas difunden comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="df853-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="df853-110">Esto es especialmente importante si el hospital depende de empleados temporales.</span><span class="sxs-lookup"><span data-stu-id="df853-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="df853-111">Una universidad puede crear un equipo para todos los profesores de una universidad en particular, incluidos los profesores adjuntos que cambian con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="df853-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="df853-112">Una línea aérea quiere crear un equipo para cada vuelo (como un martes por la tarde sin escalas de Chicago a Atlanta) y que se asigne o quite automáticamente a una cuadrilla de pilotos que cambia con frecuencia según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="df853-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="df853-113">Con esta característica, los miembros de un equipo determinado se actualizan automáticamente en función de un conjunto específico de criterios, en lugar de administrar manualmente la pertenencia.</span><span class="sxs-lookup"><span data-stu-id="df853-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="df853-114">Para ello, un administrador de inquilinos puede asignar licencias de Azure AD Premium P1 y la pertenencia al equipo [a](/azure/active-directory/users-groups-roles/groups-dynamic-membership) las propiedades de Azure AD de cualquier usuario siempre que tenga un inquilino y una cuenta de administrador.</span><span class="sxs-lookup"><span data-stu-id="df853-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's Azure AD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="df853-115">Microsoft Teams puede tardar entre unos minutos y hasta 2 horas en reflejar los cambios dinámicos de pertenencia una vez que entren en vigor en el grupo de Microsoft 365 para un equipo.</span><span class="sxs-lookup"><span data-stu-id="df853-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Microsoft 365 group for a team.</span></span>

> [!NOTE]
> - <span data-ttu-id="df853-116">Las reglas pueden definir quién es un miembro del equipo, pero no quién es el propietario del equipo.</span><span class="sxs-lookup"><span data-stu-id="df853-116">Rules can define who is a team member, but not who is a team owner.</span></span>
> - <span data-ttu-id="df853-117">Consulte [Límites y especificaciones de Microsoft Teams para](limits-specifications-teams.md) ver los límites actuales de los tamaños de equipo y canal.</span><span class="sxs-lookup"><span data-stu-id="df853-117">See [Limits and specifications for Microsoft Teams](limits-specifications-teams.md) for current limits on team and channel sizes.</span></span>
> - <span data-ttu-id="df853-118">Los propietarios no podrán agregar o quitar usuarios como miembros del equipo, ya que los miembros se definen mediante reglas dinámicas de grupo.</span><span class="sxs-lookup"><span data-stu-id="df853-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
> -    <span data-ttu-id="df853-119">Los miembros no podrán dejar los equipos con el respaldo de grupos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="df853-119">Members will not be able to leave teams backed by dynamic groups.</span></span>

## <a name="creating-and-managing-a-microsoft-365-group-with-dynamic-membership"></a><span data-ttu-id="df853-120">Crear y administrar un grupo de Microsoft 365 con pertenencia dinámica</span><span class="sxs-lookup"><span data-stu-id="df853-120">Creating and managing a Microsoft 365 group with dynamic membership</span></span>

<span data-ttu-id="df853-121">Al iniciar sesión como administrador de inquilinos, siga las instrucciones de [Crear un grupo dinámico y compruebe el estado.](/azure/active-directory/users-groups-roles/groups-create-rule)</span><span class="sxs-lookup"><span data-stu-id="df853-121">While logged in as the tenant admin, follow the instructions in [Create a dynamic group and check status](/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="df853-122">Según sea necesario, consulte [Reglas de pertenencia dinámica para grupos en Azure Active Directory.](/azure/active-directory/users-groups-roles/groups-dynamic-membership)</span><span class="sxs-lookup"><span data-stu-id="df853-122">As needed, refer to [Dynamic membership rules for groups in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span></span>

## <a name="create-a-new-team-with-your-microsoft-365-group"></a><span data-ttu-id="df853-123">Crear un nuevo equipo con el grupo de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="df853-123">Create a new team with your Microsoft 365 group</span></span>

<span data-ttu-id="df853-124">Ahora, dé tiempo para que los cambios de pertenencia sumen efecto y cree un nuevo equipo como se describe en Crear un equipo a partir [de un grupo existente.](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)</span><span class="sxs-lookup"><span data-stu-id="df853-124">Now allow time for the membership changes to take effect, and create a new team  as described in [Create a team from an existing group](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865).</span></span>

## <a name="apply-dynamic-membership-to-an-existing-team"></a><span data-ttu-id="df853-125">Aplicar pertenencia dinámica a un equipo existente</span><span class="sxs-lookup"><span data-stu-id="df853-125">Apply dynamic membership to an existing team</span></span>

<span data-ttu-id="df853-126">También puede tomar un equipo existente y cambiarlo para que tenga una pertenencia dinámica, como se describe en Cambiar la pertenencia a grupos estáticos a dinámica [en Azure Active Directory.](/azure/active-directory/users-groups-roles/groups-change-type)</span><span class="sxs-lookup"><span data-stu-id="df853-126">You can also take an existing team and change it to have a dynamic membership, as described in [Change static group membership to dynamic in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type).</span></span>

## <a name="changes-in-client-behavior"></a><span data-ttu-id="df853-127">Cambios en el comportamiento del cliente</span><span class="sxs-lookup"><span data-stu-id="df853-127">Changes in client behavior</span></span>

<span data-ttu-id="df853-128">Una vez que la pertenencia dinámica está habilitada para un equipo, los clientes de Teams ya no permitirán la administración de miembros para el equipo.</span><span class="sxs-lookup"><span data-stu-id="df853-128">Once dynamic membership is enabled for a team, Teams clients will no longer allow member management for the team.</span></span> <span data-ttu-id="df853-129">Las opciones para agregar miembros, editar roles de miembro, enviar y aprobar solicitudes de unirse y dejar el equipo están ocultas.</span><span class="sxs-lookup"><span data-stu-id="df853-129">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>