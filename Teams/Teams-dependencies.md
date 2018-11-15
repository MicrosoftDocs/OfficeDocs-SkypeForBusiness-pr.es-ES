---
title: Autorizar el acceso de invitado en Microsoft Teams
author: lolaj
ms.author: sbhatta
manager: serdars
ms.date: 11/10/17
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: sbhatta
search.appverid: MET150
description: Administre las funcionalidades y las características de acceso de invitado de Microsoft Teams a través de cuatro niveles de autorización distintos.
appliesto:
- Microsoft Teams
ms.openlocfilehash: f4fe71b4126a5fb9024de78b696383c0e2f65307
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531873"
---
<a name="authorize-guest-access-in-microsoft-teams"></a><span data-ttu-id="d7605-103">Autorizar el acceso de invitado en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d7605-103">Authorize guest access in Microsoft Teams</span></span>
===========================================

<span data-ttu-id="d7605-104">Para satisfacer los requisitos de su organización, puede administrar las funcionalidades y las características de acceso de invitado de Microsoft Teams a través de cuatro niveles de autorización distintos.</span><span class="sxs-lookup"><span data-stu-id="d7605-104">To satisfy your organization’s requirements, you can manage Microsoft Teams guest access features and capabilities through four different levels of authorization.</span></span> <span data-ttu-id="d7605-105">Todos los niveles de autorización se aplican a su inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="d7605-105">All the authorization levels apply to your Office 365 tenant.</span></span> <span data-ttu-id="d7605-106">Cada nivel de autorización controla la experiencia de invitado como se muestra a continuación:</span><span class="sxs-lookup"><span data-stu-id="d7605-106">Each authorization level controls the guest experience as shown below:</span></span>
- <span data-ttu-id="d7605-107">**Azure Active Directory**: el acceso de invitado en Microsoft Teams depende de la plataforma negocio a negocio (B2B) de Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d7605-107">**Azure Active Directory**: Guest access in Microsoft Teams relies on the Azure AD business-to-business (B2B) platform.</span></span> <span data-ttu-id="d7605-108">Controla la experiencia de invitado a nivel de directorio, inquilino y aplicación.</span><span class="sxs-lookup"><span data-stu-id="d7605-108">Controls the guest experience at the directory, tenant, and application level.</span></span> 
- <span data-ttu-id="d7605-109">**Microsoft Teams**: solo controla Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d7605-109">**Microsoft Teams**: Controls Microsoft Teams only.</span></span> 
- <span data-ttu-id="d7605-110">**Grupos de Office 365**: controla la experiencia de invitado en los Grupos de Office 365 y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d7605-110">**Office 365 Groups**: Controls the guest experience in Office 365 Groups and Microsoft Teams.</span></span>
- <span data-ttu-id="d7605-111">**SharePoint Online y OneDrive para la Empresa**: controla la experiencia de invitado en SharePoint Online, OneDrive para la Empresa, Grupos de Office 365 y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d7605-111">**SharePoint Online and OneDrive for Business**: Controls the guest experience in SharePoint Online, OneDrive for Business, Office 365 Groups, and Microsoft Teams.</span></span>

<span data-ttu-id="d7605-112">Estos niveles de autorización distintos proporcionan la flexibilidad necesaria para configurar el acceso de invitado para su organización.</span><span class="sxs-lookup"><span data-stu-id="d7605-112">These different authorization levels provide you with flexibility in how you set up guest access for your organization.</span></span> <span data-ttu-id="d7605-113">Por ejemplo, si no quiere permitir usuarios invitados en su organización de Microsoft Teams, solo tiene que desactivar el acceso de invitado en Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d7605-113">For example, if you don’t want to allow guest users in your Microsoft Teams organization, just turn off guest access in Microsoft Teams.</span></span> <span data-ttu-id="d7605-114">Otro ejemplo: podría habilitar el acceso de invitado en los niveles de AAD, Teams y Grupos, pero deshabilitaría la adición de usuarios invitados en equipos seleccionados que tengan un criterio o varios en común, como que la clasificación de datos es igual a confidencial.</span><span class="sxs-lookup"><span data-stu-id="d7605-114">Another example: You could enable guest access at the AAD, Teams, and Groups levels, but then disable guest users' addition on selected teams that match one or more criteria such as data classification equals confidential.</span></span> <span data-ttu-id="d7605-115">Además, quizá no use Grupos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="d7605-115">And, perhaps you don’t use Office 365 Groups.</span></span> <span data-ttu-id="d7605-116">SharePoint Online y OneDrive para la Empresa tienen su propia configuración de acceso de invitado que no depende de Grupos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="d7605-116">SharePoint Online and OneDrive for Business have their own guest access settings that don't rely on Office 365 Groups.</span></span> 

> [!NOTE]
> <span data-ttu-id="d7605-117">Los invitados están sujetos a los límites de servicio de [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) y [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="d7605-117">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span> 

  <span data-ttu-id="d7605-118">En el siguiente diagrama se muestra cómo se concede y se integra la dependencia de autorización de acceso de invitado entre Azure Active Directory, Microsoft Teams y Office 365.</span><span class="sxs-lookup"><span data-stu-id="d7605-118">The following diagram shows how guest access authorization dependency is granted and integrated between Azure Active Directory, Microsoft Teams, and Office 365.</span></span>


![Diagrama de las dependencias de autorización para el acceso de invitado.](media/teams_dependencies_image1.png)


## <a name="azure-active-directory"></a><span data-ttu-id="d7605-120">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d7605-120">Azure Active Directory</span></span>

<span data-ttu-id="d7605-121">Con la colaboración negocio a negocio (B2B) de Azure AD, el envío de invitaciones a posibles usuarios invitados no está restringido a los administradores de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="d7605-121">With Azure AD business-to-business (B2B) collaboration, sending invitations to potential guest users isn’t restricted to tenant admins.</span></span> <span data-ttu-id="d7605-122">En su lugar, puede usar directivas para delegar el envío de invitaciones a los usuarios que tengan roles que les permitan hacerlo.</span><span class="sxs-lookup"><span data-stu-id="d7605-122">Instead, you can use policies to delegate sending invitations to users whose roles allow them to send invitations.</span></span>

<span data-ttu-id="d7605-123">La configuración de las invitaciones se aplica a nivel de inquilino y controla la experiencia de invitado a nivel de directorio, inquilino y aplicación.</span><span class="sxs-lookup"><span data-stu-id="d7605-123">The settings for invitations apply at the tenant level and control the guest experience at the directory, tenant, and application level.</span></span> <span data-ttu-id="d7605-124">Como mínimo para admitir a los invitados, **pueden invitar los miembros** se debe establecer en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="d7605-124">At a minimum to support guests, **Members can invite** must be set to **Yes**.</span></span>


![Captura de pantalla de la configuración de usuario en el portal de Azure Active Directory.](media/teams_dependencies_image2.png)

<span data-ttu-id="d7605-126">Azure AD incluye las siguientes opciones para configurar los usuarios externos:</span><span class="sxs-lookup"><span data-stu-id="d7605-126">Azure AD includes the following settings to configure external users:</span></span>
- <span data-ttu-id="d7605-127">**Los permisos de usuario de invitado están limitados**: **Sí** significa que los invitados no tiene permiso para determinadas tareas de Active directory, como enumerar los usuarios, grupos u otros recursos de Active directory.</span><span class="sxs-lookup"><span data-stu-id="d7605-127">**Guest user permissions are limited**: **Yes** means that guests don't have permission for certain directory tasks, such as enumerate users, groups, or other directory resources.</span></span> <span data-ttu-id="d7605-128">Además, los invitados no se pueden asignar a las funciones administrativas en el directorio.</span><span class="sxs-lookup"><span data-stu-id="d7605-128">In addition, guests can't be assigned to administrative roles in your directory.</span></span> <span data-ttu-id="d7605-129">**No** significa que los invitados tiene el mismo acceso a los datos de Active directory que tienen los usuarios regulares en el directorio.</span><span class="sxs-lookup"><span data-stu-id="d7605-129">**No** means that guests have the same access to directory data that regular users have in your directory.</span></span>
- <span data-ttu-id="d7605-130">**Pueden invitar los administradores y usuarios de la función de autor de la invitación de invitado**: **Sí** significa que los administradores y usuarios de la función "Autor de la invitación invitado" podrán invitar a personas para el inquilino.</span><span class="sxs-lookup"><span data-stu-id="d7605-130">**Admins and users in the guest inviter role can invite**: **Yes** means that admins and users in the "Guest Inviter" role will be able to invite guests to the tenant.</span></span> <span data-ttu-id="d7605-131">**No** significa que los administradores y los usuarios no pueden invitar a los invitados en el inquilino.</span><span class="sxs-lookup"><span data-stu-id="d7605-131">**No** means admins and users can't invite guests to the tenant.</span></span>
- <span data-ttu-id="d7605-132">**Pueden invitar los miembros**: **Sí** significa que los miembros sin permisos de administrador del directorio de pueden invitar a los invitados puedan colaborar en recursos protegidos mediante la implementación de AD Azure, como sitios de SharePoint o los recursos de Azure.</span><span class="sxs-lookup"><span data-stu-id="d7605-132">**Members can invite**: **Yes** means that non-admin members of your directory can invite guests to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="d7605-133">**No** significa que sólo los administradores pueden invitar a invitados a su directorio.</span><span class="sxs-lookup"><span data-stu-id="d7605-133">**No** means that only admins can invite guests to your directory.</span></span>
- <span data-ttu-id="d7605-134">**Pueden invitar los invitados**: **Sí** significa que los invitados en el directorio pueden ellos mismos invitar a otro invitado a colaborar en recursos protegidos mediante la implementación de AD Azure, como sitios de SharePoint o los recursos de Azure.</span><span class="sxs-lookup"><span data-stu-id="d7605-134">**Guests can invite**: **Yes** means that guests in your directory can themselves invite other guest to collaborate on resources secured by your Azure AD, such as SharePoint sites or Azure resources.</span></span> <span data-ttu-id="d7605-135">**No** significa que los invitados no puede invitar a otros invitados para colaborar con su organización.</span><span class="sxs-lookup"><span data-stu-id="d7605-135">**No** means that guests can't invite other guests to collaborate with your organization.</span></span>
 


> [!NOTE]
> <span data-ttu-id="d7605-136">También puede administrar qué dominios se pueden invitar a su inquilino como invitados.</span><span class="sxs-lookup"><span data-stu-id="d7605-136">You can also manage which domains can be invited into your tenant as guests.</span></span> <span data-ttu-id="d7605-137">Vea [Permitir o bloquear el acceso de invitado a los grupos de Office 365](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="d7605-137">See [Allow/Block guest access to Office 365 groups](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-group-access-to-office-365-groups).</span></span> 

## <a name="microsoft-teams"></a><span data-ttu-id="d7605-138">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d7605-138">Microsoft Teams</span></span>
<span data-ttu-id="d7605-139">En Microsoft Teams, puede controlar si la experiencia de invitado está habilitada o deshabilitada en su organización.</span><span class="sxs-lookup"><span data-stu-id="d7605-139">In Microsoft Teams, you can control whether the guest experience is enabled or disabled for your organization.</span></span> <span data-ttu-id="d7605-140">La configuración está deshabilitada de forma predeterminada y se aplica en el nivel de inquilino para Microsoft Teams solo.</span><span class="sxs-lookup"><span data-stu-id="d7605-140">The setting is disabled by default and applies at the tenant level for Microsoft Teams only.</span></span>



<span data-ttu-id="d7605-141">Puede administrar la configuración del acceso de invitado de Microsoft Teams desde el Centro de administración de Office 365.</span><span class="sxs-lookup"><span data-stu-id="d7605-141">You can manage Microsoft Teams guest access settings from the Office 365 admin center.</span></span> <span data-ttu-id="d7605-142">Si desea más información, consulte [Activar o desactivar el acceso de invitado para Microsoft Teams](set-up-guests.md).</span><span class="sxs-lookup"><span data-stu-id="d7605-142">For more information, see [Turn on or off guest access to Microsoft Teams](set-up-guests.md).</span></span> 


## <a name="office-365-groups"></a><span data-ttu-id="d7605-143">Grupos de Office 365</span><span class="sxs-lookup"><span data-stu-id="d7605-143">Office 365 Groups</span></span>

<span data-ttu-id="d7605-144">Desde Grupos de Office 365, puede controlar la adición de usuarios invitados y el acceso de invitado a todos los grupos de Office 365 y Microsoft Teams en su organización.</span><span class="sxs-lookup"><span data-stu-id="d7605-144">From Office 365 Groups, you can control adding guest users and guest access to all Office 365 groups and Microsoft Teams in your organization.</span></span>

1. <span data-ttu-id="d7605-145">Inicie sesión con su cuenta de administrador global de Office 365 en [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="d7605-145">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
  
2. <span data-ttu-id="d7605-146">En el menú de navegación, elija **Configuración** y luego **Servicios y complementos**.</span><span class="sxs-lookup"><span data-stu-id="d7605-146">In the navigation menu, choose **Settings** and then select **Services &amp; add-ins**.</span></span>
    
  
3. <span data-ttu-id="d7605-147">Seleccione **Grupos de Office 365**.</span><span class="sxs-lookup"><span data-stu-id="d7605-147">Select **Office 365 Groups**.</span></span>
    
     ![Grupos de Office 365](media/e25a7920-254c-4da3-bc5f-a8c7f6b61423.png)
  

  

  
4. <span data-ttu-id="d7605-149">En la página de grupos de Office 365, configure el botón de alternancia en **Activado** o **Desactivado**, dependiendo de si quiere que los propietarios del equipo y el grupo que no pertenecen a la organización accedan a los grupos de Office 365.</span><span class="sxs-lookup"><span data-stu-id="d7605-149">On the Office 365 Groups page, set the toggle to **On** or **Off**, depending if you want to let team and group owners outside your organization access Office 365 groups.</span></span> <span data-ttu-id="d7605-150">Pulse o haga clic en el botón de alternancia, cambie a **Activado** junto a **Let group owners add people outside the organization to groups** (Permitir que los propietarios de grupo agreguen a los grupos personas externas a la organización).</span><span class="sxs-lookup"><span data-stu-id="d7605-150">Click or tap the toggle to **On** next to **Let group owners add people outside the organization to groups**.</span></span> <span data-ttu-id="d7605-151">Si cambia a Activado el botón de alternancia, verá otra opción para controlar si quiere que los propietarios de grupo y equipo puedan añadir personas externas a la organización a los grupos de Office 365 y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d7605-151">If you turn this toggle to On, you'll see another option to control whether you want to let group and team owners add people outside your organization to Office 365 groups and Microsoft teams.</span></span> <span data-ttu-id="d7605-152">Establezca el botón de alternancia en Activado si desea que los propietarios de grupo y equipo agreguen usuarios invitados.</span><span class="sxs-lookup"><span data-stu-id="d7605-152">Set this toggle to On if you want to let group and team owners add guest users.</span></span> 
 
   ![La captura de pantalla muestra el panel Grupos de Office 365 con las opciones activadas para permitir que los miembros del grupo externos a la organización accedan al contenido del grupo y para permitir que los propietarios del grupo agreguen a los grupos personas que no pertenecen a la organización.](media/eee77abd-4425-4585-91a8-5541c17ee7b2.png)




<span data-ttu-id="d7605-154">La configuración anterior se aplica a nivel de inquilino y controla la experiencia de invitado en Grupos de Office 365 y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d7605-154">The above settings apply at the tenant level and control the guest experience in Office 365 Groups and Microsoft Teams.</span></span>


## <a name="sharepoint-online-and-onedrive-for-business"></a><span data-ttu-id="d7605-155">SharePoint Online y OneDrive para la Empresa</span><span class="sxs-lookup"><span data-stu-id="d7605-155">SharePoint Online and OneDrive for Business</span></span>

<span data-ttu-id="d7605-156">Microsoft Teams depende de SharePoint Online y OneDrive para la Empresa para almacenar archivos y documentos de canales y conversaciones de chat.</span><span class="sxs-lookup"><span data-stu-id="d7605-156">Teams relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span>  
  
    
    
<span data-ttu-id="d7605-157">Para habilitar toda la experiencia de acceso de invitado de Teams, los administradores de Office 365 tienen que seleccionar **Activado** en las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="d7605-157">To enable the full Teams guest access experience, Office 365 admins need to select **On** for the following settings:</span></span>
  
    
    

- <span data-ttu-id="d7605-158">En SharePoint Online: **Only allow sharing with external users already in the directory** (Permitir solo compartir con usuarios externos que ya estén en el directorio)</span><span class="sxs-lookup"><span data-stu-id="d7605-158">In SharePoint Online: **Only allow sharing with external users already in the directory**</span></span>
    
    <span data-ttu-id="d7605-159">Para obtener más información, consulte [Administrar el uso compartido externo en su entorno de SharePoint Online](https://docs.microsoft.com/sharepoint/external-sharing-overview).</span><span class="sxs-lookup"><span data-stu-id="d7605-159">For more information, see [Manage external sharing for your SharePoint Online environment](https://docs.microsoft.com/sharepoint/external-sharing-overview).</span></span>
    
  
- <span data-ttu-id="d7605-160">En los grupos de Office 365: **Let group owners add people outside the organization to groups** (Permitir que los propietarios de grupo agreguen a los grupos personas externas a la organización)</span><span class="sxs-lookup"><span data-stu-id="d7605-160">In Office 365 groups: **Let group owners add people outside the organization to groups**</span></span>
    
    <span data-ttu-id="d7605-161">Para obtener más información, consulte [Controlar el acceso de invitado a Microsoft Teams](#controlguest).</span><span class="sxs-lookup"><span data-stu-id="d7605-161">For more information, see [Control guest access to Microsoft Teams](#controlguest).</span></span>
  

<span data-ttu-id="d7605-162">La configuración anterior se aplica a nivel de inquilino y controla la experiencia de invitado en SharePoint Online, OneDrive para la Empresa, Grupos de Office 365 y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d7605-162">The above settings apply at the tenant level and control the guest experience at SharePoint Online, OneDrive for Business, Office 365 Groups and Microsoft Teams.</span></span>


<span data-ttu-id="d7605-163">La configuración de usuarios externos de SharePoint Online se puede administrar para el sitio de equipos conectados a Teams.</span><span class="sxs-lookup"><span data-stu-id="d7605-163">You can manage SharePoint Online external user settings for the Teams connected team site.</span></span> <span data-ttu-id="d7605-164">Si desea más detalles, vea [Administrar la configuración de su sitio de grupo de SharePoint](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).﻿</span><span class="sxs-lookup"><span data-stu-id="d7605-164">For more details, see  [Manage your SharePoint team site settings](https://support.office.com/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>
