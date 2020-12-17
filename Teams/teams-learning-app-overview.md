---
title: Instalar, administrar y asignar permisos para la aplicación de aprendizaje de Teams (versión preliminar privada)
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
description: Use la aplicación de aprendizaje de Microsoft Teams para crear un concentrador central para aprender dónde los empleados pueden compartir, asignar y aprender de las bibliotecas de contenido en una organización.
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: a8fe0d3b4f86de34accb1519c80a391a9e395fbe
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703461"
---
# <a name="install-manage-and-assign-permissions-for-the-teams-learning-app-private-preview"></a><span data-ttu-id="6e163-103">Instalar, administrar y asignar permisos para la aplicación de aprendizaje de Teams (versión preliminar privada)</span><span class="sxs-lookup"><span data-stu-id="6e163-103">Install, manage, and assign permissions for the Teams Learning app (private preview)</span></span>

<span data-ttu-id="6e163-104">*Este artículo contiene contenido preliminar para la aplicación de aprendizaje de Teams, que se encuentra en la versión preliminar privada.*</span><span class="sxs-lookup"><span data-stu-id="6e163-104">*This article contains preliminary content for the Teams Learning app, which is in private preview.*</span></span>

<span data-ttu-id="6e163-105">La aplicación de aprendizaje de Microsoft Teams (versión preliminar privada) permite a los equipos y a las personas de su organización facilitar el aprendizaje de forma natural.</span><span class="sxs-lookup"><span data-stu-id="6e163-105">The Microsoft Teams Learning app (private preview) empowers teams and individuals in your organization to make learning a natural part of their day.</span></span> <span data-ttu-id="6e163-106">La aplicación crea un concentrador central en Teams en el que los empleados pueden compartir, asignar y aprender de las bibliotecas de contenido de su organización.</span><span class="sxs-lookup"><span data-stu-id="6e163-106">The app creates a central hub in Teams where employees can share, assign, and learn from content libraries across your organization.</span></span> <span data-ttu-id="6e163-107">Los administradores establecen permisos y permiten orígenes de contenido de aprendizaje para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6e163-107">Admins set permissions and allow learning content sources for the app.</span></span> <span data-ttu-id="6e163-108">El aprendizaje del contenido puede incluir LinkedIn Learning, aprendizaje de Microsoft, aprendizaje de Microsoft 365, el contenido de su organización almacenado en SharePoint Online y proveedores de terceros que son compatibles con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6e163-108">Learning content can include LinkedIn Learning, Microsoft Learn, Microsoft 365 training, your organization's own content stored in SharePoint online, and third-party providers that are supported by the app.</span></span>

<span data-ttu-id="6e163-109">Para configurar la aplicación de aprendizaje de Teams (versión preliminar privada), tendrá que incluir lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6e163-109">To set up the Teams Learning app (private preview), you'll need to involve:</span></span>

-   <span data-ttu-id="6e163-110">Administración del centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="6e163-110">Teams admin center admin</span></span>
-   <span data-ttu-id="6e163-111">Administrador del centro de administración de Microsoft 365 (es decir, un administrador global)</span><span class="sxs-lookup"><span data-stu-id="6e163-111">Microsoft 365 admin center admin (that is, a global admin)</span></span>
-   <span data-ttu-id="6e163-112">Administrador de conocimientos (un nuevo rol del centro de administración de Microsoft 365 que un administrador global (también conocido como administrador de ti o administrador de Microsoft 365) pueda asignar a cualquier persona de la organización.</span><span class="sxs-lookup"><span data-stu-id="6e163-112">Knowledge admin (a new role in the Microsoft 365 admin center that a global admin (also known as IT admin or Microsoft 365 admin) can assign to anyone in the organization.</span></span> <span data-ttu-id="6e163-113">Esta función administra las fuentes de contenido de aprendizaje de la organización a través del centro de administración de Microsoft 365.)</span><span class="sxs-lookup"><span data-stu-id="6e163-113">This role manages the organization’s learning content sources through the Microsoft 365 admin center.)</span></span> 

## <a name="manage-the-teams-learning-app-private-preview-in-the-teams-admin-center"></a><span data-ttu-id="6e163-114">Administrar la aplicación de aprendizaje de Teams (versión preliminar privada) en el centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="6e163-114">Manage the Teams Learning app (private preview) in the Teams admin center</span></span>

<span data-ttu-id="6e163-115">El administrador de Teams instala la aplicación de aprendizaje de Teams (versión preliminar privada) desde el App Store y aplica las directivas de configuración, administración y permisos de la aplicación a través del centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="6e163-115">The Teams admin installs the Teams Learning app (private preview) from the app store and applies app setup, manage, and permissions policies through the Teams admin center.</span></span>

### <a name="manage-the-teams-learning-app-private-preview"></a><span data-ttu-id="6e163-116">Administrar la aplicación de aprendizaje de Teams (vista previa privada)</span><span class="sxs-lookup"><span data-stu-id="6e163-116">Manage the Teams Learning app (private preview)</span></span>

<span data-ttu-id="6e163-117">Para administrar la configuración de la aplicación, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="6e163-117">To manage settings for app, follow these steps:</span></span>

1. <span data-ttu-id="6e163-118">En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a **aplicaciones de Teams**  >  **Manage apps**.</span><span class="sxs-lookup"><span data-stu-id="6e163-118">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Navegación izquierda en el centro de administración de teams que muestra la sección aplicaciones de Teams y administrar aplicaciones](media/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="6e163-120">En la página **Manage apps** , en el cuadro de búsqueda, escriba *Learning* para buscar la aplicación de aprendizaje de Teams (versión preliminar privada).</span><span class="sxs-lookup"><span data-stu-id="6e163-120">On the **Manage apps** page, in the search box, type *learning* to search for the Teams Learning app (private preview).</span></span>

   ![Página Administrar aplicaciones en el centro de administración de teams que muestra el cuadro de búsqueda](media/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="6e163-122">En la página de **aprendizaje** :</span><span class="sxs-lookup"><span data-stu-id="6e163-122">On the **Learning** page:</span></span>
   1. <span data-ttu-id="6e163-123">En **Estado**, seleccione **permitido** activar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6e163-123">Under **Status**, select **Allowed** to turn on the app.</span></span>
   2. <span data-ttu-id="6e163-124">En la pestaña **configuración** , en la sección configuración de la **aplicación** , vaya al centro de administración de Microsoft 365 para configurar orígenes de contenido de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="6e163-124">On the **Settings** tab, in the **App settings** section, go to the Microsoft 365 admin center to configure learning content sources.</span></span>

   ![Página de aprendizaje en el centro de administración de teams que muestra la sección configuración de la aplicación y estado](media/learning-app-teams-learning-page.png)

4. <span data-ttu-id="6e163-126">Después de administrar la configuración de la **aplicación** , vaya a **permisos y directivas de configuración** para conceder permisos a los empleados que deberían tener acceso a la aplicación como parte de la participación de su organización en la versión preliminar privada.</span><span class="sxs-lookup"><span data-stu-id="6e163-126">After **Manage app** settings, go to **Permissions and Set-up policies** to grant permission to employees who should have access to the app as part of your organization's participation in the private preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="6e163-127">Si su organización está en anillo 4,0 como parte del programa Team TAP100, es posible que tenga que hacer lo siguiente para habilitar a los usuarios aprobados en ring 3,0 para acceder a la aplicación de aprendizaje de Teams (versión preliminar privada).</span><span class="sxs-lookup"><span data-stu-id="6e163-127">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to do the following to enable approved users in Ring 3.0 to access the Teams Learning app (private preview).</span></span>

<span data-ttu-id="6e163-128">Como parte de la versión preliminar privada, la aplicación de aprendizaje de Teams (Private Preview) se publica en el anillo 3,0.</span><span class="sxs-lookup"><span data-stu-id="6e163-128">As part of private preview, the Teams Learning app (private preview) is released in Ring 3.0.</span></span> <span data-ttu-id="6e163-129">Si su organización está en timbre 4,0, no verá la aplicación en App Store.</span><span class="sxs-lookup"><span data-stu-id="6e163-129">If your organization is in Ring 4.0, you won’t see the app in the app store.</span></span> <span data-ttu-id="6e163-130">Para probar la aplicación, debe crear una directiva de permisos de aplicaciones personalizadas, establecerla para **permitir todas las aplicaciones** y asignarla a timbre 3,0 usuarios aprobados.</span><span class="sxs-lookup"><span data-stu-id="6e163-130">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span>

   ![TOQUE-AppsPermission-Plcy página que muestra permitir todas las aplicaciones seleccionadas](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a><span data-ttu-id="6e163-132">Configurar orígenes de contenido de aprendizaje en el centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6e163-132">Configure learning content sources in the Microsoft 365 admin center</span></span>

<span data-ttu-id="6e163-133">Los administradores del centro de administración de Microsoft 365 (ya sea por sí solos o asignando el rol de administrador de conocimiento a determinadas personas de su organización) pueden administrar la configuración relacionada con la aplicación de aprendizaje de Teams (versión preliminar privada) y pueden configurar los orígenes de contenido de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="6e163-133">The admins for the Microsoft 365 admin center—either by themselves or by assigning the Knowledge admin role to selected individuals in your organization—can manage settings related to the Teams Learning app (private preview) and can configure the learning content sources.</span></span>

> [!TIP]
> <span data-ttu-id="6e163-134">El administrador de conocimiento debe ser moderadomente técnico y tener credenciales de administrador de SharePoint, preferiblemente alguien que esté bien en la experiencia de educación, aprendizaje, formación o empleados de la organización.</span><span class="sxs-lookup"><span data-stu-id="6e163-134">The Knowledge admin should be moderately technical and have existing SharePoint admin credentials, preferably someone who is well-versed in the education, learning, training, or employee experience part of the organization.</span></span>
 
<span data-ttu-id="6e163-135">El administrador selecciona qué orígenes de contenido de aprendizaje (como LinkedIn Learning o SharePoint) estarán disponibles en la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6e163-135">The admin selects which learning content sources (such as LinkedIn Learning or SharePoint) will be available in the app.</span></span> <span data-ttu-id="6e163-136">Después, el administrador configura esos orígenes para asegurarse de que el contenido esté disponible para la búsqueda y la detección y que los empleados que usen la aplicación puedan examinarlo.</span><span class="sxs-lookup"><span data-stu-id="6e163-136">The admin then configures those sources to make sure the content is available for search and discovery and can be browsed by the employees who use the app.</span></span>

### <a name="assign-the-knowledge-admin-role-optional"></a><span data-ttu-id="6e163-137">Asignar el rol de administrador de conocimiento [opcional]</span><span class="sxs-lookup"><span data-stu-id="6e163-137">Assign the Knowledge admin role [Optional]</span></span>

<span data-ttu-id="6e163-138">El administrador del centro de administración de Microsoft 365 debe realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6e163-138">These steps are to be performed by the admin for the Microsoft 365 admin center.</span></span>

1.  <span data-ttu-id="6e163-139">En el centro de navegación izquierdo del centro de administración de Microsoft 365, vaya a **roles**.</span><span class="sxs-lookup"><span data-stu-id="6e163-139">In the left navigation of the Microsoft 365 admin center, go to **Roles**.</span></span>

2.  <span data-ttu-id="6e163-140">En la página **roles** , en la pestaña **Azure ad** , seleccione **Administrador de conocimiento**.</span><span class="sxs-lookup"><span data-stu-id="6e163-140">On the **Roles** page, on the **Azure AD** tab, select **Knowledge admin**.</span></span>
 
3.  <span data-ttu-id="6e163-141">En la página **Administración de conocimientos** , en la sección **administradores asignados** , seleccione **Agregar** y, a continuación, agregue la persona que elija para el rol.</span><span class="sxs-lookup"><span data-stu-id="6e163-141">On the **Knowledge admin** page, in the **Assigned Admins** section, select **Add**, and then add the person you choose for the role.</span></span>

### <a name="configure-settings-for-the-learning-content-sources-for-the-app"></a><span data-ttu-id="6e163-142">Establecer la configuración de los orígenes de contenido de aprendizaje para la aplicación</span><span class="sxs-lookup"><span data-stu-id="6e163-142">Configure settings for the learning content sources for the app</span></span>

<span data-ttu-id="6e163-143">Estos pasos son realizados por el administrador de Microsoft 365 o el administrador de la información.</span><span class="sxs-lookup"><span data-stu-id="6e163-143">These steps are to be performed by the Microsoft 365 admin or the Knowledge admin.</span></span>

1.  <span data-ttu-id="6e163-144">En el centro de navegación izquierdo del centro de administración de Microsoft 365, vaya a **configuración** de la  >  **organización configuración**.</span><span class="sxs-lookup"><span data-stu-id="6e163-144">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>

2.  <span data-ttu-id="6e163-145">En la página **configuración** , en la pestaña **servicios & complementos** , seleccione aplicación de **aprendizaje**.</span><span class="sxs-lookup"><span data-stu-id="6e163-145">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![Página configuración en el centro de administración de Microsoft 365 que muestra la aplicación de aprendizaje de la lista](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="6e163-147">En el panel de la **aplicación de aprendizaje** , seleccione los orígenes de contenido de aprendizaje que desea configurar para la organización y, a continuación, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6e163-147">On the **Learning app** panel, select the learning content sources you want to configure for the organization, and then select **Save**.</span></span>

   ![Panel de la aplicación de aprendizaje en el centro de administración de Microsoft 365 que muestra las opciones de orígenes de contenido](media/learning-app-365-settings-learning-app-panel.png)

<span data-ttu-id="6e163-149">Entre todas las fuentes de aprendizaje que existen, algunas estarán habilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6e163-149">Among all the learning sources that exist, some will be enabled by default.</span></span> <span data-ttu-id="6e163-150">Estas afectan a los siguientes aspectos, entre otros:</span><span class="sxs-lookup"><span data-stu-id="6e163-150">These include:</span></span>

- <span data-ttu-id="6e163-151">LinkedIn Learning (contenido gratuito)</span><span class="sxs-lookup"><span data-stu-id="6e163-151">LinkedIn Learning (free content)</span></span>
- <span data-ttu-id="6e163-152">Aprendizaje de Microsoft</span><span class="sxs-lookup"><span data-stu-id="6e163-152">Microsoft Learn</span></span>
- <span data-ttu-id="6e163-153">Formación de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6e163-153">Microsoft 365 Training</span></span>

> [!NOTE]
> <span data-ttu-id="6e163-154">Si su organización tiene una suscripción estándar o Pro de LinkedIn Learning, el repositorio de contenido se desbloqueará para los empleados de su organización.</span><span class="sxs-lookup"><span data-stu-id="6e163-154">If your organization has a LinkedIn Learning Standard or Pro subscription, the content repository will be unlocked for the employees in your organization.</span></span> <span data-ttu-id="6e163-155">Solo aquellos empleados que tengan permiso podrán usar todo el repositorio de contenido.</span><span class="sxs-lookup"><span data-stu-id="6e163-155">Only those employees who have permission will be able to use the entire content repository.</span></span>

<span data-ttu-id="6e163-156">Es posible que otros orígenes deban habilitarse o configurarse de forma manual.</span><span class="sxs-lookup"><span data-stu-id="6e163-156">Other sources might need to be enabled or configured manually.</span></span> <span data-ttu-id="6e163-157">Las fuentes de aprendizaje que no son de Microsoft tienen una licencia independiente entre su organización y el tercero.</span><span class="sxs-lookup"><span data-stu-id="6e163-157">Learning sources that are not from Microsoft are separately licensed between your organization and the third party.</span></span> <span data-ttu-id="6e163-158">Tendrá que comprobar que se ha suscrito a su aprendizaje para usted y sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="6e163-158">You’ll need to verify you’ve signed up for their learning for you and your users.</span></span>

<span data-ttu-id="6e163-159">Para habilitar o deshabilitar un origen de contenido de aprendizaje, active la casilla situada junto al origen.</span><span class="sxs-lookup"><span data-stu-id="6e163-159">To enable or disable a learning content source, select the check box next to the source.</span></span> <span data-ttu-id="6e163-160">Si un origen está habilitado, aparecerá una marca de verificación.</span><span class="sxs-lookup"><span data-stu-id="6e163-160">If a source is enabled, a check mark will be visible.</span></span>

## <a name="configure-sharepoint-as-a-learning-content-source"></a><span data-ttu-id="6e163-161">Configurar SharePoint como origen de contenido de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="6e163-161">Configure SharePoint as a learning content source</span></span>

<span data-ttu-id="6e163-162">La configuración de SharePoint como origen de contenido de aprendizaje para la aplicación de aprendizaje de Teams (Private Private Preview) en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6e163-162">You configure SharePoint as a learning content source for the Teams Learning app (private preview) in the Microsoft 365 admin center.</span></span>

### <a name="overview"></a><span data-ttu-id="6e163-163">Información general</span><span class="sxs-lookup"><span data-stu-id="6e163-163">Overview</span></span>

<span data-ttu-id="6e163-164">El administrador de conocimiento proporciona una dirección URL de sitio en la que el servicio de aprendizaje puede crear un repositorio de contenido centralizado de aprendizaje en forma de una lista estructurada de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="6e163-164">The Knowledge admin provides a site URL to where the Learning Service can create an empty centralized learning content repository in the form of a structured SharePoint list.</span></span> <span data-ttu-id="6e163-165">Esta lista puede ser usada por la organización para hospedar vínculos a carpetas de SharePoint entre empresas que contengan contenido de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="6e163-165">This list can be used by the organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="6e163-166">Los administradores son responsables de recopilar y organizar una lista de direcciones URL para las carpetas.</span><span class="sxs-lookup"><span data-stu-id="6e163-166">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="6e163-167">Estas carpetas solo deben incluir contenido que pueda estar disponible en la aplicación de aprendizaje de Teams (versión preliminar privada).</span><span class="sxs-lookup"><span data-stu-id="6e163-167">These folders should only include content that can be made available in the Teams Learning app (private preview).</span></span>

### <a name="permissions"></a><span data-ttu-id="6e163-168">Permisos</span><span class="sxs-lookup"><span data-stu-id="6e163-168">Permissions</span></span>

<span data-ttu-id="6e163-169">Las direcciones URL de carpeta se pueden recopilar desde cualquier sitio de SharePoint de la organización.</span><span class="sxs-lookup"><span data-stu-id="6e163-169">Folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="6e163-170">El contenido dentro de estas carpetas se puede buscar, pero solo se puede usar el contenido al que tiene permiso el empleado individual.</span><span class="sxs-lookup"><span data-stu-id="6e163-170">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>
 
### <a name="learning-service"></a><span data-ttu-id="6e163-171">Servicio de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="6e163-171">Learning Service</span></span>

<span data-ttu-id="6e163-172">El servicio de aprendizaje usa las direcciones URL de carpeta proporcionadas para obtener metadatos de todo el contenido almacenado en esas carpetas.</span><span class="sxs-lookup"><span data-stu-id="6e163-172">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="6e163-173">Dentro de las 24 horas de suministrar la URL de la carpeta en el repositorio centralizado, los empleados pueden buscar y usar el contenido de la compañía dentro de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="6e163-173">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use the company’s content within the app.</span></span> <span data-ttu-id="6e163-174">En este punto no se admite la eliminación de contenido del repositorio.</span><span class="sxs-lookup"><span data-stu-id="6e163-174">Content deletion from the repository isn't supported at this point.</span></span> <span data-ttu-id="6e163-175">El contenido de superficie no intencional solo se puede quitar si se proporciona una nueva dirección URL de sitio de SharePoint en el centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6e163-175">Unintentionally surfaced content can only be removed by supplying a new SharePoint site URL in the Microsoft 365 admin center.</span></span>

### <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="6e163-176">Configurar SharePoint como origen</span><span class="sxs-lookup"><span data-stu-id="6e163-176">Configure SharePoint as a source</span></span>

<span data-ttu-id="6e163-177">Estos pasos son realizados por el administrador de Microsoft 365 o el administrador de la información.</span><span class="sxs-lookup"><span data-stu-id="6e163-177">These steps are to be performed by Microsoft 365 admin or the Knowledge admin.</span></span>

1.  <span data-ttu-id="6e163-178">En el centro de navegación izquierdo del centro de administración de Microsoft 365, vaya a **configuración**.</span><span class="sxs-lookup"><span data-stu-id="6e163-178">In the left navigation of the Microsoft 365 admin center, go to **Settings**.</span></span>
 
2.  <span data-ttu-id="6e163-179">En la página **configuración** , en la pestaña **servicios & complementos** , seleccione aplicación de **aprendizaje**.</span><span class="sxs-lookup"><span data-stu-id="6e163-179">On the **Settings** page, on the **Services & add-ins** tab, select **Learning app**.</span></span>

   ![Página configuración en el centro de administración de Microsoft 365 que muestra la aplicación de aprendizaje de la lista](media/learning-app-365-settings-page.png)

3.  <span data-ttu-id="6e163-181">En el panel de la **aplicación de aprendizaje** , proporcione la dirección URL del sitio al sitio de SharePoint donde quiere que la aplicación cree un repositorio centralizado.</span><span class="sxs-lookup"><span data-stu-id="6e163-181">On the **Learning app** panel, provide the site URL to the SharePoint site where you want the app to create a centralized repository.</span></span>

   ![Panel de la aplicación de aprendizaje en el centro de administración de Microsoft 365 que muestra SharePoint seleccionado](media/learning-app-365-panel-sharepoint-selected.png)

4.  <span data-ttu-id="6e163-183">Se crea automáticamente una lista de SharePoint dentro del sitio de SharePoint de la organización proporcionada.</span><span class="sxs-lookup"><span data-stu-id="6e163-183">A SharePoint list is created automatically within the provided organization’s SharePoint site.</span></span> <span data-ttu-id="6e163-184">En el sitio de navegación izquierdo del sitio de SharePoint, seleccione repositorio de contenido de la **aplicación de aprendizaje**.</span><span class="sxs-lookup"><span data-stu-id="6e163-184">In the left navigation of the SharePoint site, select **Learning App Content Repository**.</span></span> 

   ![Navegación izquierda en SharePoint que muestra la sección repositorio de contenido de la aplicación de aprendizaje](media/learning-app-content-repository-nav.png)

 
5. <span data-ttu-id="6e163-186">En la página del repositorio de contenido de la **aplicación de aprendizaje** , rellene la lista de SharePoint con direcciones URL para las carpetas de contenido de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="6e163-186">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1.   <span data-ttu-id="6e163-187">Seleccione **nuevo** para ver el panel de **elementos nuevos** .</span><span class="sxs-lookup"><span data-stu-id="6e163-187">Select **New** to view the **New item** panel.</span></span> 

   ![Página del repositorio de contenido de la aplicación de aprendizaje de SharePoint que muestra la opción nuevo](media/learning-app-content-repository-new.png)
 
   2.   <span data-ttu-id="6e163-189">En el panel **nuevo elemento** , en el campo **título** , agregue un nombre de directorio de su elección.</span><span class="sxs-lookup"><span data-stu-id="6e163-189">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="6e163-190">En el campo **dirección URL** de la carpeta, agregue la dirección URL a la carpeta de contenido de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="6e163-190">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="6e163-191">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="6e163-191">Select **Save**.</span></span>

   ![Nuevo panel de elementos en SharePoint que muestra los campos de dirección URL de título y carpeta](media/learning-app-new-item-panel.png)

   3. <span data-ttu-id="6e163-193">La página del repositorio de contenido de la aplicación de aprendizaje se actualiza con el nuevo contenido de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="6e163-193">The Learning App Content Repository page is updated with the new learning content.</span></span>

   ![Página del repositorio de contenido de la aplicación de aprendizaje de SharePoint que muestra la información actualizada](media/learning-app-content-repository-populated.png)


 


