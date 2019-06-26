---
title: Publicar aplicaciones en el catálogo de aplicaciones de inquilino de Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/20/2019
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: Guía para la publicación de aplicaciones en el catálogo de aplicaciones de inquilino de Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.apppolicies.publishtenantapps
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d016fd1c341774115b9b68edafcc47a63e42b0d
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221328"
---
<a name="publish-apps-in-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="f6193-103">Publicar aplicaciones en el catálogo de aplicaciones de inquilino de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f6193-103">Publish apps in the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

<span data-ttu-id="f6193-104">Puede usar el catálogo de aplicaciones de inquilino de Microsoft Teams para probar y distribuir aplicaciones de línea de negocio a su organización.</span><span class="sxs-lookup"><span data-stu-id="f6193-104">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span>

<span data-ttu-id="f6193-105">El catálogo de aplicaciones de inquilino de Teams le permite distribuir aplicaciones de línea de negocio que se han creado específicamente para su organización y en las que confía para completar las funciones críticas de la empresa.</span><span class="sxs-lookup"><span data-stu-id="f6193-105">The Teams Tenant Apps Catalog lets you distribute line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions.</span></span>

<span data-ttu-id="f6193-106">Para publicar aplicaciones para su organización, inicie sesión en el cliente de Teams con sus credenciales de administrador global y, a continuación, siga las instrucciones a continuación.</span><span class="sxs-lookup"><span data-stu-id="f6193-106">To publish apps for your organization, sign in to your Teams client using your global admin credentials and then follow the instructions below.</span></span>

## <a name="publish-an-app-in-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="f6193-107">Publicar una aplicación en el catálogo de aplicaciones de inquilino del cliente de Teams</span><span class="sxs-lookup"><span data-stu-id="f6193-107">Publish an app in the Tenant Apps Catalog from the Teams client</span></span>

> [!NOTE]
> <span data-ttu-id="f6193-108">Debe iniciar sesión en el cliente de Microsoft Teams con sus credenciales de administrador global para publicar aplicaciones para su organización.</span><span class="sxs-lookup"><span data-stu-id="f6193-108">You need to be signed in to the Microsoft Teams client using your global admin credentials to publish apps for your organization.</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="f6193-109">Obtener un paquete de la aplicación Teams</span><span class="sxs-lookup"><span data-stu-id="f6193-109">Get a Teams app package</span></span>

<span data-ttu-id="f6193-110">Un paquete de la aplicación de Teams se crea con [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span><span class="sxs-lookup"><span data-stu-id="f6193-110">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="f6193-111">Una vez que tenga el paquete de la aplicación, puede agregarlo al catálogo de aplicaciones empresarial.</span><span class="sxs-lookup"><span data-stu-id="f6193-111">Once you have the app package, you can add it to the enterprise app catalog.</span></span> <span data-ttu-id="f6193-112">Mientras que todos los usuarios del inquilino pueden ver el catálogo de aplicaciones, actualmente solo los administradores globales tienen la capacidad de publicarlo y administrarlo.</span><span class="sxs-lookup"><span data-stu-id="f6193-112">While all users in the tenant can view the app catalog, currently only global admins have the ability to publish and manage it.</span></span> <span data-ttu-id="f6193-113">(Al final, los administradores de equipos también podrán hacerlo).</span><span class="sxs-lookup"><span data-stu-id="f6193-113">(Eventually, Teams admins will be able to do this as well.)</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="f6193-114">Ir al catálogo de aplicaciones de inquilino</span><span class="sxs-lookup"><span data-stu-id="f6193-114">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="f6193-115">Inicie el cliente de Microsoft Teams e inicie sesión con sus credenciales de administrador global.</span><span class="sxs-lookup"><span data-stu-id="f6193-115">Start the Microsoft Teams client and sign-in using your global admin credentials.</span></span> <span data-ttu-id="f6193-116">En la tienda Microsoft Teams, seleccione la nueva sección nombrada para su organización específica (en este ejemplo, contoso).</span><span class="sxs-lookup"><span data-stu-id="f6193-116">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="f6193-117">Los usuarios de su organización pueden ver las aplicaciones en el catálogo e instalarlas para los equipos de los que son miembros.</span><span class="sxs-lookup"><span data-stu-id="f6193-117">Users in your organization can view apps in the catalog and install them for teams of which they are a member.</span></span>

![Captura de pantalla de la tienda de aplicaciones de teams que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="f6193-119">Agregar una aplicación al catálogo de aplicaciones de inquilino</span><span class="sxs-lookup"><span data-stu-id="f6193-119">Add an app to the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="f6193-120">En la tienda, seleccione **cargar una** > **carga de aplicaciones personalizada para contoso**.</span><span class="sxs-lookup"><span data-stu-id="f6193-120">From the store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

    ![Captura de pantalla de la tienda de aplicaciones de teams que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image02.png)

    <span data-ttu-id="f6193-122">(También puede elegir **cargar por mí o mis equipos**, que se denomina *transferencia local*.</span><span class="sxs-lookup"><span data-stu-id="f6193-122">(You can also choose **Upload for me or my teams**, which is called *sideloading*.</span></span> <span data-ttu-id="f6193-123">La transferencia local hace que la aplicación esté disponible solo para los equipos o los equipos que seleccione.)</span><span class="sxs-lookup"><span data-stu-id="f6193-123">Sideloading makes the app available only to your teams or to teams you select.)</span></span>

2. <span data-ttu-id="f6193-124">Navegue hasta el paquete de la aplicación, selecciónelo y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="f6193-124">Navigate to the app package and select it, and then click **Open**.</span></span>

    ![Captura de pantalla de la tienda de aplicaciones de teams que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image03.png)

<span data-ttu-id="f6193-126">Cuando vuelva al catálogo de aplicaciones de inquilino, la nueva aplicación de empresa estará allí.</span><span class="sxs-lookup"><span data-stu-id="f6193-126">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="f6193-127">Recuerde que solo usted y los miembros de su organización tienen acceso a este catálogo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="f6193-127">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="f6193-128">Actualizar una aplicación en el catálogo de aplicaciones de inquilino</span><span class="sxs-lookup"><span data-stu-id="f6193-128">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="f6193-129">Desde el catálogo de aplicaciones de inquilino, seleccione "**...**"</span><span class="sxs-lookup"><span data-stu-id="f6193-129">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="f6193-130">en la parte superior derecha de la aplicación que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="f6193-130">on the top right of the app you want to update.</span></span>

2. <span data-ttu-id="f6193-131">Navegue hasta el paquete de la aplicación actualizado, selecciónelo y, a continuación, haga clic en **abrir**.</span><span class="sxs-lookup"><span data-stu-id="f6193-131">Navigate to the updated app package and select it, and then click **Open**.</span></span>

    ![Captura de pantalla de la tienda de aplicaciones de teams que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image04.png)

<span data-ttu-id="f6193-133">La aplicación se revisará como versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="f6193-133">The app will be revised to version 2.0.</span></span> <span data-ttu-id="f6193-134">También puede eliminar la aplicación de toda la empresa desde este menú.</span><span class="sxs-lookup"><span data-stu-id="f6193-134">You can also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="f6193-135">Usar el portal de administración de Office 365 para administrar el catálogo de aplicaciones de inquilino</span><span class="sxs-lookup"><span data-stu-id="f6193-135">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="f6193-136">Si tiene aplicaciones que necesitan correcciones de errores, puede deshabilitar temporalmente las aplicaciones a través del portal de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="f6193-136">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal.</span></span> <span data-ttu-id="f6193-137">Seleccione **Settings** > **Services & complementos** > **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="f6193-137">Select **Settings** > **Services & add-ins** > **Microsoft Teams**.</span></span> <span data-ttu-id="f6193-138">Además de la configuración anterior, ahora hay una sección dedicada a las aplicaciones de su empresa.</span><span class="sxs-lookup"><span data-stu-id="f6193-138">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="f6193-139">Puede elegir qué aplicaciones quiere habilitar o deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="f6193-139">You can choose which apps you want to enable or disable.</span></span>

![Captura de pantalla de la tienda de aplicaciones de teams que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image05.png)

<span data-ttu-id="f6193-141">Deshabilitar una aplicación evitará que los usuarios interactúen con la aplicación, sin eliminarla por completo.</span><span class="sxs-lookup"><span data-stu-id="f6193-141">Disabling an app will block users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="f6193-142">Estos controles ofrecen flexibilidad y control adicionales al administrar aplicaciones de su empresa.</span><span class="sxs-lookup"><span data-stu-id="f6193-142">These controls give you additional flexibility and control when managing apps in your enterprise.</span></span>
