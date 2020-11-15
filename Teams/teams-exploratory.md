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
- m365initiative-deployteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: f27dc7e8772e25b6dcc91622cabec421e058af7b
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031486"
---
<a name="manage-the-microsoft-teams-exploratory-license"></a><span data-ttu-id="2e839-103">Administrar la licencia de Microsoft Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="2e839-103">Manage the Microsoft Teams Exploratory license</span></span>
=======================================================

<span data-ttu-id="2e839-p101">La experiencia de Microsoft Teams Exploratory permite a los usuarios de la organización que tienen Azure Active Directory (Azure AD) y carecen de una licencia para Teams iniciar una experiencia exploratoria de Teams. Los administradores pueden activar o desactivar esta característica para los usuarios de su organización. La versión anterior de la [Prueba en la nube comercial de Microsoft](iw-trial-teams.md) se ha reemplazado por la experiencia de Microsoft Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="2e839-p101">The Microsoft Teams Exploratory experience lets users in your organization who have Azure Active Directory (Azure AD) and aren't licensed for Teams initiate an exploratory experience of Teams. Admins can switch this feature on or off for users in their organization. The earlier [Microsoft Commercial Cloud Trial](iw-trial-teams.md) is now replaced by The Teams Exploratory experience.</span></span>

## <a name="whats-in-the-teams-exploratory-experience"></a><span data-ttu-id="2e839-107">¿Qué incluye la experiencia de Teams Exploratory?</span><span class="sxs-lookup"><span data-stu-id="2e839-107">What's in the Teams Exploratory experience</span></span>

<span data-ttu-id="2e839-108">Los planes de servicio que verá un administrador como parte de la experiencia de Teams Exploratory son:</span><span class="sxs-lookup"><span data-stu-id="2e839-108">The service plans that an admin will see as part of the Teams Exploratory experience are:</span></span>

- <span data-ttu-id="2e839-109">Exchange Online (plan 1)</span><span class="sxs-lookup"><span data-stu-id="2e839-109">Exchange Online (Plan 1)</span></span>
- <span data-ttu-id="2e839-110">Flow para Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="2e839-110">Flow for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="2e839-111">Información de MyAnalytics</span><span class="sxs-lookup"><span data-stu-id="2e839-111">Insights by MyAnalytics</span></span>
- <span data-ttu-id="2e839-112">Microsoft Forms (plan E1)</span><span class="sxs-lookup"><span data-stu-id="2e839-112">Microsoft Forms (Plan E1)</span></span>
- <span data-ttu-id="2e839-113">Microsoft Planner</span><span class="sxs-lookup"><span data-stu-id="2e839-113">Microsoft Planner</span></span>
- <span data-ttu-id="2e839-114">Búsqueda de Microsoft</span><span class="sxs-lookup"><span data-stu-id="2e839-114">Microsoft Search</span></span>
- <span data-ttu-id="2e839-115">Microsoft StaffHub</span><span class="sxs-lookup"><span data-stu-id="2e839-115">Microsoft StaffHub</span></span>
- <span data-ttu-id="2e839-116">SKU de Microsoft Stream para Microsoft 365 y Office 365 E1 <sup>1</1></span><span class="sxs-lookup"><span data-stu-id="2e839-116">Microsoft Stream for Microsoft 365 and Office 365 E1 SKUs <sup>1</1></span></span>
- <span data-ttu-id="2e839-117">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2e839-117">Microsoft Teams</span></span>
- <span data-ttu-id="2e839-118">Administración de dispositivos móviles para Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="2e839-118">Mobile Device Management for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="2e839-119">Aplicaciones móviles de Office para Office 365</span><span class="sxs-lookup"><span data-stu-id="2e839-119">Office Mobile Apps for Office 365</span></span>
- <span data-ttu-id="2e839-120">Office Online</span><span class="sxs-lookup"><span data-stu-id="2e839-120">Office Online</span></span>
- <span data-ttu-id="2e839-121">PowerApps para Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="2e839-121">PowerApps for Microsoft 365 or Office 365</span></span>
- <span data-ttu-id="2e839-122">SharePoint Online (plan 1)</span><span class="sxs-lookup"><span data-stu-id="2e839-122">SharePoint Online (Plan 1)</span></span>
- <span data-ttu-id="2e839-123">Sway</span><span class="sxs-lookup"><span data-stu-id="2e839-123">Sway</span></span>
- <span data-ttu-id="2e839-124">To-Do (plan 1)</span><span class="sxs-lookup"><span data-stu-id="2e839-124">To-Do (Plan 1)</span></span>
- <span data-ttu-id="2e839-125">Whiteboard (plan 1)</span><span class="sxs-lookup"><span data-stu-id="2e839-125">Whiteboard (Plan 1)</span></span>
- <span data-ttu-id="2e839-126">Yammer Enterprise</span><span class="sxs-lookup"><span data-stu-id="2e839-126">Yammer Enterprise</span></span>

  <span data-ttu-id="2e839-p102"><sup>1</sup> El cambio de usar Microsoft Stream a usar [OneDrive para la Empresa y SharePoint para grabar reuniones](tmr-meeting-recording-change.md) se hará en varias fases. Durante el lanzamiento podrá participar en esta experiencia, pero en noviembre debe optar por no participar si quiere seguir usando Stream y, en algún momento, a principios de 2021, se les pedirá a todos los clientes que usen OneDrive para la Empresa y SharePoint para grabar sus reuniones nuevas.</span><span class="sxs-lookup"><span data-stu-id="2e839-p102"><sup>1</sup> The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt in to this experience. In November, you'll have to opt out if you want to continue using Stream. Sometime in early 2021, we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

## <a name="whos-eligible"></a><span data-ttu-id="2e839-131">¿Quiénes reúnen los requisitos?</span><span class="sxs-lookup"><span data-stu-id="2e839-131">Who's eligible</span></span>

<span data-ttu-id="2e839-132">Los usuarios se ajustan a los requerimientos para una experiencia de Teams Exploratory si:</span><span class="sxs-lookup"><span data-stu-id="2e839-132">Users fit the criteria for a Teams Exploratory experience if they:</span></span>

- <span data-ttu-id="2e839-133">Tienen una dirección de correo electrónico de dominio de Azure AD administrada.</span><span class="sxs-lookup"><span data-stu-id="2e839-133">Have a managed Azure AD domain email address.</span></span>
- <span data-ttu-id="2e839-134">Pertenecen a un espacio empresarial con una suscripción pagada.</span><span class="sxs-lookup"><span data-stu-id="2e839-134">Belong to a tenant with a paid subscription.</span></span>

<span data-ttu-id="2e839-p103">Se debe habilitar a los usuarios para registrarse en aplicaciones y pruebas (en el Centro de administración de Microsoft 365). Para obtener más información, consulte [Administrar la experiencia de Teams Exploratory](#manage-the-teams-exploratory-experience), más adelante en este artículo.</span><span class="sxs-lookup"><span data-stu-id="2e839-p103">Users must be enabled to sign up for apps and trials (in the Microsoft 365 admin center). For more information, see [Manage the Teams Exploratory experience](#manage-the-teams-exploratory-experience), later in this article.</span></span>

## <a name="who-isnt-eligible"></a><span data-ttu-id="2e839-137">¿Quiénes no reúnen los requisitos?</span><span class="sxs-lookup"><span data-stu-id="2e839-137">Who isn't eligible</span></span>

<span data-ttu-id="2e839-138">Los usuarios no reúnen los requerimientos si:</span><span class="sxs-lookup"><span data-stu-id="2e839-138">Users don't fit the criteria if they:</span></span>

- <span data-ttu-id="2e839-139">Actual o previamente tuvieron Teams de una licencia de prueba, pagada o no pagada.</span><span class="sxs-lookup"><span data-stu-id="2e839-139">Currently or previously had Teams from a paid, unpaid or trial license</span></span> 
- <span data-ttu-id="2e839-140">Se encuentran en un espacio empresarial que ha recibido, al menos, una oferta especial COVID.</span><span class="sxs-lookup"><span data-stu-id="2e839-140">Are in a tenant that used/received at least one special COVID offer.</span></span>

<span data-ttu-id="2e839-141">Su organización no es apta para esta oferta si usted es cliente de Syndication Partner o cliente de GCC, GCC High, DoD o EDU.</span><span class="sxs-lookup"><span data-stu-id="2e839-141">Your organization isn't eligible for this offer if you're a Syndication Partner Customer or a GCC, GCC High, DoD, or EDU customer.</span></span>

## <a name="how-users-sign-up-for-the-teams-exploratory-experience"></a><span data-ttu-id="2e839-142">¿Cómo los usuarios se pueden inscribir en la experiencia de Teams Exploratory?</span><span class="sxs-lookup"><span data-stu-id="2e839-142">How users sign up for the Teams Exploratory experience</span></span>

<span data-ttu-id="2e839-p104">Los usuarios aptos pueden registrarse para la experiencia Teams Exploratory registrándose en Teams ([teams.microsoft.com](https://teams.microsoft.com)). Se les asignará esta licencia automáticamente y el administrador del espacio empresarial recibirá una notificación por correo electrónico la primera vez que un usuario de su organización active la experiencia de Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="2e839-p104">Eligible users can sign up for the Teams Exploratory experience by signing in to Teams ([teams.microsoft.com](https://teams.microsoft.com)). They'll be assigned this license automatically and the tenant admin will receive an email notification the first time someone in your org starts the Teams Exploratory experience.</span></span>

## <a name="manage-the-teams-exploratory-experience"></a><span data-ttu-id="2e839-145">Administrar la experiencia de Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="2e839-145">Manage the Teams Exploratory experience</span></span>

<span data-ttu-id="2e839-146">La experiencia de Teams Exploratory está pensada para ser activada por usuarios finales individuales, y usted no puede activar esta oferta en nombre de los empleados que sean usuarios finales.</span><span class="sxs-lookup"><span data-stu-id="2e839-146">The Teams Exploratory experience is meant to be initiated by individual end users, and you can't initiate this offer on behalf of end-user employees.</span></span>

<span data-ttu-id="2e839-p105">La experiencia Teams Exploratory viene con una licencia de Exchange Online, pero no se asignará al usuario hasta que el administrador la asigne. Si el usuario no tiene una licencia de Exchange y el administrador aún no ha asignado la licencia de Exchange Online, el usuario no podrá programar reuniones en Teams y es posible que no disponga de otras características.</span><span class="sxs-lookup"><span data-stu-id="2e839-p105">The Teams Exploratory experience comes with an Exchange Online license, but it won't be assigned to the user until the admin assigns it. If the user doesn't have an Exchange license already, and the admin has yet to assign the Exchange Online license, the user won't be able to schedule meetings in Teams and might be missing other Teams functionality.</span></span>

<span data-ttu-id="2e839-149">Los administradores pueden desactivar la opción de que los usuarios finales ejecuten la experiencia de Teams Exploratory dentro de su organización mediante el uso del conmutador de **aplicaciones y servicios de prueba**.</span><span class="sxs-lookup"><span data-stu-id="2e839-149">Admins can disable the ability for end users to run the Teams Exploratory experience within their organization by using the **Trial apps and services** switch.</span></span>

### <a name="prevent-users-from-installing-trial-apps-and-services"></a><span data-ttu-id="2e839-150">Evitar que los usuarios instalen aplicaciones y servicios de prueba</span><span class="sxs-lookup"><span data-stu-id="2e839-150">Prevent users from installing trial apps and services</span></span>

<span data-ttu-id="2e839-151">Puede desactivar la capacidad de un usuario para instalar aplicaciones y servicios de prueba, lo que impediría al usuario ejecutar la experiencia de Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="2e839-151">You can turn off a user's ability to install trial apps and services, which would prevent the user from running the Teams Exploratory experience.</span></span>

1. <span data-ttu-id="2e839-152">Desde el Centro de administración de Microsoft 365, vaya a **Configuración** > **Configuración de la organización** , seleccione **Servicios** , y luego seleccione **Aplicaciones y servicios que son propiedad del usuario**.</span><span class="sxs-lookup"><span data-stu-id="2e839-152">From the Microsoft 365 admin center, go to **Settings** > **Org settings** , select **Services** , and then select **User owned apps and services**.</span></span>

    ![Captura de pantalla de la página Servicios en el centro de administración.](media/iw-trial-services.png)

2. <span data-ttu-id="2e839-154">Desactive la casilla **Permitir que los usuarios instalen aplicaciones y servicios de prueba**.</span><span class="sxs-lookup"><span data-stu-id="2e839-154">Clear the **Let users install trial apps and services** check box.</span></span>

    ![Captura de pantalla de la página Aplicaciones y servicios en propiedad del usuario en el centro de administración.](media/iw-trial-user-owned-apps-services.png)

    > [!NOTE]
    > <span data-ttu-id="2e839-156">Si su organización no es apta para la experiencia de Teams Exploratory, no verá la opción **Dejar que los usuarios instalen aplicaciones y servicios de prueba**. </span><span class="sxs-lookup"><span data-stu-id="2e839-156">If your organization is ineligible for the Teams Exploratory experience, you won't see the **Let users install trial apps and services** option.</span></span>

### <a name="manage-availability-for-a-user-with-a-license-that-includes-teams"></a><span data-ttu-id="2e839-157">Administrar la disponibilidad de un usuario con una licencia que incluye Teams</span><span class="sxs-lookup"><span data-stu-id="2e839-157">Manage availability for a user with a license that includes Teams</span></span>

<span data-ttu-id="2e839-p106">Un usuario al que se ha asignado una licencia que incluye Teams no es apto para la experiencia Teams Exploratory. Cuando el plan de servicio de Teams esté activado, el usuario puede iniciar sesión y usar Teams. Si el plan de servicio está deshabilitado, el usuario no podrá iniciar sesión y la experiencia Teams Exploratory no estará disponible. Debe tener privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="2e839-p106">A user who is assigned a license that includes Teams isn't eligible for the Teams Exploratory experience. When the Teams service plan is turned on, the user can sign in and use Teams. If the service plan is disabled, the user can't sign in and the Teams Exploratory experience isn't available. You must have admin privileges.</span></span>

<span data-ttu-id="2e839-162">Para desactivar el acceso a Teams:</span><span class="sxs-lookup"><span data-stu-id="2e839-162">To turn off access to Teams:</span></span>

1. <span data-ttu-id="2e839-163">En el Centro de administración de Microsoft 365, seleccione **Usuarios** > **Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="2e839-163">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="2e839-164">Seleccione la casilla junto al nombre del usuario.</span><span class="sxs-lookup"><span data-stu-id="2e839-164">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="2e839-165">En la parte derecha, en la fila **Licencias de producto** , elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2e839-165">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="2e839-166">En el panel **Licencias de producto** , cambie el botón de alternancia a **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="2e839-166">In the **Product licenses** pane, switch the toggle to **Off**.</span></span>

    ![La página de licencias del producto en el centro de administración.](media/iw-trial-enable-3.png)

### <a name="manage-teams-availability-for-users-who-are-already-using-the-teams-exploratory-experience"></a><span data-ttu-id="2e839-168">Administrar la disponibilidad de Teams para los usuarios que ya estén utilizando la experiencia Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="2e839-168">Manage Teams availability for users who are already using the Teams Exploratory experience</span></span>

<span data-ttu-id="2e839-p107">Si un usuario está usando la experiencia Teams Exploratory, puede desactivarla eliminando la licencia o el plan de servicio. Debe tener privilegios de administrador.</span><span class="sxs-lookup"><span data-stu-id="2e839-p107">If a user is running the Teams Exploratory experience, you can turn it off by removing the license or service plan. You must have admin privileges.</span></span>

<span data-ttu-id="2e839-171">Desactivar la licencia de la experiencia Teams Exploratory:</span><span class="sxs-lookup"><span data-stu-id="2e839-171">To turn off the Teams Exploratory experience license:</span></span>

1. <span data-ttu-id="2e839-172">En el Centro de administración de Microsoft 365, seleccione **Usuarios** > **Usuarios activos**.</span><span class="sxs-lookup"><span data-stu-id="2e839-172">In the Microsoft 365 admin center, select **Users** > **Active users**.</span></span>

2. <span data-ttu-id="2e839-173">Seleccione la casilla junto al nombre del usuario.</span><span class="sxs-lookup"><span data-stu-id="2e839-173">Select the box next to the name of the user.</span></span>

3. <span data-ttu-id="2e839-174">En la parte derecha, en la fila **Licencias de producto** , elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2e839-174">In the **Product licenses** row, choose **Edit**.</span></span>

4. <span data-ttu-id="2e839-175">En el panel de **licencias de producto** , cambie el botón de alternancia para la licencia exploratoria a **Desactivado**.</span><span class="sxs-lookup"><span data-stu-id="2e839-175">In the **Product licenses** pane, switch the toggle for this exploratory license to **Off**.</span></span>

    >[!Note]
    ><span data-ttu-id="2e839-176">El botón de alternancia de Teams Exploratory aparecerá después de que el primer usuario de la organización inicie la experiencia de Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="2e839-176">The Teams Exploratory toggle switch will appear after the first user in the organization launches the Teams Exploratory experience.</span></span>

### <a name="manage-teams-for-users-who-have-the-teams-exploratory-license"></a><span data-ttu-id="2e839-177">Administrar Teams para los usuarios que dispongan de la licencia de Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="2e839-177">Manage Teams for users who have the Teams Exploratory license</span></span>

<span data-ttu-id="2e839-p108">Puede administrar a los usuarios que dispongan de la licencia de Teams Exploratory al igual que a los usuarios que dispongan de una licencia pagada estándar. Para más información, consulte [Administrar la configuración de Teams para su organización](enable-features-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="2e839-p108">You can manage users who have the Teams Exploratory license just like you manage users who have a regular paid license. For more information, see [Manage Teams settings for your organization](enable-features-office-365.md).</span></span>

### <a name="upgrade-users-from-the-teams-exploratory-license"></a><span data-ttu-id="2e839-180">Actualizar los usuarios de la licencia de Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="2e839-180">Upgrade users from the Teams Exploratory license</span></span>

<span data-ttu-id="2e839-181">Para actualizar a los usuarios de la licencia de Teams Exploratory (debe tener privilegios de administrador), haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2e839-181">To upgrade users from the Teams Exploratory license (you must have admin privileges), do the following tasks:</span></span>

1. <span data-ttu-id="2e839-182">Adquiera una suscripción que incluya Teams.</span><span class="sxs-lookup"><span data-stu-id="2e839-182">Purchase a subscription that includes Teams.</span></span>

2. <span data-ttu-id="2e839-183">Elimine la suscripción del usuario a Teams Exploratory.</span><span class="sxs-lookup"><span data-stu-id="2e839-183">Remove the Teams Exploratory subscription from the user.</span></span>

3. <span data-ttu-id="2e839-184">Asignar la licencia que acaba de adquirir.</span><span class="sxs-lookup"><span data-stu-id="2e839-184">Assign the newly purchased license.</span></span>

<span data-ttu-id="2e839-185">Para más información, consulte [Descripción del servicio de Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span><span class="sxs-lookup"><span data-stu-id="2e839-185">For more information, see [Microsoft Teams service description](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description).</span></span>

> [!NOTE]
> <span data-ttu-id="2e839-p109">Si la licencia de Teams Exploratory finaliza y un usuario no se actualiza inmediatamente a una suscripción que incluya Teams, tendrá 30 días de periodo de gracia y, a continuación, otros 30 días hasta que se eliminen los datos. El usuario aún existirá en Azure Active Directory. Cuando se asigne una nueva licencia al usuario para volver a habilitar la funcionalidad de Teams, todo el contenido seguirá existiendo si el usuario se agrega durante el período de tiempo del periodo de gracia.</span><span class="sxs-lookup"><span data-stu-id="2e839-p109">If the Teams Exploratory license ends and a user isn't immediately upgraded to a subscription that includes Teams, they have 30 days of grace period and then another 30 days after which time the data is going to be deleted. The user still exists in Azure Active Directory. Once a new license is assigned to the user to enable Teams functionality again, all content will still exist if the user is added within the grace period time frame.</span></span>

## <a name="what-happens-to-legacy-microsoft-teams-commercial-cloud-trial-licenses"></a><span data-ttu-id="2e839-189">¿Qué sucede con las licencias heredadas de la versión de prueba de Microsoft Teams Commercial Cloud?</span><span class="sxs-lookup"><span data-stu-id="2e839-189">What happens to legacy Microsoft Teams Commercial Cloud Trial licenses</span></span>

<span data-ttu-id="2e839-p110">A partir del 2020 de febrero, los usuarios elegibles pueden empezar a usar la última experiencia de Microsoft Teams Exploratory. Se convertirán automáticamente a la nueva oferta todas las licencias de prueba de la nube comercial de Teams antiguas antes de que expire la versión de prueba.</span><span class="sxs-lookup"><span data-stu-id="2e839-p110">As of February 2020, eligible users can begin using the latest Microsoft Teams Exploratory experience. All legacy Teams Commercial Cloud Trial licenses will be automatically converted to the new offer before their trial expires.</span></span>

<span data-ttu-id="2e839-p111">Cuando los usuarios inician sesión por primera vez en su versión vencida de la prueba comercial en la nube de Teams, asignaremos automáticamente una licencia de experiencia exploratoria de Teams a esos usuarios. No se convertirá a los usuarios hasta que inicien sesión.</span><span class="sxs-lookup"><span data-stu-id="2e839-p111">When users sign in to their expired Teams Commercial Cloud Trial for the first time, we automatically assign a Teams Exploratory experience license to those users. Users aren't converted until they sign in.</span></span>

### <a name="remove-a-teams-exploratory-license"></a><span data-ttu-id="2e839-194">Eliminar una licencia de Teams Exploratory</span><span class="sxs-lookup"><span data-stu-id="2e839-194">Remove a Teams Exploratory license</span></span>

- <span data-ttu-id="2e839-195">Si usted desea eliminar la licencia usando PowerShell, consulte: [Eliminar las licencias de las cuentas de usuario con Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="2e839-195">If you would like to remove this license by using PowerShell, see: [Remove licenses from user accounts with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/remove-licenses-from-user-accounts-with-office-365-powershell)</span></span>

- <span data-ttu-id="2e839-196">Si quiere eliminar esta licencia a través del Portal de administración, consulte: [Quitar a un usuario de su organización](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span><span class="sxs-lookup"><span data-stu-id="2e839-196">If you would like to remove this license through the admin portal, see: [Delete a user from your organization](https://docs.microsoft.com/microsoft-365/admin/add-users/delete-a-user)</span></span>

## <a name="what-is-the-data-retention-policy"></a><span data-ttu-id="2e839-197">Qué es la directiva de retención de datos</span><span class="sxs-lookup"><span data-stu-id="2e839-197">What is the data retention policy</span></span>

<span data-ttu-id="2e839-198">Consulte [Información de la suscripción a Microsoft 365](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="2e839-198">See [Microsoft 365 subscription information](https://docs.microsoft.com/microsoft-365/commerce/subscriptions/what-if-my-subscription-expires?view=o365-worldwide).</span></span>

## <a name="how-long-does-the-teams-exploratory-experience-last"></a><span data-ttu-id="2e839-199">¿Cuánto tiempo dura la experiencia de Teams Exploratory?</span><span class="sxs-lookup"><span data-stu-id="2e839-199">How long does the Teams Exploratory experience last</span></span>

<span data-ttu-id="2e839-p112">La experiencia Microsoft Teams Exploratory está disponible sin costo adicional hasta su próximo **contrato de aniversario** o **renovación** o una vez pasado enero de 2021. En ese momento, los usuarios finales de una licencia de experiencia de Microsoft Exploratory tendrán que cambiarse a una licencia de pago que incluya Teams. Cualquier licencia de la experiencia preliminar de Microsoft Exploratory iniciada después de entonces seguirá disponible sin coste adicional hasta el siguiente **aniversario** o ciclo de **renovación**.</span><span class="sxs-lookup"><span data-stu-id="2e839-p112">The Microsoft Teams Exploratory experience is available at no additional cost until your next **agreement anniversary** or **renewal** on or after January 2021. At that time, end users on a Microsoft Exploratory experience license will need to move to a paid license that includes Teams. Any Microsoft Exploratory experience licenses initiated after that will remain available at no additional cost until your next **anniversary** or **renewal** cycle.</span></span>

### <a name="what-happens-if-an-end-user-initiates-the-microsoft-teams-exploratory-experience-just-before-the-anniversary-or-renewal-date"></a><span data-ttu-id="2e839-203">¿Qué ocurre si un usuario final inicia la experiencia de Microsoft Teams Exploratory justo antes del aniversario o fecha de renovación?</span><span class="sxs-lookup"><span data-stu-id="2e839-203">What happens if an end user initiates the Microsoft Teams Exploratory experience just before the anniversary or renewal date</span></span>

<span data-ttu-id="2e839-204">Las licencias de la experiencia de Microsoft Teams Exploratory iniciadas en un plazo de 90 días antes de la fecha de **aniversario** o **renovación del contrato** de su empresa no deberán cambiarse a una licencia de pago hasta el siguiente aniversario o ciclo de renovación.</span><span class="sxs-lookup"><span data-stu-id="2e839-204">Microsoft Teams Exploratory experience licenses initiated within 90 days of your **agreement anniversary** or **renewal** won't be required to move to a paid license until the subsequent anniversary or renewal cycle.</span></span>

### <a name="what-if-my-agreement-doesnt-have-an-anniversary-or-yearly-renewal-date-for-example-month-to-month-agreements"></a><span data-ttu-id="2e839-205">¿Qué ocurre si mi acuerdo no tiene ninguna fecha de aniversario o renovación anual (por ejemplo, acuerdos mensuales)?</span><span class="sxs-lookup"><span data-stu-id="2e839-205">What if my agreement doesn’t have an anniversary or yearly renewal date (for example, month-to-month agreements)</span></span>

<span data-ttu-id="2e839-p113">En el caso de los contratos que no tengan un aniversario o una fecha de renovación anual, el año siguiente después de que el primer usuario final active las licencias de la experiencia de Microsoft Teams Exploratory se considerará como el aniversario o la fecha de renovación. Los usuarios de la licencia de Microsoft Teams Exploratory se deben convertir a una licencia de pago en esa fecha cada año, según las directivas indicadas en este artículo.</span><span class="sxs-lookup"><span data-stu-id="2e839-p113">For agreements without an anniversary or yearly renewal date, the subsequent year after the first end-user activates the Microsoft Teams Exploratory experience licenses will be treated as the anniversary or renewal date. Users on the Microsoft Teams Exploratory license must be converted to a paid license by that date each year, according to the policies outlined in this article.</span></span>

<span data-ttu-id="2e839-208">Por ejemplo, si el primer usuario final activa Microsoft Teams Exploratory el 19 de junio de 2020, este usuario y todos los demás elegibles en el espacio empresarial del cliente deben pasar a una licencia de pago con Teams el 19 de junio de 2021.</span><span class="sxs-lookup"><span data-stu-id="2e839-208">For example, if the first end user activates Microsoft Teams Exploratory on June 19, 2020, then they and all other eligible users in the customer tenant must convert to a paid license with Teams by June 19, 2021.</span></span>

> [!Note]
> <span data-ttu-id="2e839-209">Se deshabilitará a los clientes y se les impedirá que inicien nuevas licencias de prueba de Exploratory durante 3 meses pasado la fecha de expiración de la licencia de prueba de Exploratory anterior.</span><span class="sxs-lookup"><span data-stu-id="2e839-209">Customers will be disabled and blocked from starting a new Exploratory trial licenses for 3 months past the expiration of their previous Exploratory trial license.</span></span>
