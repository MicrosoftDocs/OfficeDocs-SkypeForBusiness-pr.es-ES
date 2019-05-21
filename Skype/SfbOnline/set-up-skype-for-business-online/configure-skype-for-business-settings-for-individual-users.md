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
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.custom:
- Setup
- LIL_Placement
description: 'Learn how to change the Skype for Business settings for individual users such as: Audio and video conferencing, recording of calls and meetings. '
ms.openlocfilehash: 5be310e47a5094a0e424624cc711311865a5b842
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285308"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="440a7-103">Administradores: Configurar Skype Empresarial para usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="440a7-103">Admins: Configure Skype for Business settings for individual users</span></span>

<span data-ttu-id="440a7-104">En este artículo se explica cómo los administradores configuran Skype Empresarial para un pequeño número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="440a7-104">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="440a7-105">Para realizar estos pasos en masa, hemos incluido vínculos a los cmdlets de Windows PowerShell que puede usar.</span><span class="sxs-lookup"><span data-stu-id="440a7-105">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="440a7-106">Para permitir (o impedir) que todos en la empresa puedan comunicarse con personas ajenas a esta, consulte:</span><span class="sxs-lookup"><span data-stu-id="440a7-106">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="440a7-107">[Permitir que los usuarios se pongan en contacto con usuarios externos de Skype empresarial](allow-users-to-contact-external-skype-for-business-users.md): puede permitir que su organización use características avanzadas de Skype empresarial (compartir Escritorios, buscar quién está conectado, etc.) para comunicarse con las personas en una empresa de confianza específica (federada).</span><span class="sxs-lookup"><span data-stu-id="440a7-107">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="440a7-108">En este artículo también se explica cómo bloquear la comunicación con dominios específicos.</span><span class="sxs-lookup"><span data-stu-id="440a7-108">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="440a7-109">[Permita que los usuarios de Skype empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="440a7-109">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="440a7-110">Puede permitir que su organización use Skype Empresarial para buscar personas que usen la aplicación gratuita Skype y comunicarse con ellas con mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="440a7-110">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="440a7-111">Establecer la configuración general de un usuario</span><span class="sxs-lookup"><span data-stu-id="440a7-111">Configure general settings for one user</span></span>
<span data-ttu-id="440a7-112"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="440a7-112"></span></span>

<span data-ttu-id="440a7-113">Debe tener [permisos de administrador](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) para poder realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="440a7-113">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>

<span data-ttu-id="440a7-114">![SFB-logo-30x30. png](../images/sfb-logo-30x30.png) **con el centro de administración de Skype empresarial**</span><span class="sxs-lookup"><span data-stu-id="440a7-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="440a7-115">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="440a7-115">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="440a7-116">Seleccione **Centros de administración** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="440a7-116">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="440a7-117">Seleccione **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="440a7-117">Choose **Users**.</span></span>
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="440a7-119">Elija los usuarios que desea editar:</span><span class="sxs-lookup"><span data-stu-id="440a7-119">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="440a7-120">En el panel derecho, elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="440a7-120">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="440a7-122">En la página de opciones **General**, active o desactive las casillas correspondientes a las características que quiera cambiar y luego elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="440a7-122">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="440a7-123">**Opción**</span><span class="sxs-lookup"><span data-stu-id="440a7-123">**Option**</span></span>|<span data-ttu-id="440a7-124">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="440a7-124">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="440a7-125">Audio y vídeo HD</span><span class="sxs-lookup"><span data-stu-id="440a7-125">Audio and HD video</span></span>  <br/> |<span data-ttu-id="440a7-126">Permitir que esta persona grabe reuniones de audio, reuniones de audio y vídeo, o no les permita programar ninguna reunión (ninguna).</span><span class="sxs-lookup"><span data-stu-id="440a7-126">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meetings (none).</span></span>  <br/> |
|<span data-ttu-id="440a7-127">Registrar conversaciones y reuniones</span><span class="sxs-lookup"><span data-stu-id="440a7-127">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="440a7-128">Elija lo que puede grabar esta persona.</span><span class="sxs-lookup"><span data-stu-id="440a7-128">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="440a7-129">Esta opción no está disponible en Skype empresarial Basic.</span><span class="sxs-lookup"><span data-stu-id="440a7-129">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="440a7-130">Para cumplir con las normativas, desactive las características no archivadas</span><span class="sxs-lookup"><span data-stu-id="440a7-130">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="440a7-131">Elija esta opción si tiene la obligación legal de conservar la información almacenada por medios electrónicos.</span><span class="sxs-lookup"><span data-stu-id="440a7-131">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="440a7-132">Al seleccionar esta opción, se desactivan las características que no se capturan cuando tiene configurada una [retención local](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) en el centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="440a7-132">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) set up in the Exchange admin center.</span></span> <span data-ttu-id="440a7-133">Desactiva las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="440a7-133">It turns off the following features:</span></span> <br/>  <span data-ttu-id="440a7-134">Transferencia de archivos por mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="440a7-134">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="440a7-135">Páginas de OneNote compartidas</span><span class="sxs-lookup"><span data-stu-id="440a7-135">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="440a7-136">Anotaciones de PowerPoint</span><span class="sxs-lookup"><span data-stu-id="440a7-136">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="440a7-137">Para configurar estas opciones en masa, use PowerShell.</span><span class="sxs-lookup"><span data-stu-id="440a7-137">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="440a7-138">Consulte [configurar el equipo para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="440a7-138">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="440a7-139">Bloquear comunicaciones externas</span><span class="sxs-lookup"><span data-stu-id="440a7-139">Block external communications</span></span>
<span data-ttu-id="440a7-140"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="440a7-140"></span></span>

<span data-ttu-id="440a7-141">Después de [Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md) para todas las personas de su empresa, puede bloquear de manera selectiva las comunicaciones externas de personas específicas con estos pasos.</span><span class="sxs-lookup"><span data-stu-id="440a7-141">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="440a7-142">Elija **usuarios**, seleccione los usuarios cuya configuración desea deshabilitar y, a continuación, \*\*\*\* ![elija Editar](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png)edición.</span><span class="sxs-lookup"><span data-stu-id="440a7-142">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="440a7-143">Elija **Comunicaciones externas** y después desactive las opciones correspondientes:</span><span class="sxs-lookup"><span data-stu-id="440a7-143">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
   - <span data-ttu-id="440a7-144">**Usuarios externos de Skype Empresarial**: desactive esta casilla si no desea que el usuario pueda comunicarse con los usuarios de Skype Empresarial en dominios federados.</span><span class="sxs-lookup"><span data-stu-id="440a7-144">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
   - <span data-ttu-id="440a7-145">**Usuarios externos de Skype**: desactive esta casilla si no desea que el usuario pueda comunicarse con personas que usan la aplicación gratuita Skype.</span><span class="sxs-lookup"><span data-stu-id="440a7-145">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="440a7-146">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="440a7-146">Click **Save**.</span></span>
    
<span data-ttu-id="440a7-147">Para configurar estas opciones en masa, use PowerShell.</span><span class="sxs-lookup"><span data-stu-id="440a7-147">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="440a7-148">Consulte [configurar el equipo para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="440a7-148">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="440a7-149">Editar la configuración de audioconferencia para un usuario</span><span class="sxs-lookup"><span data-stu-id="440a7-149">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="440a7-150"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="440a7-150"></span></span>

1. <span data-ttu-id="440a7-151">Elija **usuarios**, seleccione el usuario cuya configuración de audioconferencias desee editar y, a continuación, elija **Editar** ![edición](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="440a7-151">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="440a7-152">Elija **audioconferencias**, seleccione su proveedor de servicios de audioconferencia, escriba o modifique la información solicitada y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="440a7-152">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="440a7-153">**Configuración de Audioconferencia**</span><span class="sxs-lookup"><span data-stu-id="440a7-153">**Audio conferencing setting**</span></span>|<span data-ttu-id="440a7-154">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="440a7-154">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="440a7-155">**Nombre del proveedor**</span><span class="sxs-lookup"><span data-stu-id="440a7-155">**Provider name**</span></span> <br/> |<span data-ttu-id="440a7-156">Elija su proveedor de la lista.</span><span class="sxs-lookup"><span data-stu-id="440a7-156">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="440a7-157">**Número gratuito** (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="440a7-157">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="440a7-158">Para un ACP de terceros, estos números de teléfono son los que recibió del proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="440a7-158">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="440a7-159">Si el usuario utiliza Microsoft como proveedor de audioconferencia, estos serán los números establecidos en el puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="440a7-159">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="440a7-160">Aplique formato a los números tal y como desee que aparezcan en las convocatorias de reunión de Skype empresarial y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="440a7-160">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="440a7-161">**Número gratuito**</span><span class="sxs-lookup"><span data-stu-id="440a7-161">**Toll-free number**</span></span> <br/> |<span data-ttu-id="440a7-162">Para un ACP de terceros, estos números de teléfono son los que recibió del proveedor de servicios de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="440a7-162">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="440a7-163">Si el usuario utiliza Microsoft como proveedor de audioconferencia, estos serán los números establecidos en el puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="440a7-163">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="440a7-164">Aplique formato a los números tal y como desee que aparezcan en las convocatorias de reunión de Skype empresarial y Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="440a7-164">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="440a7-165">**ID de conferencia y PIN** necesario</span><span class="sxs-lookup"><span data-stu-id="440a7-165">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="440a7-166">El PIN del participante, o código de conferencia, que se usa para unirse a las reuniones programadas por este usuario y que se proporcionan desde un proveedor de servicios de audioconferencia de terceros.</span><span class="sxs-lookup"><span data-stu-id="440a7-166">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="440a7-167">Si el usuario usa Microsoft como el proveedor de servicios de audioconferencia, esto no será necesario.</span><span class="sxs-lookup"><span data-stu-id="440a7-167">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="440a7-168">Para configurar estas opciones en masa, use PowerShell.</span><span class="sxs-lookup"><span data-stu-id="440a7-168">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="440a7-169">Consulte [establecer los números de teléfono incluidos en los invitados](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [configurar el equipo para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="440a7-169">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="440a7-170">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="440a7-170">Related topics</span></span> 

[<span data-ttu-id="440a7-171">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="440a7-171">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="440a7-172">Licencias complementarias de Skype Empresarial y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="440a7-172">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
