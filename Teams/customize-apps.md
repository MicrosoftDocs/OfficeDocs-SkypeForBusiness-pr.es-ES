---
title: Personalizar aplicaciones en Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo personalizar aplicaciones en Microsoft Teams.
ms.openlocfilehash: e2a217648abbcec4075e942b303542621f7d317a
ms.sourcegitcommit: f3e9989cbcc2f9f83ff94204bdd75b1e6ad43b5e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2021
ms.locfileid: "53408749"
---
# <a name="customize-apps-in-microsoft-teams"></a><span data-ttu-id="22c46-103">Personalizar aplicaciones en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="22c46-103">Customize apps in Microsoft Teams</span></span>

 <span data-ttu-id="22c46-104">Microsoft Teams personalización de aplicaciones para mejorar Teams experiencia.</span><span class="sxs-lookup"><span data-stu-id="22c46-104">Microsoft Teams provides app customization to enhance the Teams experience.</span></span> <span data-ttu-id="22c46-105">Algunos desarrolladores de aplicaciones permiten que el administrador de aplicaciones personalizó una aplicación Teams aplicación. El administrador puede personalizar o cambiar el nombre de las propiedades de la aplicación en función de las necesidades de la **organización** mediante la página Administrar aplicaciones Teams centro de administración.</span><span class="sxs-lookup"><span data-stu-id="22c46-105">Some app developers allow an app to be customized by the Teams admin. The admin can customize or rebrand the app properties based on the organizational needs using the Teams admin center **Manage apps** page.</span></span> <span data-ttu-id="22c46-106">Los detalles que puede personalizar son:</span><span class="sxs-lookup"><span data-stu-id="22c46-106">The details you can customize are:</span></span>

- <span data-ttu-id="22c46-107">Nombre corto</span><span class="sxs-lookup"><span data-stu-id="22c46-107">Short name</span></span>
- <span data-ttu-id="22c46-108">Descripción breve</span><span class="sxs-lookup"><span data-stu-id="22c46-108">Short description</span></span>
- <span data-ttu-id="22c46-109">Descripción completa</span><span class="sxs-lookup"><span data-stu-id="22c46-109">Full description</span></span>
- <span data-ttu-id="22c46-110">Dirección URL de la directiva de privacidad</span><span class="sxs-lookup"><span data-stu-id="22c46-110">Privacy policy URL</span></span>
- <span data-ttu-id="22c46-111">Url del sitio web</span><span class="sxs-lookup"><span data-stu-id="22c46-111">Website URL</span></span>
- <span data-ttu-id="22c46-112">Url de términos de uso</span><span class="sxs-lookup"><span data-stu-id="22c46-112">Terms of use URL</span></span>
- <span data-ttu-id="22c46-113">Icono de color</span><span class="sxs-lookup"><span data-stu-id="22c46-113">Color icon</span></span>
- <span data-ttu-id="22c46-114">Icono Esquema</span><span class="sxs-lookup"><span data-stu-id="22c46-114">Outline icon</span></span>
- <span data-ttu-id="22c46-115">Color de énfeño</span><span class="sxs-lookup"><span data-stu-id="22c46-115">Accent color</span></span>

<span data-ttu-id="22c46-116">Vea el [Teams de manifiesto para](/microsoftteams/platform/resources/schema/manifest-schema) obtener más información sobre los campos que puede personalizar.</span><span class="sxs-lookup"><span data-stu-id="22c46-116">See the [Teams Manifest schema](/microsoftteams/platform/resources/schema/manifest-schema) for details about the fields that you can customize.</span></span>

> [!NOTE]
> <span data-ttu-id="22c46-117">La personalización de aplicaciones no es compatible con Government Community Cloud High (GCCH) o department of defense (DoD) en este momento.</span><span class="sxs-lookup"><span data-stu-id="22c46-117">Customizing apps isn't supported in Government Community Cloud High (GCCH) or Department of Defense (DoD) at this time.</span></span>
> <span data-ttu-id="22c46-118">Actualmente, esta característica no está disponible para las aplicaciones Microsoft Teams carga lateral.</span><span class="sxs-lookup"><span data-stu-id="22c46-118">Currently, this feature is not available for sideloaded Microsoft Teams apps.</span></span>

## <a name="customize-the-apps-details"></a><span data-ttu-id="22c46-119">Personalizar los detalles de la aplicación</span><span class="sxs-lookup"><span data-stu-id="22c46-119">Customize the app's details</span></span>

<span data-ttu-id="22c46-120">Para empezar a personalizar una aplicación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="22c46-120">To start customizing an app, complete the following steps:</span></span>

1. <span data-ttu-id="22c46-121">Inicie la sesión en el Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="22c46-121">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="22c46-122">Expanda **Teams aplicaciones y** seleccione Administrar **aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="22c46-122">Expand **Teams Apps** and select **Manage apps**.</span></span>
3. <span data-ttu-id="22c46-123">Compruebe la **columna Personalizable** de la lista de aplicaciones y ordene por aplicaciones que se pueden personalizar.</span><span class="sxs-lookup"><span data-stu-id="22c46-123">Check the **Customizable** column of the apps list and sort by apps that are customizable.</span></span>

   ![La columna personalizar que está ordenada](media/customize-column.png)

   <span data-ttu-id="22c46-125">Hay tres puntos de entrada para acceder a la característica de personalización:</span><span class="sxs-lookup"><span data-stu-id="22c46-125">There are three entry points to access the customize feature:</span></span>

   - <span data-ttu-id="22c46-126">Seleccione junto a la aplicación que desea personalizar y, a continuación, seleccione **Personalizar**.</span><span class="sxs-lookup"><span data-stu-id="22c46-126">Select next to the app that you want to customize, and then select **Customize**.</span></span>

     ![La opción de selección personalizar 1](media/select-app-to-customize1.png)

   - <span data-ttu-id="22c46-128">Seleccione el nombre de la aplicación y, a continuación, **Personalizable.**</span><span class="sxs-lookup"><span data-stu-id="22c46-128">Select the app name and then **Customizable**.</span></span>

     ![La opción de selección personalizar 2](media/app-details-customizable.png)

   - <span data-ttu-id="22c46-130">Seleccione el nombre de la aplicación y, a continuación, **seleccione Personalizar en** el **menú** desplegable Acciones.</span><span class="sxs-lookup"><span data-stu-id="22c46-130">Select the app name, and then select **Customize** from the **Actions** dropdown.</span></span>

     ![La opción de selección personalizar 3](media/customize-action-menu.png)

4. <span data-ttu-id="22c46-132">Expanda la **sección Detalles** y personalice los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="22c46-132">Expand the **Details** section and customize the following fields:</span></span>

    - <span data-ttu-id="22c46-133">Nombre corto</span><span class="sxs-lookup"><span data-stu-id="22c46-133">Short name</span></span>
    - <span data-ttu-id="22c46-134">Descripción breve</span><span class="sxs-lookup"><span data-stu-id="22c46-134">Short description</span></span>
    - <span data-ttu-id="22c46-135">Descripción completa</span><span class="sxs-lookup"><span data-stu-id="22c46-135">Full description</span></span>
    - <span data-ttu-id="22c46-136">Sitio web</span><span class="sxs-lookup"><span data-stu-id="22c46-136">Website</span></span>
    - <span data-ttu-id="22c46-137">Dirección URL de la directiva de privacidad</span><span class="sxs-lookup"><span data-stu-id="22c46-137">Privacy policy URL</span></span>
    - <span data-ttu-id="22c46-138">Url de términos de uso</span><span class="sxs-lookup"><span data-stu-id="22c46-138">Terms of use URL</span></span>

   ![La configuración de personalización](media/customize-settings.png)

> [!Note]
> <span data-ttu-id="22c46-140">Solo estarán visibles los campos que el desarrollador de aplicaciones haya asignado como personalizables.</span><span class="sxs-lookup"><span data-stu-id="22c46-140">Only the fields that the app developer has assigned as customizable will be visible.</span></span>

5. <span data-ttu-id="22c46-141">Expanda la **sección Icono.**</span><span class="sxs-lookup"><span data-stu-id="22c46-141">Expand the **Icon** section.</span></span>

   <span data-ttu-id="22c46-142">a.</span><span class="sxs-lookup"><span data-stu-id="22c46-142">a.</span></span> <span data-ttu-id="22c46-143">Upload un icono.</span><span class="sxs-lookup"><span data-stu-id="22c46-143">Upload an icon.</span></span> <span data-ttu-id="22c46-144">Use un icono de color completo (192x192) píxel en formato PNG.</span><span class="sxs-lookup"><span data-stu-id="22c46-144">Use one full-color icon (192x192) pixel in PNG format.</span></span>

   <span data-ttu-id="22c46-145">b.</span><span class="sxs-lookup"><span data-stu-id="22c46-145">b.</span></span> <span data-ttu-id="22c46-146">Elija un color de contorno de icono.</span><span class="sxs-lookup"><span data-stu-id="22c46-146">Choose an icon outline color.</span></span> <span data-ttu-id="22c46-147">Use un píxel de contorno transparente (32x32) en formato PNG.</span><span class="sxs-lookup"><span data-stu-id="22c46-147">Use one transparent outline (32x32) pixel in PNG format.</span></span>

   <span data-ttu-id="22c46-148">c.</span><span class="sxs-lookup"><span data-stu-id="22c46-148">c.</span></span> <span data-ttu-id="22c46-149">Seleccione un color de acento de aplicación que coincida con el icono.</span><span class="sxs-lookup"><span data-stu-id="22c46-149">Select an app accent color that matches the icon.</span></span>

    ![Personalizar las opciones de color del panel de iconos](media/customize-app-colors.png)

6. <span data-ttu-id="22c46-151">Una vez que la aplicación se haya personalizado, seleccione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="22c46-151">Once your app has been customized, select **Apply**.</span></span>

7. <span data-ttu-id="22c46-152">Seleccione **Publicar** para publicar la aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="22c46-152">Select **Publish** to publish the customized app.</span></span>

   <span data-ttu-id="22c46-153">La aplicación personalizada ahora aparece en la **página Administrar aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="22c46-153">The customized app is now listed in your **Manage apps** page.</span></span> <span data-ttu-id="22c46-154">Solo tendrá una versión de la aplicación, ya que personalizar las características de la aplicación no crea una copia de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="22c46-154">You'll have only one version of the app, since customizing the app features doesn't create a copy of the app.</span></span>

<span data-ttu-id="22c46-155">Ahora, Teams usuarios finales pueden abrir su Teams cliente para ver la aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="22c46-155">Now your Teams end users can open their Teams client to see the customized app.</span></span>

   ![Aplicación personalizada en Teams cliente](media/contoso-app.png)

### <a name="special-considerations-for-customizing-an-app"></a><span data-ttu-id="22c46-157">Consideraciones especiales para personalizar una aplicación</span><span class="sxs-lookup"><span data-stu-id="22c46-157">Special considerations for customizing an app</span></span>

<span data-ttu-id="22c46-158">La siguiente nota incluye detalles importantes sobre cómo personalizar una aplicación.</span><span class="sxs-lookup"><span data-stu-id="22c46-158">The following note includes important details about customizing an app.</span></span>

> [!Note]
> - <span data-ttu-id="22c46-159">Cuando personalice las aplicaciones y cualquier descripción relacionada con una aplicación, asegúrese de que sigue las directrices de personalización si lo proporciona el editor de aplicaciones en su documentación o términos de uso.</span><span class="sxs-lookup"><span data-stu-id="22c46-159">When you customize apps, and any description related to an app, ensure that you follow any customization guidelines if provided by the app publisher in their documentation or terms of use.</span></span> <span data-ttu-id="22c46-160">También es responsable de respetar los derechos de otras personas con respecto a las imágenes de terceros que pueda usar.</span><span class="sxs-lookup"><span data-stu-id="22c46-160">You're also responsible for respecting the rights of others regarding any third-party images you might use.</span></span>
> - <span data-ttu-id="22c46-161">Los datos de personalización proporcionados por el administrador se almacenan en la región más cercana.</span><span class="sxs-lookup"><span data-stu-id="22c46-161">Admin-provided customization data is stored in the nearest region.</span></span>
> - <span data-ttu-id="22c46-162">Usted es responsable de garantizar que los vínculos a términos de uso o a la política de privacidad sean válidos.</span><span class="sxs-lookup"><span data-stu-id="22c46-162">You are responsible for ensuring that links to terms of use or privacy policy are valid.</span></span>
> - <span data-ttu-id="22c46-163">En caso de que el editor de aplicaciones ya no permita que se pueda personalizar un campo, aparecerá un mensaje en la página de detalles de la aplicación en el que se notificará al administrador sobre los campos que ya no se pueden personalizar.</span><span class="sxs-lookup"><span data-stu-id="22c46-163">In case the app publisher no longer allows a field to be customizable, a message appears on the app details page notifying the admin about the fields that can't be customized any longer.</span></span> <span data-ttu-id="22c46-164">Todos los cambios realizados en ese campo se revertirán a los valores originales.</span><span class="sxs-lookup"><span data-stu-id="22c46-164">All the changes made to that field will be reverted to the original values.</span></span>
> - <span data-ttu-id="22c46-165">Se recomienda probar los cambios de personalización de aplicaciones Teams inquilino de prueba antes de realizar estos cambios en el entorno de producción.</span><span class="sxs-lookup"><span data-stu-id="22c46-165">We recommend testing app customization changes in a Teams test tenant before making these changes in your production environment.</span></span>
> - <span data-ttu-id="22c46-166">Los cambios en la personal de marca pueden requerir hasta 24 horas para que los usuarios vean los cambios.</span><span class="sxs-lookup"><span data-stu-id="22c46-166">Changes to branding might require up to 24 hours for the users to see the changes.</span></span>

## <a name="review-app-details"></a><span data-ttu-id="22c46-167">Revisar detalles de la aplicación</span><span class="sxs-lookup"><span data-stu-id="22c46-167">Review app details</span></span>

<span data-ttu-id="22c46-168">Es posible que quiera ver los detalles de la aplicación para revisar la información.</span><span class="sxs-lookup"><span data-stu-id="22c46-168">You might want to see the app details to review the information.</span></span>

1. <span data-ttu-id="22c46-169">Inicie la sesión en el Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="22c46-169">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="22c46-170">Expanda **aplicación de Teams** y seleccione **Administrar aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="22c46-170">Expand **Teams apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="22c46-171">Seleccione el nombre de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="22c46-171">Select the app name.</span></span>

4. <span data-ttu-id="22c46-172">Ver los detalles de la aplicación, incluido el nombre original de la aplicación **Nombre corto del editor.**</span><span class="sxs-lookup"><span data-stu-id="22c46-172">View the app details, including the original app name **Short name from publisher**.</span></span>

   ![Personalizar el nombre de la aplicación del panel de iconos](media/original-app-version.png)

   <span data-ttu-id="22c46-174">El **campo Nombre corto del editor** solo está visible si ha cambiado el nombre corto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="22c46-174">The **Short name from publisher** field is only visible if you've changed the app's short name.</span></span>

## <a name="reset-app-details-to-default"></a><span data-ttu-id="22c46-175">Restablecer los detalles de la aplicación de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="22c46-175">Reset app details to default</span></span>

<span data-ttu-id="22c46-176">En cualquier momento, puede restablecer los detalles de la aplicación a la configuración original.</span><span class="sxs-lookup"><span data-stu-id="22c46-176">At any time, you can reset the app details to the original settings.</span></span>

1. <span data-ttu-id="22c46-177">Inicie la sesión en el Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="22c46-177">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="22c46-178">Expanda **Teams aplicaciones y** seleccione Administrar **aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="22c46-178">Expand **Teams Apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="22c46-179">Seleccione el nombre de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="22c46-179">Select the app name.</span></span>

4. <span data-ttu-id="22c46-180">Seleccione **Restablecer de forma predeterminada** en el menú **desplegable** Acciones.</span><span class="sxs-lookup"><span data-stu-id="22c46-180">Select **Reset to default** from the **Actions** dropdown.</span></span>

   ![Seleccionar restablecer como resaltado predeterminado](media/select-reset.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="22c46-182">Preguntas frecuentes</span><span class="sxs-lookup"><span data-stu-id="22c46-182">Frequently asked questions</span></span>

<span data-ttu-id="22c46-183">**¿Cuánto tiempo tardarán mis usuarios en ver la aplicación personalizada?**</span><span class="sxs-lookup"><span data-stu-id="22c46-183">**How long will it take for my users to see the customized app?**</span></span>

<span data-ttu-id="22c46-184">Aunque el administrador puede ver inmediatamente los cambios en el Centro de administración de Teams, los usuarios finales pueden tardar hasta 24 horas en ver los cambios.</span><span class="sxs-lookup"><span data-stu-id="22c46-184">Although the admin can immediately see the changes in Teams Admin Center, it might take up to 24 hours for the end users to see the changes.</span></span>  

<span data-ttu-id="22c46-185">**¿Puede el proveedor de aplicaciones personalizar la aplicación para sus clientes?**</span><span class="sxs-lookup"><span data-stu-id="22c46-185">**Can the app provider customize the app for its customers?**</span></span>

 <span data-ttu-id="22c46-186">No, el administrador de un inquilino debe personalizar la aplicación para su inquilino mediante el Centro de Teams de administración.</span><span class="sxs-lookup"><span data-stu-id="22c46-186">No, the admin of a tenant needs to customize the app for their tenant using the Teams Admin Center.</span></span>

<span data-ttu-id="22c46-187">**¿Se implementará automáticamente la aplicación personalizada para reemplazar mi aplicación personalizada actual en un espacio empresarial?**</span><span class="sxs-lookup"><span data-stu-id="22c46-187">**Will the customized app automatically get deployed to replace my current custom app in a tenant?**</span></span>

<span data-ttu-id="22c46-188">No, los administradores de inquilinos tendrán que quitar manualmente cualquier aplicación personalizada y publicar la versión personalizada de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="22c46-188">No, the tenant admins will have to manually remove any custom app and publish the customized version of the app.</span></span> <span data-ttu-id="22c46-189">Si ha personalizado una aplicación y la ha publicado como una aplicación personalizada, la nueva aplicación personalizada con la característica de personalización de la aplicación no reemplazará a la aplicación personalizada actual.</span><span class="sxs-lookup"><span data-stu-id="22c46-189">If you have customized an app and published it as a custom app, the new app customized using the app customization feature won't replace the current custom app.</span></span>  

<span data-ttu-id="22c46-190">**¿El informe de uso de la aplicación también mostrará los valores personalizados, como el nombre corto personalizado?**</span><span class="sxs-lookup"><span data-stu-id="22c46-190">**Will the app usage report also show the customized values such as customized short name?**</span></span>

 <span data-ttu-id="22c46-191">No, el informe de uso de la aplicación seguirá mostrándo el nombre original de la aplicación enviada desde el editor.</span><span class="sxs-lookup"><span data-stu-id="22c46-191">No, the app usage report will still show the original name of the app sent from the publisher.</span></span>

<span data-ttu-id="22c46-192">**¿Qué aplicaciones puedo personalizar con la característica de personalización de aplicaciones?**</span><span class="sxs-lookup"><span data-stu-id="22c46-192">**Which apps can I customize using the app customization feature?**</span></span>

<span data-ttu-id="22c46-193">Solo puede personalizar las aplicaciones que el editor de aplicaciones ha permitido personalizar.</span><span class="sxs-lookup"><span data-stu-id="22c46-193">You can only customize apps that have been allowed to be customizable by the app publisher.</span></span> <span data-ttu-id="22c46-194">El editor de aplicaciones tendrá que participar para permitir a sus clientes personalizar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="22c46-194">The app publisher will need to opt in to allow its customers to customize the app.</span></span>

<span data-ttu-id="22c46-195">**¿Aparecerán las propiedades personalizadas en la pantalla de consentimiento de permisos de gráfico?**</span><span class="sxs-lookup"><span data-stu-id="22c46-195">**Will the customized properties show up on the graph permission consent screen?**</span></span>

<span data-ttu-id="22c46-196">No, la pantalla de consentimiento de permisos seguirá mostrándo el valor original enviado por el editor.</span><span class="sxs-lookup"><span data-stu-id="22c46-196">No, the permission consent screen will still show the original value sent by the publisher.</span></span>

## <a name="related-article"></a><span data-ttu-id="22c46-197">Artículo relacionado</span><span class="sxs-lookup"><span data-stu-id="22c46-197">Related article</span></span>

- [<span data-ttu-id="22c46-198">Administrar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="22c46-198">Manage apps</span></span>](manage-apps.md)
- [<span data-ttu-id="22c46-199">Personalizar la tienda de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="22c46-199">Customize your app store</span></span>](customize-your-app-store.md)
- [<span data-ttu-id="22c46-200">Cambiar el nombre de las aplicaciones</span><span class="sxs-lookup"><span data-stu-id="22c46-200">Rebrand your apps</span></span>](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
