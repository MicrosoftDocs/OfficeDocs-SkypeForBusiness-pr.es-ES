---
title: Instalar, administrar y asignar permisos para la aplicación Teams Learning (versión preliminar privada)
author: ChuckEdmonson
ms.author: chucked
manager: pamgreenMSFT
ms.date: ''
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ChrisArnoldMSFT, LearningDocs2020
localization_priority: Normal
search.appverid: ''
ms.collection: ''
description: Use la aplicación Aprendizaje de Microsoft Teams para crear un centro central para aprender dónde los empleados pueden compartir, asignar y aprender de las bibliotecas de contenido de una organización.
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 6d4cb45334edb9307663eb1ffcab5e7c1085b149
ms.sourcegitcommit: b12ec4703b164c545d17b02815edd6ee28d40bed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/22/2021
ms.locfileid: "49923842"
---
# <a name="install-manage-and-assign-permissions-for-the-teams-learning-app-private-preview"></a><span data-ttu-id="8a7b6-103">Instalar, administrar y asignar permisos para la aplicación Teams Learning (versión preliminar privada)</span><span class="sxs-lookup"><span data-stu-id="8a7b6-103">Install, manage, and assign permissions for the Teams Learning app (private preview)</span></span>

<span data-ttu-id="8a7b6-104">*Este artículo contiene contenido preliminar para la aplicación Teams Learning, que está en versión preliminar privada.*</span><span class="sxs-lookup"><span data-stu-id="8a7b6-104">*This article contains preliminary content for the Teams Learning app, which is in private preview.*</span></span>

<span data-ttu-id="8a7b6-105">La aplicación Microsoft Teams Learning (versión preliminar privada) permite a los equipos y a las personas de su organización hacer que el aprendizaje sea parte natural de su día.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-105">The Microsoft Teams Learning app (private preview) empowers teams and individuals in your organization to make learning a natural part of their day.</span></span> <span data-ttu-id="8a7b6-106">La aplicación crea un concentrador central en Teams donde los empleados pueden compartir, asignar y aprender de bibliotecas de contenido en toda su organización.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-106">The app creates a central hub in Teams where employees can share, assign, and learn from content libraries across your organization.</span></span> <span data-ttu-id="8a7b6-107">Los administradores establecen permisos y permiten orígenes de contenido de aprendizaje para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-107">Admins set permissions and allow learning content sources for the app.</span></span> <span data-ttu-id="8a7b6-108">El contenido de aprendizaje puede incluir LinkedIn Learning, Microsoft Learn, formación de Microsoft 365, el contenido almacenado en SharePoint Online de su organización y proveedores de terceros compatibles con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-108">Learning content can include LinkedIn Learning, Microsoft Learn, Microsoft 365 training, your organization's own content stored in SharePoint online, and third-party providers that are supported by the app.</span></span>

<span data-ttu-id="8a7b6-109">Para configurar la aplicación Teams Learning (versión preliminar privada), tendrá que implicar:</span><span class="sxs-lookup"><span data-stu-id="8a7b6-109">To set up the Teams Learning app (private preview), you'll need to involve:</span></span>

-   <span data-ttu-id="8a7b6-110">Administrador del centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="8a7b6-110">Teams admin center admin</span></span>
-   <span data-ttu-id="8a7b6-111">Administrador del Centro de administración de Microsoft 365 (es decir, administrador global)</span><span class="sxs-lookup"><span data-stu-id="8a7b6-111">Microsoft 365 admin center admin (that is, a global admin)</span></span>

## <a name="manage-the-teams-learning-app-private-preview-in-the-teams-admin-center"></a><span data-ttu-id="8a7b6-112">Administrar la aplicación Teams Learning (versión preliminar privada) en el Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="8a7b6-112">Manage the Teams Learning app (private preview) in the Teams admin center</span></span>

<span data-ttu-id="8a7b6-113">El administrador de Teams instala la aplicación Teams Learning (versión preliminar privada) desde la tienda de aplicaciones y aplica las directivas de configuración, administración y permisos de la aplicación a través del Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-113">The Teams admin installs the Teams Learning app (private preview) from the app store and applies app setup, manage, and permissions policies through the Teams admin center.</span></span>

### <a name="manage-the-teams-learning-app-private-preview"></a><span data-ttu-id="8a7b6-114">Administrar la aplicación Teams Learning (versión preliminar privada)</span><span class="sxs-lookup"><span data-stu-id="8a7b6-114">Manage the Teams Learning app (private preview)</span></span>

<span data-ttu-id="8a7b6-115">Para administrar la configuración de la aplicación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8a7b6-115">To manage settings for app, follow these steps:</span></span>

1. <span data-ttu-id="8a7b6-116">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Administrar aplicaciones de Teams.**  >  </span><span class="sxs-lookup"><span data-stu-id="8a7b6-116">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Panel de navegación izquierdo del Centro de administración de Teams que muestra la sección Aplicaciones de Teams y Administrar aplicaciones](media/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="8a7b6-118">En la **página Administrar aplicaciones,** en el cuadro de búsqueda, escriba *"aprendizaje"* para buscar la aplicación Teams Learning (versión preliminar privada).</span><span class="sxs-lookup"><span data-stu-id="8a7b6-118">On the **Manage apps** page, in the search box, type *learning* to search for the Teams Learning app (private preview).</span></span>

   ![Página Administrar aplicaciones en el Centro de administración de Teams que muestra el cuadro de búsqueda](media/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="8a7b6-120">En la **página aprendizaje:**</span><span class="sxs-lookup"><span data-stu-id="8a7b6-120">On the **Learning** page:</span></span>
   1. <span data-ttu-id="8a7b6-121">En **Estado,** seleccione **Permitido** para activar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-121">Under **Status**, select **Allowed** to turn on the app.</span></span>
   2. <span data-ttu-id="8a7b6-122">En la **pestaña Configuración,** en la sección **Configuración de** la aplicación, vaya al Centro de administración de Microsoft 365 para configurar orígenes de contenido de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-122">On the **Settings** tab, in the **App settings** section, go to the Microsoft 365 admin center to configure learning content sources.</span></span>

   ![Página de aprendizaje del Centro de administración de Teams que muestra la sección Configuración de estado y aplicación](media/learning-app-teams-learning-page.png)

4. <span data-ttu-id="8a7b6-124">Después **de administrar** la configuración de la aplicación, vaya a Permisos y directivas de configuración para conceder permisos a los **empleados** que deberían tener acceso a la aplicación como parte de la participación de su organización en la versión preliminar privada.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-124">After **Manage app** settings, go to **Permissions and Set-up policies** to grant permission to employees who should have access to the app as part of your organization's participation in the private preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="8a7b6-125">Si su organización se encuentra en el anillo 4.0 como parte del programa TAP100 de Teams, es posible que tenga que hacer lo siguiente para permitir que los usuarios aprobados en el anillo 3.0 puedan acceder a la aplicación Teams Learning (versión preliminar privada).</span><span class="sxs-lookup"><span data-stu-id="8a7b6-125">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to do the following to enable approved users in Ring 3.0 to access the Teams Learning app (private preview).</span></span>

<span data-ttu-id="8a7b6-126">Como parte de la versión preliminar privada, la aplicación Teams Learning (versión preliminar privada) se publica en el anillo 3.0.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-126">As part of private preview, the Teams Learning app (private preview) is released in Ring 3.0.</span></span> <span data-ttu-id="8a7b6-127">Si su organización se encuentra en el anillo 4.0, no verá la aplicación en la tienda de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-127">If your organization is in Ring 4.0, you won’t see the app in the app store.</span></span> <span data-ttu-id="8a7b6-128">Para probar la aplicación, debe crear una directiva de permisos de aplicaciones personalizada, establecerla en Permitir todas las aplicaciones y asignarla a los usuarios aprobados de Llamada 3.0.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-128">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span>

   ![Página TAP-AppsPermission-Plcy que muestra Permitir todas las aplicaciones seleccionadas](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a><span data-ttu-id="8a7b6-130">Configurar orígenes de contenido de aprendizaje en el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8a7b6-130">Configure learning content sources in the Microsoft 365 admin center</span></span>

<span data-ttu-id="8a7b6-131">Los administradores del Centro de administración de Microsoft 365 pueden administrar la configuración relacionada con la aplicación Teams Learning (versión preliminar privada) y pueden configurar los orígenes de contenido de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-131">The admins for the Microsoft 365 admin center can manage settings related to the Teams Learning app (private preview) and can configure the learning content sources.</span></span>

<span data-ttu-id="8a7b6-132">El administrador selecciona los orígenes de contenido de aprendizaje (como LinkedIn Learning o SharePoint) que estarán disponibles en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-132">The admin selects which learning content sources (such as LinkedIn Learning or SharePoint) will be available in the app.</span></span> <span data-ttu-id="8a7b6-133">A continuación, el administrador configura esos orígenes para asegurarse de que el contenido está disponible para la búsqueda y detección y puede ser examinada por los empleados que usan la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-133">The admin then configures those sources to make sure the content is available for search and discovery and can be browsed by the employees who use the app.</span></span>

### <a name="configure-settings-for-the-learning-content-sources-for-the-app"></a><span data-ttu-id="8a7b6-134">Configurar las opciones de los orígenes de contenido de aprendizaje para la aplicación</span><span class="sxs-lookup"><span data-stu-id="8a7b6-134">Configure settings for the learning content sources for the app</span></span>

<span data-ttu-id="8a7b6-135">Estos pasos los debe realizar el administrador de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-135">These steps are to be performed by the Microsoft 365 admin.</span></span>

1.  <span data-ttu-id="8a7b6-136">En el panel de navegación izquierdo del Centro de administración de Microsoft 365, vaya a **Configuración de**  >  **la organización.**</span><span class="sxs-lookup"><span data-stu-id="8a7b6-136">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>

2.  <span data-ttu-id="8a7b6-137">En la **página** Configuración, en la pestaña **& complementos,** seleccione **Aplicación de aprendizaje.**</span><span class="sxs-lookup"><span data-stu-id="8a7b6-137">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![Página de configuración del Centro de administración de Microsoft 365 que muestra la aplicación Aprendizaje enumerada](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="8a7b6-139">En el **panel de la aplicación** Aprendizaje, seleccione los orígenes de contenido de aprendizaje que quiera configurar para la organización y, después, haga clic en **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="8a7b6-139">On the **Learning app** panel, select the learning content sources you want to configure for the organization, and then select **Save**.</span></span>

   ![Panel de la aplicación Aprendizaje del Centro de administración de Microsoft 365 que muestra las opciones de orígenes de contenido](media/learning-app-365-settings-learning-app-panel.png)

<span data-ttu-id="8a7b6-141">Entre todas las fuentes de aprendizaje que existen, algunas de ellas estarán habilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-141">Among all the learning sources that exist, some will be enabled by default.</span></span> <span data-ttu-id="8a7b6-142">Estas afectan a los siguientes aspectos, entre otros:</span><span class="sxs-lookup"><span data-stu-id="8a7b6-142">These include:</span></span>

- <span data-ttu-id="8a7b6-143">LinkedIn Learning (contenido gratuito)</span><span class="sxs-lookup"><span data-stu-id="8a7b6-143">LinkedIn Learning (free content)</span></span>
- <span data-ttu-id="8a7b6-144">Microsoft Learn</span><span class="sxs-lookup"><span data-stu-id="8a7b6-144">Microsoft Learn</span></span>
- <span data-ttu-id="8a7b6-145">Aprendizaje de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8a7b6-145">Microsoft 365 Training</span></span>

> [!NOTE]
> <span data-ttu-id="8a7b6-146">Si su organización tiene una suscripción a LinkedIn Learning Standard o Pro, se desbloqueará el repositorio de contenido para los empleados de la organización.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-146">If your organization has a LinkedIn Learning Standard or Pro subscription, the content repository will be unlocked for the employees in your organization.</span></span> <span data-ttu-id="8a7b6-147">Solo los empleados con permisos podrán usar todo el repositorio de contenido.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-147">Only those employees who have permission will be able to use the entire content repository.</span></span>

<span data-ttu-id="8a7b6-148">Es posible que otros orígenes deba habilitarse o configurarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-148">Other sources might need to be enabled or configured manually.</span></span> <span data-ttu-id="8a7b6-149">Las fuentes de aprendizaje que no son de Microsoft tienen licencia por separado entre su organización y los terceros.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-149">Learning sources that are not from Microsoft are separately licensed between your organization and the third party.</span></span> <span data-ttu-id="8a7b6-150">Deberá comprobar que se ha registrado para su aprendizaje para usted y sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-150">You’ll need to verify you’ve signed up for their learning for you and your users.</span></span>

<span data-ttu-id="8a7b6-151">Para habilitar o deshabilitar un origen de contenido de aprendizaje, active la casilla situada junto al origen.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-151">To enable or disable a learning content source, select the check box next to the source.</span></span> <span data-ttu-id="8a7b6-152">Si un origen está habilitado, se podrá ver una marca de verificación.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-152">If a source is enabled, a check mark will be visible.</span></span>

## <a name="configure-sharepoint-as-a-learning-content-source-coming-soon"></a><span data-ttu-id="8a7b6-153">Configurar SharePoint como un origen de contenido de aprendizaje (Próximamente)</span><span class="sxs-lookup"><span data-stu-id="8a7b6-153">Configure SharePoint as a learning content source (Coming Soon)</span></span>

<span data-ttu-id="8a7b6-154">Configure SharePoint como un origen de contenido de aprendizaje para la aplicación Teams Learning (versión preliminar privada) en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-154">You configure SharePoint as a learning content source for the Teams Learning app (private preview) in the Microsoft 365 admin center.</span></span>

### <a name="overview"></a><span data-ttu-id="8a7b6-155">Descripción general</span><span class="sxs-lookup"><span data-stu-id="8a7b6-155">Overview</span></span>

<span data-ttu-id="8a7b6-156">El administrador proporciona una dirección URL de sitio a la que el Servicio de aprendizaje puede crear un repositorio de contenido de aprendizaje centralizado vacío en forma de lista estructurada de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-156">The admin provides a site URL to where the Learning Service can create an empty centralized learning content repository in the form of a structured SharePoint list.</span></span> <span data-ttu-id="8a7b6-157">Esta lista la puede usar la organización para hospedar vínculos a carpetas de SharePoint entre empresas que contienen contenido de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-157">This list can be used by the organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="8a7b6-158">Los administradores son responsables de recopilar y curar una lista de direcciones URL de las carpetas.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-158">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="8a7b6-159">Estas carpetas solo deben incluir contenido que pueda estar disponible en la aplicación Teams Learning (versión preliminar privada).</span><span class="sxs-lookup"><span data-stu-id="8a7b6-159">These folders should only include content that can be made available in the Teams Learning app (private preview).</span></span>

### <a name="permissions"></a><span data-ttu-id="8a7b6-160">Permisos</span><span class="sxs-lookup"><span data-stu-id="8a7b6-160">Permissions</span></span>

<span data-ttu-id="8a7b6-161">Las direcciones URL de carpeta se pueden recopilar desde cualquier sitio de SharePoint de la organización.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-161">Folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="8a7b6-162">Se podrá buscar cualquier contenido dentro de estas carpetas, pero solo se podrá usar el contenido para el que cada empleado tenga permisos.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-162">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>
 
### <a name="learning-service"></a><span data-ttu-id="8a7b6-163">Servicio de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="8a7b6-163">Learning Service</span></span>

<span data-ttu-id="8a7b6-164">El Servicio de aprendizaje usa las direcciones URL de carpeta proporcionadas para obtener metadatos de todo el contenido almacenado en esas carpetas.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-164">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="8a7b6-165">24 horas después de proporcionar la dirección URL de la carpeta en el repositorio centralizado, los empleados pueden buscar y usar el contenido de la empresa dentro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-165">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use the company’s content within the app.</span></span> <span data-ttu-id="8a7b6-166">La eliminación de contenido del repositorio no es compatible en este momento.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-166">Content deletion from the repository isn't supported at this point.</span></span> <span data-ttu-id="8a7b6-167">El contenido en superficie no involuntara solo se puede quitar suministrando una nueva DIRECCIÓN URL del sitio de SharePoint en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-167">Unintentionally surfaced content can only be removed by supplying a new SharePoint site URL in the Microsoft 365 admin center.</span></span>

### <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="8a7b6-168">Configurar SharePoint como origen</span><span class="sxs-lookup"><span data-stu-id="8a7b6-168">Configure SharePoint as a source</span></span>

<span data-ttu-id="8a7b6-169">Estos pasos los debe realizar el administrador de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-169">These steps are to be performed by Microsoft 365 admin.</span></span>

1.  <span data-ttu-id="8a7b6-170">En el panel de navegación izquierdo del Centro de administración de Microsoft 365, vaya a **Configuración.**</span><span class="sxs-lookup"><span data-stu-id="8a7b6-170">In the left navigation of the Microsoft 365 admin center, go to **Settings**.</span></span>
 
2.  <span data-ttu-id="8a7b6-171">En la **página** Configuración, en la pestaña **& complementos,** seleccione **Aplicación de aprendizaje.**</span><span class="sxs-lookup"><span data-stu-id="8a7b6-171">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![Página de configuración del Centro de administración de Microsoft 365 que muestra la aplicación Aprendizaje enumerada](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="8a7b6-173">En el panel **de la aplicación** Aprendizaje, proporcione la dirección URL del sitio al sitio de SharePoint donde quiera que la aplicación cree un repositorio centralizado.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-173">On the **Learning app** panel, provide the site URL to the SharePoint site where you want the app to create a centralized repository.</span></span>

   ![Panel de la aplicación de aprendizaje en el Centro de administración de Microsoft 365 que muestra SharePoint seleccionado](media/learning-app-365-panel-sharepoint-selected.png)

4.  <span data-ttu-id="8a7b6-175">Una lista de SharePoint se crea automáticamente en el sitio de SharePoint de la organización proporcionada.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-175">A SharePoint list is created automatically within the provided organization’s SharePoint site.</span></span> <span data-ttu-id="8a7b6-176">En el panel de navegación izquierdo del sitio de SharePoint, seleccione Repositorio **de contenido de aplicaciones de aprendizaje.**</span><span class="sxs-lookup"><span data-stu-id="8a7b6-176">In the left navigation of the SharePoint site, select **Learning App Content Repository**.</span></span> 

   ![Navegación izquierda en SharePoint que muestra la sección Repositorio de contenido de la aplicación de aprendizaje](media/learning-app-content-repository-nav.png)

 
5. <span data-ttu-id="8a7b6-178">En la **página Repositorio de contenido de la aplicación** de aprendizaje, rellene la lista de SharePoint con direcciones URL en las carpetas de contenido de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-178">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1.   <span data-ttu-id="8a7b6-179">Seleccione **Nuevo** para ver el **panel Nuevo** elemento.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-179">Select **New** to view the **New item** panel.</span></span> 

   ![Página de repositorio de contenido de la aplicación de aprendizaje en SharePoint que muestra la nueva opción](media/learning-app-content-repository-new.png)
 
   2.   <span data-ttu-id="8a7b6-181">En el **panel Nuevo elemento,** en el **campo Título,** agregue el nombre del directorio que prefiera.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-181">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="8a7b6-182">En el **campo Dirección URL de** la carpeta, agregue la dirección URL a la carpeta de contenido de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-182">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="8a7b6-183">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-183">Select **Save**.</span></span>

   ![Panel Nuevo elemento en SharePoint que muestra los campos Título y Dirección URL de carpeta](media/learning-app-new-item-panel.png)

   3. <span data-ttu-id="8a7b6-185">La página repositorio de contenido de la aplicación de aprendizaje se actualiza con el nuevo contenido de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="8a7b6-185">The Learning App Content Repository page is updated with the new learning content.</span></span>

   ![Página de repositorio de contenido de la aplicación de aprendizaje en SharePoint que muestra la información actualizada](media/learning-app-content-repository-populated.png)


 


