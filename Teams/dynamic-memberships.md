---
title: Información general sobre la pertenencia dinámica para los equipos
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: conceptual
ms.service: msteams
audience: admin
search.appverid: MET150
description: Obtenga más información sobre la pertenencia a equipos dinámicos basadas en AAD.
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a4a0a7d9487b7697bad5ac565b98e605c4cc81dc
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237810"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="37fa3-103">Información general sobre la pertenencia dinámica para los equipos</span><span class="sxs-lookup"><span data-stu-id="37fa3-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="37fa3-104">Microsoft Teams es compatible con los equipos asociados con los grupos de Office 365 mediante la *pertenencia dinámica*.</span><span class="sxs-lookup"><span data-stu-id="37fa3-104">Microsoft Teams supports teams associated with Office 365 groups by using *dynamic membership*.</span></span> <span data-ttu-id="37fa3-105">La pertenencia dinámica permite a la pertenencia de un equipo definirse por una o más reglas que comprueban determinados atributos de usuario en Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="37fa3-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="37fa3-106">Los usuarios se agregan o quitan automáticamente a los equipos correctos a medida que los atributos de usuario cambian o se unen y abandonan el inquilino.</span><span class="sxs-lookup"><span data-stu-id="37fa3-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="37fa3-107">Con la pertenencia dinámica puede configurar Teams para determinados cohorts de usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="37fa3-107">With dynamic membership you can set up teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="37fa3-108">Entre los posibles escenarios se incluyen:</span><span class="sxs-lookup"><span data-stu-id="37fa3-108">Possible scenarios include:</span></span>
- <span data-ttu-id="37fa3-109">Un hospital puede crear equipos distintos para enfermeras, doctores y cirujanos para difundir las comunicaciones.</span><span class="sxs-lookup"><span data-stu-id="37fa3-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="37fa3-110">Esto es especialmente importante si el hospital depende de empleados temporales.</span><span class="sxs-lookup"><span data-stu-id="37fa3-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="37fa3-111">Una universidad puede crear un equipo para todos los profesores dentro de una universidad determinada, entre ellos un profesorado de Adjunct que cambia con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="37fa3-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="37fa3-112">Una línea aérea desea crear un equipo para cada vuelo (como un martes por la tarde sin detenerse en Chicago) y se les asigna o elimina un equipo de vuelo que cambia con frecuencia según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="37fa3-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="37fa3-113">Con esta característica, los miembros de un equipo dado se actualizan automáticamente según un conjunto específico de criterios, en lugar de administrar la pertenencia de forma manual.</span><span class="sxs-lookup"><span data-stu-id="37fa3-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="37fa3-114">Para ello, es necesario que [un administrador](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) de inquilinos pueda asignar licencias de Azure ad Premium P1 y la pertenencia al equipo a las propiedades de Azure ad de cualquier usuario siempre que tenga un inquilino y una cuenta de administrador.</span><span class="sxs-lookup"><span data-stu-id="37fa3-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's Azure AD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="37fa3-115">Microsoft Teams puede tardar desde unos minutos hasta 2 horas en reflejar los cambios dinámicos de pertenencia, una vez que se aplican al grupo de Office 365 de un equipo.</span><span class="sxs-lookup"><span data-stu-id="37fa3-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Office 365 group for a team.</span></span>

> [!NOTE]
> - <span data-ttu-id="37fa3-116">Las reglas pueden definir quién es un miembro del equipo, pero no quién es el propietario de un equipo.</span><span class="sxs-lookup"><span data-stu-id="37fa3-116">Rules can define who is a team member, but not who is a team owner.</span></span>
> - <span data-ttu-id="37fa3-117">Consulte [límites y especificaciones de Microsoft Teams](limits-specifications-teams.md) para obtener los límites actuales de los tamaños de equipo y de canal.</span><span class="sxs-lookup"><span data-stu-id="37fa3-117">See [Limits and specifications for Microsoft Teams](limits-specifications-teams.md) for current limits on team and channel sizes.</span></span>
> - <span data-ttu-id="37fa3-118">Los propietarios no podrán agregar o quitar usuarios como miembros del equipo, ya que los miembros se definen mediante reglas de grupo dinámicas.</span><span class="sxs-lookup"><span data-stu-id="37fa3-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
> - <span data-ttu-id="37fa3-119">Los miembros no podrán dejar equipos respaldados por grupos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="37fa3-119">Members will not be able to leave teams backed by dynamic groups.</span></span>


## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a><span data-ttu-id="37fa3-120">Crear y administrar un grupo de Office 365 con pertenencia dinámica</span><span class="sxs-lookup"><span data-stu-id="37fa3-120">Creating and managing an Office 365 group with dynamic membership</span></span>
<span data-ttu-id="37fa3-121">Cuando haya iniciado sesión como administrador de inquilinos, siga las instrucciones de [crear un grupo dinámico y comprobar el estado](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span><span class="sxs-lookup"><span data-stu-id="37fa3-121">While logged in as the tenant admin, follow the instructions in [Create a dynamic group and check status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="37fa3-122">Según sea necesario, consulte [reglas de pertenencia dinámica para grupos en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span><span class="sxs-lookup"><span data-stu-id="37fa3-122">As needed, refer to [Dynamic membership rules for groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span></span>

## <a name="create-a-new-team-with-your-o365-group"></a><span data-ttu-id="37fa3-123">Crear un equipo nuevo con el grupo de O365</span><span class="sxs-lookup"><span data-stu-id="37fa3-123">Create a new team with your O365 group</span></span>

<span data-ttu-id="37fa3-124">Ahora deje que se apliquen los cambios de pertenencia y cree un equipo nuevo tal y como se describe en [mejorar los grupos existentes de Office 365 con Microsoft Teams](enhance-office-365-groups.md).</span><span class="sxs-lookup"><span data-stu-id="37fa3-124">Now allow time for the membership changes to take effect, and create a new team  as described in [Enhance Existing Office 365 groups with Microsoft Teams](enhance-office-365-groups.md).</span></span>

## <a name="apply-dynamic-membership-to-an-existing-team"></a><span data-ttu-id="37fa3-125">Aplicar pertenencia dinámica a un equipo existente</span><span class="sxs-lookup"><span data-stu-id="37fa3-125">Apply dynamic membership to an existing team</span></span>

<span data-ttu-id="37fa3-126">También puede tomar un equipo existente y cambiarlo para que tenga una pertenencia dinámica, tal y como se describe en [cambiar la pertenencia a grupos estáticos a dinámico en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span><span class="sxs-lookup"><span data-stu-id="37fa3-126">You can also take an existing team and change it to have a dynamic membership, as described in [Change static group membership to dynamic in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span></span>

## <a name="changes-in-client-behavior"></a><span data-ttu-id="37fa3-127">Cambios en el comportamiento del cliente</span><span class="sxs-lookup"><span data-stu-id="37fa3-127">Changes in client behavior</span></span>

<span data-ttu-id="37fa3-128">Una vez habilitada la pertenencia dinámica para un equipo, los clientes de equipos ya no permitirán la administración de miembros del equipo.</span><span class="sxs-lookup"><span data-stu-id="37fa3-128">Once dynamic membership is enabled for a team, Teams clients will no longer allow member management for the team.</span></span> <span data-ttu-id="37fa3-129">Las opciones para agregar miembros, editar roles de miembro, enviar y aprobar solicitudes de participación, y dejar el equipo están ocultos.</span><span class="sxs-lookup"><span data-stu-id="37fa3-129">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>
