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
description: Los usuarios de Office 365 o Microsoft 365 que no tienen una licencia de Microsoft Teams pueden activar una licencia de Teams Exploratory.
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 946847793ea90e549a555cd9d100cd1ae2809fa3
ms.sourcegitcommit: f3e9989cbcc2f9f83ff94204bdd75b1e6ad43b5e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2021
ms.locfileid: "53408759"
---
# <a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="99960-103">Administrar la licencia de Microsoft Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="99960-103">Manage the Microsoft Teams Exploratory license</span></span>

<span data-ttu-id="99960-p101">La experiencia de Microsoft Teams Exploratory permite a los usuarios de su organización que tienen Azure Active Directory (Azure AD) y no tienen licencia para Teams iniciar una experiencia exploratoria de Teams. Los administradores pueden activar o desactivar esta característica para los usuarios de su organización.</span><span class="sxs-lookup"><span data-stu-id="99960-p101">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (Azure AD) and aren't licensed for Teams initiate an exploratory experience of Teams. Admins can switch this feature on or off for users in their organization.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="99960-106">¿Qué incluye la experiencia de Teams Exploratory?</span><span class="sxs-lookup"><span data-stu-id="99960-106">What's in the Teams Exploratory experience</span></span>

<span data-ttu-id="99960-107">Los planes de servicio que verá un administrador como parte de la experiencia de Teams Exploratory son:</span><span class="sxs-lookup"><span data-stu-id="99960-107">The service plans that an admin will see as part of the Teams Exploratory experience are:</span></span>

- <span data-ttu-id="99960-108">Exchange Online (plan 1)</span><span class="sxs-lookup"><span data-stu-id="99960-108">Exchange Online (Plan 1)</span></span>
- <span data-ttu-id="99960-109">Flow para Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="99960-109">Flow for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="99960-110">Información de MyAnalytics</span><span class="sxs-lookup"><span data-stu-id="99960-110">Insights by MyAnalytics</span></span>
- <span data-ttu-id="99960-111">Microsoft Forms (plan E1)</span><span class="sxs-lookup"><span data-stu-id="99960-111">Microsoft Forms (Plan E1)</span></span>
- <span data-ttu-id="99960-112">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="99960-112">Microsoft Planner</span></span>
- <span data-ttu-id="99960-113">Búsqueda de Microsoft</span><span class="sxs-lookup"><span data-stu-id="99960-113">Microsoft Search</span></span>
- <span data-ttu-id="99960-114">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="99960-114">Microsoft StaffHub</span></span>
- <span data-ttu-id="99960-115">SKU de Microsoft Stream para Microsoft 365 y Office 365 E1 <sup>1</1></span><span class="sxs-lookup"><span data-stu-id="99960-115">Microsoft Stream for Microsoft 365 and Office 365 E1 SKUs <sup>1</1></span></span>
- <span data-ttu-id="99960-116">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="99960-116">Microsoft Teams</span></span>
- <span data-ttu-id="99960-117">Administración de dispositivos móviles para Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="99960-117">Mobile Device Management for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="99960-118">Aplicaciones móviles de Office para Office 365</span><span class="sxs-lookup"><span data-stu-id="99960-118">Office Mobile Apps for Office 365</span></span>
- <span data-ttu-id="99960-119">Office Online</span><span class="sxs-lookup"><span data-stu-id="99960-119">Office Online</span></span>
- <span data-ttu-id="99960-120">PowerApps para Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="99960-120">PowerApps for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="99960-121">SharePoint Online (plan 1)</span><span class="sxs-lookup"><span data-stu-id="99960-121">SharePoint Online (Plan 1)</span></span>
- <span data-ttu-id="99960-122">Sway</span><span class="sxs-lookup"><span data-stu-id="99960-122">Sway</span></span>
- <span data-ttu-id="99960-123">To-Do (plan 1)</span><span class="sxs-lookup"><span data-stu-id="99960-123">To-Do (Plan 1)</span></span>
- <span data-ttu-id="99960-124">Whiteboard (plan 1)</span><span class="sxs-lookup"><span data-stu-id="99960-124">Whiteboard (Plan 1)</span></span>
- <span data-ttu-id="99960-125">Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="99960-125">Yammer Enterprise</span></span>

  <span data-ttu-id="99960-p102"><sup>1</sup> El cambio de usar Microsoft Stream a usar [OneDrive para la Empresa y SharePoint para grabar reuniones](tmr-meeting-recording-change.md) se hará en varias fases. Durante el lanzamiento podrá participar en esta experiencia, pero en noviembre debe optar por no participar si quiere seguir usando Stream y, en algún momento, a principios de 2021, se les pedirá a todos los clientes que usen OneDrive para la Empresa y SharePoint para grabar sus reuniones nuevas.</span><span class="sxs-lookup"><span data-stu-id="99960-p102"><sup>1</sup> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach. At launch, you'll be able to opt in to this experience. In November, you'll have to opt out if you want to continue using Stream. Sometime in early 2021, we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

## <a name="whos-eligible"></a><span data-ttu-id="99960-130">Quién reúne los requisitos</span><span class="sxs-lookup"><span data-stu-id="99960-130">Who's eligible</span></span>

<span data-ttu-id="99960-131">Los usuarios se ajustan a los requerimientos para una experiencia de Teams Exploratory si:</span><span class="sxs-lookup"><span data-stu-id="99960-131">Users fit the criteria for a Teams Exploratory experience if they:</span></span>

- <span data-ttu-id="99960-132">Tienen una dirección de correo electrónico de dominio de Azure AD administrada.</span><span class="sxs-lookup"><span data-stu-id="99960-132">Have a managed Azure AD domain email address.</span></span>
- <span data-ttu-id="99960-133">Pertenecen a un espacio empresarial con una suscripción pagada.</span><span class="sxs-lookup"><span data-stu-id="99960-133">Belong to a tenant with a paid subscription.</span></span>
- <span data-ttu-id="99960-134">No tienen una licencia activa de Teams.</span><span class="sxs-lookup"><span data-stu-id="99960-134">Do not have an active Teams license.</span></span>
- <span data-ttu-id="99960-135">No están en un espacio empresarial donde se creó una directiva de asignación de licencias.</span><span class="sxs-lookup"><span data-stu-id="99960-135">Are not in a tenant where a license assignment policy was created.</span></span>

<span data-ttu-id="99960-p103">Se debe habilitar a los usuarios para registrarse en aplicaciones y pruebas (en el Centro de administración de Microsoft 365). Para obtener más información, consulte [Administrar la experiencia de Teams Exploratory](#manage-the-teams-exploratory-experience), más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="99960-p103">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center). For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.</span></span>

## <a name="who-isnt-eligible"></a><span data-ttu-id="99960-138">¿Quiénes no reúnen los requisitos?</span><span class="sxs-lookup"><span data-stu-id="99960-138">Who isn't eligible</span></span>

<span data-ttu-id="99960-139">Los usuarios no reúnen los requerimientos si:</span><span class="sxs-lookup"><span data-stu-id="99960-139">Users don't fit the criteria if they:</span></span>

- <span data-ttu-id="99960-140">Actualmente tiene Teams con una licencia de pago o de prueba, o bien tenía anteriormente una licencia de prueba.</span><span class="sxs-lookup"><span data-stu-id="99960-140">Currently have Teams from a paid license or trial license, or previously had trial license</span></span>
- <span data-ttu-id="99960-141">Se encuentran en un espacio empresarial que ha recibido, al menos, una oferta especial COVID.</span><span class="sxs-lookup"><span data-stu-id="99960-141">Are in a tenant that used/received at least one special COVID offer.</span></span>

<span data-ttu-id="99960-142">Su organización no es apta para esta oferta si usted es cliente de Syndication Partner o cliente de GCC, GCC High, DoD o EDU.</span><span class="sxs-lookup"><span data-stu-id="99960-142">Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or EDU customer.</span></span>

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="99960-143">¿Cómo los usuarios se pueden inscribir en la experiencia de Teams Exploratory?</span><span class="sxs-lookup"><span data-stu-id="99960-143">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="99960-144">Los usuarios que son aptos pueden inscribirse en la experiencia de Teams Exploratory iniciando sesión en Teams desde el equipo o la Web ([teams.microsoft.com](https://teams.microsoft.com)).</span><span class="sxs-lookup"><span data-stu-id="99960-144">Eligible users can sign up for the Teams Exploratory experience by signing in to Teams from the desktop or web ([teams.microsoft.com](https://teams.microsoft.com)).</span></span> <span data-ttu-id="99960-145">Por ahora, no está disponible la habilitación de Exploratory mediante dispositivos móviles.</span><span class="sxs-lookup"><span data-stu-id="99960-145">At this time, enabling Exploratory through mobile is not supported.</span></span> <span data-ttu-id="99960-146">Al registrarse, se les asignará esta licencia de manera automática, y el administrador del espacio empresarial recibirá una notificación por correo electrónico la primera vez que un usuario de su organización active la experiencia de Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="99960-146">When they sign up, they'll be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="99960-147">Administrar la experiencia de Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="99960-147">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="99960-148">La experiencia de Teams Exploratory está pensada para ser activada por usuarios finales individuales, y usted no puede activar esta oferta en nombre de los empleados que sean usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="99960-148">The Teams Exploratory experience is meant to be initiated by individual end users, and you can't initiate this offer on behalf of end-user employees.</span></span>

<span data-ttu-id="99960-p105">La experiencia Teams Exploratory viene con una licencia de Exchange Online, pero no se asignará al usuario hasta que el administrador la asigne. Si el usuario no tiene una licencia de Exchange y el administrador aún no ha asignado la licencia de Exchange Online, el usuario no podrá programar reuniones en Teams y es posible que no disponga de otras características.</span><span class="sxs-lookup"><span data-stu-id="99960-p105">The Teams Exploratory experience comes with an Exchange Online license, but it won't be assigned to the user until the admin assigns it. If the user doesn't have an Exchange license already, and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and might be missing other Teams functionality.</span></span>

<span data-ttu-id="99960-151">Los administradores pueden desactivar la opción de que los usuarios finales ejecuten la experiencia de Teams Exploratory dentro de su organización mediante el uso del conmutador de **aplicaciones y servicios de prueba**.</span><span class="sxs-lookup"><span data-stu-id="99960-151">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>

### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="99960-152">Evitar que los usuarios instalen aplicaciones y servicios de prueba</span><span class="sxs-lookup"><span data-stu-id="99960-152">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="99960-153">Puede desactivar la capacidad de un usuario para instalar aplicaciones y servicios de prueba, lo que impediría al usuario ejecutar la experiencia de Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="99960-153">You can turn off a user's ability to install trial apps and services, which would prevent the user from running the Teams Exploratory experience.</span></span>

1. <span data-ttu-id="99960-154">Desde el Centro de administración de Microsoft 365, vaya a **Configuración** > **Configuración de la organización**, seleccione **Servicios**, y luego seleccione **Aplicaciones y servicios que son propiedad del usuario**.</span><span class="sxs-lookup"><span data-stu-id="99960-154">From the Microsoft 365 admin center, go to **Settings** > **Org settings**, select **Services**, and then select **User owned apps and services**.</span></span>

    ![Captura de pantalla de la página Servicios en el centro de administración.](media/iw-trial-services.png)

2. <span data-ttu-id="99960-156">Quite la marca de verificación de **Permitir que los usuarios instalen aplicaciones y servicios de prueba**.</span><span class="sxs-lookup"><span data-stu-id="99960-156">Clear the check mark from **Let users install trial apps and services**.</span></span>

    ![Captura de pantalla de la página Aplicaciones y servicios en propiedad del usuario en el centro de administración.](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > <span data-ttu-id="99960-158">Si su organización no es apta para la experiencia de Teams Exploratory, no verá la opción **Dejar que los usuarios instalen aplicaciones y servicios de prueba**. </span><span class="sxs-lookup"><span data-stu-id="99960-158">If your organization is ineligible for the Teams Exploratory experience, you won't see the **Let users install trial apps and services** option.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="99960-159">Administrar la disponibilidad de un usuario con una licencia que incluye Teams</span><span class="sxs-lookup"><span data-stu-id="99960-159">Manage availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="99960-p106">Un usuario al que se ha asignado una licencia que incluye Teams no es apto para la experiencia Teams Exploratory. Cuando el plan de servicio de Teams esté activado, el usuario puede iniciar sesión y usar Teams. Si el plan de servicio está deshabilitado, el usuario no podrá iniciar sesión y la experiencia Teams Exploratory no estará disponible. Debe tener privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="99960-p106">A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience. When the Teams service plan is turned on, the user can sign in and use Teams. If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available. You must have admin privileges.</span></span>

<span data-ttu-id="99960-164">Para desactivar el acceso a Teams:</span><span class="sxs-lookup"><span data-stu-id="99960-164">To turn off access to Teams:</span></span>

1. <span data-ttu-id="99960-165">En el Centro de administración de Microsoft 365, seleccione **Usuarios** > **Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="99960-165">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="99960-166">Seleccione la casilla junto al nombre del usuario.</span><span class="sxs-lookup"><span data-stu-id="99960-166">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="99960-167">En la parte derecha, en la fila **Licencias de producto**, elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="99960-167">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="99960-168">En el panel **Licencias de producto**, cambie el botón de alternancia a **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="99960-168">In the **Product licenses** pane, switch the toggle to **Off**.</span></span>

    ![La página de licencias del producto en el centro de administración.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="99960-170">Administrar la disponibilidad de Teams para los usuarios que ya estén utilizando la experiencia Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="99960-170">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="99960-p107">Si un usuario está usando la experiencia Teams Exploratory, puede desactivarla eliminando la licencia o el plan de servicio. Debe tener privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="99960-p107">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan. You must have admin privileges.</span></span>

<span data-ttu-id="99960-173">Desactivar la licencia de la experiencia Teams Exploratory:</span><span class="sxs-lookup"><span data-stu-id="99960-173">To turn off the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="99960-174">En el Centro de administración de Microsoft 365, seleccione **Usuarios** > **Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="99960-174">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="99960-175">Seleccione la casilla junto al nombre del usuario.</span><span class="sxs-lookup"><span data-stu-id="99960-175">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="99960-176">En la parte derecha, en la fila **Licencias de producto**, elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="99960-176">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="99960-177">En el panel de **licencias de producto**, cambie el botón de alternancia para la licencia exploratoria a **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="99960-177">In the **Product licenses** pane, switch the toggle for this exploratory license to **Off**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="99960-178">El botón de alternancia de Teams Exploratory aparecerá después de que el primer usuario de la organización inicie la experiencia de Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="99960-178">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="99960-179">Administrar Teams para los usuarios que dispongan de la licencia de Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="99960-179">Manage Teams for users who have the Teams Exploratory license</span></span>

<span data-ttu-id="99960-p108">Puede administrar a los usuarios que dispongan de la licencia de Teams Exploratory al igual que a los usuarios que dispongan de una licencia pagada estándar. Para más información, consulte [Administrar la configuración de Teams para su organización](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="99960-p108">You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license. For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-teams-exploratory"></a><span data-ttu-id="99960-182">Actualizar los usuarios de Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="99960-182">Upgrade users from Teams Exploratory</span></span>

<span data-ttu-id="99960-183">Debe tener privilegios de administrador para actualizar usuarios de Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="99960-183">You must have admin privileges to upgrade users from Teams Exploratory.</span></span> <span data-ttu-id="99960-184">Para obtener más información, vea [Actualizar usuarios desde la versión de prueba de Teams Exploratory](upgrade-from-teams-exploratory.md).</span><span class="sxs-lookup"><span data-stu-id="99960-184">For more information see [Upgrade users from the Teams Exploratory trial](upgrade-from-teams-exploratory.md).</span></span>

> [!NOTE]
> <span data-ttu-id="99960-p110">Si la licencia exploratoria de Teams finaliza y un usuario no se actualiza inmediatamente a una suscripción que incluye Teams, perderá el acceso a Teams después de un período de gracia de 30 días. Otros 30 días después de los cuales, se eliminan los datos. El usuario todavía existe en Azure Active Directory. Una vez que se asigna una nueva licencia al usuario para habilitar la funcionalidad de Teams nuevamente, todo el contenido seguirá existiendo si el usuario se agrega dentro del período de tiempo de gracia.</span><span class="sxs-lookup"><span data-stu-id="99960-p110">If the Teams Exploratory license ends and a user isn't immediately upgraded to a subscription that includes Teams, they lose access to Teams after a 30-days grace period. Another 30 days after which, the data is deleted. The user still exists in Azure Active Directory. Once a new license is assigned to the user to enable Teams functionality again, all content will still exist if the user is added within the grace period time frame.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="99960-189">Eliminar una licencia de Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="99960-189">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="99960-190">Si usted desea eliminar la licencia usando PowerShell, consulte: [Eliminar las licencias de las cuentas de usuario con Office 365 PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="99960-190">If you would like to remove this license by using PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="99960-191">Si quiere eliminar esta licencia a través del Portal de administración, consulte: [Quitar a un usuario de su organización](/microsoft-365/admin/add-users/delete-a-user)</span><span class="sxs-lookup"><span data-stu-id="99960-191">If you would like to remove this license through the admin portal, see: [Delete a user from your organization](/microsoft-365/admin/add-users/delete-a-user)</span></span>

## <a name="what-is-the-data-retention-policy"></a><span data-ttu-id="99960-192">Qué es la directiva de retención de datos</span><span class="sxs-lookup"><span data-stu-id="99960-192">What is the data retention policy</span></span>

<span data-ttu-id="99960-193">Consulte [Información de la suscripción a Microsoft 365](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="99960-193">See [Microsoft 365 subscription information](/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span></span>

## <a name="how-long-does-the-teams-exploratory-experience-last"></a><span data-ttu-id="99960-194">¿Cuánto tiempo dura la experiencia de Teams Exploratory?</span><span class="sxs-lookup"><span data-stu-id="99960-194">How long does the Teams Exploratory experience last</span></span>

<span data-ttu-id="99960-195">Desde principios de 2021, Teams Exploratory está disponible como una suscripción de 12 meses (desde el registro inicial del usuario) para todos los clientes nuevos.</span><span class="sxs-lookup"><span data-stu-id="99960-195">As of early 2021, Teams Exploratory is available as a 12 month subscription (from initial user sign-up) for all new customers.</span></span> <span data-ttu-id="99960-196">La nueva suscripción de Teams Exploratory comienza cuando el primer usuario de una organización se registra en Teams Exploratory y expirará después de 12 meses.</span><span class="sxs-lookup"><span data-stu-id="99960-196">The new Teams Exploratory subscription starts when the first user in an organization signs-up for Teams Exploratory and it will expire after 12 months.</span></span> <span data-ttu-id="99960-197">La fecha de expiración se aplicará a todos los usuarios del mismo espacio empresarial que el período de 12 meses que comienza en la fecha de registro del primer usuario.</span><span class="sxs-lookup"><span data-stu-id="99960-197">The expiry date will apply to all users in the same tenant as the 12-month term begins on the first user's sign-up date.</span></span>

> [!NOTE]
> <span data-ttu-id="99960-198">La fecha de finalización de la experiencia se configura en un nivel de organización, lo que significa que se aplicará a todos los usuarios de la misma organización.</span><span class="sxs-lookup"><span data-stu-id="99960-198">The end date for the experience is configured at an organization level, meaning it will apply to all users in the same organization.</span></span> <span data-ttu-id="99960-199">Por ejemplo, el usuario 1 se registra en la suscripción el 1 de enero de 2021.</span><span class="sxs-lookup"><span data-stu-id="99960-199">For example, User 1 signs up for the subscription on January 1, 2021.</span></span> <span data-ttu-id="99960-200">Esto inicia una fecha de finalización de la suscripción del 31 de diciembre de 2021.</span><span class="sxs-lookup"><span data-stu-id="99960-200">This initiates a subscription end-date of December 31, 2021.</span></span> <span data-ttu-id="99960-201">Otro usuario, el usuario 2, se registra en la suscripción el 1 de octubre de 2021.</span><span class="sxs-lookup"><span data-stu-id="99960-201">Another user, User 2, signs up for the subscription on October 1, 2021.</span></span> <span data-ttu-id="99960-202">El usuario 2 puede usar Teams Exploratory durante dos meses, ya que su fecha de finalización será el 31 de diciembre de 2021, porque está en la misma suscripción de organización que el usuario 1.</span><span class="sxs-lookup"><span data-stu-id="99960-202">User 2 can use Teams Exploratory for two months, as their end-date will be December 31, 2021 because they're under the same organization's subscription as User 1.</span></span>

### <a name="what-should-administrators-do-at-the-end-of-the-12-month-teams-exploratory-experience"></a><span data-ttu-id="99960-203">Qué deberían hacer los administradores al final de la experiencia explorativa de 12 meses de Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="99960-203">What should administrators do at the end of the 12 month Teams Exploratory experience</span></span>

<span data-ttu-id="99960-204">Al final de la suscripción de 12 meses, los administradores deberían cambiar a todos los usuarios de Teams Exploratory a una licencia de pago que incluya Teams.</span><span class="sxs-lookup"><span data-stu-id="99960-204">At the end of the 12 month subscription, administrators should convert all Teams Exploratory users to a paid license that includes Teams.</span></span> <span data-ttu-id="99960-205">Es fundamental asegurarse de que se completa antes de que expire la suscripción de Teams Exploratory para evitar interrupciones en la experiencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="99960-205">It is vital to ensure this is completed before the Teams Exploratory subscription expires to avoid any disruption to user's experience.</span></span>


> [!NOTE]
> <span data-ttu-id="99960-206">Se deshabilitará a los clientes y se les impedirá que inicien nuevas licencias de prueba de Exploratory durante 3 meses pasado la fecha de expiración de la licencia de prueba de Exploratory anterior.</span><span class="sxs-lookup"><span data-stu-id="99960-206">Customers will be disabled and blocked from starting a new Exploratory trial licenses for 3 months past the expiration of their previous Exploratory trial license.</span></span>

<span data-ttu-id="99960-207">Para más información, consulte [Actualizar usuarios desde la licencia de Teams Exploratory](#upgrade-users-from-teams-exploratory), más arriba en este artículo.</span><span class="sxs-lookup"><span data-stu-id="99960-207">For more information, see [Upgrade users from Teams Exploratory](#upgrade-users-from-teams-exploratory), above in this article.</span></span>
