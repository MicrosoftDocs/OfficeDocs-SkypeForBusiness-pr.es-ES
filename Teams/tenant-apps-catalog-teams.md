---
title: Publicar aplicaciones en el catálogo de aplicaciones de inquilino de Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: prem
audience: admin
description: Instrucciones para la publicación de aplicaciones en el catálogo de aplicaciones de inquilino de Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.publishtenantapps
- ms.teamsadmincenter.apppolicies.publishtenantapps
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1f3d4f5937c766c1c4f6f54a6a38872e793a3825
ms.sourcegitcommit: 10046048a670b66d93e8ac3ba7c3ebc9c3c5fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "42161619"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-app-catalog"></a><span data-ttu-id="af88d-103">Publicar aplicaciones en el catálogo de aplicaciones de inquilino de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="af88d-103">Publish apps in the Microsoft Teams tenant app catalog</span></span>
=======================================================

<span data-ttu-id="af88d-104">Puede usar el catálogo de aplicaciones de inquilino de Microsoft Teams para probar y distribuir aplicaciones de línea de negocio a su organización.</span><span class="sxs-lookup"><span data-stu-id="af88d-104">You can use the Microsoft Teams tenant app catalog to test and distribute line-of-business applications to your organization.</span></span>

<span data-ttu-id="af88d-105">El catálogo de aplicaciones de inquilino de Teams le permite distribuir aplicaciones de línea de negocio que se han creado específicamente para su organización y en las que confía para completar las funciones críticas de la empresa.</span><span class="sxs-lookup"><span data-stu-id="af88d-105">The Teams tenant app catalog lets you distribute line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions.</span></span>

<span data-ttu-id="af88d-106">Para publicar aplicaciones para su organización, inicie sesión en el cliente de Teams mediante una cuenta con el rol de administrador global o de administrador de servicios de equipo y, a continuación, siga los pasos que se indican a continuación.</span><span class="sxs-lookup"><span data-stu-id="af88d-106">To publish apps for your organization, sign in to the Teams client using an account with either the global admin or teams service admin role and then follow the steps below.</span></span>

## <a name="publish-an-app-in-the-tenant-app-catalog-from-the-teams-client"></a><span data-ttu-id="af88d-107">Publicar una aplicación en el catálogo de aplicaciones de inquilino del cliente de Teams</span><span class="sxs-lookup"><span data-stu-id="af88d-107">Publish an app in the tenant app catalog from the Teams client</span></span>

> [!NOTE]
> <span data-ttu-id="af88d-108">Estos pasos describen cómo publicar una aplicación con el cliente de Teams.</span><span class="sxs-lookup"><span data-stu-id="af88d-108">These steps describe how to publish an app by using the Teams client.</span></span> <span data-ttu-id="af88d-109">También puede publicar una aplicación en la página **Manage apps** en el centro de administración de Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="af88d-109">You can also publish an app on the **Manage apps** page in the Microsoft Teams admin center.</span></span> <span data-ttu-id="af88d-110">Para obtener más información, consulte [Administrar aplicaciones en Teams](manage-apps.md).</span><span class="sxs-lookup"><span data-stu-id="af88d-110">To learn more, see [Manage apps in Teams](manage-apps.md).</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="af88d-111">Obtener un paquete de la aplicación Teams</span><span class="sxs-lookup"><span data-stu-id="af88d-111">Get a Teams app package</span></span>

<span data-ttu-id="af88d-112">Un paquete de la aplicación de Teams se crea con [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span><span class="sxs-lookup"><span data-stu-id="af88d-112">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="af88d-113">Una vez que tenga el paquete de la aplicación, puede agregarlo al catálogo de aplicaciones del inquilino.</span><span class="sxs-lookup"><span data-stu-id="af88d-113">Once you have the app package, you can add it to the tenant app catalog.</span></span> <span data-ttu-id="af88d-114">Mientras todos los usuarios de su organización pueden ver el catálogo de aplicaciones, solo los administradores globales y los administradores de servicios de equipos tienen la capacidad de publicarlos y administrarlos.</span><span class="sxs-lookup"><span data-stu-id="af88d-114">While all users in your organization can view the app catalog, only global admins and teams service admins have the ability to publish and manage it.</span></span>

### <a name="go-to-the-tenant-app-catalog"></a><span data-ttu-id="af88d-115">Ir al catálogo de aplicaciones de inquilino</span><span class="sxs-lookup"><span data-stu-id="af88d-115">Go to the tenant app catalog</span></span>

<span data-ttu-id="af88d-116">Inicie Teams e inicie sesión con sus credenciales de administrador de servicio global o Teams.</span><span class="sxs-lookup"><span data-stu-id="af88d-116">Start Teams and sign in using your global or teams service admin credentials.</span></span> <span data-ttu-id="af88d-117">Seleccione **aplicaciones** en la parte izquierda de la aplicación y, a continuación, seleccione la nueva sección nombrada para su organización específica (en este ejemplo, contoso).</span><span class="sxs-lookup"><span data-stu-id="af88d-117">Select **Apps** on the left side of the app, and then select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="af88d-118">Los usuarios de su organización pueden ver las aplicaciones en el catálogo e instalarlas para los equipos de los que son miembros.</span><span class="sxs-lookup"><span data-stu-id="af88d-118">Users in your organization can view apps in the catalog and install them for teams of which they are a member.</span></span>

![Captura de pantalla de la tienda de aplicaciones de teams que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-app-catalog"></a><span data-ttu-id="af88d-120">Agregar una aplicación al catálogo de aplicaciones de inquilino</span><span class="sxs-lookup"><span data-stu-id="af88d-120">Add an app to the tenant app catalog</span></span>

1. <span data-ttu-id="af88d-121">En la página **aplicaciones** , seleccione **cargar una aplicación** > **de carga personalizada para contoso**.</span><span class="sxs-lookup"><span data-stu-id="af88d-121">On the **Apps** page, select **Upload a custom app** > **Upload for Contoso**.</span></span>

    ![Captura de pantalla de la tienda de aplicaciones de teams que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image02.png)

    <span data-ttu-id="af88d-123">(También puede elegir **cargar por mí o mis equipos**, que se denomina *transferencia local*.</span><span class="sxs-lookup"><span data-stu-id="af88d-123">(You can also choose **Upload for me or my teams**, which is called *sideloading*.</span></span> <span data-ttu-id="af88d-124">La transferencia local hace que la aplicación esté disponible solo para los equipos o los equipos que seleccione.)</span><span class="sxs-lookup"><span data-stu-id="af88d-124">Sideloading makes the app available only to your teams or to teams you select.)</span></span>

2. <span data-ttu-id="af88d-125">Navegue hasta el paquete de la aplicación, selecciónelo y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="af88d-125">Navigate to the app package and select it, and then click **Open**.</span></span>

    ![Captura de pantalla de la tienda de aplicaciones de teams que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image03.png)

<span data-ttu-id="af88d-127">Cuando vuelva al catálogo de aplicaciones de inquilino, la nueva aplicación de empresa estará allí.</span><span class="sxs-lookup"><span data-stu-id="af88d-127">When you go back to your tenant app catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="af88d-128">Recuerde que solo usted y los miembros de su organización tienen acceso a este catálogo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="af88d-128">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-app-catalog"></a><span data-ttu-id="af88d-129">Actualizar una aplicación en el catálogo de aplicaciones de inquilino</span><span class="sxs-lookup"><span data-stu-id="af88d-129">Update an app in the tenant app catalog</span></span>

1. <span data-ttu-id="af88d-130">Desde el catálogo de aplicaciones de inquilino, seleccione "**...**"</span><span class="sxs-lookup"><span data-stu-id="af88d-130">From your tenant app catalog, select “**…**”</span></span> <span data-ttu-id="af88d-131">en la parte superior derecha de la aplicación que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="af88d-131">on the top right of the app you want to update.</span></span>

2. <span data-ttu-id="af88d-132">Navegue hasta el paquete de la aplicación actualizado, selecciónelo y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="af88d-132">Navigate to the updated app package and select it, and then click **Open**.</span></span>

    ![Captura de pantalla de la tienda de aplicaciones de teams que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image04.png)

<span data-ttu-id="af88d-134">La aplicación se revisará como versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="af88d-134">The app will be revised to version 2.0.</span></span> <span data-ttu-id="af88d-135">También puede eliminar la aplicación de toda la empresa desde este menú.</span><span class="sxs-lookup"><span data-stu-id="af88d-135">You can also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-microsoft-teams-admin-center-to-manage-the-tenant-app-catalog"></a><span data-ttu-id="af88d-136">Usar el centro de administración de Microsoft Teams para administrar el catálogo de aplicaciones de inquilino</span><span class="sxs-lookup"><span data-stu-id="af88d-136">Use the Microsoft Teams admin center to manage the tenant app catalog</span></span>

<span data-ttu-id="af88d-137">Si tiene aplicaciones que necesitan correcciones de errores, puede deshabilitar temporalmente las aplicaciones para los usuarios en una directiva de permisos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="af88d-137">If you have apps that need bug fixes, you can temporarily disable apps for users in an app permission policy.</span></span>

1. <span data-ttu-id="af88d-138">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a > **directivas de permisos**de las **aplicaciones de Teams**.</span><span class="sxs-lookup"><span data-stu-id="af88d-138">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="af88d-139">Seleccione la Directiva de permisos de la aplicación que desea editar y, a continuación, haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="af88d-139">Select the app permission policy that you want to edit, and then click **Edit**.</span></span>
3. <span data-ttu-id="af88d-140">En **aplicaciones de inquilino**, seleccione **bloquear aplicaciones específicas y permitir a todos los demás**y, a continuación, agregue las aplicaciones que quiera bloquear.</span><span class="sxs-lookup"><span data-stu-id="af88d-140">Under **Tenant apps**, select **Block specific apps and allow all others**, and then add the apps that you want to block.</span></span>

<span data-ttu-id="af88d-141">Deshabilitar una aplicación impide que los usuarios interactúen con la aplicación, sin eliminarla por completo.</span><span class="sxs-lookup"><span data-stu-id="af88d-141">Disabling an app blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="af88d-142">Estos controles ofrecen flexibilidad y control adicionales al administrar aplicaciones de su organización.</span><span class="sxs-lookup"><span data-stu-id="af88d-142">These controls give you additional flexibility and control when managing apps in your organization.</span></span>

<span data-ttu-id="af88d-143">Para obtener más información, vea [Administrar directivas de permisos de aplicaciones en Teams](teams-app-permission-policies.md).</span><span class="sxs-lookup"><span data-stu-id="af88d-143">To learn more, see [Manage app permission policies in Teams](teams-app-permission-policies.md).</span></span>