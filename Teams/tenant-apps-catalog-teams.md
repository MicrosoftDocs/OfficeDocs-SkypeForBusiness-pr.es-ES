---
title: Publicar aplicaciones en el catálogo de aplicaciones del inquilino de equipos de Microsoft
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/02/2018
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: Instrucciones para la publicación de aplicaciones en el catálogo de aplicaciones de inquilino de los equipos de Microsoft.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 11b1ccf53715b15098b772e460602ce5eddade62
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23866375"
---
<a name="publish-apps-to-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="666d3-103">Publicar aplicaciones en el catálogo de aplicaciones del inquilino de equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="666d3-103">Publish apps to the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

<span data-ttu-id="666d3-104">Puede usar el catálogo de aplicaciones de inquilino de los equipos de Microsoft para probar y distribuir aplicaciones de línea de negocio para su organización.</span><span class="sxs-lookup"><span data-stu-id="666d3-104">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span> 

<span data-ttu-id="666d3-105">El catálogo de aplicaciones de los equipos de inquilino permite distribuir las aplicaciones de línea de negocio que han sido creadas específicamente para su organización y que se basan en para completan las funciones empresariales fundamentales para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="666d3-105">The Teams Tenant Apps Catalog lets you distribute your line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions to your users.</span></span> 
 
<span data-ttu-id="666d3-106">Puede publicar aplicaciones en el catálogo de aplicaciones del inquilino de equipos directamente desde el cliente de los equipos.</span><span class="sxs-lookup"><span data-stu-id="666d3-106">You can publish apps to the Teams Tenant Apps Catalog directly from the Teams client.</span></span>

## <a name="publish-an-app-to-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="666d3-107">Publicar una aplicación en el catálogo de aplicaciones de inquilino desde el cliente de los equipos</span><span class="sxs-lookup"><span data-stu-id="666d3-107">Publish an app to the Tenant Apps Catalog from the Teams client</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="666d3-108">Obtener un paquete de la aplicación de los equipos</span><span class="sxs-lookup"><span data-stu-id="666d3-108">Get a Teams app package</span></span>

<span data-ttu-id="666d3-109">Se crea un paquete de aplicación de los equipos mediante el uso de [Los equipos de aplicación Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span><span class="sxs-lookup"><span data-stu-id="666d3-109">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="666d3-110">Una vez que el paquete de la aplicación, puede agregarlo al catálogo de aplicaciones de empresa.</span><span class="sxs-lookup"><span data-stu-id="666d3-110">Once you have the app package, you can add it to enterprise app catalog.</span></span> <span data-ttu-id="666d3-111">Mientras todos los usuarios en el inquilino puede ver el catálogo de aplicaciones, actualmente sólo global los administradores tienen la capacidad para publicar y administrarlo.</span><span class="sxs-lookup"><span data-stu-id="666d3-111">While all users in the tenant can view the app catalog, currently only global admins have the ability to publish and manage it.</span></span> <span data-ttu-id="666d3-112">(Al final, los administradores de los equipos podrán hacerlo así como.)</span><span class="sxs-lookup"><span data-stu-id="666d3-112">(Eventually, Teams admins will be able to do this as well.)</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="666d3-113">Vaya al catálogo de aplicaciones de inquilinos</span><span class="sxs-lookup"><span data-stu-id="666d3-113">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="666d3-114">De Microsoft Teams Store, seleccione la nueva sección con nombre para su organización específica (en este ejemplo, Contoso).</span><span class="sxs-lookup"><span data-stu-id="666d3-114">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="666d3-115">Los usuarios de su organización pueden ver aplicaciones en el catálogo y los instale en los equipos de los cuales son miembros.</span><span class="sxs-lookup"><span data-stu-id="666d3-115">Users in your organization can view apps in the catalog and install them to teams of which they are a member.</span></span> 

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="666d3-117">Agregar una aplicación para el catálogo de aplicaciones de inquilinos</span><span class="sxs-lookup"><span data-stu-id="666d3-117">Add an app to the Tenant Apps Catalog</span></span>

<span data-ttu-id="666d3-118">En el almacén, seleccione **carga una aplicación personalizada** > **Cargar para Contoso**.</span><span class="sxs-lookup"><span data-stu-id="666d3-118">From the Store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image02.png)

<span data-ttu-id="666d3-120">(También puede **Cargar para mí o a Mis equipos**, que se denomina sideloading, que hace que la aplicación esté disponible únicamente para los o los equipos seleccionados.)</span><span class="sxs-lookup"><span data-stu-id="666d3-120">(You can also choose **Upload for me or my teams**, which is called sideloading, that makes the app available only to your or your selected teams.)</span></span> 

<span data-ttu-id="666d3-121">Navegue hasta el paquete de la aplicación y selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="666d3-121">Navigate to the app package and select it.</span></span>

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image03.png)

<span data-ttu-id="666d3-123">Cuando vuelva a su catálogo de aplicaciones del inquilino, será la nueva aplicación de empresa no existe.</span><span class="sxs-lookup"><span data-stu-id="666d3-123">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="666d3-124">Recuerde que sólo usted y los miembros de la organización tienen acceso a este catálogo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="666d3-124">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="666d3-125">Actualizar una aplicación en el catálogo de aplicaciones de inquilinos</span><span class="sxs-lookup"><span data-stu-id="666d3-125">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="666d3-126">En el catálogo de aplicaciones inquilino, seleccione "**...**"</span><span class="sxs-lookup"><span data-stu-id="666d3-126">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="666d3-127">en esquina superior derecha de la aplicación que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="666d3-127">on top right of the app you want to update.</span></span>
2. <span data-ttu-id="666d3-128">Navegue al paquete de la aplicación actualizada y selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="666d3-128">Navigate to the updated app package and select it.</span></span>

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image04.png)

<span data-ttu-id="666d3-130">La aplicación se revisará a la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="666d3-130">The app will be revised to version 2.0.</span></span> <span data-ttu-id="666d3-131">También se elimina la aplicación para toda la empresa desde este menú.</span><span class="sxs-lookup"><span data-stu-id="666d3-131">You also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="666d3-132">Usar el portal de administración de Office 365 para administrar el catálogo de aplicaciones de inquilinos</span><span class="sxs-lookup"><span data-stu-id="666d3-132">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="666d3-133">Si tiene aplicaciones que necesitan correcciones de errores, puede deshabilitar temporalmente aplicaciones a través del portal de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="666d3-133">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal.</span></span> <span data-ttu-id="666d3-134">Además de la configuración anterior, ahora hay una sección dedicada a las aplicaciones de su empresa.</span><span class="sxs-lookup"><span data-stu-id="666d3-134">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="666d3-135">Puede elegir qué aplicaciones que desea habilitar o deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="666d3-135">You can choose which apps you want to enable or disable.</span></span>

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image05.png)

<span data-ttu-id="666d3-137">Esto impide que los usuarios interactuar con la aplicación, sin eliminar por completo la aplicación.</span><span class="sxs-lookup"><span data-stu-id="666d3-137">This blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="666d3-138">Estos controles dar a los administradores más flexibilidad y control cuando gobierno de aplicaciones en la empresa.</span><span class="sxs-lookup"><span data-stu-id="666d3-138">These controls give admins additional flexibility and control when governance of apps in your enterprise.</span></span> 


