---
title: Administración de la tienda de aplicaciones de Microsoft los equipos privados
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/05/2018
ms.topic: article
ms.service: msteams
ms.reviewer: prem
description: Instrucciones para la administración de aplicaciones en la tienda de aplicaciones privada de Microsoft Teams.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6aaa763c423d7756808856706375f96f99224b9e
ms.sourcegitcommit: d979aecf73da0ba493a0b3be1db4d8b997c6ce2d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2018
ms.locfileid: "19694892"
---
<a name="publish-apps-to-the-microsoft-teams-private-app-store"></a><span data-ttu-id="effc3-103">Publicar aplicaciones en la tienda de aplicaciones de Microsoft los equipos privados</span><span class="sxs-lookup"><span data-stu-id="effc3-103">Publish Apps to the Microsoft Teams Private App Store</span></span>
============================================

> [!IMPORTANT]
> <span data-ttu-id="effc3-104">Esta página describe una característica de la versión preliminar y contiene contenido preliminar que puede cambiar considerablemente antes de que se libere.</span><span class="sxs-lookup"><span data-stu-id="effc3-104">This page describes a pre-release feature and contains preliminary content that might change substantially before it is released.</span></span> <span data-ttu-id="effc3-105">Las capturas de pantalla son marcadores de posición y podrían ser diferentes de lo que se ve.</span><span class="sxs-lookup"><span data-stu-id="effc3-105">Any screenshots are placeholders and might look different than what you see.</span></span>

<span data-ttu-id="effc3-106">Puede usar Microsoft Teams Private App Store para probar y distribuir aplicaciones de línea de negocio para su organización.</span><span class="sxs-lookup"><span data-stu-id="effc3-106">You can use the Microsoft Teams Private App Store to test and distribute line-of-business applications to your organization.</span></span> 

<span data-ttu-id="effc3-107">Microsoft Teams Private App Store permite distribuir las aplicaciones de línea de negocio que han sido creadas específicamente para su organización y que se basan en para completan las funciones empresariales fundamentales para los usuarios.</span><span class="sxs-lookup"><span data-stu-id="effc3-107">The Microsoft Teams Private App Store lets you distribute your line-of-business applications that were built specifically for your organization and that you rely on to complete critical business functions to your users.</span></span> 
 
<span data-ttu-id="effc3-108">Existen dos métodos para publicar aplicaciones en la tienda de aplicaciones privada de los equipos:</span><span class="sxs-lookup"><span data-stu-id="effc3-108">There are two methods to publish apps to the Teams Private App Store:</span></span>
- <span data-ttu-id="effc3-109">Directamente desde el cliente de los equipos</span><span class="sxs-lookup"><span data-stu-id="effc3-109">Directly from the Teams client</span></span> 
- <span data-ttu-id="effc3-110">Cmdlets que aprovechan las API de gráfico de Microsoft (este método no está todavía disponible para vista previa.)</span><span class="sxs-lookup"><span data-stu-id="effc3-110">Cmdlets that leverage Microsoft Graph APIs (This method is not yet available for preview.)</span></span>

## <a name="publish-an-app-to-the-teams-private-app-store-from-the-teams-client"></a><span data-ttu-id="effc3-111">Publicar una aplicación en la tienda de aplicaciones privada de los equipos desde el cliente de los equipos</span><span class="sxs-lookup"><span data-stu-id="effc3-111">Publish an App to the Teams Private App Store from the Teams client</span></span>

### <a name="get-a-teams-app-package"></a><span data-ttu-id="effc3-112">Obtener un paquete de la aplicación de los equipos</span><span class="sxs-lookup"><span data-stu-id="effc3-112">Get a Teams app package</span></span>

<span data-ttu-id="effc3-113">Se crea un paquete de aplicación de los equipos mediante el uso de [Los equipos de aplicación Studio](https://docs.microsoft.com/en-us/microsoftteams/platform/get-started/get-started-app-studio).</span><span class="sxs-lookup"><span data-stu-id="effc3-113">A Teams app package is created by using [Teams App Studio](https://docs.microsoft.com/en-us/microsoftteams/platform/get-started/get-started-app-studio).</span></span> <span data-ttu-id="effc3-114">Una vez que el paquete de la aplicación, puede agregarlo al catálogo de aplicaciones de empresa.</span><span class="sxs-lookup"><span data-stu-id="effc3-114">Once you have the app package, you can add it to enterprise app catalog.</span></span> <span data-ttu-id="effc3-115">Si bien todos los usuarios en el inquilino pueden ver el catálogo de aplicaciones, sólo los administradores tienen la capacidad de administrar.</span><span class="sxs-lookup"><span data-stu-id="effc3-115">While all users in the tenant can view the app catalog, only admins have the ability to manage it.</span></span>

### <a name="go-to-the-teams-private-app-store"></a><span data-ttu-id="effc3-116">Vaya a la tienda de aplicaciones privada de los equipos</span><span class="sxs-lookup"><span data-stu-id="effc3-116">Go to the Teams Private App Store</span></span>

<span data-ttu-id="effc3-117">De Microsoft Teams Store, seleccione la nueva sección con nombre para su organización específica (en este ejemplo, Contoso).</span><span class="sxs-lookup"><span data-stu-id="effc3-117">From the Microsoft Teams Store, select the new section named for your specific organization (in this example, Contoso).</span></span> <span data-ttu-id="effc3-118">Los usuarios de su organización pueden ver aplicaciones en el catálogo y los instale en los equipos de los cuales son miembros.</span><span class="sxs-lookup"><span data-stu-id="effc3-118">Users in your organization can view apps in the catalog and install them to teams of which they are a member.</span></span> 

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image01.png)

### <a name="add-an-app-to-the-teams-private-app-store"></a><span data-ttu-id="effc3-120">Agregar una aplicación a la tienda de aplicaciones privada de los equipos</span><span class="sxs-lookup"><span data-stu-id="effc3-120">Add an app to the Teams Private App Store</span></span>

<span data-ttu-id="effc3-121">En el almacén, seleccione **carga una aplicación personalizada** > **Cargar para Contoso**.</span><span class="sxs-lookup"><span data-stu-id="effc3-121">From the Store, select **Upload a custom app** > **Upload for Contoso**.</span></span>

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image02.png)

<span data-ttu-id="effc3-123">(También puede **Cargar para mí o a Mis equipos**, que se denomina sideloading, que hace que la aplicación esté disponible únicamente para los o los equipos seleccionados.)</span><span class="sxs-lookup"><span data-stu-id="effc3-123">(You can also choose **Upload for me or my teams**, which is called sideloading, that makes the app available only to your or your selected teams.)</span></span> 

<span data-ttu-id="effc3-124">Navegue hasta el paquete de la aplicación y selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="effc3-124">Navigate to the app package and select it.</span></span>

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image03.png)

<span data-ttu-id="effc3-126">Cuando vuelva a su catálogo de aplicaciones, la nueva aplicación de empresa va a estar allí.</span><span class="sxs-lookup"><span data-stu-id="effc3-126">When you go back to your app catalog, the new enterprise app will be there.</span></span> <span data-ttu-id="effc3-127">Recuerde que sólo usted y los miembros de la organización tienen acceso a este catálogo de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="effc3-127">Remember, only you and members of your organization have access to this app catalog.</span></span>

### <a name="update-an-app-in-the-teams-private-app-store"></a><span data-ttu-id="effc3-128">Actualizar una aplicación en la tienda de aplicaciones privada de los equipos</span><span class="sxs-lookup"><span data-stu-id="effc3-128">Update an app in the Teams Private App Store</span></span>

1. <span data-ttu-id="effc3-129">En el catálogo de aplicaciones, seleccione "**...**"</span><span class="sxs-lookup"><span data-stu-id="effc3-129">From your app catalog, select “**…**”</span></span> <span data-ttu-id="effc3-130">en esquina superior derecha de la aplicación que desea actualizar.</span><span class="sxs-lookup"><span data-stu-id="effc3-130">on top right of the app you want to update.</span></span>
2. <span data-ttu-id="effc3-131">Navegue al paquete de la aplicación actualizada y selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="effc3-131">Navigate to the updated app package and select it.</span></span>

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image04.png)

<span data-ttu-id="effc3-133">La aplicación se revisará a la versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="effc3-133">The app will be revised to version 2.0.</span></span> <span data-ttu-id="effc3-134">También se elimina la aplicación para toda la empresa desde este menú.</span><span class="sxs-lookup"><span data-stu-id="effc3-134">You also delete the app for your entire company from this menu.</span></span>

## <a name="manage-the-teams-private-app-store-by-using-cmdlets-and-microsoft-graph-apis"></a><span data-ttu-id="effc3-135">Administración de la tienda de aplicaciones privada de los equipos mediante el uso de los cmdlets y las API de Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="effc3-135">Manage the Teams Private App Store by using cmdlets and Microsoft Graph APIs</span></span>

<span data-ttu-id="effc3-136">Este método aún no está disponible para vista previa.</span><span class="sxs-lookup"><span data-stu-id="effc3-136">This method is not yet available for preview.</span></span>

## <a name="use-the-office-365-admin-portal-to-manage-private-apps"></a><span data-ttu-id="effc3-137">Usar el portal de administración de Office 365 para administrar aplicaciones de privado</span><span class="sxs-lookup"><span data-stu-id="effc3-137">Use the Office 365 admin portal to manage Private Apps</span></span>

<span data-ttu-id="effc3-138">Si tiene aplicaciones que necesitan correcciones de errores, puede deshabilitar temporalmente aplicaciones a través del portal de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="effc3-138">If you have apps that need bug fixes, you can temporarily disable apps through the Office 365 admin portal.</span></span> <span data-ttu-id="effc3-139">Además de la configuración anterior, ahora hay una sección dedicada a las aplicaciones de su empresa.</span><span class="sxs-lookup"><span data-stu-id="effc3-139">In addition to previous settings, there is now a section dedicated to your company's apps.</span></span> <span data-ttu-id="effc3-140">Puede elegir qué aplicaciones que desea habilitar o deshabilitar.</span><span class="sxs-lookup"><span data-stu-id="effc3-140">You can choose which apps you want to enable or disable.</span></span>

![Captura de pantalla de la tienda de aplicaciones de los equipos que muestra el catálogo de aplicaciones.](media/private-app-store-teams-image05.png)

<span data-ttu-id="effc3-142">Esto impide que los usuarios interactuar con la aplicación, sin eliminar por completo la aplicación.</span><span class="sxs-lookup"><span data-stu-id="effc3-142">This blocks users from interacting with the app, without deleting the app entirely.</span></span> <span data-ttu-id="effc3-143">Estos controles dar a los administradores más flexibilidad y control cuando gobierno de aplicaciones en la empresa.</span><span class="sxs-lookup"><span data-stu-id="effc3-143">These controls give admins additional flexibility and control when governance of apps in your enterprise.</span></span> 


