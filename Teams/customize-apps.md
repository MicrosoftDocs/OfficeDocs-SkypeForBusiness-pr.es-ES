---
title: Personalizar aplicaciones de Microsoft en Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: vaagarw
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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a87ce5f7dd63a78af4a7a1ea5f56aed1cad7263a
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574159"
---
# <a name="customize-apps-in-microsoft-teams"></a><span data-ttu-id="f27df-103">Personalizar aplicaciones en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f27df-103">Customize apps in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

 <span data-ttu-id="f27df-104">Microsoft Teams proporciona personalización de aplicaciones para mejorar la experiencia de Teams.</span><span class="sxs-lookup"><span data-stu-id="f27df-104">Microsoft Teams provides app customization to enhance the Teams experience.</span></span> <span data-ttu-id="f27df-105">Algunos desarrolladores de aplicaciones permiten que el administrador de Teams personalizó una aplicación. El administrador puede personalizar o cambiar el nombre de las propiedades de la aplicación en función de las necesidades de la organización con la página Administrar aplicaciones del Centro de administración **de** Teams.</span><span class="sxs-lookup"><span data-stu-id="f27df-105">Some app developers allow an app to be customized by the Teams admin. The admin can customize or rebrand the app properties based on the organizational needs using the Teams admin center **Manage apps** page.</span></span> <span data-ttu-id="f27df-106">Los detalles que puede personalizar son:</span><span class="sxs-lookup"><span data-stu-id="f27df-106">The details you can customize are:</span></span>

- <span data-ttu-id="f27df-107">Nombre corto</span><span class="sxs-lookup"><span data-stu-id="f27df-107">Short name</span></span>
- <span data-ttu-id="f27df-108">Descripción breve</span><span class="sxs-lookup"><span data-stu-id="f27df-108">Short description</span></span>
- <span data-ttu-id="f27df-109">Descripción completa</span><span class="sxs-lookup"><span data-stu-id="f27df-109">Full description</span></span>
- <span data-ttu-id="f27df-110">Dirección URL de la directiva de privacidad</span><span class="sxs-lookup"><span data-stu-id="f27df-110">Privacy policy URL</span></span>
- <span data-ttu-id="f27df-111">Url del sitio web</span><span class="sxs-lookup"><span data-stu-id="f27df-111">Website URL</span></span>
- <span data-ttu-id="f27df-112">Url de términos de uso</span><span class="sxs-lookup"><span data-stu-id="f27df-112">Terms of use URL</span></span>
- <span data-ttu-id="f27df-113">Icono de color</span><span class="sxs-lookup"><span data-stu-id="f27df-113">Color icon</span></span>
- <span data-ttu-id="f27df-114">Icono Esquema</span><span class="sxs-lookup"><span data-stu-id="f27df-114">Outline icon</span></span>
- <span data-ttu-id="f27df-115">Color de énfeño</span><span class="sxs-lookup"><span data-stu-id="f27df-115">Accent color</span></span>

<span data-ttu-id="f27df-116">Vea el [esquema Manifiesto de Teams](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema) para obtener más información sobre los campos que puede personalizar.</span><span class="sxs-lookup"><span data-stu-id="f27df-116">See the [Teams Manifest schema](https://docs.microsoft.com/microsoftteams/platform/resources/schema/manifest-schema) for details about the fields that you can customize.</span></span>

## <a name="customize-the-apps-details"></a><span data-ttu-id="f27df-117">Personalizar los detalles de la aplicación</span><span class="sxs-lookup"><span data-stu-id="f27df-117">Customize the app's details</span></span>

<span data-ttu-id="f27df-118">Para empezar a personalizar una aplicación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="f27df-118">To start customizing an app, complete the following steps:</span></span>

1. <span data-ttu-id="f27df-119">Inicie la sesión en el Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="f27df-119">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="f27df-120">Expanda **Aplicaciones de Teams** y seleccione Administrar **aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="f27df-120">Expand **Teams Apps** and select **Manage apps**.</span></span>
3. <span data-ttu-id="f27df-121">Compruebe la **columna Personalizable** de la lista de aplicaciones y ordene por aplicaciones que se pueden personalizar.</span><span class="sxs-lookup"><span data-stu-id="f27df-121">Check the **Customizable** column of the apps list and sort by apps that are customizable.</span></span>

   ![La columna personalizar que está ordenada](media/customize-column.png)

   <span data-ttu-id="f27df-123">Hay tres puntos de entrada para acceder a la característica de personalización:</span><span class="sxs-lookup"><span data-stu-id="f27df-123">There are three entry points to access the customize feature:</span></span>

   - <span data-ttu-id="f27df-124">Seleccione junto a la aplicación que desea personalizar y, a continuación, seleccione **Personalizar**.</span><span class="sxs-lookup"><span data-stu-id="f27df-124">Select next to the app that you want to customize, and then select **Customize**.</span></span>

     ![La opción de selección personalizar 1](media/select-app-to-customize1.png)

   - <span data-ttu-id="f27df-126">Seleccione el nombre de la aplicación y, a continuación, **Personalizable.**</span><span class="sxs-lookup"><span data-stu-id="f27df-126">Select the app name and then **Customizable**.</span></span>

     ![La opción de selección personalizar 2](media/app-details-customizable.png)

   - <span data-ttu-id="f27df-128">Seleccione el nombre de la aplicación y, a continuación, **seleccione Personalizar en** el **menú** desplegable Acciones.</span><span class="sxs-lookup"><span data-stu-id="f27df-128">Select the app name, and then select **Customize** from the **Actions** dropdown.</span></span>

     ![La opción de selección personalizar 3](media/customize-action-menu.png)

4. <span data-ttu-id="f27df-130">Expanda la **sección Detalles** y personalice los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="f27df-130">Expand the **Details** section and customize the following fields:</span></span>

    - <span data-ttu-id="f27df-131">Nombre corto</span><span class="sxs-lookup"><span data-stu-id="f27df-131">Short name</span></span>
    - <span data-ttu-id="f27df-132">Descripción breve</span><span class="sxs-lookup"><span data-stu-id="f27df-132">Short description</span></span>
    - <span data-ttu-id="f27df-133">Descripción completa</span><span class="sxs-lookup"><span data-stu-id="f27df-133">Full description</span></span>
    - <span data-ttu-id="f27df-134">Sitio web</span><span class="sxs-lookup"><span data-stu-id="f27df-134">Website</span></span>
    - <span data-ttu-id="f27df-135">Dirección URL de la directiva de privacidad</span><span class="sxs-lookup"><span data-stu-id="f27df-135">Privacy policy URL</span></span>
    - <span data-ttu-id="f27df-136">Url de términos de uso</span><span class="sxs-lookup"><span data-stu-id="f27df-136">Terms of use URL</span></span>

   ![La configuración de personalización](media/customize-settings.png)

> [!Note]
> <span data-ttu-id="f27df-138">Solo estarán visibles los campos que el desarrollador de aplicaciones haya asignado como personalizables.</span><span class="sxs-lookup"><span data-stu-id="f27df-138">Only the fields that the app developer has assigned as customizable will be visible.</span></span>

5. <span data-ttu-id="f27df-139">Expanda la **sección Icono.**</span><span class="sxs-lookup"><span data-stu-id="f27df-139">Expand the **Icon** section.</span></span>

   <span data-ttu-id="f27df-140">a.</span><span class="sxs-lookup"><span data-stu-id="f27df-140">a.</span></span> <span data-ttu-id="f27df-141">Cargar un icono.</span><span class="sxs-lookup"><span data-stu-id="f27df-141">Upload an icon.</span></span> <span data-ttu-id="f27df-142">Use un icono de color completo (192x192) píxel en formato PNG.</span><span class="sxs-lookup"><span data-stu-id="f27df-142">Use one full-color icon (192x192) pixel in PNG format.</span></span>

   <span data-ttu-id="f27df-143">b.</span><span class="sxs-lookup"><span data-stu-id="f27df-143">b.</span></span> <span data-ttu-id="f27df-144">Elija un color de contorno de icono.</span><span class="sxs-lookup"><span data-stu-id="f27df-144">Choose an icon outline color.</span></span> <span data-ttu-id="f27df-145">Use un píxel de contorno transparente (32x32) en formato PNG.</span><span class="sxs-lookup"><span data-stu-id="f27df-145">Use one transparent outline (32x32) pixel in PNG format.</span></span>

   <span data-ttu-id="f27df-146">c.</span><span class="sxs-lookup"><span data-stu-id="f27df-146">c.</span></span> <span data-ttu-id="f27df-147">Seleccione un color de acento de aplicación que coincida con el icono.</span><span class="sxs-lookup"><span data-stu-id="f27df-147">Select an app accent color that matches the icon.</span></span>

    ![Personalizar las opciones de color del panel de iconos](media/customize-app-colors.png)

6. <span data-ttu-id="f27df-149">Una vez que la aplicación se haya personalizado, seleccione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="f27df-149">Once your app has been customized, select **Apply**.</span></span>

7. <span data-ttu-id="f27df-150">Seleccione **Publicar** para publicar la aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="f27df-150">Select **Publish** to publish the customized app.</span></span>

   <span data-ttu-id="f27df-151">La aplicación personalizada ahora aparece en la **página Administrar aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="f27df-151">The customized app is now listed in your **Manage apps** page.</span></span> <span data-ttu-id="f27df-152">Solo tendrá una versión de la aplicación, ya que personalizar las características de la aplicación no crea una copia de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f27df-152">You'll have only one version of the app, since customizing the app features doesn't create a copy of the app.</span></span>

<span data-ttu-id="f27df-153">Ahora los usuarios finales de Teams pueden abrir su cliente de Teams para ver la aplicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="f27df-153">Now your Teams end users can open their Teams client to see the customized app.</span></span>

   ![Aplicación personalizada en el cliente de Teams](media/find-customized-app.png)

### <a name="special-considerations-for-customizing-an-app"></a><span data-ttu-id="f27df-155">Consideraciones especiales para personalizar una aplicación</span><span class="sxs-lookup"><span data-stu-id="f27df-155">Special considerations for customizing an app</span></span>

<span data-ttu-id="f27df-156">La siguiente nota incluye detalles importantes sobre cómo personalizar una aplicación.</span><span class="sxs-lookup"><span data-stu-id="f27df-156">The following note includes important details about customizing an app.</span></span>

> [!Note]
> - <span data-ttu-id="f27df-157">Cuando personalice las aplicaciones y cualquier descripción relacionada con una aplicación, asegúrese de que sigue las directrices de personalización si lo proporciona el editor de aplicaciones en su documentación o términos de uso.</span><span class="sxs-lookup"><span data-stu-id="f27df-157">When you customize apps, and any description related to an app, ensure that you follow any customization guidelines if provided by the app publisher in their documentation or terms of use.</span></span> <span data-ttu-id="f27df-158">También es responsable de respetar los derechos de otras personas con respecto a las imágenes de terceros que pueda usar.</span><span class="sxs-lookup"><span data-stu-id="f27df-158">You're also responsible for respecting the rights of others regarding any third-party images you might use.</span></span>
> - <span data-ttu-id="f27df-159">Los datos de personalización proporcionados por el administrador se almacenan en la región más cercana.</span><span class="sxs-lookup"><span data-stu-id="f27df-159">Admin-provided customization data is stored in the nearest region.</span></span>
> - <span data-ttu-id="f27df-160">Usted es responsable de garantizar que los vínculos a términos de uso o a la política de privacidad sean válidos.</span><span class="sxs-lookup"><span data-stu-id="f27df-160">You are responsible for ensuring that links to terms of use or privacy policy are valid.</span></span>
> - <span data-ttu-id="f27df-161">En caso de que el editor de aplicaciones ya no permita que se pueda personalizar un campo, aparecerá un mensaje en la página de detalles de la aplicación en el que se notificará al administrador sobre los campos que ya no se pueden personalizar.</span><span class="sxs-lookup"><span data-stu-id="f27df-161">In case the app publisher no longer allows a field to be customizable, a message appears on the app details page notifying the admin about the fields that can't be customized any longer.</span></span> <span data-ttu-id="f27df-162">Todos los cambios realizados en ese campo se revertirán a los valores originales.</span><span class="sxs-lookup"><span data-stu-id="f27df-162">All the changes made to that field will be reverted to the original values.</span></span>
> - <span data-ttu-id="f27df-163">Los cambios en la personal de marca pueden requerir hasta 24 horas para que los usuarios vean los cambios.</span><span class="sxs-lookup"><span data-stu-id="f27df-163">Changes to branding might require up to 24 hours for the users to see the changes.</span></span>

## <a name="review-app-details"></a><span data-ttu-id="f27df-164">Revisar detalles de la aplicación</span><span class="sxs-lookup"><span data-stu-id="f27df-164">Review app details</span></span>

<span data-ttu-id="f27df-165">Es posible que quiera ver los detalles de la aplicación para revisar la información.</span><span class="sxs-lookup"><span data-stu-id="f27df-165">You might want to see the app details to review the information.</span></span>

1. <span data-ttu-id="f27df-166">Inicie la sesión en el Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="f27df-166">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="f27df-167">Expanda **aplicación de Teams** y seleccione **Administrar aplicaciones**.</span><span class="sxs-lookup"><span data-stu-id="f27df-167">Expand **Teams apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="f27df-168">Seleccione el nombre de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f27df-168">Select the app name.</span></span>

4. <span data-ttu-id="f27df-169">Ver los detalles de la aplicación, incluido el nombre original de la aplicación **Nombre corto del editor.**</span><span class="sxs-lookup"><span data-stu-id="f27df-169">View the app details, including the original app name **Short name from publisher**.</span></span>

   ![Personalizar el nombre de la aplicación del panel de iconos](media/app-details-original-name.png)

   <span data-ttu-id="f27df-171">El **campo Nombre corto del editor** solo está visible si ha cambiado el nombre corto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f27df-171">The **Short name from publisher** field is only visible if you've changed the app's short name.</span></span>

## <a name="reset-app-details-to-default"></a><span data-ttu-id="f27df-172">Restablecer los detalles de la aplicación de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="f27df-172">Reset app details to default</span></span>

<span data-ttu-id="f27df-173">En cualquier momento, puede restablecer los detalles de la aplicación a la configuración original.</span><span class="sxs-lookup"><span data-stu-id="f27df-173">At any time, you can reset the app details to the original settings.</span></span>

1. <span data-ttu-id="f27df-174">Inicie la sesión en el Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="f27df-174">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="f27df-175">Expanda **Aplicaciones de Teams** y seleccione Administrar **aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="f27df-175">Expand **Teams Apps** and select **Manage apps**.</span></span>

3. <span data-ttu-id="f27df-176">Seleccione el nombre de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f27df-176">Select the app name.</span></span>

4. <span data-ttu-id="f27df-177">Seleccione **Restablecer de forma predeterminada** en el menú **desplegable** Acciones.</span><span class="sxs-lookup"><span data-stu-id="f27df-177">Select **Reset to default** from the **Actions** dropdown.</span></span>

   ![Seleccionar restablecer como resaltado predeterminado](media/select-reset.png)

## <a name="frequently-asked-questions"></a><span data-ttu-id="f27df-179">Preguntas frecuentes</span><span class="sxs-lookup"><span data-stu-id="f27df-179">Frequently asked questions</span></span>

<span data-ttu-id="f27df-180">**¿Cuánto tiempo tardarán mis usuarios en ver la aplicación personalizada?**</span><span class="sxs-lookup"><span data-stu-id="f27df-180">**How long will it take for my users to see the customized app?**</span></span>

<span data-ttu-id="f27df-181">Aunque el administrador puede ver inmediatamente los cambios en el Centro de administración de Teams, los usuarios finales pueden tardar hasta 24 horas en ver los cambios.</span><span class="sxs-lookup"><span data-stu-id="f27df-181">Although the admin can immediately see the changes in Teams Admin Center, it might take up to 24 hours for the end users to see the changes.</span></span>  

<span data-ttu-id="f27df-182">**¿Puede el proveedor de aplicaciones personalizar la aplicación para sus clientes?**</span><span class="sxs-lookup"><span data-stu-id="f27df-182">**Can the app provider customize the app for its customers?**</span></span>

 <span data-ttu-id="f27df-183">No, el administrador de un inquilino debe personalizar la aplicación para su inquilino con el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="f27df-183">No, the admin of a tenant needs to customize the app for their tenant using the Teams Admin Center.</span></span>

<span data-ttu-id="f27df-184">**¿Se implementará automáticamente la aplicación personalizada para reemplazar mi aplicación personalizada actual en un espacio empresarial?**</span><span class="sxs-lookup"><span data-stu-id="f27df-184">**Will the customized app automatically get deployed to replace my current custom app in a tenant?**</span></span>

<span data-ttu-id="f27df-185">No, los administradores de inquilinos tendrán que quitar manualmente cualquier aplicación personalizada y publicar la versión personalizada de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f27df-185">No, the tenant admins will have to manually remove any custom app and publish the customized version of the app.</span></span> <span data-ttu-id="f27df-186">Si ha personalizado una aplicación y la ha publicado como una aplicación personalizada, la nueva aplicación personalizada con la característica de personalización de la aplicación no reemplazará a la aplicación personalizada actual.</span><span class="sxs-lookup"><span data-stu-id="f27df-186">If you have customized an app and published it as a custom app, the new app customized using the app customization feature won't replace the current custom app.</span></span>  

<span data-ttu-id="f27df-187">**¿El informe de uso de la aplicación también mostrará los valores personalizados, como el nombre corto personalizado?**</span><span class="sxs-lookup"><span data-stu-id="f27df-187">**Will the app usage report also show the customized values such as customized short name?**</span></span>

 <span data-ttu-id="f27df-188">No, el informe de uso de la aplicación seguirá mostrándo el nombre original de la aplicación enviada desde el editor.</span><span class="sxs-lookup"><span data-stu-id="f27df-188">No, the app usage report will still show the original name of the app sent from the publisher.</span></span>

<span data-ttu-id="f27df-189">**¿Qué aplicaciones puedo personalizar con la característica de personalización de aplicaciones?**</span><span class="sxs-lookup"><span data-stu-id="f27df-189">**Which apps can I customize using the app customization feature?**</span></span>

<span data-ttu-id="f27df-190">Solo puede personalizar las aplicaciones que el editor de aplicaciones ha permitido personalizar.</span><span class="sxs-lookup"><span data-stu-id="f27df-190">You can only customize apps that have been allowed to be customizable by the app publisher.</span></span> <span data-ttu-id="f27df-191">El editor de aplicaciones tendrá que participar para permitir a sus clientes personalizar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f27df-191">The app publisher will need to opt in to allow its customers to customize the app.</span></span>

<span data-ttu-id="f27df-192">**¿Aparecerán las propiedades personalizadas en la pantalla de consentimiento de permisos de gráfico?**</span><span class="sxs-lookup"><span data-stu-id="f27df-192">**Will the customized properties show up on the graph permission consent screen?**</span></span>

<span data-ttu-id="f27df-193">No, la pantalla de consentimiento de permisos seguirá mostrándo el valor original enviado por el editor.</span><span class="sxs-lookup"><span data-stu-id="f27df-193">No, the permission consent screen will still show the original value sent by the publisher.</span></span>

## <a name="related-article"></a><span data-ttu-id="f27df-194">Artículo relacionado</span><span class="sxs-lookup"><span data-stu-id="f27df-194">Related article</span></span>

- [<span data-ttu-id="f27df-195">Administrar aplicaciones</span><span class="sxs-lookup"><span data-stu-id="f27df-195">Manage apps</span></span>](manage-apps.md)
- [<span data-ttu-id="f27df-196">Personalizar la tienda de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="f27df-196">Customize your app store</span></span>](customize-your-app-store.md)
