---
title: Crear una aplicación del portal de intranet de un equipo "desde un sitio o una página de SharePoint Online
author: LanaChin
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: Tome un sitio o página de SharePoint Online y cree una pestaña estática independiente que se puede usar como un portal de intranet para su organización.
localization_priority: Normal
ms.openlocfilehash: 772063a7444e9c31d2740ac48635dc0f2e367435
ms.sourcegitcommit: aaae9df142ebb844a1fea27d3ae3b95130903d6a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2020
ms.locfileid: "43100368"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a><span data-ttu-id="4a426-103">Crear una aplicación del portal de intranet de un equipo "desde un sitio o una página de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4a426-103">Create a Teams 'Intranet Portal app' from a SharePoint Online site or page</span></span>

<span data-ttu-id="4a426-104">Siga los pasos descritos en este artículo para crear una aplicación independiente y estática dentro de teams que se vincule al sitio de intranet de su organización.</span><span class="sxs-lookup"><span data-stu-id="4a426-104">Use the steps in this article to create a standalone and static app inside of Teams that links to the intranet site for your org.</span></span>

<span data-ttu-id="4a426-105">Se crea una *aplicación personal de Teams* de su sitio de intranet de SharePoint y aparecerá como una pestaña dentro de Teams.</span><span class="sxs-lookup"><span data-stu-id="4a426-105">A *Teams Personal App* of your SharePoint intranet site is created, and will appear as a tab inside of Teams.</span></span> <span data-ttu-id="4a426-106">Esta pestaña puede contener información importante para todos los usuarios de su equipo.</span><span class="sxs-lookup"><span data-stu-id="4a426-106">This tab can contain information important to all your Teams users.</span></span> <span data-ttu-id="4a426-107">Es una forma rápida y cómoda para que los usuarios de Teams accedan a las actualizaciones con un solo clic.</span><span class="sxs-lookup"><span data-stu-id="4a426-107">It is a quick and convenient way for Teams users to access updates just a tab click away.</span></span>

<span data-ttu-id="4a426-108">Tenga en cuenta que el proceso que se muestra **debe usar** un sitio o página de SharePoint *moderno* para trabajar.</span><span class="sxs-lookup"><span data-stu-id="4a426-108">Be aware that the process shown **must use** a *modern* SharePoint site or page to work.</span></span> <span data-ttu-id="4a426-109">Este proceso no está disponible para sitios o páginas *clásicas* .</span><span class="sxs-lookup"><span data-stu-id="4a426-109">This process is not available for *classical* sites or pages.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4a426-110">Asegúrese de que la carga de las aplicaciones de Teams está habilitada para su inquilino.</span><span class="sxs-lookup"><span data-stu-id="4a426-110">Make certain that side-loading of Teams apps is enabled for your tenant.</span></span> <span data-ttu-id="4a426-111">En función de dónde se encuentre en el proceso de migración del portal de administración de Teams, es posible que tenga que habilitarlo en Teams > admin, o en la configuración de > de administrador > servicios y complementos > aplicaciones de Microsoft Teams > > aplicaciones externas, en la versión anterior del portal.</span><span class="sxs-lookup"><span data-stu-id="4a426-111">Depending on where you are in the migration process of the Teams Admin portal, you might need to enable it either under Teams > Admin, or under Admin > Settings > Services and Add-ins > Microsoft Teams > Apps > External Apps, in the previous version of the portal!</span></span> 

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a><span data-ttu-id="4a426-112">Usar App Studio para crear una aplicación independiente de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4a426-112">Use App Studio to create your standalone SharePoint Online app</span></span>

<span data-ttu-id="4a426-113">Antes de empezar:</span><span class="sxs-lookup"><span data-stu-id="4a426-113">Before you begin:</span></span>
1. <span data-ttu-id="4a426-114">Tendrá que conocer la dirección URL de una comunicación moderna de SharePoint Online o un sitio de grupo o página.</span><span class="sxs-lookup"><span data-stu-id="4a426-114">You'll need to know the URL of a SharePoint Online modern Communication or Team site, or page.</span></span>
    - <span data-ttu-id="4a426-115">Estos sitios siempre tendrán */equipos/* o */sites/* en sus rutas.</span><span class="sxs-lookup"><span data-stu-id="4a426-115">These sites will always have either */teams/* or */sites/* in their paths.</span></span>

2. <span data-ttu-id="4a426-116">Necesitará conocer el subdominio del inquilino, que se usará en el marcador de posición **{{subdominio}}**.</span><span class="sxs-lookup"><span data-stu-id="4a426-116">You'll need to know your tenant's subdomain, which will be used in the placeholder **{{subdomain}}**.</span></span>

3. <span data-ttu-id="4a426-117">En este artículo se usará el marcador de posición **{{siteUrl}}** como *dirección URL* del sitio o página que elija.</span><span class="sxs-lookup"><span data-stu-id="4a426-117">This article will use **{{siteUrl}}** placeholder for your the *URL* of the site or page you chose.</span></span>
    - <span data-ttu-id="4a426-118">*Direcciones URL*de https://contoso.sharepoint.com/teams/Contosoejemplo: *o*   https://contoso.sharepoint.com/sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="4a426-118">Example *URLs*:   https://contoso.sharepoint.com/teams/Contoso   *or* https://contoso.sharepoint.com/sites/Contoso</span></span> 
4. <span data-ttu-id="4a426-119">Además, se usará **{{sitePath}}** para indicar la ruta de *acceso* de la dirección URL (por ejemplo:/Teams/contoso).</span><span class="sxs-lookup"><span data-stu-id="4a426-119">Also, **{{sitePath}}** will be used to denote the *path* of the URL (ex: /teams/Contoso).</span></span>
    - <span data-ttu-id="4a426-120">*Rutas*de ejemplo:/Teams/contoso *o* /sites/contoso</span><span class="sxs-lookup"><span data-stu-id="4a426-120">Example *paths*:   /teams/Contoso   *or* /sites/Contoso</span></span> 

<span data-ttu-id="4a426-121">Empiece siguiendo los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="4a426-121">Begin by following the steps below:</span></span>

1. <span data-ttu-id="4a426-122">Vaya a la tienda de Teams.</span><span class="sxs-lookup"><span data-stu-id="4a426-122">Go to the Teams Store.</span></span>

2. <span data-ttu-id="4a426-123">Instale o abra App Studio.</span><span class="sxs-lookup"><span data-stu-id="4a426-123">Install or open App Studio.</span></span>

3. <span data-ttu-id="4a426-124">Haga clic en **abrir**, junto a la opción aplicación.</span><span class="sxs-lookup"><span data-stu-id="4a426-124">Click **Open**, next to the App option.</span></span>

4. <span data-ttu-id="4a426-125">Con App Studio abierto, haga clic en el **Editor de manifiestos**.</span><span class="sxs-lookup"><span data-stu-id="4a426-125">With App Studio open, click on **Manifest Editor**.</span></span>

5. <span data-ttu-id="4a426-126">**Crear una nueva aplicación**.</span><span class="sxs-lookup"><span data-stu-id="4a426-126">**Create a new app**.</span></span>

6. <span data-ttu-id="4a426-127">Rellene todos los detalles de la **aplicación**.</span><span class="sxs-lookup"><span data-stu-id="4a426-127">Fill in all **App Details**.</span></span>

7. <span data-ttu-id="4a426-128">En capacidades, haga clic en **pestañas** .</span><span class="sxs-lookup"><span data-stu-id="4a426-128">Click on **Tabs** under Capabilities.</span></span>

8. <span data-ttu-id="4a426-129">Haga clic en **Agregar** en la pestaña personal.</span><span class="sxs-lookup"><span data-stu-id="4a426-129">Click **Add** under Personal Tab.</span></span>

9. <span data-ttu-id="4a426-130">Rellene el **nombre** y elija **un nuevo identificador de entidad única**.</span><span class="sxs-lookup"><span data-stu-id="4a426-130">Fill in the **Name** and choose **a new unique Entity ID**.</span></span>

10. <span data-ttu-id="4a426-131">Rellene el **contentURL y la dirección URL del sitio web**.</span><span class="sxs-lookup"><span data-stu-id="4a426-131">Fill in the **contentURL and Website URL**.</span></span> 

- <span data-ttu-id="4a426-132">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx? SPFX = true&dest = {{sitePath}}</span><span class="sxs-lookup"><span data-stu-id="4a426-132">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span></span>  
- <span data-ttu-id="4a426-133">**websiteUrl**: {{siteUrl}}</span><span class="sxs-lookup"><span data-stu-id="4a426-133">**websiteUrl**: {{siteUrl}}</span></span> 

    <span data-ttu-id="4a426-134">Ejemplo **contentURL**:https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span><span class="sxs-lookup"><span data-stu-id="4a426-134">Example **contentURL**: https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span></span> 

11. <span data-ttu-id="4a426-135">Vaya a **dominios y permisos**.</span><span class="sxs-lookup"><span data-stu-id="4a426-135">Navigate to **Domains and Permissions**.</span></span> <span data-ttu-id="4a426-136">Asegúrese de que la sección dominios válidos contiene el nombre de dominio de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4a426-136">Make sure the valid domains section contains your SharePoint online domain name.</span></span>

    <span data-ttu-id="4a426-137">Ejemplo: contoso.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="4a426-137">Example: contoso.sharepoint.com</span></span>

12. <span data-ttu-id="4a426-138">Agregue las siguientes propiedades de **Inicio de sesión único** de la aplicación web:</span><span class="sxs-lookup"><span data-stu-id="4a426-138">Add the following web app **single sign-on** properties:</span></span> 
     
     <span data-ttu-id="4a426-139">Ejemplo: **identificador de la aplicación AAD**: **dirección URL del recurso**00000003-0000-0ff1-ce00-000000000000: {{subdominio}}. SharePoint. com</span><span class="sxs-lookup"><span data-stu-id="4a426-139">Example:  **AAD application ID**: 00000003-0000-0ff1-ce00-000000000000  **Resource Url**: {{subdomain}}.sharepoint.com</span></span>

    ![Inicio de sesión único de la aplicación Web, con el identificador y la dirección URL.](media/personal-app.png)

13. <span data-ttu-id="4a426-141">**Guarde** estas propiedades y, a continuación, vaya a **probar y distribuir**.</span><span class="sxs-lookup"><span data-stu-id="4a426-141">**Save** these properties and then navigate to **Test and distribute**.</span></span> 

14. <span data-ttu-id="4a426-142">Instale la aplicación para probar personalmente la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4a426-142">Install the app to test the application personally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4a426-143">Si no usa Teams App Studio, tendrá que. zip el manifiesto. Archivo JSON que acaba de crear, navegue hasta el App Store en Teams y haga clic en el vínculo **cargar aplicación personalizada** (en la parte inferior derecha de la App Store).</span><span class="sxs-lookup"><span data-stu-id="4a426-143">If you aren't using Teams App Studio, you will have to .zip the manifest.JSON file you just created, navigate to the App Store in Teams, and click  **upload custom app** link (at the bottom right of the App Store).</span></span> <span data-ttu-id="4a426-144">Esto hará que la aplicación esté disponible para usted.</span><span class="sxs-lookup"><span data-stu-id="4a426-144">This will make the app available to you.</span></span>

15. <span data-ttu-id="4a426-145">Ahora la aplicación está disponible como una pestaña estática para que la cargue y la vea en Teams.</span><span class="sxs-lookup"><span data-stu-id="4a426-145">Now the app is available as a static tab for you to load and view in Teams.</span></span>

## <a name="test-and-view-your-new-static-tab"></a><span data-ttu-id="4a426-146">Probar y ver la nueva ficha estática</span><span class="sxs-lookup"><span data-stu-id="4a426-146">Test and view your new static tab</span></span>

<span data-ttu-id="4a426-147">Para ver la nueva pestaña en el escritorio de Teams, navegue hasta los puntos suspensivos (**...**) en el lado izquierdo de la barra de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="4a426-147">To view the new tab on the Teams desktop, navigate to the ellipses (**…**) in the left-hand side of your app bar.</span></span> <span data-ttu-id="4a426-148">Busque su nueva aplicación, cargarla y pruebe su aplicación independiente en Teams.</span><span class="sxs-lookup"><span data-stu-id="4a426-148">Find your new app, load it, and test your standalone application in Teams.</span></span>

<span data-ttu-id="4a426-149">Si desea que la nueva aplicación esté disponible en el menú de la izquierda en una posición superior, debe usar una configuración de directiva de aplicación.</span><span class="sxs-lookup"><span data-stu-id="4a426-149">If you want to make the new app available in the left menu at a higher position, you must use an app policy setting for this.</span></span> <span data-ttu-id="4a426-150">Esta opción puede encontrarse en la sección administrador de grupo > Directiva de aplicación > agregar una aplicación anclada.</span><span class="sxs-lookup"><span data-stu-id="4a426-150">This setting can be found under the Team admin section > app policy > add a pinned application.</span></span> <span data-ttu-id="4a426-151">Cuando asigne la Directiva a un usuario para realizar pruebas, el cambio aparecerá 24 horas más tarde.</span><span class="sxs-lookup"><span data-stu-id="4a426-151">When you assign the policy to a user for testing, the change will appear 24 hours later.</span></span> <span data-ttu-id="4a426-152">Teniendo esto en mente, decida dónde debe aparecer la aplicación en la primera comodidad para ayudar a evitar retrasos.</span><span class="sxs-lookup"><span data-stu-id="4a426-152">With this in mind, please decide where the app should appear at your earliest convenience to help avoid delays.</span></span>

<span data-ttu-id="4a426-153">Para ver y probar la nueva aplicación en un dispositivo móvil, abra el alimentador de aplicaciones pulsando en la comilla angular (**^**) situada encima de la barra de pestañas situada cerca de la parte inferior de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="4a426-153">To view and test the new app on a mobile device, open the app drawer by tapping on the chevron (**^**) above the tab bar near the bottom of your screen.</span></span> <span data-ttu-id="4a426-154">Busque la aplicación y desplácese hasta ella en el dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="4a426-154">Find your app and navigate to it on your mobile device.</span></span>

> [!CAUTION]
> <span data-ttu-id="4a426-155">La compatibilidad con teléfonos móviles está actualmente en Developer Preview.</span><span class="sxs-lookup"><span data-stu-id="4a426-155">Mobile support is currently in Developer Preview.</span></span> <span data-ttu-id="4a426-156">Para habilitar Developer Preview, ve a configuración > acerca de y habilita el modo de vista previa para desarrolladores.</span><span class="sxs-lookup"><span data-stu-id="4a426-156">To enable Developer Preview, navigate to Settings > About and then enable Developer Preview mode.</span></span>

## <a name="a-sample-manifestjson-file"></a><span data-ttu-id="4a426-157">Un archivo manifest. JSON de ejemplo</span><span class="sxs-lookup"><span data-stu-id="4a426-157">A Sample Manifest.JSON file</span></span>

<span data-ttu-id="4a426-158">El archivo JSON que generes tendrá un aspecto similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="4a426-158">The JSON file you generate will look something like the one below.</span></span>

```JSON
{ 

    "$schema": "https://developer.microsoft.com/en-us/json-schemas/teams/v1.5/MicrosoftTeams.schema.json", 

    "manifestVersion": "1.5", 

    "version": "1.0.0", 

    "id": "33ebded3-931c-4333-b0c5-b51dd8738873", 

    "packageName": "com.contoso.teams.devapp", 

    "developer": { 

        "name": "Contoso", 

        "websiteUrl": "https://www.contoso.com", 

        "privacyUrl": "https://www.contoso.com/privacy", 

        "termsOfUseUrl": "https://www.contoso.com/terms" 

    }, 

    "icons": { 

        "color": "color.png", 

        "outline": "outline.png" 

    }, 

    "name": { 

        "short": "Contoso Intranet", 

        "full": "Intranet Portal for Contoso" 

    }, 

    "description": { 

        "short": "Intranet portal for Contoso", 

        "full": "This app is to demonstrate the capabilities of hosting a SharePoint communication and team site as a standalone app in Teams" 

    }, 

    "accentColor": "#FFFFFF", 

    "staticTabs": [ 

        { 

            "entityId": "communicationSiteTab", 

            "name": "Contoso Net", 

            "contentUrl": "https://contoso.sharepoint.com/sites/ContosoNet/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoNet/", 

            "websiteUrl": "https://contoso.sharepoint.com/sites/ContosoNet", 

            "scopes": [ 

                "personal" 

            ] 

        }, 

        { 

            "entityId": "teamSiteTab", 

            "name": "Team Contoso", 

            "contentUrl": "https://contoso.sharepoint.com/teams/TeamContoso/_layouts/15/teamslogon.aspx?SPFX=true&dest=/teams/TeamContoso/", 

            "websiteUrl": "https://contoso.sharepoint.com/teams/TeamContoso", 

            "scopes": [ 

                "personal" 

            ] 

        } 

    ], 

    "permissions": [ 

        "identity", 

        "messageTeamMembers" 

    ], 

    "validDomains": [ 

        "contoso.sharepoint.com" 

    ], 

    "webApplicationInfo": { 

        "id": "00000003-0000-0ff1-ce00-000000000000", 

        "resource": "https://contoso.sharepoint.com" 

    } 

}
```