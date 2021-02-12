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
ms.openlocfilehash: cf54637bda51a7994121035b3db1585213c56c00
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753425"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="51d74-103">Administradores: Configurar Skype Empresarial para usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="51d74-103">Admins: Configure Skype for Business settings for individual users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="51d74-104">El Centro de administración de Microsoft Teams ha sustituido al Centro de administración de Skype Empresarial (portal heredado).</span><span class="sxs-lookup"><span data-stu-id="51d74-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="51d74-105">Todas las configuraciones para administrar Skype Empresarial se encuentran ahora en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="51d74-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="51d74-106">Debe tener asignado el rol de administrador de [Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) de administrador global o de administrador de Skype Empresarial para administrar las características de Skype Empresarial en el Centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="51d74-106">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="51d74-107">Para conocer más, consulte [Administrar la configuración de Skype empresarial en el Centro de administración de Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json)</span><span class="sxs-lookup"><span data-stu-id="51d74-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="51d74-108">En este artículo se explica cómo los administradores configuran Skype Empresarial para un pequeño número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="51d74-108">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="51d74-109">Para realizar estos pasos en masa, hemos incluido vínculos a los Windows PowerShell cmdlet que puede usar.</span><span class="sxs-lookup"><span data-stu-id="51d74-109">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="51d74-110">Para permitir (o impedir) que todos en la empresa puedan comunicarse con personas ajenas a esta, consulte:</span><span class="sxs-lookup"><span data-stu-id="51d74-110">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="51d74-111">Permitir que los usuarios se pongan en contacto con usuarios externos de [Skype](allow-users-to-contact-external-skype-for-business-users.md)Empresarial: puede permitir que su organización use las características avanzadas de Skype Empresarial (compartir escritorios, buscar quién está en línea, etc.) para comunicarse con personas de una empresa de confianza (federada) específica.</span><span class="sxs-lookup"><span data-stu-id="51d74-111">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="51d74-112">En este artículo también se explica cómo bloquear la comunicación con dominios específicos.</span><span class="sxs-lookup"><span data-stu-id="51d74-112">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="51d74-113">[Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype.](let-skype-for-business-users-add-skype-contacts.md)</span><span class="sxs-lookup"><span data-stu-id="51d74-113">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="51d74-114">Puede permitir que su organización use Skype Empresarial para buscar personas que usen la aplicación gratuita Skype y comunicarse con ellas con mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="51d74-114">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="51d74-115">Establecer la configuración general de un usuario</span><span class="sxs-lookup"><span data-stu-id="51d74-115">Configure general settings for one user</span></span>
<span data-ttu-id="51d74-116"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="51d74-116"><a name="__toc325019204"> </a></span></span>

<span data-ttu-id="51d74-117">Debe tener permisos [de administrador para](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="51d74-117">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>

<span data-ttu-id="51d74-118">![Icono que muestra el logotipo de Skype Empresarial](../images/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**</span><span class="sxs-lookup"><span data-stu-id="51d74-118">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="51d74-119">Inicie sesión con su cuenta del trabajo o de la escuela.</span><span class="sxs-lookup"><span data-stu-id="51d74-119">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="51d74-120">Seleccione **Centros de administración** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="51d74-120">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="51d74-121">Seleccione **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="51d74-121">Choose **Users**.</span></span>
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="51d74-123">Elija los usuarios que desea editar:</span><span class="sxs-lookup"><span data-stu-id="51d74-123">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="51d74-124">En el panel derecho, elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="51d74-124">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="51d74-126">En la página de opciones **General**, active o desactive las casillas correspondientes a las características que quiera cambiar y luego elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="51d74-126">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="51d74-127">**Opción**</span><span class="sxs-lookup"><span data-stu-id="51d74-127">**Option**</span></span>|<span data-ttu-id="51d74-128">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="51d74-128">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="51d74-129">Audio y vídeo HD</span><span class="sxs-lookup"><span data-stu-id="51d74-129">Audio and HD video</span></span>  <br/> |<span data-ttu-id="51d74-130">Permita que esta persona grabe reuniones de audio, reuniones de audio y vídeo, o no le permita programar ninguna reunión (ninguna).</span><span class="sxs-lookup"><span data-stu-id="51d74-130">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meetings (none).</span></span>  <br/> |
|<span data-ttu-id="51d74-131">Registrar conversaciones y reuniones</span><span class="sxs-lookup"><span data-stu-id="51d74-131">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="51d74-132">Elija lo que puede grabar esta persona.</span><span class="sxs-lookup"><span data-stu-id="51d74-132">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="51d74-133">Esta opción no está disponible con Skype Empresarial Basic.</span><span class="sxs-lookup"><span data-stu-id="51d74-133">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="51d74-134">Para cumplir con las normativas, desactive las características no archivadas</span><span class="sxs-lookup"><span data-stu-id="51d74-134">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="51d74-135">Elija esta opción si tiene la obligación legal de conservar la información almacenada por medios electrónicos.</span><span class="sxs-lookup"><span data-stu-id="51d74-135">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="51d74-136">Al seleccionar esta opción, se desactivan las [](https://technet.microsoft.com/library/ff637980%28v=exchg.150%29.aspx) características que no se capturan cuando tiene configurada una retención local en el Centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="51d74-136">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/library/ff637980%28v=exchg.150%29.aspx) set up in the Exchange admin center.</span></span> <span data-ttu-id="51d74-137">Desactiva las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="51d74-137">It turns off the following features:</span></span> <br/>  <span data-ttu-id="51d74-138">Transferencia de archivos por mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="51d74-138">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="51d74-139">Páginas de OneNote compartidas</span><span class="sxs-lookup"><span data-stu-id="51d74-139">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="51d74-140">Anotaciones de PowerPoint</span><span class="sxs-lookup"><span data-stu-id="51d74-140">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="51d74-141">Para configurar estas opciones en masa, use PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51d74-141">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="51d74-142">Vea [Configurar el equipo para Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="51d74-142">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="51d74-143">Bloquear comunicaciones externas</span><span class="sxs-lookup"><span data-stu-id="51d74-143">Block external communications</span></span>
<span data-ttu-id="51d74-144"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="51d74-144"><a name="__toc325019206"> </a></span></span>

<span data-ttu-id="51d74-145">Después de [Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md) para todas las personas de su empresa, puede bloquear de manera selectiva las comunicaciones externas de personas específicas con estos pasos.</span><span class="sxs-lookup"><span data-stu-id="51d74-145">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="51d74-146">Elija **Usuarios,** seleccione los usuarios cuya configuración desea deshabilitar y, a continuación, **elija** ![ ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) Editar.</span><span class="sxs-lookup"><span data-stu-id="51d74-146">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="51d74-147">Elija **Comunicaciones externas** y después desactive las opciones correspondientes:</span><span class="sxs-lookup"><span data-stu-id="51d74-147">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
   - <span data-ttu-id="51d74-148">**Usuarios externos de Skype Empresarial**: desactive esta casilla si no desea que el usuario pueda comunicarse con los usuarios de Skype Empresarial en dominios federados.</span><span class="sxs-lookup"><span data-stu-id="51d74-148">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
   - <span data-ttu-id="51d74-149">**Usuarios externos de Skype**: desactive esta casilla si no desea que el usuario pueda comunicarse con personas que usan la aplicación gratuita Skype.</span><span class="sxs-lookup"><span data-stu-id="51d74-149">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="51d74-150">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="51d74-150">Click **Save**.</span></span>
    
<span data-ttu-id="51d74-151">Para configurar estas opciones en masa, use PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51d74-151">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="51d74-152">Vea [Configurar el equipo para Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="51d74-152">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="51d74-153">Editar la configuración de audioconferencia para un usuario</span><span class="sxs-lookup"><span data-stu-id="51d74-153">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="51d74-154"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="51d74-154"><a name="__toc314837483"> </a></span></span>

1. <span data-ttu-id="51d74-155">Elija **Usuarios,** seleccione el usuario cuya configuración de audioconferencia desea editar y, a continuación, **elija** ![ ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) Editar.</span><span class="sxs-lookup"><span data-stu-id="51d74-155">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="51d74-156">Elija **Audioconferencia,** seleccione su proveedor de servicios de audioconferencia, escriba o cambie la información solicitada y, a continuación, haga clic en **Guardar.**</span><span class="sxs-lookup"><span data-stu-id="51d74-156">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="51d74-157">**Configuración de Audioconferencia**</span><span class="sxs-lookup"><span data-stu-id="51d74-157">**Audio conferencing setting**</span></span>|<span data-ttu-id="51d74-158">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="51d74-158">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="51d74-159">**Nombre del proveedor**</span><span class="sxs-lookup"><span data-stu-id="51d74-159">**Provider name**</span></span> <br/> |<span data-ttu-id="51d74-160">Elija su proveedor de la lista.</span><span class="sxs-lookup"><span data-stu-id="51d74-160">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="51d74-161">**Número gratuito** (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="51d74-161">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="51d74-162">Para un ACP de terceros, estos números de teléfono son los que recibió del proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="51d74-162">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="51d74-163">Si el usuario utiliza Microsoft como proveedor de audioconferencia, estos serán los números establecidos en el puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="51d74-163">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="51d74-164">Haga que los números aparezcan en las solicitudes de reunión de Skype Empresarial y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="51d74-164">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="51d74-165">**Número gratuito**</span><span class="sxs-lookup"><span data-stu-id="51d74-165">**Toll-free number**</span></span> <br/> |<span data-ttu-id="51d74-166">Para un ACP de terceros, estos números de teléfono son los que recibió del proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="51d74-166">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="51d74-167">Si el usuario utiliza Microsoft como proveedor de audioconferencia, estos serán los números establecidos en el puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="51d74-167">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="51d74-168">Haga que los números aparezcan en las solicitudes de reunión de Skype Empresarial y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="51d74-168">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="51d74-169">**Id. de conferencia y PIN** (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="51d74-169">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="51d74-170">El PIN de participante, o código de conferencia, que se usa para unirse a reuniones programadas por este usuario y proporcionadas por un proveedor de servicios de audioconferencia de terceros.</span><span class="sxs-lookup"><span data-stu-id="51d74-170">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="51d74-171">Si el usuario está usando Microsoft como el proveedor de servicios de audioconferencia, esto no será necesario.</span><span class="sxs-lookup"><span data-stu-id="51d74-171">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="51d74-172">Para configurar estas opciones en masa, use PowerShell.</span><span class="sxs-lookup"><span data-stu-id="51d74-172">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="51d74-173">Vea [Establecer los números de teléfono incluidos en las invitaciones](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) Configurar el equipo para [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="51d74-173">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="51d74-174">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="51d74-174">Related topics</span></span> 

[<span data-ttu-id="51d74-175">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="51d74-175">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="51d74-176">Licencias complementarias de Skype Empresarial y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="51d74-176">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
