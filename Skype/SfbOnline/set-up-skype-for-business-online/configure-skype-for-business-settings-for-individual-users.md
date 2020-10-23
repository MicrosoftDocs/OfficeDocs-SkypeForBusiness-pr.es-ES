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
ms.openlocfilehash: 546e693dd1fb6e9becf7119c35d7b00875eda99a
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739178"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="f2749-103">Administradores: Configurar Skype Empresarial para usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="f2749-103">Admins: Configure Skype for Business settings for individual users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f2749-104">El centro de administración de Microsoft Teams ha reemplazado al centro de administración de Skype empresarial (portal heredado).</span><span class="sxs-lookup"><span data-stu-id="f2749-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="f2749-105">Toda la configuración para administrar Skype empresarial ahora está en el centro de administración de Teams.</span><span class="sxs-lookup"><span data-stu-id="f2749-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="f2749-106">Para obtener más información, vea [administrar la configuración de Skype empresarial en el centro de administración de Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="f2749-106">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="f2749-107">En este artículo se explica cómo los administradores configuran Skype Empresarial para un pequeño número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="f2749-107">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="f2749-108">Para realizar estos pasos en masa, hemos incluido vínculos a los cmdlets de Windows PowerShell que puede usar.</span><span class="sxs-lookup"><span data-stu-id="f2749-108">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="f2749-109">Para permitir (o impedir) que todos en la empresa puedan comunicarse con personas ajenas a esta, consulte:</span><span class="sxs-lookup"><span data-stu-id="f2749-109">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="f2749-110">[Permitir que los usuarios se pongan en contacto con usuarios externos de Skype empresarial](allow-users-to-contact-external-skype-for-business-users.md): puede permitir que su organización use características avanzadas de Skype empresarial (compartir Escritorios, buscar quién está conectado, etc.) para comunicarse con las personas en una empresa de confianza específica (federada).</span><span class="sxs-lookup"><span data-stu-id="f2749-110">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="f2749-111">En este artículo también se explica cómo bloquear la comunicación con dominios específicos.</span><span class="sxs-lookup"><span data-stu-id="f2749-111">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="f2749-112">[Permita que los usuarios de Skype empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="f2749-112">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="f2749-113">Puede permitir que su organización use Skype Empresarial para buscar personas que usen la aplicación gratuita Skype y comunicarse con ellas con mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="f2749-113">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="f2749-114">Establecer la configuración general de un usuario</span><span class="sxs-lookup"><span data-stu-id="f2749-114">Configure general settings for one user</span></span>
<span data-ttu-id="f2749-115"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="f2749-115"><a name="__toc325019204"> </a></span></span>

<span data-ttu-id="f2749-116">Debe tener [permisos de administrador](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) para poder realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f2749-116">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>

<span data-ttu-id="f2749-117">![Icono que muestra el logotipo de Skype Empresarial](../images/sfb-logo-30x30.png) **Usar el Centro de administración de Skype Empresarial**</span><span class="sxs-lookup"><span data-stu-id="f2749-117">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="f2749-118">Inicie sesión con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="f2749-118">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="f2749-119">Seleccione **Centros de administración** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="f2749-119">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="f2749-120">Seleccione **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="f2749-120">Choose **Users**.</span></span>
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="f2749-122">Elija los usuarios que desea editar:</span><span class="sxs-lookup"><span data-stu-id="f2749-122">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="f2749-123">En el panel derecho, elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f2749-123">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="f2749-125">En la página de opciones **General**, active o desactive las casillas correspondientes a las características que quiera cambiar y luego elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f2749-125">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="f2749-126">**Opción**</span><span class="sxs-lookup"><span data-stu-id="f2749-126">**Option**</span></span>|<span data-ttu-id="f2749-127">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="f2749-127">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f2749-128">Audio y vídeo HD</span><span class="sxs-lookup"><span data-stu-id="f2749-128">Audio and HD video</span></span>  <br/> |<span data-ttu-id="f2749-129">Permitir que esta persona grabe reuniones de audio, reuniones de audio y vídeo, o no les permita programar ninguna reunión (ninguna).</span><span class="sxs-lookup"><span data-stu-id="f2749-129">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meetings (none).</span></span>  <br/> |
|<span data-ttu-id="f2749-130">Registrar conversaciones y reuniones</span><span class="sxs-lookup"><span data-stu-id="f2749-130">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="f2749-131">Elija lo que puede grabar esta persona.</span><span class="sxs-lookup"><span data-stu-id="f2749-131">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="f2749-132">Esta opción no está disponible en Skype empresarial Basic.</span><span class="sxs-lookup"><span data-stu-id="f2749-132">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="f2749-133">Para cumplir con las normativas, desactive las características no archivadas</span><span class="sxs-lookup"><span data-stu-id="f2749-133">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="f2749-134">Elija esta opción si tiene la obligación legal de conservar la información almacenada por medios electrónicos.</span><span class="sxs-lookup"><span data-stu-id="f2749-134">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="f2749-135">Al seleccionar esta opción, se desactivan las características que no se capturan cuando tiene configurada una [retención local](https://technet.microsoft.com/library/ff637980%28v=exchg.150%29.aspx) en el centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="f2749-135">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/library/ff637980%28v=exchg.150%29.aspx) set up in the Exchange admin center.</span></span> <span data-ttu-id="f2749-136">Desactiva las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="f2749-136">It turns off the following features:</span></span> <br/>  <span data-ttu-id="f2749-137">Transferencia de archivos por mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="f2749-137">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="f2749-138">Páginas de OneNote compartidas</span><span class="sxs-lookup"><span data-stu-id="f2749-138">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="f2749-139">Anotaciones de PowerPoint</span><span class="sxs-lookup"><span data-stu-id="f2749-139">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="f2749-140">Para configurar estas opciones en masa, use PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2749-140">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="f2749-141">Consulte [configurar el equipo para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="f2749-141">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="f2749-142">Bloquear comunicaciones externas</span><span class="sxs-lookup"><span data-stu-id="f2749-142">Block external communications</span></span>
<span data-ttu-id="f2749-143"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="f2749-143"><a name="__toc325019206"> </a></span></span>

<span data-ttu-id="f2749-144">Después de [Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md) para todas las personas de su empresa, puede bloquear de manera selectiva las comunicaciones externas de personas específicas con estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f2749-144">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="f2749-145">Elija **usuarios**, seleccione los usuarios cuya configuración desea deshabilitar y, a continuación, elija **Editar** ![ Edición ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) .</span><span class="sxs-lookup"><span data-stu-id="f2749-145">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="f2749-146">Elija **Comunicaciones externas** y después desactive las opciones correspondientes:</span><span class="sxs-lookup"><span data-stu-id="f2749-146">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
   - <span data-ttu-id="f2749-147">**Usuarios externos de Skype Empresarial**: desactive esta casilla si no desea que el usuario pueda comunicarse con los usuarios de Skype Empresarial en dominios federados.</span><span class="sxs-lookup"><span data-stu-id="f2749-147">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
   - <span data-ttu-id="f2749-148">**Usuarios externos de Skype**: desactive esta casilla si no desea que el usuario pueda comunicarse con personas que usan la aplicación gratuita Skype.</span><span class="sxs-lookup"><span data-stu-id="f2749-148">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="f2749-149">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f2749-149">Click **Save**.</span></span>
    
<span data-ttu-id="f2749-150">Para configurar estas opciones en masa, use PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2749-150">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="f2749-151">Consulte [configurar el equipo para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="f2749-151">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="f2749-152">Editar la configuración de audioconferencia para un usuario</span><span class="sxs-lookup"><span data-stu-id="f2749-152">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="f2749-153"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="f2749-153"><a name="__toc314837483"> </a></span></span>

1. <span data-ttu-id="f2749-154">Elija **usuarios**, seleccione el usuario cuya configuración de audioconferencias desee editar y, a continuación, elija **Editar** ![ Edición ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) .</span><span class="sxs-lookup"><span data-stu-id="f2749-154">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="f2749-155">Elija **audioconferencias**, seleccione su proveedor de servicios de audioconferencia, escriba o modifique la información solicitada y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f2749-155">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="f2749-156">**Configuración de Audioconferencia**</span><span class="sxs-lookup"><span data-stu-id="f2749-156">**Audio conferencing setting**</span></span>|<span data-ttu-id="f2749-157">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="f2749-157">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f2749-158">**Nombre del proveedor**</span><span class="sxs-lookup"><span data-stu-id="f2749-158">**Provider name**</span></span> <br/> |<span data-ttu-id="f2749-159">Elija su proveedor de la lista.</span><span class="sxs-lookup"><span data-stu-id="f2749-159">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="f2749-160">**Número gratuito** (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="f2749-160">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="f2749-161">Para un ACP de terceros, estos números de teléfono son los que recibió del proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="f2749-161">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="f2749-162">Si el usuario utiliza Microsoft como proveedor de audioconferencia, estos serán los números establecidos en el puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="f2749-162">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="f2749-163">Aplique formato a los números tal y como desee que aparezcan en las convocatorias de reunión de Skype empresarial y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f2749-163">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="f2749-164">**Número gratuito**</span><span class="sxs-lookup"><span data-stu-id="f2749-164">**Toll-free number**</span></span> <br/> |<span data-ttu-id="f2749-165">Para un ACP de terceros, estos números de teléfono son los que recibió del proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="f2749-165">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="f2749-166">Si el usuario utiliza Microsoft como proveedor de audioconferencia, estos serán los números establecidos en el puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="f2749-166">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="f2749-167">Aplique formato a los números tal y como desee que aparezcan en las convocatorias de reunión de Skype empresarial y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f2749-167">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="f2749-168">**ID de conferencia y PIN** (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="f2749-168">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="f2749-169">El PIN del participante, o código de conferencia, que se usa para unirse a las reuniones programadas por este usuario y que se proporcionan desde un proveedor de servicios de audioconferencia de terceros.</span><span class="sxs-lookup"><span data-stu-id="f2749-169">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="f2749-170">Si el usuario usa Microsoft como el proveedor de servicios de audioconferencia, esto no será necesario.</span><span class="sxs-lookup"><span data-stu-id="f2749-170">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="f2749-171">Para configurar estas opciones en masa, use PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2749-171">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="f2749-172">Consulte [establecer los números de teléfono incluidos en los invitados](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [configurar el equipo para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="f2749-172">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="f2749-173">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="f2749-173">Related topics</span></span> 

[<span data-ttu-id="f2749-174">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="f2749-174">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="f2749-175">Licencias complementarias de Skype Empresarial y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f2749-175">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
