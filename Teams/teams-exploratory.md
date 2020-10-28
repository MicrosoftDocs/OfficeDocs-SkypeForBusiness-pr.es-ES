---
title: Administrar la experiencia de Microsoft Teams Exploratory
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: reference
audience: Admin
ms.reviewer: baluc
ms.service: msteams
search.appverid: MET150
localization_priority: Priority
description: Los usuarios de Office 365 o Microsoft 365 que no tienen una licencia de Microsoft Teams pueden activar una licencia de Teams Exploratory.
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: 35ebe9f93321b67806b9fd777aba948f83954c04
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753585"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="82534-103">Administrar la licencia de Microsoft Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="82534-103">Manage the Microsoft Teams Exploratory license</span></span>
=======================================================

<span data-ttu-id="82534-104">La experiencia de Microsoft Teams Exploratory permite a los usuarios de su organización que tienen Azure Active Directory (Azure AD) y no tengan licencia para los Teams iniciar una experiencia exploratoria de los Teams.</span><span class="sxs-lookup"><span data-stu-id="82534-104">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (Azure AD) and aren't licensed for Teams initiate an exploratory experience of Teams.</span></span> <span data-ttu-id="82534-105">Los administradores pueden activar o desactivar esta característica para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="82534-105">Admins can switch this feature on or off for users in their organization.</span></span> <span data-ttu-id="82534-106">La anterior [oferta de prueba comercial en la nube de Microsoft](iw-trial-teams.md) se ha reemplazado por la experiencia exploratoria de Teams.</span><span class="sxs-lookup"><span data-stu-id="82534-106">The earlier [Microsoft Commercial Cloud Trial](iw-trial-teams.md) is now replaced by The Teams Exploratory experience.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="82534-107">¿Qué incluye la experiencia de Teams Exploratory?</span><span class="sxs-lookup"><span data-stu-id="82534-107">What's in the Teams Exploratory experience</span></span>

<span data-ttu-id="82534-108">Los planes de servicio que verá un administrador como parte de la experiencia de Teams Exploratory son:</span><span class="sxs-lookup"><span data-stu-id="82534-108">The service plans that an admin will see as part of the Teams Exploratory experience are:</span></span>

- <span data-ttu-id="82534-109">Exchange Online (plan 1)</span><span class="sxs-lookup"><span data-stu-id="82534-109">Exchange Online (Plan 1)</span></span>
- <span data-ttu-id="82534-110">Flow para Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="82534-110">Flow for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="82534-111">Información de MyAnalytics</span><span class="sxs-lookup"><span data-stu-id="82534-111">Insights by MyAnalytics</span></span>
- <span data-ttu-id="82534-112">Microsoft Forms (plan E1)</span><span class="sxs-lookup"><span data-stu-id="82534-112">Microsoft Forms (Plan E1)</span></span>
- <span data-ttu-id="82534-113">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="82534-113">Microsoft Planner</span></span>
- <span data-ttu-id="82534-114">Búsqueda de Microsoft</span><span class="sxs-lookup"><span data-stu-id="82534-114">Microsoft Search</span></span>
- <span data-ttu-id="82534-115">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="82534-115">Microsoft StaffHub</span></span>
- <span data-ttu-id="82534-116">SKU de Microsoft Stream para Microsoft 365 y Office 365 E1 <sup>1</1></span><span class="sxs-lookup"><span data-stu-id="82534-116">Microsoft Stream for Microsoft 365 and Office 365 E1 SKUs <sup>1</1></span></span>
- <span data-ttu-id="82534-117">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="82534-117">Microsoft Teams</span></span>
- <span data-ttu-id="82534-118">Administración de dispositivos móviles para Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="82534-118">Mobile Device Management for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="82534-119">Aplicaciones móviles de Office para Office 365</span><span class="sxs-lookup"><span data-stu-id="82534-119">Office Mobile Apps for Office 365</span></span>
- <span data-ttu-id="82534-120">Office Online</span><span class="sxs-lookup"><span data-stu-id="82534-120">Office Online</span></span>
- <span data-ttu-id="82534-121">PowerApps para Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="82534-121">PowerApps for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="82534-122">SharePoint Online (plan 1)</span><span class="sxs-lookup"><span data-stu-id="82534-122">SharePoint Online (Plan 1)</span></span>
- <span data-ttu-id="82534-123">Sway</span><span class="sxs-lookup"><span data-stu-id="82534-123">Sway</span></span>
- <span data-ttu-id="82534-124">To-Do (plan 1)</span><span class="sxs-lookup"><span data-stu-id="82534-124">To-Do (Plan 1)</span></span>
- <span data-ttu-id="82534-125">Whiteboard (plan 1)</span><span class="sxs-lookup"><span data-stu-id="82534-125">Whiteboard (Plan 1)</span></span>
- <span data-ttu-id="82534-126">Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="82534-126">Yammer Enterprise</span></span>

  <span data-ttu-id="82534-127"><sup>1</sup> El cambio de uso desde Microsoft Stream a [OneDrive para la Empresa y SharePoint para grabar reuniones](tmr-meeting-recording-change.md) estará basado en fases.</span><span class="sxs-lookup"><span data-stu-id="82534-127"><sup>1</sup> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach.</span></span> <span data-ttu-id="82534-128">Durante el lanzamiento podrá participar en esta experiencia.</span><span class="sxs-lookup"><span data-stu-id="82534-128">At launch you'll be able to opt in to this experience.</span></span> <span data-ttu-id="82534-129">En noviembre, tendrá que decidir si quiere seguir usando la secuencia.</span><span class="sxs-lookup"><span data-stu-id="82534-129">In November, you'll have to opt out if you want to continue using Stream.</span></span> <span data-ttu-id="82534-130">En un momento, a principios de 2021, requerimos que todos los clientes usen OneDrive para la Empresa y SharePoint para las nuevas grabaciones de la reunión.</span><span class="sxs-lookup"><span data-stu-id="82534-130">Sometime in early 2021, we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

## <a name="whos-eligible"></a><span data-ttu-id="82534-131">Quién reúne los requisitos</span><span class="sxs-lookup"><span data-stu-id="82534-131">Who's eligible</span></span>

<span data-ttu-id="82534-132">Los usuarios se ajustan a los requerimientos para una experiencia de Teams Exploratory si:</span><span class="sxs-lookup"><span data-stu-id="82534-132">Users fit the criteria for a Teams Exploratory experience if they:</span></span>

- <span data-ttu-id="82534-133">Tienen una dirección de correo electrónico de dominio de Azure AD administrada.</span><span class="sxs-lookup"><span data-stu-id="82534-133">Have a managed Azure AD domain email address.</span></span>
- <span data-ttu-id="82534-134">Pertenecen a un inquilino con una suscripción pagada.</span><span class="sxs-lookup"><span data-stu-id="82534-134">Belong to a tenant with a paid subscription.</span></span>

<span data-ttu-id="82534-135">Los usuarios deben estar habilitados para registrarse en aplicaciones y versiones de prueba (en el Centro de administración de Microsoft 365).</span><span class="sxs-lookup"><span data-stu-id="82534-135">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center).</span></span> <span data-ttu-id="82534-136">Para más información, vea [Administrar la experiencia Teams Exploratory](#manage-the-teams-exploratory-experience), más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="82534-136">For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.</span></span>

## <a name="who-isnt-eligible"></a><span data-ttu-id="82534-137">¿Quiénes no cumplen los requisitos?</span><span class="sxs-lookup"><span data-stu-id="82534-137">Who isn't eligible</span></span>

<span data-ttu-id="82534-138">Los usuarios no se ajustan a los requerimientos si:</span><span class="sxs-lookup"><span data-stu-id="82534-138">Users don't fit the criteria if they:</span></span>

- <span data-ttu-id="82534-139">Tienen una licencia de Teams o previamente tenía una licencia de Teams de pago.</span><span class="sxs-lookup"><span data-stu-id="82534-139">Have a Teams license or previously had a paid Teams license.</span></span>
- <span data-ttu-id="82534-140">Está usando una prueba o una oferta de prueba de COVID.</span><span class="sxs-lookup"><span data-stu-id="82534-140">Are using a trial or COVID trial offer.</span></span>
- <span data-ttu-id="82534-141">Está en un espacio empresarial que tiene al menos una oferta de prueba especial de COVID.</span><span class="sxs-lookup"><span data-stu-id="82534-141">Are in a tenant that has at least one special COVID trial offer.</span></span>

<span data-ttu-id="82534-142">Su organización no es apta para esta oferta si usted es cliente de Syndication Partner o cliente de GCC, GCC High, DoD o EDU.</span><span class="sxs-lookup"><span data-stu-id="82534-142">Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or EDU customer.</span></span>

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="82534-143">¿Cómo los usuarios se pueden inscribir en la experiencia de Teams Exploratory?</span><span class="sxs-lookup"><span data-stu-id="82534-143">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="82534-144">Los usuarios que son aptos pueden registrarse para la oferta de la experiencia de Teams Exploratory iniciando sesión en Teams ([teams.microsoft.com](https://teams.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="82534-144">Eligible users can sign up for the Teams Exploratory experience by signing in to Teams ([teams.microsoft.com](https://teams.microsoft.com)).</span></span> <span data-ttu-id="82534-145">Se les asignará esta licencia automáticamente y el administrador del espacio empresarial recibirá una notificación por correo electrónico la primera vez que un usuario de su organización active la experiencia de Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="82534-145">They'll be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="82534-146">Administrar la experiencia de Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="82534-146">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="82534-147">La experiencia de Teams Exploratory está pensada para ser iniciada por usuarios finales individuales, y usted no puede iniciar esta oferta en nombre de los empleados que sean usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="82534-147">The Teams Exploratory experience is meant to be initiated by individual end users, and you can't initiate this offer on behalf of end-user employees.</span></span>

<span data-ttu-id="82534-148">La experiencia de Teams Exploratory viene con una licencia de Exchange Online pero no será asignada al usuario hasta que el administrador la asigne.</span><span class="sxs-lookup"><span data-stu-id="82534-148">The Teams Exploratory experience comes with an Exchange Online license, but it won't be assigned to the user until the admin assigns it.</span></span> <span data-ttu-id="82534-149">Si el usuario no tiene una licencia de Exchange y el administrador aún no ha asignado la licencia de Exchange Online, el usuario no podrá programar reuniones en Teams y es posible que no disponga de otras características.</span><span class="sxs-lookup"><span data-stu-id="82534-149">If the user doesn't have an Exchange license already, and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and might be missing other Teams functionality.</span></span>

<span data-ttu-id="82534-150">Los administradores pueden desactivar la opción de que los usuarios finales ejecuten la experiencia de Teams Exploratory dentro de su organización mediante el uso del conmutador de **aplicaciones y servicios de prueba** .</span><span class="sxs-lookup"><span data-stu-id="82534-150">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>

### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="82534-151">Evitar que los usuarios instalen aplicaciones y servicios de prueba</span><span class="sxs-lookup"><span data-stu-id="82534-151">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="82534-152">Puede desactivar la capacidad de un usuario para instalar aplicaciones y servicios de prueba, lo que impediría al usuario ejecutar la experiencia de Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="82534-152">You can turn off a user's ability to install trial apps and services, which would prevent the user from running the Teams Exploratory experience.</span></span>

1. <span data-ttu-id="82534-153">Desde el Centro de administración de Microsoft 365, vaya a **Configuración** > **Configuración de la organización** , seleccione **Servicios** , y luego seleccione **Aplicaciones y servicios que son propiedad del usuario** .</span><span class="sxs-lookup"><span data-stu-id="82534-153">From the Microsoft 365 admin center, go to **Settings** > **Org settings** , select **Services** , and then select **User owned apps and services** .</span></span>

    ![la página servicios en el centro de administración de](media/iw-trial-services.png)

2. <span data-ttu-id="82534-155">Desactive la casilla **Permitir que los usuarios instalen aplicaciones de prueba y servicios** .</span><span class="sxs-lookup"><span data-stu-id="82534-155">Clear the **Let users install trial apps and services** check box.</span></span>

    ![la página de aplicaciones y servicios que pertenecen al usuario en el centro de administración](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > <span data-ttu-id="82534-157">Si su organización no es apta para la experiencia de Teams Exploratory, no verá la opción **Dejar que los usuarios instalen aplicaciones y servicios de prueba** . </span><span class="sxs-lookup"><span data-stu-id="82534-157">If your organization is ineligible for the Teams Exploratory experience, you won't see the **Let users install trial apps and services** option.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="82534-158">Administrar la disponibilidad de un usuario con una licencia que incluye Teams</span><span class="sxs-lookup"><span data-stu-id="82534-158">Manage availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="82534-159">Un usuario al que se le asigne una licencia que incluya Teams no es apto para la experiencia de Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="82534-159">A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience.</span></span> <span data-ttu-id="82534-160">Cuando el plan de servicio de Teams está activado, el usuario puede iniciar sesión y utilizarlo.</span><span class="sxs-lookup"><span data-stu-id="82534-160">When the Teams service plan is turned on, the user can sign in and use Teams.</span></span> <span data-ttu-id="82534-161">Si el plan de servicio está desactivado, el usuario no puede iniciar sesión y la experiencia de Teams Exploratory no estará disponible.</span><span class="sxs-lookup"><span data-stu-id="82534-161">If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available.</span></span> <span data-ttu-id="82534-162">Debe tener privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="82534-162">You must have admin privileges.</span></span>

<span data-ttu-id="82534-163">Para desactivar el acceso a Teams:</span><span class="sxs-lookup"><span data-stu-id="82534-163">To turn off access to Teams:</span></span>

1. <span data-ttu-id="82534-164">En el Centro de administración de Microsoft 365, seleccione **Usuarios** > **Usuarios activos** .</span><span class="sxs-lookup"><span data-stu-id="82534-164">In the Microsoft 365 admin center, select **Users** > **Active users** .</span></span>

2. <span data-ttu-id="82534-165">Seleccione la casilla junto al nombre del usuario.</span><span class="sxs-lookup"><span data-stu-id="82534-165">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="82534-166">En la fila **Licencias de producto** , elija **Editar** .</span><span class="sxs-lookup"><span data-stu-id="82534-166">In the **Product licenses** row, choose **Edit** .</span></span>

4. <span data-ttu-id="82534-167">En el panel **Licencias de producto** , cambie el botón de alternancia a **Desactivado** .</span><span class="sxs-lookup"><span data-stu-id="82534-167">In the **Product licenses** pane, switch the toggle to **Off** .</span></span>

    ![la página licencias de producto en el centro de administración.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="82534-169">Administrar la disponibilidad de Teams para los usuarios que ya estén utilizando la experiencia Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="82534-169">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="82534-170">Si un usuario está usando la experiencia Teams Exploratory, puede desactivarla eliminando la licencia o el plan de servicio.</span><span class="sxs-lookup"><span data-stu-id="82534-170">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan.</span></span> <span data-ttu-id="82534-171">Debe tener privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="82534-171">You must have admin privileges.</span></span>

<span data-ttu-id="82534-172">Para desactivar la licencia de la experiencia de Teams Exploratory:</span><span class="sxs-lookup"><span data-stu-id="82534-172">To turn off the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="82534-173">En el Centro de administración de Microsoft 365, seleccione **Usuarios** > **Usuarios activos** .</span><span class="sxs-lookup"><span data-stu-id="82534-173">In the Microsoft 365 admin center, select **Users** > **Active users** .</span></span>

2. <span data-ttu-id="82534-174">Seleccione la casilla junto al nombre del usuario.</span><span class="sxs-lookup"><span data-stu-id="82534-174">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="82534-175">En la fila **Licencias de producto** , elija **Editar** .</span><span class="sxs-lookup"><span data-stu-id="82534-175">In the **Product licenses** row, choose **Edit** .</span></span>

4. <span data-ttu-id="82534-176">En el panel de **licencias de producto** , cambie el botón de alternancia para la licencia exploratoria a **Desactivado** .</span><span class="sxs-lookup"><span data-stu-id="82534-176">In the **Product licenses** pane, switch the toggle for this exploratory license to **Off** .</span></span>

    >[!Note]
    ><span data-ttu-id="82534-177">El botón de alternancia de Teams Exploratory aparecerá después de que el primer usuario de la organización inicie la experiencia de Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="82534-177">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="82534-178">Administrar Teams para los usuarios que dispongan de la licencia de Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="82534-178">Manage Teams for users who have the Teams Exploratory license</span></span>

<span data-ttu-id="82534-179">Puede administrar a los usuarios que dispongan de la licencia de Teams Exploratory al igual que a los usuarios que dispongan de una licencia pagada estándar.</span><span class="sxs-lookup"><span data-stu-id="82534-179">You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license.</span></span> <span data-ttu-id="82534-180">Para más información, vea [Administrar la configuración de Teams para su organización](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="82534-180">For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-the-teams-exploratory-license"></a><span data-ttu-id="82534-181">Actualizar los usuarios de la licencia de Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="82534-181">Upgrade users from the Teams Exploratory license</span></span>

<span data-ttu-id="82534-182">Para actualizar los usuarios de la licencia de Teams Exploratory (debe tener privilegios de administrador), realice las siguientes tareas:</span><span class="sxs-lookup"><span data-stu-id="82534-182">To upgrade users from the Teams Exploratory license (you must have admin privileges), do the following tasks:</span></span>

1. <span data-ttu-id="82534-183">Adquiera una suscripción que incluya Teams.</span><span class="sxs-lookup"><span data-stu-id="82534-183">Purchase a subscription that includes Teams.</span></span>

2. <span data-ttu-id="82534-184">Elimine la suscripción del usuario a Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="82534-184">Remove the Teams Exploratory subscription from the user.</span></span>

3. <span data-ttu-id="82534-185">Asignar la licencia que acaba de adquirir.</span><span class="sxs-lookup"><span data-stu-id="82534-185">Assign the newly purchased license.</span></span>

<span data-ttu-id="82534-186">Para más información, consulte [Descripción del servicio de Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="82534-186">For more information, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

> [!NOTE]
> <span data-ttu-id="82534-187">Si la licencia de Teams Exploratory finaliza y un usuario no se actualiza inmediatamente a una suscripción que incluya Teams, tiene 30 días de periodo de gracia y, a continuación, en el plazo de 30 días tras el que se van a eliminar los datos.</span><span class="sxs-lookup"><span data-stu-id="82534-187">If the Teams Exploratory license ends and a user isn't immediately upgraded to a subscription that includes Teams, they have 30 days of grace period and then another 30 days after which time the data is going to be deleted.</span></span> <span data-ttu-id="82534-188">El usuario aún existe en Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="82534-188">The user still exists in Azure Active Directory.</span></span> <span data-ttu-id="82534-189">Una vez que se asigne una nueva licencia al usuario para habilitar de nuevo la funcionalidad de Teams, todo el contenido seguirá existiendo si se agrega el usuario dentro del plazo del período de gracia.</span><span class="sxs-lookup"><span data-stu-id="82534-189">Once a new license is assigned to the user to enable Teams functionality again, all content will still exist if the user is added within the grace period time frame.</span></span>

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a><span data-ttu-id="82534-190">Qué sucede con las licencias heredadas de la versión de prueba de Microsoft Teams Commercial Cloud</span><span class="sxs-lookup"><span data-stu-id="82534-190">What happens to legacy Microsoft Teams Commercial Cloud Trial licenses</span></span>

<span data-ttu-id="82534-191">A partir de febrero de 2020, los usuarios aptos podrán utilizar la versión más reciente de la experiencia de Microsoft Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="82534-191">As of February 2020, eligible users can begin using the latest Microsoft Teams Exploratory experience.</span></span> <span data-ttu-id="82534-192">Todas las licencias heredadas de la versión de prueba de Commercial Cloud de Teams se convertirán automáticamente a un nuevo plan antes de que expire su versión de prueba.</span><span class="sxs-lookup"><span data-stu-id="82534-192">All legacy Teams Commercial Cloud Trial licenses will be automatically converted to the new offer before their trial expires.</span></span>

<span data-ttu-id="82534-193">Cuando los usuarios inician sesión en su versión de prueba de Teams Commercial Cloud expirada por primera vez, asignamos automáticamente una licencia de la experiencia de Teams Exploratory a estos usuarios.</span><span class="sxs-lookup"><span data-stu-id="82534-193">When users sign in to their expired Teams Commercial Cloud Trial for the first time, we automatically assign a Teams Exploratory experience license to those users.</span></span> <span data-ttu-id="82534-194">Los usuarios no se convierten hasta que inician sesión.</span><span class="sxs-lookup"><span data-stu-id="82534-194">Users aren't converted until they sign in.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="82534-195">Eliminar la licencia de Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="82534-195">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="82534-196">Si usted desea eliminar la licencia usando PowerShell, vea: [Eliminar las licencias de las cuentas de usuario con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="82534-196">If you would like to remove this license by using PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="82534-197">Si quiere eliminar esta licencia a través del Portal de administración, consulte: [Quitar a un usuario de su organización](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span><span class="sxs-lookup"><span data-stu-id="82534-197">If you would like to remove this license through the admin portal, see: [Delete a user from your organization](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span></span>

## <a name="what-is-the-data-retention-policy"></a><span data-ttu-id="82534-198">Qué es la directiva de retención de datos</span><span class="sxs-lookup"><span data-stu-id="82534-198">What is the data retention policy?</span></span>

<span data-ttu-id="82534-199">Vea [información de la suscripción a Microsoft 365](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="82534-199">See [Microsoft 365 subscription information](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span></span>

## <a name="how-long-does-the-teams-exploratory-experience-last"></a><span data-ttu-id="82534-200">¿Cuánto tiempo dura la experiencia de Teams Exploratory?</span><span class="sxs-lookup"><span data-stu-id="82534-200">How long does the Teams Exploratory experience last</span></span>

<span data-ttu-id="82534-201">La experiencia de Microsoft Teams Exploratory está disponible sin costo adicional hasta la próxima fecha de **aniversario** o **renovación del contrato** empresarial, en enero de 2021 o después.</span><span class="sxs-lookup"><span data-stu-id="82534-201">The Microsoft Teams Exploratory experience is available at no additional cost until your next **agreement anniversary** or **renewal** on or after January 2021.</span></span> <span data-ttu-id="82534-202">En ese momento, los usuarios finales de una licencia de la experiencia de Microsoft Exploratory tendrán que cambiarse a una licencia de pago que incluya Teams.</span><span class="sxs-lookup"><span data-stu-id="82534-202">At that time, end users on a Microsoft Exploratory experience license will need to move to a paid license that includes Teams.</span></span> <span data-ttu-id="82534-203">Aquellas licencias de experiencia de Microsoft Exploratory que se inicien después de esa fecha permanecerán disponibles sin costo adicional hasta su próximo **aniversario** o ciclo de **renovación** .</span><span class="sxs-lookup"><span data-stu-id="82534-203">Any Microsoft Exploratory experience licenses initiated after that will remain available at no additional cost until your next **anniversary** or **renewal** cycle.</span></span>

### <a name="what-happens-if-an-end-user-initiates-the-microsoft-teams-exploratory-experience-just-before-the-anniversary-or-renewal-date"></a><span data-ttu-id="82534-204">Qué ocurre si un usuario final inicia la experiencia de Microsoft Teams Exploratory justo antes del aniversario o fecha de renovación</span><span class="sxs-lookup"><span data-stu-id="82534-204">What happens if an end user initiates the Microsoft Teams Exploratory experience just before the anniversary or renewal date</span></span>

<span data-ttu-id="82534-205">Las licencias de la experiencia de Microsoft Teams Exploratory iniciadas en un plazo de 90 días antes de la fecha de su **acuerdos de aniversario** o **renovación** de su empresa no deberán cambiarse a una licencia de pago hasta el siguiente aniversario o ciclo de renovación.</span><span class="sxs-lookup"><span data-stu-id="82534-205">Microsoft Teams Exploratory experience licenses initiated within 90 days of your **agreement anniversary** or **renewal** won't be required to move to a paid license until the subsequent anniversary or renewal cycle.</span></span>

### <a name="what-if-my-agreement-doesnt-have-an-anniversary-or-yearly-renewal-date-for-example-month-to-month-agreements"></a><span data-ttu-id="82534-206">Qué ocurre si mi acuerdo no tiene ninguna fecha de aniversario o renovación anual (por ejemplo, acuerdos mensuales)</span><span class="sxs-lookup"><span data-stu-id="82534-206">What if my agreement doesn’t have an anniversary or yearly renewal date (for example, month-to-month agreements)</span></span>

<span data-ttu-id="82534-207">En el caso de contratos sin una fecha de aniversario o una renovación anual, el año siguiente después de que el primer usuario final active las licencias de experiencia de Microsoft Teams Exploratory se considerará como el aniversario o la fecha de renovación.</span><span class="sxs-lookup"><span data-stu-id="82534-207">For agreements without an anniversary or yearly renewal date, the subsequent year after the first end-user activates the Microsoft Teams Exploratory experience licenses will be treated as the anniversary or renewal date.</span></span> <span data-ttu-id="82534-208">Los usuarios que tengan licencia de Microsoft Teams Exploratory deben pasar a una licencia de pago en esa fecha cada año, según las directivas indicadas en este artículo.</span><span class="sxs-lookup"><span data-stu-id="82534-208">Users on the Microsoft Teams Exploratory license must be converted to a paid license by that date each year, according to the policies outlined in this article.</span></span>

<span data-ttu-id="82534-209">Por ejemplo, si el primer usuario final activa Microsoft Teams Exploratory el 19 de junio de 2020, este usuario y todos los demás elegibles en el espacio empresarial del cliente deben pasar a una licencia de pago con Teams el 19 de junio de 2021.</span><span class="sxs-lookup"><span data-stu-id="82534-209">For example, if the first end user activates Microsoft Teams Exploratory on June 19, 2020, then they and all other eligible users in the customer tenant must convert to a paid license with Teams by June 19, 2021.</span></span>

> [!Note]
> <span data-ttu-id="82534-210">Se deshabilitará a los clientes y se les impedirá que inicien nuevas licencias de prueba de Exploratory durante 3 meses pasado la fecha de expiración de la licencia de prueba de Exploratory anterior.</span><span class="sxs-lookup"><span data-stu-id="82534-210">Customers will be disabled and blocked from starting a new Exploratory trial licenses for 3 months past the expiration of their previous Exploratory trial license.</span></span>
