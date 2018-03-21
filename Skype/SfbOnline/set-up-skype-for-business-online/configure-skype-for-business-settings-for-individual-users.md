---
title: Administradores Configurar Skype Empresarial para usuarios individuales
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
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
ms.openlocfilehash: 3be7ff64d3dfe84ea05753de77f4b0420c6e5787
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2018
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="ed76d-103">Administradores: Configurar Skype Empresarial para usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="ed76d-103">Admins: Configure Skype for Business settings for individual users</span></span>

<span data-ttu-id="ed76d-104">En este artículo se explica cómo los administradores configuran Skype Empresarial para un pequeño número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="ed76d-104">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="ed76d-105">Para realizar estos pasos de forma masiva, hemos incluido vínculos a los cmdlets de Windows PowerShell que puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="ed76d-105">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="ed76d-106">Para permitir (o impedir) que todos en la empresa puedan comunicarse con personas ajenas a esta, consulte:</span><span class="sxs-lookup"><span data-stu-id="ed76d-106">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="ed76d-107">[Permitir a los usuarios ponerse en contacto con Skype externo para usuarios profesionales](allow-users-to-contact-external-skype-for-business-users.md): puede hacer que su organización utilice avanzada Skype para funciones de negocios (compartir escritorios, busque quién está en línea, etc.) para comunicarse con otras personas en un determinado de confianza empresarial (federado).</span><span class="sxs-lookup"><span data-stu-id="ed76d-107">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="ed76d-108">El artículo también explica cómo bloquear la comunicación con dominios específicos.</span><span class="sxs-lookup"><span data-stu-id="ed76d-108">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="ed76d-109">[Permiten Skype para usuarios de negocios agregar contactos de Skype](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="ed76d-109">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="ed76d-110">Puede permitir que su organización use Skype Empresarial para buscar personas que usen la aplicación gratuita Skype y comunicarse con ellas con mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="ed76d-110">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="ed76d-111">Establecer la configuración general de un usuario</span><span class="sxs-lookup"><span data-stu-id="ed76d-111">Configure general settings for one user</span></span>
<span data-ttu-id="ed76d-112"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="ed76d-112"></span></span>

<span data-ttu-id="ed76d-113">Debe tener [permisos de administrador](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) para realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ed76d-113">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>
  
1. <span data-ttu-id="ed76d-114">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="ed76d-114">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="ed76d-115">Seleccione **Centros de administración** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="ed76d-115">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="ed76d-116">Seleccione **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="ed76d-116">Choose **Users**.</span></span>
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="ed76d-118">Elija los usuarios que desea editar:</span><span class="sxs-lookup"><span data-stu-id="ed76d-118">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="ed76d-119">En el panel derecho, elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="ed76d-119">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="ed76d-121">En la página de opciones **General**, active o desactive las casillas correspondientes a las características que quiera cambiar y luego elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ed76d-121">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="ed76d-122">**Opción**</span><span class="sxs-lookup"><span data-stu-id="ed76d-122">**Option**</span></span>|<span data-ttu-id="ed76d-123">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="ed76d-123">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ed76d-124">Audio y vídeo HD</span><span class="sxs-lookup"><span data-stu-id="ed76d-124">Audio and HD video</span></span>  <br/> |<span data-ttu-id="ed76d-125">Permita que esta persona pueda grabar reuniones de audio, reuniones con audio y vídeo, o impedirle que programe reuniones (ninguna).</span><span class="sxs-lookup"><span data-stu-id="ed76d-125">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meeetings (none).</span></span>  <br/> |
|<span data-ttu-id="ed76d-126">Registrar conversaciones y reuniones</span><span class="sxs-lookup"><span data-stu-id="ed76d-126">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="ed76d-127">Elija lo que puede grabar esta persona.</span><span class="sxs-lookup"><span data-stu-id="ed76d-127">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="ed76d-128">Esta opción no está disponible con Skype para Business Basic.</span><span class="sxs-lookup"><span data-stu-id="ed76d-128">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="ed76d-129">Para cumplir con las normativas, desactive las características no archivadas</span><span class="sxs-lookup"><span data-stu-id="ed76d-129">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="ed76d-130">Elija esta opción si tiene la obligación legal de conservar la información almacenada por medios electrónicos.</span><span class="sxs-lookup"><span data-stu-id="ed76d-130">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="ed76d-131">Esta opción desactiva las funciones que no se capturan cuando haya un [Mantenga In situ](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) establecido el centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="ed76d-131">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) set up in in the Exchange admin center.</span></span> <span data-ttu-id="ed76d-132">Desactiva las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="ed76d-132">It turns off the following features:</span></span> <br/>  <span data-ttu-id="ed76d-133">Transferencia de archivos por mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="ed76d-133">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="ed76d-134">Páginas de OneNote compartidas</span><span class="sxs-lookup"><span data-stu-id="ed76d-134">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="ed76d-135">Anotaciones de PowerPoint</span><span class="sxs-lookup"><span data-stu-id="ed76d-135">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="ed76d-136">Para configurar estas opciones de forma masiva, usar PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed76d-136">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="ed76d-137">Consulte [Gestión de directivas en Skype para los negocios en línea](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="ed76d-137">See [Managing policies in Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="ed76d-138">Bloquear comunicaciones externas</span><span class="sxs-lookup"><span data-stu-id="ed76d-138">Block external communications</span></span>
<span data-ttu-id="ed76d-139"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="ed76d-139"></span></span>

<span data-ttu-id="ed76d-140">Después de [Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md) para todas las personas de su empresa, puede bloquear de manera selectiva las comunicaciones externas de personas específicas con estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ed76d-140">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="ed76d-141">Elegir **usuarios**, seleccione los usuarios cuya configuración desea deshabilitar y, a continuación, elija **Editar** ![editar](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="ed76d-141">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="ed76d-142">Elija **Comunicaciones externas** y después desactive las opciones correspondientes:</span><span class="sxs-lookup"><span data-stu-id="ed76d-142">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
  - <span data-ttu-id="ed76d-143">**Usuarios externos de Skype Empresarial**: desactive esta casilla si no desea que el usuario pueda comunicarse con los usuarios de Skype Empresarial en dominios federados.</span><span class="sxs-lookup"><span data-stu-id="ed76d-143">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
  - <span data-ttu-id="ed76d-144">**Usuarios externos de Skype**: desactive esta casilla si no desea que el usuario pueda comunicarse con personas que usan la aplicación gratuita Skype.</span><span class="sxs-lookup"><span data-stu-id="ed76d-144">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="ed76d-145">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ed76d-145">Click **Save**.</span></span>
    
<span data-ttu-id="ed76d-146">Para configurar estas opciones de forma masiva, usar PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed76d-146">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="ed76d-147">Consulte [administración de las comunicaciones en Skype para los negocios en línea con usuarios externos y las organizaciones](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="ed76d-147">See [Managing communications in Skype for Business Online with outside users and organizations](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="ed76d-148">Editar configuración de conferencia de audio de un usuario</span><span class="sxs-lookup"><span data-stu-id="ed76d-148">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="ed76d-149"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="ed76d-149"></span></span>

1. <span data-ttu-id="ed76d-150">Seleccione **los usuarios**, seleccione el usuario cuya configuración de conferencias de audio que desea para editar, y, a continuación, elija **Editar** ![editar](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="ed76d-150">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="ed76d-151">Elegir **las conferencias de Audio**, seleccione el proveedor de conferencia de audio, escriba o cambie la información solicitada y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ed76d-151">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="ed76d-152">**Configuración de Audioconferencia**</span><span class="sxs-lookup"><span data-stu-id="ed76d-152">**Audio conferencing setting**</span></span>|<span data-ttu-id="ed76d-153">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="ed76d-153">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ed76d-154">**Nombre del proveedor**</span><span class="sxs-lookup"><span data-stu-id="ed76d-154">**Provider name**</span></span> <br/> |<span data-ttu-id="ed76d-155">Elija el proveedor de la lista.</span><span class="sxs-lookup"><span data-stu-id="ed76d-155">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="ed76d-156">**Número gratuito** (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="ed76d-156">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="ed76d-157">Para un ACP de terceros, estos números de teléfono son los que recibe del proveedor de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="ed76d-157">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="ed76d-158">Si el usuario utiliza Microsoft como proveedor de conferencia de audio, estos serán los números que se establecen en el puente de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="ed76d-158">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="ed76d-159">Dar formato a los números como desee que aparezcan en Skype para las convocatorias de reunión de negocios y Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ed76d-159">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="ed76d-160">**Número gratuito**</span><span class="sxs-lookup"><span data-stu-id="ed76d-160">**Toll-free number**</span></span> <br/> |<span data-ttu-id="ed76d-161">Para un ACP de terceros, estos números de teléfono son los que recibe del proveedor de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="ed76d-161">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="ed76d-162">Si el usuario utiliza Microsoft como proveedor de conferencia de audio, estos serán los números que se establecen en el puente de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="ed76d-162">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="ed76d-163">Dar formato a los números como desee que aparezcan en Skype para las convocatorias de reunión de negocios y Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ed76d-163">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="ed76d-164">**Conferencia ID y PIN** (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="ed76d-164">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="ed76d-165">El participante PIN o conferencia código utilizado para unirse a las reuniones que son programadas por este usuario y son proporcionadas por un proveedor de conferencia de audio de terceros.</span><span class="sxs-lookup"><span data-stu-id="ed76d-165">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="ed76d-166">Si el usuario utiliza Microsoft como proveedor de conferencia de audio, esto no será necesario.</span><span class="sxs-lookup"><span data-stu-id="ed76d-166">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="ed76d-167">Para configurar estas opciones de forma masiva, usar PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ed76d-167">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="ed76d-168">Consulte [el teléfono invita números incluidos en](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="ed76d-168">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="ed76d-169">See also</span><span class="sxs-lookup"><span data-stu-id="ed76d-169">Related topics</span></span> 

[<span data-ttu-id="ed76d-170">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="ed76d-170">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

<span data-ttu-id="ed76d-171">Puede obtener más información en [Conferencias de acceso telefónico en Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="ed76d-171">[Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span></span>
  
## <a name="feedback"></a><span data-ttu-id="ed76d-172">¿Comentarios?</span><span class="sxs-lookup"><span data-stu-id="ed76d-172">Feedback?</span></span>
<span data-ttu-id="ed76d-173">Para proporcionar comentarios sobre el producto o para hacernos saber cómo lo estamos haciendo, vea [Skype para comentarios de comercio](https://www.skypefeedback.com).</span><span class="sxs-lookup"><span data-stu-id="ed76d-173">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>