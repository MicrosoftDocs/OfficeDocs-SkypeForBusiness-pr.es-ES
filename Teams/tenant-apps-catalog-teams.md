---
title: Publicar aplicaciones en el catálogo de aplicaciones del inquilino de equipos de Microsoft
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/26/2018
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: Instrucciones para la publicación de aplicaciones en el catálogo de aplicaciones de inquilino de los equipos de Microsoft.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 298caf3cee6fe6af38f22ef9ac7dd85991fd6dba
ms.sourcegitcommit: b42a6a56a0e1e4be1239174c1c3b4ab86517d043
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/26/2018
ms.locfileid: "20050462"
---
<a name="publish-apps-to-the-microsoft-teams-tenant-apps-catalog"></a><span data-ttu-id="624ed-103">Publicar aplicaciones en el catálogo de aplicaciones del inquilino de equipos de Microsoft</span><span class="sxs-lookup"><span data-stu-id="624ed-103">Publish apps to the Microsoft Teams Tenant Apps Catalog</span></span>
=======================================================

> [!IMPORTANT]
> <span data-ttu-id="624ed-104">Esta página describe una característica de la versión preliminar y contiene contenido preliminar que puede cambiar considerablemente antes de que se libere.</span><span class="sxs-lookup"><span data-stu-id="624ed-104">This page describes a pre-release feature and contains preliminary content that might change substantially before it is released.</span></span> <span data-ttu-id="624ed-105">Las capturas de pantalla son marcadores de posición y podrían ser diferentes de lo que se ve.</span><span class="sxs-lookup"><span data-stu-id="624ed-105">Any screenshots are placeholders and might look different than what you see.</span></span>

<span data-ttu-id="624ed-106">Puede usar el catálogo de aplicaciones de inquilino de los equipos de Microsoft para probar y distribuir aplicaciones de línea de negocio para su organización.</span><span class="sxs-lookup"><span data-stu-id="624ed-106">You can use the Microsoft Teams Tenant Apps Catalog to test and distribute line-of-business applications to your organization.</span></span> 

<span data-ttu-id="624ed-107">El catálogo de aplicaciones de los equipos de inquilino permite distribuir las aplicaciones de línea de negocio que han sido creadas específicamente para su organización y que se basan en para completan las funciones empresariales fundamentales para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="624ed-107">The Teams Tenant Apps Catalog lets you distribute your line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions to your users.</span></span> 
 
<span data-ttu-id="624ed-108">Puede publicar aplicaciones en el catálogo de aplicaciones del inquilino de equipos directamente desde el cliente de los equipos.</span><span class="sxs-lookup"><span data-stu-id="624ed-108">You can publish apps to the Teams Tenant Apps Catalog directly from the Teams client.</span></span>

## <a name="publish-an-app-to-the-tenant-apps-catalog-from-the-teams-client"></a><span data-ttu-id="624ed-109">Publicar una aplicación en el catálogo de aplicaciones de inquilino desde el cliente de los equipos</span><span class="sxs-lookup"><span data-stu-id="624ed-109">Publish an app to the Tenant Apps Catalog from the Teams client</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="624ed-110">Obtener un paquete de la aplicación de los equipos</span><span class="sxs-lookup"><span data-stu-id="624ed-110">Get a Teams app package</span></span>

<span data-ttu-id="624ed-111">Se crea un paquete de aplicación de los equipos mediante el uso de [Los equipos de aplicación Studio](https://docs.microsoft.com/en-us/microsoftteams/platform/get-started/get-started-app-studio).</span><span class="sxs-lookup"><span data-stu-id="624ed-111">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/en-us/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="624ed-112">Una vez que el paquete de la aplicación, puede agregarlo al catálogo de aplicaciones de empresa.</span><span class="sxs-lookup"><span data-stu-id="624ed-112">Once you have the app package, you can add it to enterprise app catalog.</span></span> <span data-ttu-id="624ed-113">Si bien todos los usuarios en el inquilino pueden ver el catálogo de aplicaciones, sólo los administradores tienen la capacidad de administrar.</span><span class="sxs-lookup"><span data-stu-id="624ed-113">While all users in the tenant can view the app catalog, only admins have the ability to manage it.</span></span>

### <a name="go-to-the-tenant-apps-catalog"></a><span data-ttu-id="624ed-114">Vaya al catálogo de aplicaciones de inquilinos</span><span class="sxs-lookup"><span data-stu-id="624ed-114">Go to the Tenant Apps Catalog</span></span>

<span data-ttu-id="624ed-115">De Microsoft Teams Store, seleccione la nueva sección con nombre para su organización específica (en este ejemplo, Contoso).</span><span class="sxs-lookup"><span data-stu-id="624ed-115">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="624ed-116">Los usuarios de su organización pueden ver aplicaciones en el catálogo y los instale en los equipos de los cuales son miembros.</span><span class="sxs-lookup"><span data-stu-id="624ed-116">Users in your organization can view apps in the catalog and install them to teams of which they are a member.</span></span> 

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-tenant-apps-catalog"></a><span data-ttu-id="624ed-118">Agregar una aplicación para el catálogo de aplicaciones de inquilinos</span><span class="sxs-lookup"><span data-stu-id="624ed-118">Add an app to the Tenant Apps Catalog</span></span>

<span data-ttu-id="624ed-119">En el almacén, seleccione **carga una aplicación personalizada** > **Cargar para Contoso**.</span><span class="sxs-lookup"><span data-stu-id="624ed-119">From the Store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image02.png)

<span data-ttu-id="624ed-121">(También puede **Cargar para mí o a Mis equipos**, que se denomina sideloading, que hace que la aplicación esté disponible únicamente para los o los equipos seleccionados.)</span><span class="sxs-lookup"><span data-stu-id="624ed-121">(You can also choose **Upload for me or my teams**, which is called sideloading, that makes the app available only to your or your selected teams.)</span></span> 

<span data-ttu-id="624ed-122">Navegue hasta el paquete de la aplicación y selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="624ed-122">Navigate to the app package and select it.</span></span>

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image03.png)

<span data-ttu-id="624ed-124">Cuando vuelva a su catálogo de aplicaciones del inquilino, será la nueva aplicación de empresa no existe.</span><span class="sxs-lookup"><span data-stu-id="624ed-124">When you go back to your Tenant Apps Catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="624ed-125">Recuerde que sólo usted y los miembros de la organización tienen acceso a este catálogo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="624ed-125">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-tenant-apps-catalog"></a><span data-ttu-id="624ed-126">Actualizar una aplicación en el catálogo de aplicaciones de inquilinos</span><span class="sxs-lookup"><span data-stu-id="624ed-126">Update an app in the Tenant Apps Catalog</span></span>

1. <span data-ttu-id="624ed-127">En el catálogo de aplicaciones inquilino, seleccione "**...**"</span><span class="sxs-lookup"><span data-stu-id="624ed-127">From your Tenant Apps Catalog, select “**…**”</span></span> <span data-ttu-id="624ed-128">en esquina superior derecha de la aplicación que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="624ed-128">on top right of the app you want to update.</span></span>
2. <span data-ttu-id="624ed-129">Navegue al paquete de la aplicación actualizada y selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="624ed-129">Navigate to the updated app package and select it.</span></span>

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image04.png)

<span data-ttu-id="624ed-131">La aplicación se revisará a la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="624ed-131">The app will be revised to version 2.0.</span></span> <span data-ttu-id="624ed-132">También se elimina la aplicación para toda la empresa desde este menú.</span><span class="sxs-lookup"><span data-stu-id="624ed-132">You also delete the app for your entire company from this menu.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-the-tenant-apps-catalog"></a><span data-ttu-id="624ed-133">Usar el portal de administración de Office 365 para administrar el catálogo de aplicaciones de inquilinos</span><span class="sxs-lookup"><span data-stu-id="624ed-133">Use the Office 365 admin portal to manage the Tenant Apps Catalog</span></span>

<span data-ttu-id="624ed-134">Si tiene aplicaciones que necesitan correcciones de errores, puede deshabilitar temporalmente aplicaciones a través del portal de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="624ed-134">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal.</span></span> <span data-ttu-id="624ed-135">Además de la configuración anterior, ahora hay una sección dedicada a las aplicaciones de su empresa.</span><span class="sxs-lookup"><span data-stu-id="624ed-135">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="624ed-136">Puede elegir qué aplicaciones que desea habilitar o deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="624ed-136">You can choose which apps you want to enable or disable.</span></span>

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image05.png)

<span data-ttu-id="624ed-138">Esto impide que los usuarios interactuar con la aplicación, sin eliminar por completo la aplicación.</span><span class="sxs-lookup"><span data-stu-id="624ed-138">This blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="624ed-139">Estos controles dar a los administradores más flexibilidad y control cuando gobierno de aplicaciones en la empresa.</span><span class="sxs-lookup"><span data-stu-id="624ed-139">These controls give admins additional flexibility and control when governance of apps in your enterprise.</span></span> 


