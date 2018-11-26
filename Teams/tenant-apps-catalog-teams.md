---
title: Publicar aplicaciones en el catálogo de aplicaciones del inquilino de equipos de Microsoft
author: ChuckEdmonson
ms.author: lolaj
manager: serdars
ms.date: 08/02/2018
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: Instrucciones para la publicación de aplicaciones en el catálogo de aplicaciones de inquilino de los equipos de Microsoft.
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2454ad195fbecb25b30218ac156e62d396b4a6dd
ms.sourcegitcommit: fbcd150e724456ea4521d68cf3acb351e3525e2e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2018
ms.locfileid: "26674823"
---
<a name="publish-apps-to-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="5f40b-103">Publicar aplicaciones en el catálogo de aplicaciones del inquilino de equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="5f40b-103">Publish apps to the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

<span data-ttu-id="5f40b-104">Puede usar el catálogo de aplicaciones de inquilino de los equipos de Microsoft para probar y distribuir aplicaciones de línea de negocio para su organización.</span><span class="sxs-lookup"><span data-stu-id="5f40b-104">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span> 

<span data-ttu-id="5f40b-105">El catálogo de aplicaciones de los equipos de inquilino permite distribuir las aplicaciones de línea de negocio que han sido creadas específicamente para su organización y que se basan en para completan las funciones empresariales fundamentales para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="5f40b-105">The Teams Tenant Apps Catalog lets you distribute your line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions to your users.</span></span> 
 
<span data-ttu-id="5f40b-106">Inicie sesión en el cliente de los equipos con sus credenciales de administrador global y publicar aplicaciones para su organización.</span><span class="sxs-lookup"><span data-stu-id="5f40b-106">Sign in to your Teams client using your global admin credentials and publish apps for your organization.</span></span> 

## <a name="publish-an-app-to-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="5f40b-107">Publicar una aplicación en el catálogo de aplicaciones de inquilino desde el cliente de los equipos</span><span class="sxs-lookup"><span data-stu-id="5f40b-107">Publish an app to the Tenant Apps Catalog from the Teams client</span></span>

<span data-ttu-id="5f40b-108">Nota: Debe haber iniciado sesión en el cliente de Microsoft Teams con sus credenciales de administrador global para publicar aplicaciones para la organización.</span><span class="sxs-lookup"><span data-stu-id="5f40b-108">NOTE: You need to be signed in to the Microsoft Teams client using your global admin credentials to publish apps for your organization.</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="5f40b-109">Obtener un paquete de la aplicación de los equipos</span><span class="sxs-lookup"><span data-stu-id="5f40b-109">Get a Teams app package</span></span>

<span data-ttu-id="5f40b-110">Se crea un paquete de aplicación de los equipos mediante el uso de [Los equipos de aplicación Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span><span class="sxs-lookup"><span data-stu-id="5f40b-110">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="5f40b-111">Una vez que el paquete de la aplicación, puede agregarlo al catálogo de aplicaciones de empresa.</span><span class="sxs-lookup"><span data-stu-id="5f40b-111">Once you have the app package, you can add it to enterprise app catalog.</span></span> <span data-ttu-id="5f40b-112">Mientras todos los usuarios en el inquilino puede ver el catálogo de aplicaciones, actualmente sólo global los administradores tienen la capacidad para publicar y administrarlo.</span><span class="sxs-lookup"><span data-stu-id="5f40b-112">While all users in the tenant can view the app catalog, currently only global admins have the ability to publish and manage it.</span></span> <span data-ttu-id="5f40b-113">(Al final, los administradores de los equipos podrán hacerlo así como.)</span><span class="sxs-lookup"><span data-stu-id="5f40b-113">(Eventually, Teams admins will be able to do this as well.)</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="5f40b-114">Vaya al catálogo de aplicaciones de inquilinos</span><span class="sxs-lookup"><span data-stu-id="5f40b-114">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="5f40b-115">Iniciar al cliente de Microsoft Teams e inicio de sesión con sus credenciales de administrador global.</span><span class="sxs-lookup"><span data-stu-id="5f40b-115">Launch the Microsoft Teams client and sign-in using your global admin credentials.</span></span> <span data-ttu-id="5f40b-116">De Microsoft Teams Store, seleccione la nueva sección con nombre para su organización específica (en este ejemplo, Contoso).</span><span class="sxs-lookup"><span data-stu-id="5f40b-116">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="5f40b-117">Los usuarios de su organización pueden ver aplicaciones en el catálogo y los instale en los equipos de los cuales son miembros.</span><span class="sxs-lookup"><span data-stu-id="5f40b-117">Users in your organization can view apps in the catalog and install them to teams of which they are a member.</span></span> 

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="5f40b-119">Agregar una aplicación para el catálogo de aplicaciones de inquilinos</span><span class="sxs-lookup"><span data-stu-id="5f40b-119">Add an app to the Tenant Apps Catalog</span></span>

<span data-ttu-id="5f40b-120">En el almacén, seleccione **carga una aplicación personalizada** > **Cargar para Contoso**.</span><span class="sxs-lookup"><span data-stu-id="5f40b-120">From the Store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image02.png)

<span data-ttu-id="5f40b-122">(También puede **Cargar para mí o a Mis equipos**, que se denomina sideloading, que hace que la aplicación esté disponible únicamente para los o los equipos seleccionados.)</span><span class="sxs-lookup"><span data-stu-id="5f40b-122">(You can also choose **Upload for me or my teams**, which is called sideloading, that makes the app available only to your or your selected teams.)</span></span> 

<span data-ttu-id="5f40b-123">Navegue hasta el paquete de la aplicación y selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="5f40b-123">Navigate to the app package and select it.</span></span>

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image03.png)

<span data-ttu-id="5f40b-125">Cuando vuelva a su catálogo de aplicaciones del inquilino, será la nueva aplicación de empresa no existe.</span><span class="sxs-lookup"><span data-stu-id="5f40b-125">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="5f40b-126">Recuerde que sólo usted y los miembros de la organización tienen acceso a este catálogo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="5f40b-126">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="5f40b-127">Actualizar una aplicación en el catálogo de aplicaciones de inquilinos</span><span class="sxs-lookup"><span data-stu-id="5f40b-127">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="5f40b-128">En el catálogo de aplicaciones inquilino, seleccione "**...**"</span><span class="sxs-lookup"><span data-stu-id="5f40b-128">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="5f40b-129">en esquina superior derecha de la aplicación que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="5f40b-129">on top right of the app you want to update.</span></span>
2. <span data-ttu-id="5f40b-130">Navegue al paquete de la aplicación actualizada y selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="5f40b-130">Navigate to the updated app package and select it.</span></span>

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image04.png)

<span data-ttu-id="5f40b-132">La aplicación se revisará a la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="5f40b-132">The app will be revised to version 2.0.</span></span> <span data-ttu-id="5f40b-133">También se elimina la aplicación para toda la empresa desde este menú.</span><span class="sxs-lookup"><span data-stu-id="5f40b-133">You also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="5f40b-134">Usar el portal de administración de Office 365 para administrar el catálogo de aplicaciones de inquilinos</span><span class="sxs-lookup"><span data-stu-id="5f40b-134">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="5f40b-135">Si tiene aplicaciones que necesitan correcciones de errores, puede deshabilitar temporalmente aplicaciones a través del portal de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="5f40b-135">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal.</span></span> <span data-ttu-id="5f40b-136">Además de la configuración anterior, ahora hay una sección dedicada a las aplicaciones de su empresa.</span><span class="sxs-lookup"><span data-stu-id="5f40b-136">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="5f40b-137">Puede elegir qué aplicaciones que desea habilitar o deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="5f40b-137">You can choose which apps you want to enable or disable.</span></span>

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image05.png)

<span data-ttu-id="5f40b-139">Esto impide que los usuarios interactuar con la aplicación, sin eliminar por completo la aplicación.</span><span class="sxs-lookup"><span data-stu-id="5f40b-139">This blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="5f40b-140">Estos controles dar a los administradores más flexibilidad y control cuando gobierno de aplicaciones en la empresa.</span><span class="sxs-lookup"><span data-stu-id="5f40b-140">These controls give admins additional flexibility and control when governance of apps in your enterprise.</span></span> 


