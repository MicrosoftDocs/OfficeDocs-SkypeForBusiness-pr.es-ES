---
title: Instalar, administrar y asignar permisos para Microsoft Viva Learning (versión preliminar privada)
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
description: Use Microsoft Viva Learning (versión preliminar privada) para crear un centro central de aprendizaje donde los empleados puedan compartir, asignar y aprender de bibliotecas de contenido de una organización.
f1.keywords: ''
appliesto:
- Microsoft Teams
ms.custom: ''
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 3b99cdcd49dc35a558d6217e28bf57bbb8563827
ms.sourcegitcommit: b56727299d7ea47e23807114a4f5881e289c0b6a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2021
ms.locfileid: "51880384"
---
# <a name="install-manage-and-assign-permissions-for-microsoft-viva-learning-private-preview"></a><span data-ttu-id="8b19e-103">Instalar, administrar y asignar permisos para Microsoft Viva Learning (versión preliminar privada)</span><span class="sxs-lookup"><span data-stu-id="8b19e-103">Install, manage, and assign permissions for Microsoft Viva Learning (private preview)</span></span>

<span data-ttu-id="8b19e-104">*Este artículo contiene contenido preliminar para Microsoft Viva Learning, que está en versión preliminar privada.*</span><span class="sxs-lookup"><span data-stu-id="8b19e-104">*This article contains preliminary content for Microsoft Viva Learning, which is in private preview.*</span></span>

<span data-ttu-id="8b19e-105">Microsoft Viva Learning (versión preliminar privada) permite a los equipos e individuos de su organización hacer que el aprendizaje sea una parte natural de su día.</span><span class="sxs-lookup"><span data-stu-id="8b19e-105">Microsoft Viva Learning (private preview) empowers teams and individuals in your organization to make learning a natural part of their day.</span></span> <span data-ttu-id="8b19e-106">La aplicación crea un concentrador central en Teams donde los empleados pueden compartir, asignar y aprender de bibliotecas de contenido de toda la organización.</span><span class="sxs-lookup"><span data-stu-id="8b19e-106">The app creates a central hub in Teams where employees can share, assign, and learn from content libraries across your organization.</span></span>

<span data-ttu-id="8b19e-107">Los administradores establecen permisos y permiten orígenes de contenido de aprendizaje para Viva Learning (versión preliminar privada).</span><span class="sxs-lookup"><span data-stu-id="8b19e-107">Admins set permissions and allow learning content sources for Viva Learning (private preview).</span></span> <span data-ttu-id="8b19e-108">El contenido de aprendizaje puede incluir LinkedIn Learning, Microsoft Learn, aprendizaje de Microsoft 365, contenido propio de su organización almacenado en SharePoint Online y proveedores de terceros compatibles con Viva Learning (versión preliminar privada).</span><span class="sxs-lookup"><span data-stu-id="8b19e-108">Learning content can include LinkedIn Learning, Microsoft Learn, Microsoft 365 training, your organization's own content stored in SharePoint online, and third-party providers that are supported by Viva Learning (private preview).</span></span>

## <a name="admin-roles"></a><span data-ttu-id="8b19e-109">Roles de administrador</span><span class="sxs-lookup"><span data-stu-id="8b19e-109">Admin roles</span></span>

<span data-ttu-id="8b19e-110">Para configurar Viva Learning (versión preliminar privada), necesitará permisos como:</span><span class="sxs-lookup"><span data-stu-id="8b19e-110">To set up Viva Learning (private preview), you'll need permissions as:</span></span>

- <span data-ttu-id="8b19e-111">Administrador de Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8b19e-111">Microsoft Teams admin</span></span>
- <span data-ttu-id="8b19e-112">Administrador global de Microsoft 365 o administrador de SharePoint</span><span class="sxs-lookup"><span data-stu-id="8b19e-112">Microsoft 365 global administrator or SharePoint administrator</span></span>
- <span data-ttu-id="8b19e-113">Administrador de conocimientos: este es un nuevo rol en el Centro de administración de Microsoft 365 que se puede asignar a cualquier persona de la organización.</span><span class="sxs-lookup"><span data-stu-id="8b19e-113">Knowledge admin — This is a new role in the Microsoft 365 admin center that can be assigned to anyone in the organization.</span></span> <span data-ttu-id="8b19e-114">Este rol administra los orígenes de contenido de aprendizaje de la organización a través del Centro de administración de Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8b19e-114">This role manages the organization’s learning content sources through the Microsoft 365 admin center.</span></span> 

> [!TIP]
> <span data-ttu-id="8b19e-115">El administrador de conocimientos debe ser moderadamente técnico y tener credenciales de administrador de SharePoint existentes, preferiblemente alguien que tenga una buena experiencia en el sector educativo, de aprendizaje, de aprendizaje o de experiencia de empleados de la organización.</span><span class="sxs-lookup"><span data-stu-id="8b19e-115">The knowledge admin should be moderately technical and have existing SharePoint admin credentials, preferably someone who is well-versed in the education, learning, training, or employee experience part of the organization.</span></span>
 
## <a name="manage-viva-learning-private-preview-in-the-teams-admin-center"></a><span data-ttu-id="8b19e-116">Administrar Viva Learning (versión preliminar privada) en el Centro de administración de Teams</span><span class="sxs-lookup"><span data-stu-id="8b19e-116">Manage Viva Learning (private preview) in the Teams admin center</span></span>

<span data-ttu-id="8b19e-117">El administrador de Teams instala Viva Learning (versión preliminar privada) desde la tienda de aplicaciones y, a continuación, aplica directivas de configuración, administración y permisos a través del Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="8b19e-117">The Teams admin installs Viva Learning (private preview) from the app store, and then applies setup, manage, and permission policies through the Teams admin center.</span></span>

### <a name="manage-settings-for-viva-learning-private-preview"></a><span data-ttu-id="8b19e-118">Administrar la configuración de Viva Learning (versión preliminar privada)</span><span class="sxs-lookup"><span data-stu-id="8b19e-118">Manage settings for Viva Learning (private preview)</span></span>

<span data-ttu-id="8b19e-119">Debe ser administrador en el Centro de administración de Teams para realizar estas tareas.</span><span class="sxs-lookup"><span data-stu-id="8b19e-119">You must be an administrator in the Teams admin center to perform these tasks.</span></span>

<span data-ttu-id="8b19e-120">Para administrar la configuración de Viva Learning, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8b19e-120">To manage settings for Viva Learning, follow these steps:</span></span>

1. <span data-ttu-id="8b19e-121">En el panel de navegación izquierdo del Centro de administración de Teams, vaya a **Aplicaciones de Teams Administrar**  >  **aplicaciones.**</span><span class="sxs-lookup"><span data-stu-id="8b19e-121">In the left navigation of the Teams admin center, go to **Teams apps** > **Manage apps**.</span></span>

   ![Navegación izquierda en el Centro de administración de Teams que muestra las aplicaciones de Teams y la sección Administrar aplicaciones](media/learning-app-teams-manage-apps-nav.png)

2. <span data-ttu-id="8b19e-123">En la **página Administrar aplicaciones,** en el cuadro de búsqueda, escriba *Aprendizaje* para buscar la aplicación Teams Learning (vista previa privada).</span><span class="sxs-lookup"><span data-stu-id="8b19e-123">On the **Manage apps** page, in the search box, type *learning* to search for the Teams Learning app (private preview).</span></span>

   ![Página Administrar aplicaciones en el Centro de administración de Teams que muestra el cuadro de búsqueda](media/learning-app-teams-manage-apps-page.png)

3. <span data-ttu-id="8b19e-125">En la **página Aprendizaje:**</span><span class="sxs-lookup"><span data-stu-id="8b19e-125">On the **Learning** page:</span></span>
   1. <span data-ttu-id="8b19e-126">En **Estado,** seleccione **Permitido** para activar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="8b19e-126">Under **Status**, select **Allowed** to turn on the app.</span></span>
   2. <span data-ttu-id="8b19e-127">En la **pestaña Configuración,** en la sección **Configuración de** la aplicación, vaya al Centro de administración de Microsoft 365 para configurar orígenes de contenido de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="8b19e-127">On the **Settings** tab, in the **App settings** section, go to the Microsoft 365 admin center to configure learning content sources.</span></span>

   ![Página de aprendizaje en el Centro de administración de Teams que muestra la sección Configuración de estado y aplicación](media/learning-app-teams-learning-page.png)

4. <span data-ttu-id="8b19e-129">Después **de** administrar la configuración de la aplicación, vaya a Permisos y directivas de configuración para conceder permisos a los **empleados** que deben tener acceso a la aplicación como parte de la participación de su organización en la vista previa privada.</span><span class="sxs-lookup"><span data-stu-id="8b19e-129">After **Manage app** settings, go to **Permissions and Set-up policies** to grant permission to employees who should have access to the app as part of your organization's participation in the private preview.</span></span>

> [!NOTE]
>  <span data-ttu-id="8b19e-130">Si su organización está en Anillo 4.0 como parte del programa TAP100 de Teams, es posible que deba hacer lo siguiente para permitir que los usuarios aprobados en Anillo 3.0 accedan a Viva Learning (versión preliminar privada).</span><span class="sxs-lookup"><span data-stu-id="8b19e-130">If your organization is in Ring 4.0 as part of Teams TAP100 program, you might need to do the following to enable approved users in Ring 3.0 to access Viva Learning (private preview).</span></span>

<span data-ttu-id="8b19e-131">Como parte de la vista previa privada, Viva Learning (versión preliminar privada) se publica en Anillo 3.0.</span><span class="sxs-lookup"><span data-stu-id="8b19e-131">As part of private preview, Viva Learning (private preview) is released in Ring 3.0.</span></span> <span data-ttu-id="8b19e-132">Si su organización está en Anillo 4.0, no verá la aplicación en la tienda de aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="8b19e-132">If your organization is in Ring 4.0, you won’t see the app in the app store.</span></span> <span data-ttu-id="8b19e-133">Para probar la aplicación, debe crear una directiva de permisos de aplicaciones personalizadas, establecerla en Permitir todas las aplicaciones y asignarla a usuarios aprobados en Ring 3.0.</span><span class="sxs-lookup"><span data-stu-id="8b19e-133">To test the app, you need to create a custom apps permission policy, set it to **Allow all apps**, and assign it to Ring 3.0 approved users.</span></span>

   ![Página TAP-AppsPermission-Plcy que muestra Permitir todas las aplicaciones seleccionadas](media/learning-app-tap-appspermission-plcy.png)

## <a name="configure-learning-content-sources-in-the-microsoft-365-admin-center"></a><span data-ttu-id="8b19e-135">Configurar orígenes de contenido de aprendizaje en el Centro de administración de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8b19e-135">Configure learning content sources in the Microsoft 365 admin center</span></span>

<span data-ttu-id="8b19e-136">Los administradores del Centro de administración de Microsoft 365, ya sea por su cuenta o asignando el rol de administrador de conocimientos a individuos seleccionados de su organización, pueden administrar la configuración relacionada con Viva Learning (versión preliminar privada) y pueden configurar los orígenes de contenido de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="8b19e-136">The administrators for the Microsoft 365 admin center—either by themselves or by assigning the knowledge admin role to selected individuals in your organization—can manage settings related to Viva Learning (private preview) and can configure the learning content sources.</span></span>

<span data-ttu-id="8b19e-137">El administrador selecciona qué orígenes de contenido de aprendizaje adicionales (por ejemplo, SharePoint o orígenes de proveedores de contenido de terceros compatibles) estarán disponibles para los usuarios de Viva Learning (versión preliminar privada).</span><span class="sxs-lookup"><span data-stu-id="8b19e-137">The administrator selects which additional learning content sources (for example, SharePoint or supported third-party content provider sources) will be available to users of Viva Learning (private preview).</span></span> <span data-ttu-id="8b19e-138">A continuación, el administrador configura esos orígenes para asegurarse de que el contenido está disponible para la búsqueda y detección y puede ser explorado por los empleados que usan Viva Learning (versión preliminar privada).</span><span class="sxs-lookup"><span data-stu-id="8b19e-138">The admin then configures those sources to make sure the content is available for search and discovery and can be browsed by the employees who use Viva Learning (private preview).</span></span>

> [!NOTE]
>  <span data-ttu-id="8b19e-139">Los usuarios inician sesión en aprendizajes que no son de Microsoft y LinkedIn Learning Pro en un explorador o visor incrustado.</span><span class="sxs-lookup"><span data-stu-id="8b19e-139">Users sign in to non-Microsoft and LinkedIn Learning Pro learnings in a browser or embedded viewer.</span></span> <span data-ttu-id="8b19e-140">Este aprendizaje configurado está sujeto a los términos de licencia, privacidad y servicio independientes entre su organización y los terceros, y no a los términos de Viva Learning (versión preliminar privada).</span><span class="sxs-lookup"><span data-stu-id="8b19e-140">This configured learning is subject to the separate license, privacy and service terms between your organization and the third party, and not the Viva Learning (private preview) terms.</span></span> <span data-ttu-id="8b19e-141">Antes de seleccionar este tipo de aprendizaje, compruebe que tiene un acuerdo para su organización y los usuarios.</span><span class="sxs-lookup"><span data-stu-id="8b19e-141">Before selecting this type of learning, verify you have an agreement in place for your organization and users.</span></span>

### <a name="assign-the-knowledge-admin-role-optional"></a><span data-ttu-id="8b19e-142">Asignar el rol de administrador de conocimientos [Opcional]</span><span class="sxs-lookup"><span data-stu-id="8b19e-142">Assign the knowledge admin role [Optional]</span></span>

<span data-ttu-id="8b19e-143">Debe ser administrador global de Microsoft 365 para realizar estas tareas.</span><span class="sxs-lookup"><span data-stu-id="8b19e-143">You must be a Microsoft 365 global administrator to perform these tasks.</span></span>

<span data-ttu-id="8b19e-144">Para asignar un administrador de conocimientos para Viva Learning, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8b19e-144">To assign a knowledge admin for Viva Learning, follow these steps:</span></span>

1.  <span data-ttu-id="8b19e-145">En el panel de navegación izquierdo del Centro de administración de Microsoft 365, vaya a **Roles**.</span><span class="sxs-lookup"><span data-stu-id="8b19e-145">In the left navigation of the Microsoft 365 admin center, go to **Roles**.</span></span>

2.  <span data-ttu-id="8b19e-146">En la **página Roles,** en la pestaña **Azure AD,** seleccione **Administrador de conocimientos.**</span><span class="sxs-lookup"><span data-stu-id="8b19e-146">On the **Roles** page, on the **Azure AD** tab, select **Knowledge admin**.</span></span>
 
3.  <span data-ttu-id="8b19e-147">En la **página Administrador de** conocimientos, en la sección Administradores **asignados,** seleccione Agregar **y,** a continuación, agregue la persona que elija para el rol.</span><span class="sxs-lookup"><span data-stu-id="8b19e-147">On the **Knowledge admin** page, in the **Assigned Admins** section, select **Add**, and then add the person you choose for the role.</span></span>

### <a name="configure-settings-for-the-learning-content-sources-for-viva-learning-private-preview"></a><span data-ttu-id="8b19e-148">Configurar la configuración de los orígenes de contenido de aprendizaje para Viva Learning (versión preliminar privada)</span><span class="sxs-lookup"><span data-stu-id="8b19e-148">Configure settings for the learning content sources for Viva Learning (private preview)</span></span>

<span data-ttu-id="8b19e-149">Debe ser administrador global de Microsoft 365 o administrador de conocimientos para realizar estas tareas.</span><span class="sxs-lookup"><span data-stu-id="8b19e-149">You must be a Microsoft 365 global administrator or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="8b19e-150">Para configurar la configuración de orígenes de contenido de aprendizaje en Viva Learning, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8b19e-150">To configure settings for learning content sources in Viva Learning, follow these steps:</span></span>

1.  <span data-ttu-id="8b19e-151">En el panel de navegación izquierdo del Centro de administración de Microsoft 365, vaya a **Configuración**  >  **de la organización.**</span><span class="sxs-lookup"><span data-stu-id="8b19e-151">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>

2.  <span data-ttu-id="8b19e-152">En la **página Configuración de la** organización, en la pestaña **Servicios,** seleccione **Aplicación de aprendizaje (vista previa).**</span><span class="sxs-lookup"><span data-stu-id="8b19e-152">On the **Org settings** page, on the **Services** tab, select **Learning app (Preview)**.</span></span>

     ![Página configuración en el Centro de administración de Microsoft 365 que muestra la aplicación Aprendizaje en la lista](media/learning-sharepoint-configure1.png)

3.  <span data-ttu-id="8b19e-154">En el panel De aprendizaje de la aplicación **(vista** previa), seleccione los orígenes de contenido de aprendizaje que desea configurar para la organización y, a continuación, **seleccione Guardar.**</span><span class="sxs-lookup"><span data-stu-id="8b19e-154">On the **Learning app (Preview)** panel, select the learning content sources you want to configure for the organization, and then select **Save**.</span></span>

     ![Panel de aprendizaje en el Centro de administración de Microsoft 365 que muestra las opciones de orígenes de contenido](media/learning-sharepoint-configure2.png)

<span data-ttu-id="8b19e-156">Entre todos los orígenes de aprendizaje que existen, algunos estarán habilitados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="8b19e-156">Among all the learning sources that exist, some will be enabled by default.</span></span> <span data-ttu-id="8b19e-157">Estas afectan a los siguientes aspectos, entre otros:</span><span class="sxs-lookup"><span data-stu-id="8b19e-157">These include:</span></span>

- <span data-ttu-id="8b19e-158">LinkedIn Learning (contenido gratuito)</span><span class="sxs-lookup"><span data-stu-id="8b19e-158">LinkedIn Learning (free content)</span></span>
- <span data-ttu-id="8b19e-159">Microsoft Learn</span><span class="sxs-lookup"><span data-stu-id="8b19e-159">Microsoft Learn</span></span>
- <span data-ttu-id="8b19e-160">Aprendizaje de Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8b19e-160">Microsoft 365 Training</span></span>

> [!NOTE]
> <span data-ttu-id="8b19e-161">Si su organización tiene una suscripción a LinkedIn Learning Standard o Pro, el repositorio de contenido se desbloqueará para los empleados de su organización.</span><span class="sxs-lookup"><span data-stu-id="8b19e-161">If your organization has a LinkedIn Learning Standard or Pro subscription, the content repository will be unlocked for the employees in your organization.</span></span> <span data-ttu-id="8b19e-162">Solo aquellos empleados que tengan permiso podrán usar todo el repositorio de contenido.</span><span class="sxs-lookup"><span data-stu-id="8b19e-162">Only those employees who have permission will be able to use the entire content repository.</span></span> <br><span data-ttu-id="8b19e-163">Es posible que otros orígenes deba habilitarse o configurarse manualmente.</span><span class="sxs-lookup"><span data-stu-id="8b19e-163">Other sources might need to be enabled or configured manually.</span></span> <span data-ttu-id="8b19e-164">Los orígenes de aprendizaje que no son de Microsoft tienen licencia por separado entre su organización y el tercero.</span><span class="sxs-lookup"><span data-stu-id="8b19e-164">Learning sources that are not from Microsoft are separately licensed between your organization and the third party.</span></span> <span data-ttu-id="8b19e-165">Tendrá que comprobar que se ha registrado para su aprendizaje para usted y sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="8b19e-165">You’ll need to verify you’ve signed up for their learning for you and your users.</span></span>

<span data-ttu-id="8b19e-166">Para habilitar o deshabilitar un origen de contenido de aprendizaje, active la casilla situada junto al origen.</span><span class="sxs-lookup"><span data-stu-id="8b19e-166">To enable or disable a learning content source, select the check box next to the source.</span></span> <span data-ttu-id="8b19e-167">Si un origen está habilitado, se mostrará una marca de verificación.</span><span class="sxs-lookup"><span data-stu-id="8b19e-167">If a source is enabled, a check mark will be visible.</span></span>

## <a name="configure-sharepoint-as-a-learning-content-source"></a><span data-ttu-id="8b19e-168">Configurar SharePoint como un origen de contenido de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="8b19e-168">Configure SharePoint as a learning content source</span></span>

<span data-ttu-id="8b19e-169">Puede configurar SharePoint como un origen de contenido de aprendizaje para que el propio contenido de su organización esté disponible en Viva Learning (versión preliminar privada).</span><span class="sxs-lookup"><span data-stu-id="8b19e-169">You can configure SharePoint as a learning content source to make your organization's own content available in Viva Learning (private preview).</span></span>

### <a name="overview"></a><span data-ttu-id="8b19e-170">Información general</span><span class="sxs-lookup"><span data-stu-id="8b19e-170">Overview</span></span>

<span data-ttu-id="8b19e-171">El administrador de conocimientos (o administrador global) proporciona una dirección URL del sitio a la que el servicio de aprendizaje puede crear una ubicación centralizada vacía(el repositorio de contenido de la aplicación de aprendizaje) en forma de lista estructurada de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8b19e-171">The knowledge admin (or global administrator) provides a site URL to where the Learning Service can create an empty centralized location—the Learning App Content Repository—in the form of a structured SharePoint list.</span></span> <span data-ttu-id="8b19e-172">Su organización puede usar esta lista para hospedar vínculos a carpetas de SharePoint entre empresas que contienen contenido de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="8b19e-172">This list can be used by your organization to house links to cross-company SharePoint folders that contain learning content.</span></span> <span data-ttu-id="8b19e-173">Los administradores son responsables de recopilar y curar una lista de direcciones URL de carpetas.</span><span class="sxs-lookup"><span data-stu-id="8b19e-173">Admins are responsible for collecting and curating a list of URLs for folders.</span></span> <span data-ttu-id="8b19e-174">Estas carpetas solo deben incluir contenido que pueda estar disponible en Viva Learning (versión preliminar privada).</span><span class="sxs-lookup"><span data-stu-id="8b19e-174">These folders should only include content that can be made available in Viva Learning (private preview).</span></span>

<span data-ttu-id="8b19e-175">Viva Learning (versión preliminar privada) admite los siguientes tipos de documentos:</span><span class="sxs-lookup"><span data-stu-id="8b19e-175">Viva Learning (private preview) supports the following document types:</span></span>

- <span data-ttu-id="8b19e-176">Word, PowerPoint, Excel, PDF</span><span class="sxs-lookup"><span data-stu-id="8b19e-176">Word, PowerPoint, Excel, PDF</span></span>
- <span data-ttu-id="8b19e-177">Audio (.m4a)</span><span class="sxs-lookup"><span data-stu-id="8b19e-177">Audio (.m4a)</span></span>
- <span data-ttu-id="8b19e-178">Vídeo (.mov, .mp4, .avi)</span><span class="sxs-lookup"><span data-stu-id="8b19e-178">Video (.mov, .mp4, .avi)</span></span>

<span data-ttu-id="8b19e-179">Para obtener más información, vea la [documentación de SharePoint Online.](https://docs.microsoft.com/sharepoint/introductionlink)</span><span class="sxs-lookup"><span data-stu-id="8b19e-179">For more information, see the [SharePoint Online documentation](https://docs.microsoft.com/sharepoint/introductionlink).</span></span> 

### <a name="permissions"></a><span data-ttu-id="8b19e-180">Permisos</span><span class="sxs-lookup"><span data-stu-id="8b19e-180">Permissions</span></span>

<span data-ttu-id="8b19e-181">Las direcciones URL de carpetas de biblioteca de documentos se pueden recopilar desde cualquier sitio de SharePoint de la organización.</span><span class="sxs-lookup"><span data-stu-id="8b19e-181">Document library folder URLs can be collected from any SharePoint site in the organization.</span></span> <span data-ttu-id="8b19e-182">Viva Learning (versión preliminar privada) sigue todos los permisos de contenido existentes.</span><span class="sxs-lookup"><span data-stu-id="8b19e-182">Viva Learning (private preview) follows all existing content permissions.</span></span> <span data-ttu-id="8b19e-183">Por lo tanto, solo el contenido para el que un usuario tiene permiso de acceso es visible y se puede buscar en Viva Learning (versión preliminar privada).</span><span class="sxs-lookup"><span data-stu-id="8b19e-183">Therefore, only content for which a user has permission to access is searchable and visable within Viva Learning (private preview).</span></span> <span data-ttu-id="8b19e-184">Se podrá buscar cualquier contenido dentro de estas carpetas, pero solo se podrá usar el contenido al que el empleado individual tenga permisos.</span><span class="sxs-lookup"><span data-stu-id="8b19e-184">Any content within these folders will be searchable, but only content to which the individual employee has permissions can be used.</span></span>

<span data-ttu-id="8b19e-185">La eliminación de contenido del repositorio de su organización no es compatible actualmente.</span><span class="sxs-lookup"><span data-stu-id="8b19e-185">Content deletion from your organization’s repository is not currently supported.</span></span>

<span data-ttu-id="8b19e-186">Para quitar contenido de superficie involuntarla, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8b19e-186">To remove unintentionally surfaced content, follow these steps:</span></span>

1.  <span data-ttu-id="8b19e-187">Para restringir el acceso en la biblioteca de documentos, seleccione la **opción Mostrar acciones** y, a continuación, seleccione Administrar **acceso.**</span><span class="sxs-lookup"><span data-stu-id="8b19e-187">To restrict access on the document library, select the **Show actions** option, and then select **Manage access**.</span></span>
     
     ![Página de biblioteca de documentos en SharePoint que muestra la opción Mostrar acciones con Administrar acceso altamente disponible.](media/learning-sharepoint-permissions2.png)

2.  <span data-ttu-id="8b19e-189">Elimine el documento original dentro de la biblioteca de documentos.</span><span class="sxs-lookup"><span data-stu-id="8b19e-189">Delete the original document within the document library.</span></span>

<span data-ttu-id="8b19e-190">Para obtener más información, vea [Uso compartido y permisos en la experiencia moderna de SharePoint.](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)</span><span class="sxs-lookup"><span data-stu-id="8b19e-190">For more information, see [Sharing and permissions in the SharePoint modern experience](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions).</span></span> 

### <a name="learning-service"></a><span data-ttu-id="8b19e-191">Servicio de aprendizaje</span><span class="sxs-lookup"><span data-stu-id="8b19e-191">Learning Service</span></span>

<span data-ttu-id="8b19e-192">El servicio de aprendizaje usa las direcciones URL de carpeta proporcionadas para obtener metadatos de todo el contenido almacenado en esas carpetas.</span><span class="sxs-lookup"><span data-stu-id="8b19e-192">The Learning Service uses the provided folder URLs to get metadata from all content stored in those folders.</span></span> <span data-ttu-id="8b19e-193">En un plazo de 24 horas después de proporcionar la dirección URL de carpeta en el repositorio centralizado, los empleados pueden buscar y usar el contenido de su organización en Viva Learning (versión preliminar privada).</span><span class="sxs-lookup"><span data-stu-id="8b19e-193">Within 24 hours of supplying the folder URL in the centralized repository, employees can search for and use your organization’s content within Viva Learning (private preview).</span></span> <span data-ttu-id="8b19e-194">Todos los cambios en el contenido, incluidos los metadatos y permisos actualizados, también se aplicarán en el servicio de aprendizaje en un plazo de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="8b19e-194">All changes to content, including updated metadata and permissions, will also be applied in the Learning Service within 24 hours.</span></span>

### <a name="configure-sharepoint-as-a-source"></a><span data-ttu-id="8b19e-195">Configurar SharePoint como origen</span><span class="sxs-lookup"><span data-stu-id="8b19e-195">Configure SharePoint as a source</span></span>

<span data-ttu-id="8b19e-196">Debe ser administrador global de Microsoft 365, administrador de SharePoint o administrador de conocimientos para realizar estas tareas.</span><span class="sxs-lookup"><span data-stu-id="8b19e-196">You must be a Microsoft 365 global administrator, SharePoint administrator, or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="8b19e-197">Para configurar SharePoint como orígenes de contenido de aprendizaje para Viva Learning (versión preliminar privada), siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8b19e-197">To configure SharePoint as a learning content sources in for Viva Learning (private preview), follow these steps:</span></span>

1.  <span data-ttu-id="8b19e-198">En el panel de navegación izquierdo del Centro de administración de Microsoft 365, vaya a **Configuración**  >  **de la organización.**</span><span class="sxs-lookup"><span data-stu-id="8b19e-198">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>
 
2.  <span data-ttu-id="8b19e-199">En la **página Configuración de la** organización, en la pestaña **Servicios,** seleccione **Aplicación de aprendizaje (vista previa).**</span><span class="sxs-lookup"><span data-stu-id="8b19e-199">On the **Org settings** page, on the **Services** tab, select **Learning app (Preview)**.</span></span>

     ![Página de configuración del Centro de administración de Microsoft 365 que muestra Viva Learning en la lista.](media/learning-sharepoint-configure1.png)

3.  <span data-ttu-id="8b19e-201">En el panel De aprendizaje de la aplicación **(versión preliminar),** en **SharePoint,** proporcione la dirección URL del sitio al sitio de SharePoint donde quiera que Viva Learning cree un repositorio centralizado.</span><span class="sxs-lookup"><span data-stu-id="8b19e-201">On the **Learning app (Preview)** panel, under **SharePoint**, provide the site URL to the SharePoint site where you want Viva Learning to create a centralized repository.</span></span>

     ![Panel de aprendizaje en el Centro de administración de Microsoft 365 que muestra SharePoint seleccionado.](media/learning-sharepoint-configure2.png)

4.  <span data-ttu-id="8b19e-203">Una lista de SharePoint se crea automáticamente en el sitio de SharePoint proporcionado.</span><span class="sxs-lookup"><span data-stu-id="8b19e-203">A SharePoint list is created automatically within the provided SharePoint site.</span></span>

     ![Lista de SharePoint recién creada dentro del sitio de SharePoint.](media/learning-sharepoint-configure3.png)

     <span data-ttu-id="8b19e-205">En el panel de navegación izquierdo del sitio de SharePoint, seleccione Contenido **del** sitio Repositorio de contenido de  >  **la aplicación de aprendizaje.**</span><span class="sxs-lookup"><span data-stu-id="8b19e-205">In the left navigation of the SharePoint site, select **Site contents** > **Learning App Content Repository**.</span></span> 

     ![Lista de SharePoint que muestra la navegación del contenido del sitio y la sección Repositorio de contenido de la aplicación de aprendizaje.](media/learning-sharepoint-configure4.png) 

5. <span data-ttu-id="8b19e-207">En la página Repositorio de contenido de la aplicación **de aprendizaje,** rellene la lista de SharePoint con direcciones URL en las carpetas de contenido de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="8b19e-207">On the **Learning App Content Repository** page, populate the SharePoint list with URLs to the learning content folders.</span></span>

   1. <span data-ttu-id="8b19e-208">Seleccione **Nuevo** para ver el **panel Nuevo** elemento.</span><span class="sxs-lookup"><span data-stu-id="8b19e-208">Select **New** to view the **New item** panel.</span></span> 

       ![Página repositorio de contenido de aprendizaje en SharePoint que muestra la opción Nuevo.](media/learning-sharepoint-configure5.png)
 
   2. <span data-ttu-id="8b19e-210">En el **panel Nuevo elemento,** en el **campo Título,** agregue un nombre de directorio de su elección.</span><span class="sxs-lookup"><span data-stu-id="8b19e-210">On the **New item** panel, in the **Title** field, add a directory name of your choice.</span></span> <span data-ttu-id="8b19e-211">En el **campo Dirección URL de** carpeta, agregue la dirección URL a la carpeta de contenido de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="8b19e-211">In the **Folder URL** field, add the URL to the learning content folder.</span></span> <span data-ttu-id="8b19e-212">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8b19e-212">Select **Save**.</span></span>

       ![Nuevo panel de elementos en SharePoint que muestra los campos Dirección URL de título y carpeta.](media/learning-sharepoint-configure6.png)

   3. <span data-ttu-id="8b19e-214">La página Repositorio de **contenido de la aplicación de** aprendizaje se actualiza con el nuevo contenido de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="8b19e-214">The **Learning App Content Repository** page is updated with the new learning content.</span></span>

       ![Página repositorio de contenido de aprendizaje en SharePoint que muestra la información actualizada.](media/learning-sharepoint-configure7.png)

> [!NOTE]
> <span data-ttu-id="8b19e-216">Para permitir un acceso más amplio al repositorio de contenido de la aplicación de aprendizaje, pronto estará disponible un vínculo a la lista en la interfaz de Viva Learning (versión preliminar privada), donde los usuarios pueden solicitar acceso y, en última instancia, ayudar a rellenar la lista.</span><span class="sxs-lookup"><span data-stu-id="8b19e-216">To allow for broader access to the Learning App Content Repository, a link to the list soon will be available in the Viva Learning (private preview) interface where users can request access and ultimately help populate the list.</span></span> <span data-ttu-id="8b19e-217">Los propietarios del sitio y los administradores globales deberán conceder acceso a la lista.</span><span class="sxs-lookup"><span data-stu-id="8b19e-217">Site owners and global administrators will be required to grant access to the list.</span></span> <span data-ttu-id="8b19e-218">Access es específico de la lista solo y no se aplica al sitio donde se almacena la lista.</span><span class="sxs-lookup"><span data-stu-id="8b19e-218">Access is specific to the list only and does not apply to the site where the list is stored.</span></span>

### <a name="folder-url-document-library-curation"></a><span data-ttu-id="8b19e-219">Curación de la biblioteca de documentos url de carpeta</span><span class="sxs-lookup"><span data-stu-id="8b19e-219">Folder URL document library curation</span></span>

<span data-ttu-id="8b19e-220">Los metadatos predeterminados (como la fecha de modificación, creados por, el nombre del documento, el tipo de contenido y el nombre de la organización) se extraen automáticamente en Viva Learning (versión preliminar privada) mediante la API de Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="8b19e-220">Default metadata (such as modified date, created by, document name, content type, and organization name) is automatically pulled into Viva Learning (private preview) by the Microsoft Graph API.</span></span>
 
<span data-ttu-id="8b19e-221">Para mejorar la relevancia de búsqueda y detección general del contenido, se recomienda agregar una **columna** Descripción.</span><span class="sxs-lookup"><span data-stu-id="8b19e-221">To improve overall discovery and search relevance of the content, we recommend adding a **Description** column.</span></span>

<span data-ttu-id="8b19e-222">Para agregar una columna **Descripción** a la página de la biblioteca de documentos, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8b19e-222">To add a **Description** column to the document library page, follow these steps:</span></span>

1.  <span data-ttu-id="8b19e-223">En la **página Documentos,** seleccione **Agregar columna.**</span><span class="sxs-lookup"><span data-stu-id="8b19e-223">On the **Documents** page, select **Add column**.</span></span>

2. <span data-ttu-id="8b19e-224">Seleccione la **opción Mostrar acciones** y, a continuación, seleccione Una sola línea de **texto.**</span><span class="sxs-lookup"><span data-stu-id="8b19e-224">Select the **Show actions** option, and then select **Single line of text**.</span></span>

     ![Página Documentos en SharePoint que muestra las opciones Mostrar acciones con una sola línea de texto resaltada.](media/learning-sharepoint-curation1.png)

3. <span data-ttu-id="8b19e-226">En el **panel Crear una columna,** en el **campo Nombre,** agregue un nombre descriptivo para la columna.</span><span class="sxs-lookup"><span data-stu-id="8b19e-226">On the **Create a column** panel, in the **Name** field, add a descriptive name for the column.</span></span> <span data-ttu-id="8b19e-227">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="8b19e-227">Select **Save**.</span></span>

     ![Cree un panel de columnas en SharePoint que muestre el nombre y otros campos.](media/learning-sharepoint-curation2.png)
 
4. <span data-ttu-id="8b19e-229">En la **página Documentos,** en la **columna** Descripción, agregue descripciones personalizadas para cada elemento.</span><span class="sxs-lookup"><span data-stu-id="8b19e-229">On the **Documents** page, in the **Description** column, add custom descriptions for each item.</span></span> <span data-ttu-id="8b19e-230">Si no se proporciona ninguna descripción, Viva Learning (versión preliminar privada) proporcionará un mensaje predeterminado que resalta el contenido como de su propia biblioteca de SharePoint.</span><span class="sxs-lookup"><span data-stu-id="8b19e-230">If no description is supplied, Viva Learning (private preview) will provide a default message that highlights the content as being from your own SharePoint library.</span></span> 

     ![Página Documentos en SharePoint que muestra las descripciones en la columna Descripción.](media/learning-sharepoint-curation3.png)
 
