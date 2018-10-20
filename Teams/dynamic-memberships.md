---
title: Información general de pertenencia dinámica para los equipos
author: jambirk
ms.author: jambirk
manager: serdars
ms.date: 10/10/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre pertenencia dinámica de equipos en función de AAD.
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a98009237d6575e97705ae7a8eea4b444ac77a0
ms.sourcegitcommit: 044286f9dec2743a622bdaeac03469418cfdfa0d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/19/2018
ms.locfileid: "25682369"
---
# <a name="overview-of-dynamic-membership-for-teams"></a><span data-ttu-id="0cdb2-103">Información general de pertenencia dinámica para los equipos</span><span class="sxs-lookup"><span data-stu-id="0cdb2-103">Overview of dynamic membership for teams</span></span>

<span data-ttu-id="0cdb2-104">Microsoft Teams es compatible con los equipos asociados con grupos de Office 365 mediante pertenencia dinámica.</span><span class="sxs-lookup"><span data-stu-id="0cdb2-104">Microsoft Teams supports teams associated with Office 365 groups using dynamic membership.</span></span> <span data-ttu-id="0cdb2-105">Pertenencia dinámica permite la pertenencia de un equipo a definirse por una o varias reglas que comprobación ciertos atributos de usuario en Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="0cdb2-105">Dynamic membership enables the membership of a team to be defined by one or more rules that check for certain user attributes in Azure Active Directory (AAD).</span></span> <span data-ttu-id="0cdb2-106">Los usuarios automáticamente se agregan o quitan a los equipos de la correctos como cambian atributos de usuario o los usuarios al unirse y abandonar al inquilino.</span><span class="sxs-lookup"><span data-stu-id="0cdb2-106">Users are automatically added or removed to the correct teams as user attributes change or users join and leave the tenant.</span></span>

<span data-ttu-id="0cdb2-107">Con pertenencia dinámica que se puede el programa de instalación para determinados equipos a las cohortes de los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="0cdb2-107">With dynamic membership you can setup teams for certain cohorts of users in your organization.</span></span> <span data-ttu-id="0cdb2-108">Los escenarios posibles son:</span><span class="sxs-lookup"><span data-stu-id="0cdb2-108">Possible scenarios include:</span></span>
- <span data-ttu-id="0cdb2-109">Un hospital puede crear distintos equipos para enfermeras, médicos y cirujanos difundir communications.</span><span class="sxs-lookup"><span data-stu-id="0cdb2-109">A hospital can create distinct teams for nurses, doctors, and surgeons to broadcast communications.</span></span> <span data-ttu-id="0cdb2-110">Esto es especialmente importante si el hospital se basa en los empleados temporales.</span><span class="sxs-lookup"><span data-stu-id="0cdb2-110">This is especially important if the hospital relies on temp employees.</span></span>
- <span data-ttu-id="0cdb2-111">Una universidad puede crear un equipo para todos los profesores dentro de un determinado universitario, incluido un profesor adjuntos que cambia con frecuencia.</span><span class="sxs-lookup"><span data-stu-id="0cdb2-111">A university can create a team for all faculty within a particular college, including an adjunct faculty that changes frequently.</span></span>
- <span data-ttu-id="0cdb2-112">Un compañías aéreas desea crear un equipo para cada vuelo (al igual que un martes por la tarde sin interrupciones de Chicago a Atlanta) y tienen un crew vuelo que cambia con frecuencia asignada automáticamente o quitan según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="0cdb2-112">An airline wants to create a team for each flight (like a Tuesday afternoon non-stop from Chicago to Atlanta) and have a frequently changing flight crew automatically assigned or removed as needed.</span></span>

<span data-ttu-id="0cdb2-113">Uso de esta característica, actualización de los miembros de un equipo determinado automáticamente según un conjunto específico de criterios, en lugar de administrar manualmente pertenencia.</span><span class="sxs-lookup"><span data-stu-id="0cdb2-113">Using this feature, a given team's members update automatically based on a specific set of criteria, instead of manually managing membership.</span></span> <span data-ttu-id="0cdb2-114">Esta acción requiere licencias de Azure AD Premium P1 y los miembros del equipo pueden ser [asignado por un administrador de inquilinos](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) a las propiedades AAD de cualquier usuario siempre y que cuando disponga de un inquilino y una cuenta de administrador.</span><span class="sxs-lookup"><span data-stu-id="0cdb2-114">Doing this requires Azure AD Premium P1 licenses and team membership can be [assigned by a tenant admin](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership) to any user's AAD properties provided you have a tenant and an admin account.</span></span>

<span data-ttu-id="0cdb2-115">Microsoft Teams puede durar desde unos minutos hasta 2 horas para reflejar los cambios de pertenencia dinámica una vez que surtan efecto en el grupo de Office 365 para un equipo.</span><span class="sxs-lookup"><span data-stu-id="0cdb2-115">Microsoft Teams may take anywhere from a few minutes to up to 2 hours to reflect dynamic membership changes once they take effect in the Office 365 group for a team.</span></span>

> [!NOTE]
> <span data-ttu-id="0cdb2-116">Pueden definir las reglas de los miembros del equipo, pero no los propietarios del equipo.</span><span class="sxs-lookup"><span data-stu-id="0cdb2-116">Rules can define Team members, but not team Owners.</span></span>

## <a name="creating-and-managing-an-office-365-group-with-dynamic-membership"></a><span data-ttu-id="0cdb2-117">Creación y administración de un grupo de Office 365 con pertenencia dinámica</span><span class="sxs-lookup"><span data-stu-id="0cdb2-117">Creating and managing an Office 365 group with dynamic membership</span></span>
<span data-ttu-id="0cdb2-118">Cuando haya iniciado sesión como el Administrador de inquilinos, siga las instrucciones de [crear un grupo dinámico y compruebe el estado](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span><span class="sxs-lookup"><span data-stu-id="0cdb2-118">While logged in as the tenant Admin, follow the instructions in [Create a dynamic group and check status](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule).</span></span> <span data-ttu-id="0cdb2-119">Según sea necesario, hacer referencia a [las reglas de pertenencia dinámica para los grupos en Active Directory de Azure](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span><span class="sxs-lookup"><span data-stu-id="0cdb2-119">As needed, refer to [Dynamic membership rules for groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-dynamic-membership).</span></span>

## <a name="create-a-new-team-with-your-o365-group"></a><span data-ttu-id="0cdb2-120">Crear un nuevo equipo con su grupo de O365</span><span class="sxs-lookup"><span data-stu-id="0cdb2-120">Create a new team with your O365 group</span></span>

<span data-ttu-id="0cdb2-121">Ahora Permitir tiempo para que surtan efecto los cambios de pertenencia y crear un nuevo equipo tal como se describe en [grupos de mejorar existente Office 365 con los equipos de Microsoft](enhance-office-365-groups.md).</span><span class="sxs-lookup"><span data-stu-id="0cdb2-121">Now allow time for the membership changes to take effect, and create a new team  as described in [Enhance Existing Office 365 groups with Microsoft Teams](enhance-office-365-groups.md).</span></span>

## <a name="apply-dynamic-membership-to-an-existing-team"></a><span data-ttu-id="0cdb2-122">Aplicar pertenencia dinámica a un equipo existente</span><span class="sxs-lookup"><span data-stu-id="0cdb2-122">Apply dynamic membership to an existing team</span></span>

<span data-ttu-id="0cdb2-123">También puede tomar un equipo existente y cámbiela para que tenga una pertenencia dinámica, tal como se describe en [cambiar la pertenencia a grupo estático a dinámico en Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span><span class="sxs-lookup"><span data-stu-id="0cdb2-123">You can also take an existing team and change it to have a dynamic membership, as described in [Change static group membership to dynamic in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-change-type).</span></span>

## <a name="changes-in-client-behavior"></a><span data-ttu-id="0cdb2-124">Cambios en el comportamiento del cliente</span><span class="sxs-lookup"><span data-stu-id="0cdb2-124">Changes in client behavior</span></span>

<span data-ttu-id="0cdb2-125">Una vez habilitada la pertenencia dinámica para un equipo, los clientes de equipos ya no le permitirá la gestión de miembros para el equipo.</span><span class="sxs-lookup"><span data-stu-id="0cdb2-125">Once dynamic membership is enabled for a team, Teams clients will no longer allow member management for the team.</span></span> <span data-ttu-id="0cdb2-126">Todas las opciones para agregar a miembros, editar funciones miembro, enviar y aprobar las solicitudes de participación y deje el equipo están ocultos.</span><span class="sxs-lookup"><span data-stu-id="0cdb2-126">Options to add members, edit member roles, send and approve join requests, and leave the team are all hidden.</span></span>
