---
title: Crear una aplicación de portal de intranet de Teams desde un sitio o una página de SharePoint Online
author: cichur
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
ms.reviewer: vinbel
search.appverid: MET150
description: Elija un sitio o una página de SharePoint Online ya existente y cree una pestaña estática independiente que se pueda usar como portal de intranet de su organización.
localization_priority: Priority
ms.openlocfilehash: 080adc58059a88e585f5c975972399e552640e3d
ms.sourcegitcommit: b12ec4703b164c545d17b02815edd6ee28d40bed
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49923812"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a><span data-ttu-id="1098a-103">Crear una aplicación de portal de intranet de Teams desde un sitio o una página de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1098a-103">Create a Teams 'Intranet Portal app' from a SharePoint Online site or page</span></span>

<span data-ttu-id="1098a-104">Siga los pasos de este artículo para crear una aplicación independiente y estática en Teams que se vincule al sitio de intranet de su organización.</span><span class="sxs-lookup"><span data-stu-id="1098a-104">Use the steps in this article to create a standalone and static app inside of Teams that links to the intranet site for your org.</span></span>

<span data-ttu-id="1098a-105">Se creará una *Aplicación personal de Teams* del sitio de intranet de SharePoint y se mostrará como una pestaña dentro de Teams.</span><span class="sxs-lookup"><span data-stu-id="1098a-105">A *Teams Personal App* of your SharePoint intranet site is created, and will appear as a tab inside of Teams.</span></span> <span data-ttu-id="1098a-106">Esta pestaña puede contener información importante para todos los usuarios de Teams.</span><span class="sxs-lookup"><span data-stu-id="1098a-106">This tab can contain information important to all your Teams users.</span></span> <span data-ttu-id="1098a-107">Es una forma rápida y cómoda de que los usuarios de Teams tengan acceso a las actualizaciones con tan solo un clic en una pestaña.</span><span class="sxs-lookup"><span data-stu-id="1098a-107">It is a quick and convenient way for Teams users to access updates just a tab click away.</span></span>

<span data-ttu-id="1098a-108">Tenga en cuenta que el proceso que se muestra **debe usar** un sitio o una página de SharePoint *modernos* para funcionar.</span><span class="sxs-lookup"><span data-stu-id="1098a-108">Be aware that the process shown **must use** a *modern* SharePoint site or page to work.</span></span> <span data-ttu-id="1098a-109">Este proceso no está disponible para páginas y sitios *clásicos*.</span><span class="sxs-lookup"><span data-stu-id="1098a-109">This process is not available for *classical* sites or pages.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1098a-110">Asegúrese de que la carga lateral de aplicaciones de Teams está habilitada para su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="1098a-110">Make certain that side-loading of Teams apps is enabled for your tenant.</span></span> <span data-ttu-id="1098a-111">Según lo avanzado que se encuentre el proceso de migración del portal de administración de Teams, es posible que tenga que habilitarlo en Teams > Administrador o, en la versión anterior del portal, en Administrador > Configuración > Servicios y complementos > Microsoft Teams > Aplicaciones > Aplicaciones externas.</span><span class="sxs-lookup"><span data-stu-id="1098a-111">Depending on where you are in the migration process of the Teams Admin portal, you might need to enable it either under Teams > Admin, or under Admin > Settings > Services and Add-ins > Microsoft Teams > Apps > External Apps, in the previous version of the portal!</span></span>

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a><span data-ttu-id="1098a-112">Usar App Studio para crear una aplicación independiente de SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="1098a-112">Use App Studio to create your standalone SharePoint Online app</span></span>

<span data-ttu-id="1098a-113">Antes de empezar:</span><span class="sxs-lookup"><span data-stu-id="1098a-113">Before you begin:</span></span>

1. <span data-ttu-id="1098a-114">Tendrá que conocer la dirección URL de un sitio o una página de grupo o de comunicación de SharePoint Online moderno.</span><span class="sxs-lookup"><span data-stu-id="1098a-114">You'll need to know the URL of a SharePoint Online modern Communication or Team site, or page.</span></span>
    - <span data-ttu-id="1098a-115">Estos sitios siempre incluirán */teams/* o */sites/* en sus rutas de acceso.</span><span class="sxs-lookup"><span data-stu-id="1098a-115">These sites will always have either */teams/* or */sites/* in their paths.</span></span>

2. <span data-ttu-id="1098a-116">Tendrá que conocer el subdominio de su espacio empresarial, que se usará en el marcador de posición **{{subdomain}}**.</span><span class="sxs-lookup"><span data-stu-id="1098a-116">You'll need to know your tenant's subdomain, which will be used in the placeholder **{{subdomain}}**.</span></span>

3. <span data-ttu-id="1098a-117">Este artículo usará el marcador de posición **{{siteUrl}}** para la *dirección URL* del sitio o la página que haya elegido.</span><span class="sxs-lookup"><span data-stu-id="1098a-117">This article will use **{{siteUrl}}** as a placeholder for the *URL* of the site or page you chose.</span></span>
    - <span data-ttu-id="1098a-118">Ejemplo de *direcciones URL*: `https://contoso.sharepoint.com/teams/Contoso`</span><span class="sxs-lookup"><span data-stu-id="1098a-118">Example *URLs*: `https://contoso.sharepoint.com/teams/Contoso`</span></span>
        <span data-ttu-id="1098a-119">*o* `https://contoso.sharepoint.com/sites/Contoso`</span><span class="sxs-lookup"><span data-stu-id="1098a-119">*or* `https://contoso.sharepoint.com/sites/Contoso`</span></span>
4. <span data-ttu-id="1098a-120">Además, se usará **{{sitePath}}** para indicar la *ruta de acceso* de la dirección URL (ej.: /teams/Contoso).</span><span class="sxs-lookup"><span data-stu-id="1098a-120">Also, **{{sitePath}}** will be used to denote the *path* of the URL (ex: /teams/Contoso).</span></span>
    - <span data-ttu-id="1098a-121">Ejemplo de *rutas de acceso*:   /teams/Contoso   *o* /sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="1098a-121">Example *paths*:   /teams/Contoso   *or* /sites/Contoso</span></span>

<span data-ttu-id="1098a-122">En primer lugar, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="1098a-122">Begin by following the steps below:</span></span>

1. <span data-ttu-id="1098a-123">Vaya a la tienda de Teams.</span><span class="sxs-lookup"><span data-stu-id="1098a-123">Go to the Teams Store.</span></span>

2. <span data-ttu-id="1098a-124">Instale o abra App Studio.</span><span class="sxs-lookup"><span data-stu-id="1098a-124">Install or open App Studio.</span></span>

3. <span data-ttu-id="1098a-125">Haga clic en **Abrir**, junto a la opción Aplicación.</span><span class="sxs-lookup"><span data-stu-id="1098a-125">Click **Open**, next to the App option.</span></span>

4. <span data-ttu-id="1098a-126">Con App Studio abierto, haga clic en **Editor de manifiestos**.</span><span class="sxs-lookup"><span data-stu-id="1098a-126">With App Studio open, click on **Manifest Editor**.</span></span>

5. <span data-ttu-id="1098a-127">**Cree una nueva aplicación**.</span><span class="sxs-lookup"><span data-stu-id="1098a-127">**Create a new app**.</span></span>

6. <span data-ttu-id="1098a-128">Rellene todos los **Detalles de la aplicación**.</span><span class="sxs-lookup"><span data-stu-id="1098a-128">Fill in all **App Details**.</span></span>

7. <span data-ttu-id="1098a-129">Haga clic en **Pestañas** en Capacidades.</span><span class="sxs-lookup"><span data-stu-id="1098a-129">Click on **Tabs** under Capabilities.</span></span>

8. <span data-ttu-id="1098a-130">Haga clic en **Agregar** en la Pestaña personal.</span><span class="sxs-lookup"><span data-stu-id="1098a-130">Click **Add** under Personal Tab.</span></span>

9. <span data-ttu-id="1098a-131">Rellene el **Nombre** y elija **un identificador de entidad único nuevo**.</span><span class="sxs-lookup"><span data-stu-id="1098a-131">Fill in the **Name** and choose **a new unique Entity ID**.</span></span>

10. <span data-ttu-id="1098a-132">Rellene **contentURL y la dirección URL del sitio web**.</span><span class="sxs-lookup"><span data-stu-id="1098a-132">Fill in the **contentURL and Website URL**.</span></span>

- <span data-ttu-id="1098a-133">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span><span class="sxs-lookup"><span data-stu-id="1098a-133">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span></span>  
- <span data-ttu-id="1098a-134">**websiteUrl**: {{siteUrl}}</span><span class="sxs-lookup"><span data-stu-id="1098a-134">**websiteUrl**: {{siteUrl}}</span></span>

    <span data-ttu-id="1098a-135">Ejemplo de **contentURL**: `https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub`</span><span class="sxs-lookup"><span data-stu-id="1098a-135">Example **contentURL**: `https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub`</span></span>

11. <span data-ttu-id="1098a-136">Desplácese hasta **Dominios y permisos**.</span><span class="sxs-lookup"><span data-stu-id="1098a-136">Navigate to **Domains and Permissions**.</span></span> <span data-ttu-id="1098a-137">Asegúrese de que la sección dominios válidos contiene el nombre de dominio de SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1098a-137">Make sure the valid domains section contains your SharePoint online domain name.</span></span>

    <span data-ttu-id="1098a-138">Ejemplo: `contoso.sharepoint.com`</span><span class="sxs-lookup"><span data-stu-id="1098a-138">Example: `contoso.sharepoint.com`</span></span>

12. <span data-ttu-id="1098a-139">Agregue las siguientes propiedades de **inicio de sesión único** de la aplicación web:</span><span class="sxs-lookup"><span data-stu-id="1098a-139">Add the following web app **single sign-on** properties:</span></span>

     <span data-ttu-id="1098a-140">Ejemplo:  **Id. de aplicación de AAD**: 00000003-0000-0ff1-ce00-000000000000  **Dirección URL de recurso**: {{subdomain}}.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="1098a-140">Example:  **AAD application ID**: 00000003-0000-0ff1-ce00-000000000000  **Resource Url**: {{subdomain}}.sharepoint.com</span></span>

    ![Realice el inicio de sesión único de la aplicación web, con id. y dirección URL.](media/personal-app.png)

13. <span data-ttu-id="1098a-142">**Guarde** estas propiedades y, luego, desplácese hasta **Probar y distribuir**.</span><span class="sxs-lookup"><span data-stu-id="1098a-142">**Save** these properties and then navigate to **Test and distribute**.</span></span>

14. <span data-ttu-id="1098a-143">Instale la aplicación para probar la aplicación personalmente.</span><span class="sxs-lookup"><span data-stu-id="1098a-143">Install the app to test the application personally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1098a-144">Si no usa Teams App Studio, tendrá que comprimir el archivo manifest.JSON que acaba de crear; vaya a la tienda de aplicaciones de Teams y haga clic en el vínculo **cargar aplicación personalizada** (en la parte inferior derecha de la tienda de aplicaciones).</span><span class="sxs-lookup"><span data-stu-id="1098a-144">If you aren't using Teams App Studio, you will have to .zip the manifest.JSON file you just created, navigate to the App Store in Teams, and click  **upload custom app** link (at the bottom right of the App Store).</span></span> <span data-ttu-id="1098a-145">Esto hará que la aplicación esté disponible para usted.</span><span class="sxs-lookup"><span data-stu-id="1098a-145">This will make the app available to you.</span></span>

15. <span data-ttu-id="1098a-146">Ahora la aplicación está disponible como una pestaña estática para que pueda cargarla y verla en Teams.</span><span class="sxs-lookup"><span data-stu-id="1098a-146">Now the app is available as a static tab for you to load and view in Teams.</span></span>

## <a name="test-and-view-your-new-static-tab"></a><span data-ttu-id="1098a-147">Probar y ver la nueva pestaña estática</span><span class="sxs-lookup"><span data-stu-id="1098a-147">Test and view your new static tab</span></span>

<span data-ttu-id="1098a-148">Para ver la nueva pestaña en el escritorio de Teams, desplácese hasta el signo de puntos suspensivos (**...**) en la parte izquierda de la barra de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="1098a-148">To view the new tab on the Teams desktop, navigate to the ellipses (**…**) in the left-hand side of your app bar.</span></span> <span data-ttu-id="1098a-149">Buque la nueva aplicación, cargue y pruebe la aplicación independiente en Teams.</span><span class="sxs-lookup"><span data-stu-id="1098a-149">Find your new app, load it, and test your standalone application in Teams.</span></span>

<span data-ttu-id="1098a-150">Si desea que la nueva aplicación esté disponible en el menú de la izquierda en una posición superior, debe usar una configuración de directiva de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="1098a-150">If you want to make the new app available in the left menu at a higher position, you must use an app policy setting for this.</span></span> <span data-ttu-id="1098a-151">Encontrará esta opción en la sección Administrador de equipo > directiva de aplicaciones > agregar una aplicación anclada.</span><span class="sxs-lookup"><span data-stu-id="1098a-151">This setting can be found under the Team admin section > app policy > add a pinned application.</span></span> <span data-ttu-id="1098a-152">Cuando asigne la directiva a un usuario para realizar pruebas, el cambio se mostrará unas horas más tarde.</span><span class="sxs-lookup"><span data-stu-id="1098a-152">When you assign the policy to a user for testing, the change will appear a few hours later.</span></span> <span data-ttu-id="1098a-153">Teniendo esto en cuenta, decida lo antes posible donde debería aparecer la aplicación para evitar retrasos.</span><span class="sxs-lookup"><span data-stu-id="1098a-153">With this in mind, please decide where the app should appear at your earliest convenience to help avoid delays.</span></span>

<span data-ttu-id="1098a-154">Para ver y probar la nueva aplicación en un dispositivo móvil, abra el cajón de aplicaciones pulsando en la comilla angular (**^**) situada encima de la barra de pestañas de la parte inferior de la pantalla.</span><span class="sxs-lookup"><span data-stu-id="1098a-154">To view and test the new app on a mobile device, open the app drawer by tapping on the chevron (**^**) above the tab bar near the bottom of your screen.</span></span> <span data-ttu-id="1098a-155">Busque la aplicación y desplácese hasta ella en el dispositivo móvil.</span><span class="sxs-lookup"><span data-stu-id="1098a-155">Find your app and navigate to it on your mobile device.</span></span>

## <a name="a-sample-manifestjson-file"></a><span data-ttu-id="1098a-156">Ejemplo de archivo Manifest.JSON</span><span class="sxs-lookup"><span data-stu-id="1098a-156">A Sample Manifest.JSON file</span></span>

<span data-ttu-id="1098a-157">El archivo JSON que genere tendrá un aspecto similar al siguiente.</span><span class="sxs-lookup"><span data-stu-id="1098a-157">The JSON file you generate will look something like the one below.</span></span>

```JSON'
{

    "$schema": "https://developer.microsoft.com/en-us/json-schemas/teams/v1.5/MicrosoftTeams.schema.json",

    "manifestVersion": "1.5",

    "version": "1.0.0",

    "id": "33ebded3-931c-4333-b0c5-b51dd8738873",

    "packageName": "com.contoso.teams.devapp",

    "developer": {

        "name": "Contoso", ''

        "websiteUrl": "https://www.contoso.com",

        "privacyUrl": "https://www.contoso.com/privacy",

        "termsOfUseUrl": "https://www.contoso.com/terms"

    },

    "icons": {

        "color": "color.png",

        "outline": "outline.png"

    },

    "name": {

        "short": "Contoso Intranet", '

        "full": "Intranet Portal for Contoso"

    },

    "des    ription": {

        "short": "Intranet portal for Contoso",

        "full": "This app is to demonstrate the capabilities of hosting a SharePoint communication and team site as a standalone app in Teams"

    },

    "accentColor": "#FFFFFF",

    "staticTabs": [

        {

                     "       nti        Id":       "com    unicat    onSi    eTab",

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
