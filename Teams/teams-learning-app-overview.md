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
ms.openlocfilehash: 6dd82c786c30fb4f2ac2ae70f2df6810cfe5d6ad
ms.sourcegitcommit: 75d710e3858f79ef601cd92e435a4a29dae0aba0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/18/2021
ms.locfileid: "50285624"
---
# <a name="install-manage-and-assign-permissions-for-the-teams-learning-app-private-preview"></a><span data-ttu-id="ee586-103">Instalar, administrar y asignar permisos para la aplicación Teams Learning (versión preliminar privada)</span><span class="sxs-lookup"><span data-stu-id="ee586-103">Install, manage, and assign permissions for the Teams Learning app (private preview)</span></span>

<span data-ttu-id="ee586-104">*Este artículo contiene contenido preliminar para la aplicación Teams Learning, que está en versión preliminar privada.*</span><span class="sxs-lookup"><span data-stu-id="ee586-104">*This article contains preliminary content for the Teams Learning app, which is in private preview.*</span></span>

<span data-ttu-id="ee586-105">La aplicación Microsoft Teams Learning (versión preliminar privada) permite a los equipos y a las personas de su organización hacer que el aprendizaje sea parte natural de su día.</span><span class="sxs-lookup"><span data-stu-id="ee586-105">The Microsoft Teams Learning app (private preview) empowers teams and individuals in your organization to make learning a natural part of their day.</span></span> <span data-ttu-id="ee586-106">La aplicación crea un concentrador central en Teams donde los empleados pueden compartir, asignar y aprender de bibliotecas de contenido en toda su organización.</span><span class="sxs-lookup"><span data-stu-id="ee586-106">The app creates a central hub in Teams where employees can share, assign, and learn from content libraries across your organization.</span></span> <span data-ttu-id="ee586-107">Los administradores establecen permisos y permiten orígenes de contenido de aprendizaje para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ee586-107">Admins set permissions and allow learning content sources for the app.</span></span> <span data-ttu-id="ee586-108">El contenido de aprendizaje puede incluir LinkedIn Learning, Microsoft Learn, formación de Microsoft 365, el contenido almacenado en SharePoint Online de su organización y proveedores de terceros compatibles con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ee586-108">Learning content can include LinkedIn Learning, Microsoft Learn, Microsoft 365 training, your organization's own content stored in SharePoint online, and third-party providers that are supported by the app.</span></span>

<span data-ttu-id="ee586-109">Para configurar la aplicación Teams Learning (versión preliminar privada), tendrá que implicar:</span><span class="sxs-lookup"><span data-stu-id="ee586-109">To set up the Teams Learning app (private preview), you'll need to involve:</span></span>

-   <span data-ttu-id="ee586-110">Administrador del centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="ee586-110">Teams admin center admin</span></span>
-   <span data-ttu-id="ee586-111">Administrador del centro de administración de Microsoft 365 (es decir, administrador global)</span><span class="sxs-lookup"><span data-stu-id="ee586-111">Microsoft 365 admin center admin (that is, a global admin)</span></span>

## <a name="manage-the-teams-learning-app-private-preview-in-the-teams-admin-center"></a><span data-ttu-id="ee586-112">Administrar la aplicación Teams Learning (versión preliminar privada) en el Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="ee586-112">Manage the Teams Learning app (private preview) in the Teams admin center</span></span>

<span data-ttu-id="ee586-113">El administrador de Teams instala la aplicación Teams Learning (versión preliminar privada) desde la tienda de aplicaciones y aplica las directivas de configuración, administración y permisos de la aplicación a través del Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="ee586-113">The Teams admin installs the Teams Learning app (private preview) from the app store and applies app setup, manage, and permissions policies through the Teams admin center.</span></span>

### <a name="manage-the-teams-learning-app-private-preview"></a><span data-ttu-id="ee586-114">Administrar la aplicación Teams Learning (versión preliminar privada)</span><span class="sxs-lookup"><span data-stu-id="ee586-114">Manage the Teams Learning app (private preview)</span></span>

<span data-ttu-id="ee586-115">Para administrar la configuración de la aplicación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="ee586-115">To manage settings for app, follow these steps:</span></span>

1. <span data-ttu-id="ee586-116">En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Administrar aplicaciones**  >  **de** Teams.</span><span class="sxs-lookup"><span data-stu-id="ee586-116">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Panel de navegación izquierdo del Centro de administración de Teams que muestra la sección Aplicaciones de Teams y Administrar aplicaciones](media/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="ee586-118">En la **página Administrar aplicaciones,** en el cuadro de búsqueda, escriba *"aprendizaje"* para buscar la aplicación Teams Learning (versión preliminar privada).</span><span class="sxs-lookup"><span data-stu-id="ee586-118">On the **Manage apps** page, in the search box, type *learning* to search for the Teams Learning app (private preview).</span></span>

   ![Página Administrar aplicaciones en el Centro de administración de Teams que muestra el cuadro de búsqueda](media/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="ee586-120">En la **página aprendizaje:**</span><span class="sxs-lookup"><span data-stu-id="ee586-120">On the **Learning** page:</span></span>
   1. <span data-ttu-id="ee586-121">En **Estado,** seleccione **Permitido** para activar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ee586-121">Under **Status**, select **Allowed** to turn on the app.</span></span>
   2. <span data-ttu-id="ee586-122">En la **pestaña Configuración,** en la sección **Configuración de** la aplicación, vaya al Centro de administración de Microsoft 365 para configurar orígenes de contenido de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="ee586-122">On the **Settings** tab, in the **App settings** section, go to the Microsoft 365 admin center to configure learning content sources.</span></span>

   ![Página de aprendizaje del Centro de administración de Teams que muestra la sección Configuración de estado y aplicación](media/learning-app-teams-learning-page.png)

4. <span data-ttu-id="ee586-124">Después **de administrar** la configuración de la aplicación, vaya a Permisos y directivas de configuración para conceder permisos a los **empleados** que deberían tener acceso a la aplicación como parte de la participación de su organización en la versión preliminar privada.</span><span class="sxs-lookup"><span data-stu-id="ee586-124">After **Manage app** settings, go to **Permissions and Set-up policies** to grant permission to employees who should have access to the app as part of your organization's participation in the private preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="ee586-125">Si su organización se encuentra en el anillo 4.0 como parte del programa TAP100 de Teams, es posible que tenga que hacer lo siguiente para permitir que los usuarios aprobados en el anillo 3.0 puedan acceder a la aplicación Teams Learning (versión preliminar privada).</span><span class="sxs-lookup"><span data-stu-id="ee586-125">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to do the following to enable approved users in Ring 3.0 to access the Teams Learning app (private preview).</span></span>

<span data-ttu-id="ee586-126">Como parte de la versión preliminar privada, la aplicación Teams Learning (versión preliminar privada) se publica en el anillo 3.0.</span><span class="sxs-lookup"><span data-stu-id="ee586-126">As part of private preview, the Teams Learning app (private preview) is released in Ring 3.0.</span></span> <span data-ttu-id="ee586-127">Si su organización está en el anillo 4.0, no verá la aplicación en la tienda de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="ee586-127">If your organization is in Ring 4.0, you won’t see the app in the app store.</span></span> <span data-ttu-id="ee586-128">Para probar la aplicación, debe crear una directiva de permisos de aplicaciones personalizada, establecerla en Permitir todas las aplicaciones y asignarla a los usuarios aprobados de Llamada 3.0.</span><span class="sxs-lookup"><span data-stu-id="ee586-128">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span>

   ![Página TAP-AppsPermission-Plcy que muestra Permitir todas las aplicaciones seleccionadas](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a><span data-ttu-id="ee586-130">Configurar orígenes de contenido de aprendizaje en el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ee586-130">Configure learning content sources in the Microsoft 365 admin center</span></span>

<span data-ttu-id="ee586-131">Los administradores del Centro de administración de Microsoft 365 pueden administrar la configuración relacionada con la aplicación Teams Learning (versión preliminar privada) y pueden configurar los orígenes de contenido de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="ee586-131">The admins for the Microsoft 365 admin center can manage settings related to the Teams Learning app (private preview) and can configure the learning content sources.</span></span>

<span data-ttu-id="ee586-132">El administrador puede seleccionar qué orígenes de contenido de aprendizaje adicionales (por ejemplo, SharePoint u orígenes de proveedores de contenido de terceros compatibles) estarán disponibles para los usuarios de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ee586-132">The admin can select which additional learning content sources (for example, SharePoint or supported third-party content provider sources) will be available to users of the app.</span></span> <span data-ttu-id="ee586-133">A continuación, el administrador configura esos orígenes para asegurarse de que el contenido está disponible para la búsqueda y detección y puede ser examinada por los empleados que usan la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ee586-133">The admin then configures those sources to make sure the content is available for search and discovery and can be browsed by the employees who use the app.</span></span>

> [!NOTE]
>  <span data-ttu-id="ee586-134">Los usuarios inician sesión en aprendizajes que no son de Microsoft y LinkedIn Learning Pro en un explorador o en un visor incrustado.</span><span class="sxs-lookup"><span data-stu-id="ee586-134">Users sign in to non-Microsoft and LinkedIn Learning Pro learnings in a browser or embedded viewer.</span></span> <span data-ttu-id="ee586-135">Este aprendizaje configurado está sujeto a los términos de licencia, privacidad y servicio independientes entre su organización y los terceros, y no a los términos de aprendizaje (versión preliminar).</span><span class="sxs-lookup"><span data-stu-id="ee586-135">This configured learning is subject to the separate license, privacy and service terms between your organization and the third party, and not the Learning (Preview) terms.</span></span> <span data-ttu-id="ee586-136">Antes de seleccionar este aprendizaje en Aprendizaje (versión preliminar), compruebe que tiene un acuerdo para su organización y los usuarios.</span><span class="sxs-lookup"><span data-stu-id="ee586-136">Before selecting this learning in Learning (Preview), verify you have an agreement in place for your organization and users.</span></span>

### <a name="configure-settings-for-the-learning-content-sources-for-the-app"></a><span data-ttu-id="ee586-137">Configurar las opciones de los orígenes de contenido de aprendizaje para la aplicación</span><span class="sxs-lookup"><span data-stu-id="ee586-137">Configure settings for the learning content sources for the app</span></span>

<span data-ttu-id="ee586-138">Estos pasos los debe realizar el administrador de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ee586-138">These steps are to be performed by the Microsoft 365 admin.</span></span>

1.  <span data-ttu-id="ee586-139">En el panel de navegación izquierdo del Centro de administración de Microsoft 365, vaya a **Configuración de**  >  **la organización.**</span><span class="sxs-lookup"><span data-stu-id="ee586-139">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>

2.  <span data-ttu-id="ee586-140">En la **página** Configuración, en la pestaña **& complementos,** seleccione **Aplicación de aprendizaje.**</span><span class="sxs-lookup"><span data-stu-id="ee586-140">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![Página de configuración del Centro de administración de Microsoft 365 que muestra la aplicación Aprendizaje enumerada](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="ee586-142">En el **panel de la aplicación** Aprendizaje, seleccione los orígenes de contenido de aprendizaje que quiera configurar para la organización y, después, haga clic en **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="ee586-142">On the **Learning app** panel, select the learning content sources you want to configure for the organization, and then select **Save**.</span></span>

   ![Panel de la aplicación Aprendizaje del Centro de administración de Microsoft 365 que muestra las opciones de orígenes de contenido](media/learning-app-365-settings-learning-app-panel.png)

<span data-ttu-id="ee586-144">Entre todas las fuentes de aprendizaje que existen, algunas de ellas estarán habilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ee586-144">Among all the learning sources that exist, some will be enabled by default.</span></span> <span data-ttu-id="ee586-145">Estas afectan a los siguientes aspectos, entre otros:</span><span class="sxs-lookup"><span data-stu-id="ee586-145">These include:</span></span>

- <span data-ttu-id="ee586-146">LinkedIn Learning (contenido gratuito)</span><span class="sxs-lookup"><span data-stu-id="ee586-146">LinkedIn Learning (free content)</span></span>
- <span data-ttu-id="ee586-147">Microsoft Learn</span><span class="sxs-lookup"><span data-stu-id="ee586-147">Microsoft Learn</span></span>
- <span data-ttu-id="ee586-148">Aprendizaje de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ee586-148">Microsoft 365 Training</span></span>

> [!NOTE]
> <span data-ttu-id="ee586-149">Si su organización tiene una suscripción a LinkedIn Learning Standard o Pro, se desbloqueará el repositorio de contenido para los empleados de la organización.</span><span class="sxs-lookup"><span data-stu-id="ee586-149">If your organization has a LinkedIn Learning Standard or Pro subscription, the content repository will be unlocked for the employees in your organization.</span></span> <span data-ttu-id="ee586-150">Solo los empleados con permisos podrán usar todo el repositorio de contenido.</span><span class="sxs-lookup"><span data-stu-id="ee586-150">Only those employees who have permission will be able to use the entire content repository.</span></span>

<span data-ttu-id="ee586-151">Es posible que otros orígenes deba habilitarse o configurarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="ee586-151">Other sources might need to be enabled or configured manually.</span></span> <span data-ttu-id="ee586-152">Las fuentes de aprendizaje que no son de Microsoft tienen licencia por separado entre su organización y los terceros.</span><span class="sxs-lookup"><span data-stu-id="ee586-152">Learning sources that are not from Microsoft are separately licensed between your organization and the third party.</span></span> <span data-ttu-id="ee586-153">Deberá comprobar que se ha registrado para su aprendizaje para usted y sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="ee586-153">You’ll need to verify you’ve signed up for their learning for you and your users.</span></span>

<span data-ttu-id="ee586-154">Para habilitar o deshabilitar un origen de contenido de aprendizaje, active la casilla situada junto al origen.</span><span class="sxs-lookup"><span data-stu-id="ee586-154">To enable or disable a learning content source, select the check box next to the source.</span></span> <span data-ttu-id="ee586-155">Si un origen está habilitado, se podrá ver una marca de verificación.</span><span class="sxs-lookup"><span data-stu-id="ee586-155">If a source is enabled, a check mark will be visible.</span></span>

## <a name="configure-sharepoint-as-a-learning-content-source-coming-soon"></a><span data-ttu-id="ee586-156">Configurar SharePoint como un origen de contenido de aprendizaje (Próximamente)</span><span class="sxs-lookup"><span data-stu-id="ee586-156">Configure SharePoint as a learning content source (Coming Soon)</span></span>

<span data-ttu-id="ee586-157">Configure SharePoint como un origen de contenido de aprendizaje para la aplicación Teams Learning (versión preliminar privada) en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ee586-157">You configure SharePoint as a learning content source for the Teams Learning app (private preview) in the Microsoft 365 admin center.</span></span>

### <a name="overview"></a><span data-ttu-id="ee586-158">Información general</span><span class="sxs-lookup"><span data-stu-id="ee586-158">Overview</span></span>

<span data-ttu-id="ee586-159">El administrador proporciona una dirección URL de sitio a la que el Servicio de aprendizaje puede crear un repositorio de contenido de aprendizaje centralizado vacío en forma de lista estructurada de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ee586-159">The admin provides a site URL to where the Learning Service can create an empty centralized learning content repository in the form of a structured SharePoint list.</span></span> <span data-ttu-id="ee586-160">Esta lista la puede usar la organización para hospedar vínculos a carpetas de SharePoint entre empresas que contienen contenido de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="ee586-160">This list can be used by the organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="ee586-161">Los administradores son responsables de recopilar y curar una lista de direcciones URL de las carpetas.</span><span class="sxs-lookup"><span data-stu-id="ee586-161">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="ee586-162">Estas carpetas solo deben incluir contenido que pueda estar disponible en la aplicación Teams Learning (versión preliminar privada).</span><span class="sxs-lookup"><span data-stu-id="ee586-162">These folders should only include content that can be made available in the Teams Learning app (private preview).</span></span>

### <a name="permissions"></a><span data-ttu-id="ee586-163">Permisos</span><span class="sxs-lookup"><span data-stu-id="ee586-163">Permissions</span></span>

<span data-ttu-id="ee586-164">Las direcciones URL de carpeta se pueden recopilar desde cualquier sitio de SharePoint de la organización.</span><span class="sxs-lookup"><span data-stu-id="ee586-164">Folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="ee586-165">Se podrá buscar cualquier contenido dentro de estas carpetas, pero solo se podrá usar el contenido para el que cada empleado tenga permisos.</span><span class="sxs-lookup"><span data-stu-id="ee586-165">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>
 
### <a name="learning-service"></a><span data-ttu-id="ee586-166">Servicio de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="ee586-166">Learning Service</span></span>

<span data-ttu-id="ee586-167">El Servicio de aprendizaje usa las direcciones URL de carpeta proporcionadas para obtener metadatos de todo el contenido almacenado en esas carpetas.</span><span class="sxs-lookup"><span data-stu-id="ee586-167">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="ee586-168">24 horas después de proporcionar la dirección URL de la carpeta en el repositorio centralizado, los empleados pueden buscar y usar el contenido de la empresa dentro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="ee586-168">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use the company’s content within the app.</span></span> <span data-ttu-id="ee586-169">En este momento no se admite la eliminación de contenido del repositorio.</span><span class="sxs-lookup"><span data-stu-id="ee586-169">Content deletion from the repository isn't supported at this point.</span></span> <span data-ttu-id="ee586-170">El contenido en superficie no involuntara solo se puede quitar suministrando una nueva DIRECCIÓN URL del sitio de SharePoint en el Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ee586-170">Unintentionally surfaced content can only be removed by supplying a new SharePoint site URL in the Microsoft 365 admin center.</span></span>

### <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="ee586-171">Configurar SharePoint como origen</span><span class="sxs-lookup"><span data-stu-id="ee586-171">Configure SharePoint as a source</span></span>

<span data-ttu-id="ee586-172">Estos pasos los realizará el administrador de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ee586-172">These steps are to be performed by Microsoft 365 admin.</span></span>

1.  <span data-ttu-id="ee586-173">En el panel de navegación izquierdo del Centro de administración de Microsoft 365, vaya a **Configuración.**</span><span class="sxs-lookup"><span data-stu-id="ee586-173">In the left navigation of the Microsoft 365 admin center, go to **Settings**.</span></span>
 
2.  <span data-ttu-id="ee586-174">En la **página** Configuración, en la pestaña **& complementos,** seleccione **Aplicación de aprendizaje.**</span><span class="sxs-lookup"><span data-stu-id="ee586-174">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![Página de configuración del Centro de administración de Microsoft 365 que muestra la aplicación Aprendizaje enumerada](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="ee586-176">En el panel **de la aplicación** Aprendizaje, proporcione la dirección URL del sitio al sitio de SharePoint donde quiera que la aplicación cree un repositorio centralizado.</span><span class="sxs-lookup"><span data-stu-id="ee586-176">On the **Learning app** panel, provide the site URL to the SharePoint site where you want the app to create a centralized repository.</span></span>

   ![Panel de la aplicación de aprendizaje en el Centro de administración de Microsoft 365 que muestra SharePoint seleccionado](media/learning-app-365-panel-sharepoint-selected.png)

4.  <span data-ttu-id="ee586-178">Una lista de SharePoint se crea automáticamente en el sitio de SharePoint de la organización proporcionada.</span><span class="sxs-lookup"><span data-stu-id="ee586-178">A SharePoint list is created automatically within the provided organization’s SharePoint site.</span></span> <span data-ttu-id="ee586-179">En el panel de navegación izquierdo del sitio de SharePoint, seleccione Repositorio **de contenido de aplicaciones de aprendizaje.**</span><span class="sxs-lookup"><span data-stu-id="ee586-179">In the left navigation of the SharePoint site, select **Learning App Content Repository**.</span></span> 

   ![Navegación izquierda en SharePoint que muestra la sección Repositorio de contenido de la aplicación de aprendizaje](media/learning-app-content-repository-nav.png)

 
5. <span data-ttu-id="ee586-181">En la **página Repositorio de contenido de la aplicación** de aprendizaje, rellene la lista de SharePoint con direcciones URL para las carpetas de contenido de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="ee586-181">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1.   <span data-ttu-id="ee586-182">Seleccione **Nuevo** para ver el **panel Nuevo** elemento.</span><span class="sxs-lookup"><span data-stu-id="ee586-182">Select **New** to view the **New item** panel.</span></span> 

   ![Página de repositorio de contenido de la aplicación de aprendizaje en SharePoint que muestra la nueva opción](media/learning-app-content-repository-new.png)
 
   2.   <span data-ttu-id="ee586-184">En el **panel Nuevo elemento,** en el **campo Título,** agregue el nombre del directorio que prefiera.</span><span class="sxs-lookup"><span data-stu-id="ee586-184">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="ee586-185">En el **campo Dirección URL de** la carpeta, agregue la dirección URL a la carpeta de contenido de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="ee586-185">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="ee586-186">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ee586-186">Select **Save**.</span></span>

   ![Panel Nuevo elemento en SharePoint que muestra los campos Título y Dirección URL de carpeta](media/learning-app-new-item-panel.png)

   3. <span data-ttu-id="ee586-188">La página repositorio de contenido de la aplicación de aprendizaje se actualiza con el nuevo contenido de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="ee586-188">The Learning App Content Repository page is updated with the new learning content.</span></span>

   ![Página de repositorio de contenido de la aplicación de aprendizaje en SharePoint que muestra la información actualizada](media/learning-app-content-repository-populated.png)


 


