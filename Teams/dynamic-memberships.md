---
title: Información general sobre la pertenencia dinámica para los equipos
author: jambirk
ms.author: jambirk
manager: serdars
ms.reviewer: kblevens, phlouie
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre pertenencia dinámica de equipos en función de AAD.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 512ca6de74f5061976203b3467e7e17bdfe6a800
ms.sourcegitcommit: d90beb625c2d12616fb9aee39b6dd1c2d4c12947
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "30408278"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="859f5-103">Información general sobre la pertenencia dinámica para los equipos</span><span class="sxs-lookup"><span data-stu-id="859f5-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="859f5-104">Microsoft Teams es compatible con los equipos asociados con grupos de Office 365 mediante pertenencia dinámica.</span><span class="sxs-lookup"><span data-stu-id="859f5-104">Microsoft Teams supports teams associated with Office 365 groups using dynamic membership.</span></span> <span data-ttu-id="859f5-105">Pertenencia dinámica permite la pertenencia de un equipo a definirse por una o varias reglas que comprobación ciertos atributos de usuario en Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="859f5-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (AAD).</span></span> <span data-ttu-id="859f5-106">Los usuarios automáticamente se agregan o quitan a los equipos de la correctos como cambian atributos de usuario o los usuarios al unirse y abandonar al inquilino.</span><span class="sxs-lookup"><span data-stu-id="859f5-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="859f5-107">Con pertenencia dinámica que se puede el programa de instalación para determinados equipos a las cohortes de los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="859f5-107">With dynamic membership you can setup teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="859f5-108">Los escenarios posibles son:</span><span class="sxs-lookup"><span data-stu-id="859f5-108">Possible scenarios include:</span></span>
- <span data-ttu-id="859f5-109">Un hospital puede crear distintos equipos para enfermeras, médicos y cirujanos difundir communications.</span><span class="sxs-lookup"><span data-stu-id="859f5-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="859f5-110">Esto es especialmente importante si el hospital se basa en los empleados temporales.</span><span class="sxs-lookup"><span data-stu-id="859f5-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="859f5-111">Una universidad puede crear un equipo para todos los profesores dentro de un determinado universitario, incluido un profesor adjuntos que cambia con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="859f5-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="859f5-112">Un compañías aéreas desea crear un equipo para cada vuelo (al igual que un martes por la tarde sin interrupciones de Chicago a Atlanta) y tienen un crew vuelo que cambia con frecuencia asignada automáticamente o quitan según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="859f5-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="859f5-113">Uso de esta característica, actualización de los miembros de un equipo determinado automáticamente según un conjunto específico de criterios, en lugar de administrar manualmente pertenencia.</span><span class="sxs-lookup"><span data-stu-id="859f5-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="859f5-114">Esta acción requiere licencias de Azure AD Premium P1 y los miembros del equipo pueden ser [asignado por un administrador de inquilinos](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) a las propiedades AAD de cualquier usuario siempre y que cuando disponga de un inquilino y una cuenta de administrador.</span><span class="sxs-lookup"><span data-stu-id="859f5-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's AAD properties provided you have a tenant and an admin account.</span></span> 

<span data-ttu-id="859f5-115">Microsoft Teams puede durar desde unos minutos hasta 2 horas para reflejar los cambios de pertenencia dinámica una vez que surtan efecto en el grupo de Office 365 para un equipo.</span><span class="sxs-lookup"><span data-stu-id="859f5-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Office 365 group for a team.</span></span> 

> [!NOTE]
> - <span data-ttu-id="859f5-116">Pueden definir reglas que es un miembro del equipo, pero no que es un equipo propietario.</span><span class="sxs-lookup"><span data-stu-id="859f5-116">Rules can define who is a team member, but not who is a team Owner.</span></span>
> - <span data-ttu-id="859f5-117">Vea [los límites y las especificaciones de los equipos de Microsoft](limits-specifications-teams.md) para conocer los límites actuales en los tamaños de canal y el equipo.</span><span class="sxs-lookup"><span data-stu-id="859f5-117">See [Limits and specifications for Microsoft Teams](limits-specifications-teams.md) for current limits on Team and channel sizes.</span></span>
> - <span data-ttu-id="859f5-118">Los propietarios no podrá agregar o quitar usuarios como miembros del equipo, ya que los miembros se definen por las reglas de grupo dinámico.</span><span class="sxs-lookup"><span data-stu-id="859f5-118">Owners will not be able to add or remove users as members of the team, since members are defined by dynamic group rules.</span></span>
> - <span data-ttu-id="859f5-119">Los miembros no podrá dejar los equipos respaldados por grupos dinámicos.</span><span class="sxs-lookup"><span data-stu-id="859f5-119">Members will not be able to leave teams backed by dynamic groups.</span></span>


## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a><span data-ttu-id="859f5-120">Creación y administración de un grupo de Office 365 con pertenencia dinámica</span><span class="sxs-lookup"><span data-stu-id="859f5-120">Creating and managing an Office 365 group with dynamic membership</span></span>
<span data-ttu-id="859f5-121">Cuando haya iniciado sesión como el Administrador de inquilinos, siga las instrucciones de [crear un grupo dinámico y compruebe el estado](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span><span class="sxs-lookup"><span data-stu-id="859f5-121">While logged in as the tenant Admin, follow the instructions in [Create a dynamic group and check status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="859f5-122">Según sea necesario, hacer referencia a [las reglas de pertenencia dinámica para los grupos en Active Directory de Azure](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span><span class="sxs-lookup"><span data-stu-id="859f5-122">As needed, refer to [Dynamic membership rules for groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span></span>

## <a name="create-a-new-team-with-your-o365-group"></a><span data-ttu-id="859f5-123">Crear un nuevo equipo con su grupo de O365</span><span class="sxs-lookup"><span data-stu-id="859f5-123">Create a new team with your O365 group</span></span>

<span data-ttu-id="859f5-124">Ahora Permitir tiempo para que surtan efecto los cambios de pertenencia y crear un nuevo equipo tal como se describe en [grupos de mejorar existente Office 365 con los equipos de Microsoft](enhance-office-365-groups.md).</span><span class="sxs-lookup"><span data-stu-id="859f5-124">Now allow time for the membership changes to take effect, and create a new team  as described in [Enhance Existing Office 365 groups with Microsoft Teams](enhance-office-365-groups.md).</span></span>

## <a name="apply-dynamic-membership-to-an-existing-team"></a><span data-ttu-id="859f5-125">Aplicar pertenencia dinámica a un equipo existente</span><span class="sxs-lookup"><span data-stu-id="859f5-125">Apply dynamic membership to an existing team</span></span>

<span data-ttu-id="859f5-126">También puede tomar un equipo existente y cámbiela para que tenga una pertenencia dinámica, tal como se describe en [cambiar la pertenencia a grupo estático a dinámico en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span><span class="sxs-lookup"><span data-stu-id="859f5-126">You can also take an existing team and change it to have a dynamic membership, as described in [Change static group membership to dynamic in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span></span>

## <a name="changes-in-client-behavior"></a><span data-ttu-id="859f5-127">Cambios en el comportamiento del cliente</span><span class="sxs-lookup"><span data-stu-id="859f5-127">Changes in client behavior</span></span>

<span data-ttu-id="859f5-128">Una vez habilitada la pertenencia dinámica para un equipo, los clientes de equipos ya no le permitirá la gestión de miembros para el equipo.</span><span class="sxs-lookup"><span data-stu-id="859f5-128">Once dynamic membership is enabled for a team, Teams clients will no longer allow member management for the team.</span></span> <span data-ttu-id="859f5-129">Todas las opciones para agregar a miembros, editar funciones miembro, enviar y aprobar las solicitudes de participación y deje el equipo están ocultos.</span><span class="sxs-lookup"><span data-stu-id="859f5-129">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>
