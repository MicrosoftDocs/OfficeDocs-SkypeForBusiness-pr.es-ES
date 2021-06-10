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
description: Obtenga información sobre cómo Microsoft Teams equipos asociados con Microsoft 365 mediante la pertenencia dinámica.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 74974f7b94a5d1bcadb340e132dae9e3b39a7704
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856329"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="d90ff-103">Información general sobre la pertenencia dinámica para los equipos</span><span class="sxs-lookup"><span data-stu-id="d90ff-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="d90ff-104">Microsoft Teams admite equipos asociados con Microsoft 365 mediante la *pertenencia dinámica.*</span><span class="sxs-lookup"><span data-stu-id="d90ff-104">Microsoft Teams supports teams associated with Microsoft 365 groups by using *dynamic membership*.</span></span> <span data-ttu-id="d90ff-105">La pertenencia dinámica permite definir la pertenencia a un equipo mediante una o varias reglas que comprueban si hay determinados atributos de usuario en Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="d90ff-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="d90ff-106">Los usuarios se agregan o quitan automáticamente a los equipos correctos a medida que cambian los atributos de usuario o los usuarios se unen y abandonan el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="d90ff-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="d90ff-107">Con la pertenencia dinámica, puede configurar equipos para determinadas cohortes de usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="d90ff-107">With dynamic membership you can set up teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="d90ff-108">Entre los posibles escenarios se incluyen:</span><span class="sxs-lookup"><span data-stu-id="d90ff-108">Possible scenarios include:</span></span>
- <span data-ttu-id="d90ff-109">Un hospital puede crear equipos distintos para que enfermeras, médicos y cirujanas difunden comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="d90ff-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="d90ff-110">Esto es especialmente importante si el hospital depende de empleados temporales.</span><span class="sxs-lookup"><span data-stu-id="d90ff-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="d90ff-111">Una universidad puede crear un equipo para todos los profesores de una universidad en particular, incluidos los profesores adjuntos que cambian con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="d90ff-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="d90ff-112">Una línea aérea quiere crear un equipo para cada vuelo (como un martes por la tarde sin escalas de Chicago a Atlanta) y que se asigne o quite automáticamente a una cuadrilla de pilotos que cambia con frecuencia según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="d90ff-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="d90ff-113">Con esta característica, los miembros de un equipo determinado se actualizan automáticamente en función de un conjunto específico de criterios, en lugar de administrar manualmente la pertenencia.</span><span class="sxs-lookup"><span data-stu-id="d90ff-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="d90ff-114">Para ello, un administrador de inquilinos puede asignar licencias de Azure AD Premium P1 y pertenencia al equipo [a](/azure/active-directory/users-groups-roles/groups-dynamic-membership) las propiedades de Azure AD de cualquier usuario siempre que tenga un inquilino y una cuenta de administrador.</span><span class="sxs-lookup"><span data-stu-id="d90ff-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's Azure AD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="d90ff-115">Microsoft Teams puede tardar entre unos minutos y hasta 2 horas en reflejar los cambios dinámicos de pertenencia una vez que entren en vigor en el grupo de Microsoft 365 para un equipo.</span><span class="sxs-lookup"><span data-stu-id="d90ff-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Microsoft 365 group for a team.</span></span>

<span data-ttu-id="d90ff-116">Al usar equipos con grupos dinámicos:</span><span class="sxs-lookup"><span data-stu-id="d90ff-116">When using teams with dynamic groups:</span></span>

- <span data-ttu-id="d90ff-117">Las reglas pueden definir quién es un miembro del equipo, pero no quién es el propietario del equipo.</span><span class="sxs-lookup"><span data-stu-id="d90ff-117">Rules can define who is a team member, but not who is a team owner.</span></span>
- <span data-ttu-id="d90ff-118">Los propietarios no podrán agregar o quitar usuarios como miembros del equipo, ya que los miembros se definen mediante reglas dinámicas de grupo.</span><span class="sxs-lookup"><span data-stu-id="d90ff-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
- <span data-ttu-id="d90ff-119">Teams clientes no permiten la administración de miembros para el equipo.</span><span class="sxs-lookup"><span data-stu-id="d90ff-119">Teams clients don't allow member management for the team.</span></span> <span data-ttu-id="d90ff-120">Las opciones para agregar miembros, editar roles de miembro, enviar y aprobar solicitudes de unirse y dejar el equipo están ocultas.</span><span class="sxs-lookup"><span data-stu-id="d90ff-120">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>

<span data-ttu-id="d90ff-121">Para crear un equipo que use pertenencia dinámica, empiece por crear un grupo de Microsoft 365 dinámico y, [a](/azure/active-directory/users-groups-roles/groups-create-rule) continuación, cree un equipo [a partir de ese grupo.](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865)</span><span class="sxs-lookup"><span data-stu-id="d90ff-121">To create a team that uses dynamic membership, start by [creating a dynamic Microsoft 365 group](/azure/active-directory/users-groups-roles/groups-create-rule) and then [create a team from that group](https://support.microsoft.com/en-us/office/create-a-team-from-an-existing-group-24ec428e-40d7-4a1a-ab87-29be7d145865).</span></span>

<span data-ttu-id="d90ff-122">Puede cambiar un equipo existente para que tenga una pertenencia dinámica.</span><span class="sxs-lookup"><span data-stu-id="d90ff-122">You can change an existing team to have a dynamic membership.</span></span> <span data-ttu-id="d90ff-123">Vea [Cambiar la pertenencia a grupos estáticos a dinámica en Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type) para obtener información.</span><span class="sxs-lookup"><span data-stu-id="d90ff-123">See [Change static group membership to dynamic in Azure Active Directory](/azure/active-directory/users-groups-roles/groups-change-type) for information.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d90ff-124">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="d90ff-124">Related topics</span></span>

[<span data-ttu-id="d90ff-125">Límites y especificaciones para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d90ff-125">Limits and specifications for Microsoft Teams</span></span>](limits-specifications-teams.md)

[<span data-ttu-id="d90ff-126">Reglas de pertenencia dinámica para grupos de Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d90ff-126">Dynamic membership rules for groups in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-dynamic-membership)
