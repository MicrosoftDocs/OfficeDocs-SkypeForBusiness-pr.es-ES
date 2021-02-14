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
ms.openlocfilehash: 75bd058d79b1f54a40ad0e42207178c9c29d08cd
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583929"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="f8103-103">Información general sobre la pertenencia dinámica para los equipos</span><span class="sxs-lookup"><span data-stu-id="f8103-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="f8103-104">Microsoft Teams admite equipos asociados con grupos de Microsoft 365 mediante *la pertenencia dinámica.*</span><span class="sxs-lookup"><span data-stu-id="f8103-104">Microsoft Teams supports teams associated with Microsoft 365 groups by using *dynamic membership*.</span></span> <span data-ttu-id="f8103-105">La pertenencia dinámica permite que la pertenencia a un equipo se defina mediante una o más reglas que comprueban determinados atributos de usuario en Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="f8103-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="f8103-106">Los usuarios se agregan o quitan automáticamente a los equipos correctos a medida que cambian los atributos de usuario o los usuarios se unen y abandonan el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="f8103-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="f8103-107">Con la pertenencia dinámica, puede configurar equipos para ciertos grupos de usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="f8103-107">With dynamic membership you can set up teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="f8103-108">Entre los posibles escenarios se incluyen:</span><span class="sxs-lookup"><span data-stu-id="f8103-108">Possible scenarios include:</span></span>
- <span data-ttu-id="f8103-109">Un hospital puede crear distintos equipos para enfermeras, médicos y facultativos para difundir las comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="f8103-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="f8103-110">Esto es especialmente importante si el hospital depende de empleados temp.</span><span class="sxs-lookup"><span data-stu-id="f8103-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="f8103-111">Una universidad puede crear un equipo para todos los profesores de un instituto en particular, incluidos los profesores adjuntos que cambian con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="f8103-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="f8103-112">Una línea aérea quiere crear un equipo para cada vuelo (por ejemplo, un martes por la tarde sin parar desde Chicago a Atlanta) y tener asignados o quitados de forma automática un equipo de pilotos que cambia con frecuencia según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f8103-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="f8103-113">Con esta característica, los miembros de un equipo determinado se actualizan automáticamente en función de un conjunto específico de criterios, en lugar de administrar manualmente la pertenencia.</span><span class="sxs-lookup"><span data-stu-id="f8103-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="f8103-114">Para ello, es necesario asignar licencias de Azure AD Premium P1 y la pertenencia a equipos por parte de un administrador de inquilinos [a](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) cualquier propiedad de Azure AD del usuario, siempre que tenga un inquilino y una cuenta de administrador.</span><span class="sxs-lookup"><span data-stu-id="f8103-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's Azure AD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="f8103-115">Microsoft Teams puede tardar entre unos minutos y dos horas en reflejar los cambios dinámicos de pertenencia una vez que se han hecho efectivos en el grupo de Microsoft 365 de un equipo.</span><span class="sxs-lookup"><span data-stu-id="f8103-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Microsoft 365 group for a team.</span></span>

> [!NOTE]
> - <span data-ttu-id="f8103-116">Las reglas pueden definir quién es un miembro del equipo, pero no quién es propietario del equipo.</span><span class="sxs-lookup"><span data-stu-id="f8103-116">Rules can define who is a team member, but not who is a team owner.</span></span>
> - <span data-ttu-id="f8103-117">Consulte [los límites y las especificaciones de Microsoft Teams para ver](limits-specifications-teams.md) los límites actuales de los tamaños de los equipos y canales.</span><span class="sxs-lookup"><span data-stu-id="f8103-117">See [Limits and specifications for Microsoft Teams](limits-specifications-teams.md) for current limits on team and channel sizes.</span></span>
> - <span data-ttu-id="f8103-118">Los propietarios no podrán agregar o quitar usuarios como miembros del equipo, ya que los miembros se definen mediante reglas de grupo dinámicos.</span><span class="sxs-lookup"><span data-stu-id="f8103-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
> -    <span data-ttu-id="f8103-119">Los miembros no podrán dejar equipos con el apoyo de grupos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="f8103-119">Members will not be able to leave teams backed by dynamic groups.</span></span>

## <a name="creating-and-managing-a-microsoft-365-group-with-dynamic-membership"></a><span data-ttu-id="f8103-120">Crear y administrar un grupo de Microsoft 365 con pertenencia dinámica</span><span class="sxs-lookup"><span data-stu-id="f8103-120">Creating and managing a Microsoft 365 group with dynamic membership</span></span>

<span data-ttu-id="f8103-121">Una vez que haya iniciado sesión como administrador de inquilinos, siga las instrucciones de [Crear un grupo dinámico y compruebe el estado.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)</span><span class="sxs-lookup"><span data-stu-id="f8103-121">While logged in as the tenant admin, follow the instructions in [Create a dynamic group and check status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="f8103-122">Si es necesario, consulte reglas [de pertenencia dinámica para grupos de Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership)</span><span class="sxs-lookup"><span data-stu-id="f8103-122">As needed, refer to [Dynamic membership rules for groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span></span>

## <a name="create-a-new-team-with-your-microsoft-365-group"></a><span data-ttu-id="f8103-123">Crear un equipo nuevo con el grupo de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f8103-123">Create a new team with your Microsoft 365 group</span></span>

<span data-ttu-id="f8103-124">Ahora deje tiempo para que los cambios de pertenencia se a efecto y cree un equipo nuevo como se describe en Crear un equipo [a partir de un grupo existente.](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)</span><span class="sxs-lookup"><span data-stu-id="f8103-124">Now allow time for the membership changes to take effect, and create a new team  as described in [Create a team from an existing group](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865).</span></span>

## <a name="apply-dynamic-membership-to-an-existing-team"></a><span data-ttu-id="f8103-125">Aplicar pertenencia dinámica a un equipo existente</span><span class="sxs-lookup"><span data-stu-id="f8103-125">Apply dynamic membership to an existing team</span></span>

<span data-ttu-id="f8103-126">También puede elegir un equipo existente y cambiarlo para que tenga una pertenencia dinámica, como se describe en Cambiar la pertenencia a grupos estáticos a dinámico [en Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type)</span><span class="sxs-lookup"><span data-stu-id="f8103-126">You can also take an existing team and change it to have a dynamic membership, as described in [Change static group membership to dynamic in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span></span>

## <a name="changes-in-client-behavior"></a><span data-ttu-id="f8103-127">Cambios en el comportamiento del cliente</span><span class="sxs-lookup"><span data-stu-id="f8103-127">Changes in client behavior</span></span>

<span data-ttu-id="f8103-128">Una vez habilitada la pertenencia dinámica para un equipo, los clientes de Teams ya no permitirán la administración de miembros para el equipo.</span><span class="sxs-lookup"><span data-stu-id="f8103-128">Once dynamic membership is enabled for a team, Teams clients will no longer allow member management for the team.</span></span> <span data-ttu-id="f8103-129">Las opciones para agregar miembros, editar roles de miembro, enviar y aprobar solicitudes de unión y abandonar el equipo están ocultas.</span><span class="sxs-lookup"><span data-stu-id="f8103-129">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>
