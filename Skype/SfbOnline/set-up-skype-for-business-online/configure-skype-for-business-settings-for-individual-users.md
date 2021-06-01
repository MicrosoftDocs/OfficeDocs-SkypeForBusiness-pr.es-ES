---
title: Administradores Configurar Skype Empresarial para usuarios individuales
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- LIL_Placement
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
description: 'Learn how to change the Skype for Business settings for individual users such as: Audio and video conferencing, recording of calls and meetings. '
ms.openlocfilehash: 0123f285101b8d7190dd7450ddb876a136de13ce
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237536"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="394ee-103">Administradores: Configurar Skype Empresarial para usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="394ee-103">Admins: Configure Skype for Business settings for individual users</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> <span data-ttu-id="394ee-104">El Microsoft Teams de administración ha sustituido al Skype Empresarial de administración (portal heredado).</span><span class="sxs-lookup"><span data-stu-id="394ee-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="394ee-105">Todas las opciones de Skype Empresarial están ahora en el centro Teams administración.</span><span class="sxs-lookup"><span data-stu-id="394ee-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="394ee-106">Debe tener asignado el rol de administrador de [Azure AD](/azure/active-directory/roles/permissions-reference) de administrador global o Skype Empresarial administrador para administrar Skype Empresarial características en el centro Teams administración.</span><span class="sxs-lookup"><span data-stu-id="394ee-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="394ee-107">Para conocer más, consulte [Administrar la configuración de Skype empresarial en el Centro de administración de Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json)</span><span class="sxs-lookup"><span data-stu-id="394ee-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="394ee-108">En este artículo se explica cómo los administradores configuran Skype Empresarial para un pequeño número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="394ee-108">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="394ee-109">Para realizar estos pasos en masa, hemos incluido vínculos a los cmdlets Windows PowerShell que puede usar.</span><span class="sxs-lookup"><span data-stu-id="394ee-109">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="394ee-110">Para permitir (o impedir) que todos en la empresa puedan comunicarse con personas ajenas a esta, consulte:</span><span class="sxs-lookup"><span data-stu-id="394ee-110">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="394ee-111">[](allow-users-to-contact-external-skype-for-business-users.md)Permitir a los usuarios ponerse en contacto con usuarios de Skype Empresarial externos: puede permitir que su organización use características avanzadas de Skype Empresarial (compartir escritorios, buscar quién está en línea, etc.) para comunicarse con personas de una empresa específica de confianza (federada).</span><span class="sxs-lookup"><span data-stu-id="394ee-111">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="394ee-112">En el artículo también se explica cómo bloquear la comunicación con dominios específicos.</span><span class="sxs-lookup"><span data-stu-id="394ee-112">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="394ee-113">[Permitir Skype Empresarial usuarios agregar Skype contactos.](let-skype-for-business-users-add-skype-contacts.md)</span><span class="sxs-lookup"><span data-stu-id="394ee-113">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="394ee-114">Puede permitir que su organización use Skype Empresarial para buscar personas que usen la aplicación gratuita Skype y comunicarse con ellas con mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="394ee-114">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="394ee-115">Establecer la configuración general de un usuario</span><span class="sxs-lookup"><span data-stu-id="394ee-115">Configure general settings for one user</span></span>
<span data-ttu-id="394ee-116"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="394ee-116"><a name="__toc325019204"> </a></span></span>

<span data-ttu-id="394ee-117">Debe tener permisos [de administrador para](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="394ee-117">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>

<span data-ttu-id="394ee-118">![Icono que muestra el logotipo de Skype Empresarial](../images/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**</span><span class="sxs-lookup"><span data-stu-id="394ee-118">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="394ee-119">Inicie sesión con su cuenta de trabajo o escuela.</span><span class="sxs-lookup"><span data-stu-id="394ee-119">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="394ee-120">Seleccione **Centros de administración** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="394ee-120">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="394ee-121">Seleccione **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="394ee-121">Choose **Users**.</span></span>
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="394ee-123">Elija los usuarios que desea editar:</span><span class="sxs-lookup"><span data-stu-id="394ee-123">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="394ee-124">En el panel derecho, elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="394ee-124">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="394ee-126">En la página de opciones **General**, active o desactive las casillas correspondientes a las características que quiera cambiar y luego elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="394ee-126">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="394ee-127">**Opción**</span><span class="sxs-lookup"><span data-stu-id="394ee-127">**Option**</span></span>|<span data-ttu-id="394ee-128">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="394ee-128">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="394ee-129">Audio y vídeo HD</span><span class="sxs-lookup"><span data-stu-id="394ee-129">Audio and HD video</span></span>  <br/> |<span data-ttu-id="394ee-130">Permita que esta persona grabe reuniones de audio, reuniones de audio y vídeo, o que no le permita programar ninguna reunión (ninguna).</span><span class="sxs-lookup"><span data-stu-id="394ee-130">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meetings (none).</span></span>  <br/> |
|<span data-ttu-id="394ee-131">Registrar conversaciones y reuniones</span><span class="sxs-lookup"><span data-stu-id="394ee-131">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="394ee-132">Elija lo que puede grabar esta persona.</span><span class="sxs-lookup"><span data-stu-id="394ee-132">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="394ee-133">Esta opción no está disponible con Skype Empresarial Básico.</span><span class="sxs-lookup"><span data-stu-id="394ee-133">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="394ee-134">Para cumplir con las normativas, desactive las características no archivadas</span><span class="sxs-lookup"><span data-stu-id="394ee-134">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="394ee-135">Elija esta opción si tiene la obligación legal de conservar la información almacenada por medios electrónicos.</span><span class="sxs-lookup"><span data-stu-id="394ee-135">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="394ee-136">Al seleccionar esta opción, se desactivan las [](/exchange/security-and-compliance/in-place-and-litigation-holds) características que no se capturan cuando tiene una retención local configurada en el centro de administración Exchange local.</span><span class="sxs-lookup"><span data-stu-id="394ee-136">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](/exchange/security-and-compliance/in-place-and-litigation-holds) set up in the Exchange admin center.</span></span> <span data-ttu-id="394ee-137">Desactiva las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="394ee-137">It turns off the following features:</span></span> <br/>  <span data-ttu-id="394ee-138">Transferencia de archivos por mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="394ee-138">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="394ee-139">Páginas de OneNote compartidas</span><span class="sxs-lookup"><span data-stu-id="394ee-139">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="394ee-140">Anotaciones de PowerPoint</span><span class="sxs-lookup"><span data-stu-id="394ee-140">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="394ee-141">Para configurar estas opciones en masa, use PowerShell.</span><span class="sxs-lookup"><span data-stu-id="394ee-141">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="394ee-142">Consulte [Configurar el equipo para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="394ee-142">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="394ee-143">Bloquear comunicaciones externas</span><span class="sxs-lookup"><span data-stu-id="394ee-143">Block external communications</span></span>
<span data-ttu-id="394ee-144"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="394ee-144"><a name="__toc325019206"> </a></span></span>

<span data-ttu-id="394ee-145">Después de [Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md) para todas las personas de su empresa, puede bloquear de manera selectiva las comunicaciones externas de personas específicas con estos pasos.</span><span class="sxs-lookup"><span data-stu-id="394ee-145">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="394ee-146">Elija **Usuarios,** seleccione los usuarios cuya configuración desea deshabilitar y, a continuación, **elija Editar** editar ![ ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) .</span><span class="sxs-lookup"><span data-stu-id="394ee-146">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="394ee-147">Elija **Comunicaciones externas** y después desactive las opciones correspondientes:</span><span class="sxs-lookup"><span data-stu-id="394ee-147">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
   - <span data-ttu-id="394ee-148">**Usuarios externos de Skype Empresarial**: desactive esta casilla si no desea que el usuario pueda comunicarse con los usuarios de Skype Empresarial en dominios federados.</span><span class="sxs-lookup"><span data-stu-id="394ee-148">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
   - <span data-ttu-id="394ee-149">**Usuarios externos de Skype**: desactive esta casilla si no desea que el usuario pueda comunicarse con personas que usan la aplicación gratuita Skype.</span><span class="sxs-lookup"><span data-stu-id="394ee-149">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="394ee-150">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="394ee-150">Click **Save**.</span></span>
    
<span data-ttu-id="394ee-151">Para configurar estas opciones en masa, use PowerShell.</span><span class="sxs-lookup"><span data-stu-id="394ee-151">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="394ee-152">Consulte [Configurar el equipo para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="394ee-152">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="394ee-153">Editar la configuración de audioconferencia para un usuario</span><span class="sxs-lookup"><span data-stu-id="394ee-153">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="394ee-154"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="394ee-154"><a name="__toc314837483"> </a></span></span>

1. <span data-ttu-id="394ee-155">Elija **Usuarios,** seleccione el usuario cuya configuración de audioconferencia desea editar y, a continuación, **elija Editar** ![ ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) edición.</span><span class="sxs-lookup"><span data-stu-id="394ee-155">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="394ee-156">Elija **Audioconferencia,** seleccione su proveedor de audioconferencias, escriba o cambie la información solicitada y, después, haga clic en **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="394ee-156">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="394ee-157">**Configuración de Audioconferencia**</span><span class="sxs-lookup"><span data-stu-id="394ee-157">**Audio conferencing setting**</span></span>|<span data-ttu-id="394ee-158">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="394ee-158">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="394ee-159">**Nombre del proveedor**</span><span class="sxs-lookup"><span data-stu-id="394ee-159">**Provider name**</span></span> <br/> |<span data-ttu-id="394ee-160">Elija su proveedor de la lista.</span><span class="sxs-lookup"><span data-stu-id="394ee-160">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="394ee-161">**Número gratuito** (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="394ee-161">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="394ee-162">Para un ACP de terceros, estos números de teléfono son los que ha recibido del proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="394ee-162">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="394ee-163">Si el usuario utiliza Microsoft como proveedor de audioconferencia, estos serán los números establecidos en el puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="394ee-163">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="394ee-164">Aplicar formato a los números como desee que aparezcan en Skype Empresarial y Microsoft Teams de reunión.</span><span class="sxs-lookup"><span data-stu-id="394ee-164">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="394ee-165">**Número gratuito**</span><span class="sxs-lookup"><span data-stu-id="394ee-165">**Toll-free number**</span></span> <br/> |<span data-ttu-id="394ee-166">Para un ACP de terceros, estos números de teléfono son los que ha recibido del proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="394ee-166">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="394ee-167">Si el usuario utiliza Microsoft como proveedor de audioconferencia, estos serán los números establecidos en el puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="394ee-167">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="394ee-168">Aplicar formato a los números como desee que aparezcan en Skype Empresarial y Microsoft Teams de reunión.</span><span class="sxs-lookup"><span data-stu-id="394ee-168">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="394ee-169">**Id. de conferencia y PIN** (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="394ee-169">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="394ee-170">El PIN del participante, o código de conferencia, se usa para unirse a las reuniones programadas por este usuario y se proporcionan desde un proveedor de audioconferencia de terceros.</span><span class="sxs-lookup"><span data-stu-id="394ee-170">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="394ee-171">Si el usuario usa Microsoft como proveedor de audioconferencias, no será necesario.</span><span class="sxs-lookup"><span data-stu-id="394ee-171">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="394ee-172">Para configurar estas opciones en masa, use PowerShell.</span><span class="sxs-lookup"><span data-stu-id="394ee-172">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="394ee-173">Vea [Establecer los números de teléfono incluidos en las invitaciones](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) Configurar el equipo para [Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="394ee-173">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="394ee-174">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="394ee-174">Related topics</span></span> 

[<span data-ttu-id="394ee-175">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="394ee-175">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="394ee-176">Licencias complementarias de Skype Empresarial y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="394ee-176">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
