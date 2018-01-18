---
title: "Administradores de configurar Skype para configuración de negocio para usuarios individuales"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.custom:
- Setup
- LIL_Placement
description: "Obtenga información sobre cómo cambiar el Skype para configuración de negocio para usuarios individuales como: conferencias de Audio y vídeo, grabación de llamadas y reuniones. "
ms.openlocfilehash: 0623c6dd913316584bd38e4076317c050c4a2812
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="28cf0-103">Administradores: Configurar Skype negocio para usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="28cf0-103">Admins: Configure Skype for Business settings for individual users</span></span>

<span data-ttu-id="28cf0-104">Este artículo explica cómo los administradores configuran Skype para el negocio para un número reducido de usuarios.</span><span class="sxs-lookup"><span data-stu-id="28cf0-104">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="28cf0-105">Para realizar estos pasos de forma masiva, hemos incluido vínculos a los cmdlets de Windows PowerShell que puede utilizar.</span><span class="sxs-lookup"><span data-stu-id="28cf0-105">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="28cf0-106">Para permitir (o bloquean) todas las personas de su empresa para comunicarse con usuarios externos, consulte:</span><span class="sxs-lookup"><span data-stu-id="28cf0-106">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="28cf0-107">[Permitir a los usuarios ponerse en contacto con Skype externo para usuarios profesionales](allow-users-to-contact-external-skype-for-business-users.md): puede hacer que su organización utilice avanzada Skype para funciones de negocios (compartir escritorios, busque quién está en línea, etc.) para comunicarse con otras personas en un determinado de confianza empresarial (federado).</span><span class="sxs-lookup"><span data-stu-id="28cf0-107">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="28cf0-108">El artículo también explica cómo bloquear la comunicación con dominios específicos.</span><span class="sxs-lookup"><span data-stu-id="28cf0-108">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="28cf0-109">[Permiten Skype para usuarios de negocios agregar contactos de Skype](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="28cf0-109">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="28cf0-110">Puede permitir a la organización utilizar Skype para empresarios para buscar y mensajería instantánea que utilizan Skype, la aplicación gratuita.</span><span class="sxs-lookup"><span data-stu-id="28cf0-110">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="28cf0-111">Configuración general para un usuario</span><span class="sxs-lookup"><span data-stu-id="28cf0-111">Configure general settings for one user</span></span>
<span data-ttu-id="28cf0-112"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="28cf0-112"></span></span>

<span data-ttu-id="28cf0-113">Debe tener [permisos de administrador](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) para realizar estos pasos.</span><span class="sxs-lookup"><span data-stu-id="28cf0-113">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>
  
1. <span data-ttu-id="28cf0-114">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="28cf0-114">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="28cf0-115">Seleccione **Admin centros** > **Skype para el negocio**.</span><span class="sxs-lookup"><span data-stu-id="28cf0-115">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="28cf0-116">Elegir **los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="28cf0-116">Choose **Users**.</span></span>
    
    ![En Skype para el centro de administración de negocios, elegir los usuarios.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="28cf0-118">Seleccione los usuarios que desea editar.</span><span class="sxs-lookup"><span data-stu-id="28cf0-118">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="28cf0-119">En el panel derecho, elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="28cf0-119">In the right panel, choose **Edit**.</span></span>
    
    ![Elija el icono de edición.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="28cf0-121">En la página opciones **generales** , seleccione o desactive la casilla de verificación situada junto a las características que desea cambiar y, a continuación, elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="28cf0-121">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="28cf0-122">**Opción**</span><span class="sxs-lookup"><span data-stu-id="28cf0-122">**Option**</span></span>|<span data-ttu-id="28cf0-123">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="28cf0-123">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="28cf0-124">Audio y vídeo de alta definición</span><span class="sxs-lookup"><span data-stu-id="28cf0-124">Audio and HD video</span></span>  <br/> |<span data-ttu-id="28cf0-125">Permitir a esta persona para grabar reuniones audio, reuniones de audio y vídeo, o no les permiten programar cualquier meeetings (ninguno).</span><span class="sxs-lookup"><span data-stu-id="28cf0-125">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meeetings (none).</span></span>  <br/> |
|<span data-ttu-id="28cf0-126">Reuniones y grabar conversaciones</span><span class="sxs-lookup"><span data-stu-id="28cf0-126">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="28cf0-127">Elija lo que esta persona puede registrar.</span><span class="sxs-lookup"><span data-stu-id="28cf0-127">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="28cf0-128">Esta opción no está disponible con Skype para Business Basic.</span><span class="sxs-lookup"><span data-stu-id="28cf0-128">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="28cf0-129">Para el cumplimiento, desactivar las características no son archivados</span><span class="sxs-lookup"><span data-stu-id="28cf0-129">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="28cf0-130">Elija esta opción si está legalmente necesaria para conservar la información almacenada electrónicamente.</span><span class="sxs-lookup"><span data-stu-id="28cf0-130">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="28cf0-131">Esta opción desactiva las funciones que no se capturan cuando haya un [Mantenga In situ](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) establecido el centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="28cf0-131">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) set up in in the Exchange admin center.</span></span> <span data-ttu-id="28cf0-132">Desactiva las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="28cf0-132">It turns off the following features:</span></span> <br/>  <span data-ttu-id="28cf0-133">Transferencia de archivos por mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="28cf0-133">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="28cf0-134">Páginas de OneNote compartidas</span><span class="sxs-lookup"><span data-stu-id="28cf0-134">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="28cf0-135">Anotaciones de PowerPoint</span><span class="sxs-lookup"><span data-stu-id="28cf0-135">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="28cf0-136">Para configurar estas opciones de forma masiva, usar PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28cf0-136">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="28cf0-137">Consulte [Gestión de directivas en Skype para los negocios en línea](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="28cf0-137">See [Managing policies in Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="28cf0-138">Bloque de comunicaciones externas</span><span class="sxs-lookup"><span data-stu-id="28cf0-138">Block external communications</span></span>
<span data-ttu-id="28cf0-139"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="28cf0-139"></span></span>

<span data-ttu-id="28cf0-140">Después de [Permitir Skype para usuarios de negocios agregar contactos de Skype](let-skype-for-business-users-add-skype-contacts.md) para todos los usuarios de su empresa, puede bloquear selectivamente comunicaciones externas de determinados individuos siguiendo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="28cf0-140">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="28cf0-141">Elegir **usuarios**, seleccione los usuarios cuya configuración desea deshabilitar y, a continuación, elija **Editar** ![editar](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="28cf0-141">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="28cf0-142">Elija **comunicaciones externas**y, a continuación, desactive las opciones según corresponda:</span><span class="sxs-lookup"><span data-stu-id="28cf0-142">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
  - <span data-ttu-id="28cf0-143">**Skype externo para usuarios profesionales**: desactive esta casilla si no desea que el usuario pueda comunicarse con Skype para usuarios profesionales de dominios federados.</span><span class="sxs-lookup"><span data-stu-id="28cf0-143">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
  - <span data-ttu-id="28cf0-144">**Los usuarios externos de Skype**: desactive esta casilla si no desea que el usuario sea capaz de comunicarse con personas que utilizan la aplicación freeSkype.</span><span class="sxs-lookup"><span data-stu-id="28cf0-144">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="28cf0-145">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="28cf0-145">Click **Save**.</span></span>
    
<span data-ttu-id="28cf0-146">Para configurar estas opciones de forma masiva, usar PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28cf0-146">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="28cf0-147">Consulte [administración de las comunicaciones en Skype para los negocios en línea con usuarios externos y las organizaciones](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="28cf0-147">See [Managing communications in Skype for Business Online with outside users and organizations](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="28cf0-148">Editar configuración de conferencia de audio de un usuario</span><span class="sxs-lookup"><span data-stu-id="28cf0-148">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="28cf0-149"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="28cf0-149"></span></span>

1. <span data-ttu-id="28cf0-150">Seleccione **los usuarios**, seleccione el usuario cuya configuración de conferencias de audio que desea para editar, y, a continuación, elija **Editar** ![editar](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="28cf0-150">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="28cf0-151">Elegir **las conferencias de Audio**, seleccione el proveedor de conferencia de audio, escriba o cambie la información solicitada y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="28cf0-151">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="28cf0-152">**Configuración de Audioconferencia**</span><span class="sxs-lookup"><span data-stu-id="28cf0-152">**Audio conferencing setting**</span></span>|<span data-ttu-id="28cf0-153">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="28cf0-153">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="28cf0-154">**Nombre del proveedor**</span><span class="sxs-lookup"><span data-stu-id="28cf0-154">**Provider name**</span></span> <br/> |<span data-ttu-id="28cf0-155">Elija el proveedor de la lista.</span><span class="sxs-lookup"><span data-stu-id="28cf0-155">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="28cf0-156">**Número gratuito** (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="28cf0-156">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="28cf0-157">Para un ACP de terceros, estos números de teléfono son los que recibe del proveedor de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="28cf0-157">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="28cf0-158">Si el usuario utiliza Microsoft como proveedor de conferencia de audio, estos serán los números que se establecen en el puente de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="28cf0-158">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="28cf0-159">Dar formato a los números como desee que aparezcan en Skype para las convocatorias de reunión de negocios y Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="28cf0-159">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="28cf0-160">**Número gratuito**</span><span class="sxs-lookup"><span data-stu-id="28cf0-160">**Toll-free number**</span></span> <br/> |<span data-ttu-id="28cf0-161">Para un ACP de terceros, estos números de teléfono son los que recibe del proveedor de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="28cf0-161">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="28cf0-162">Si el usuario utiliza Microsoft como proveedor de conferencia de audio, estos serán los números que se establecen en el puente de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="28cf0-162">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="28cf0-163">Dar formato a los números como desee que aparezcan en Skype para las convocatorias de reunión de negocios y Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="28cf0-163">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="28cf0-164">**Conferencia ID y PIN** (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="28cf0-164">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="28cf0-165">El participante PIN o conferencia código utilizado para unirse a las reuniones que son programadas por este usuario y son proporcionadas por un proveedor de conferencia de audio de terceros.</span><span class="sxs-lookup"><span data-stu-id="28cf0-165">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="28cf0-166">Si el usuario utiliza Microsoft como proveedor de conferencia de audio, esto no será necesario.</span><span class="sxs-lookup"><span data-stu-id="28cf0-166">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="28cf0-167">Para configurar estas opciones de forma masiva, usar PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28cf0-167">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="28cf0-168">Consulte [el teléfono invita números incluidos en](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="28cf0-168">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="28cf0-169">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="28cf0-169">Related topics</span></span> 

[<span data-ttu-id="28cf0-170">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="28cf0-170">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

<span data-ttu-id="28cf0-171">Puede obtener más información en [Conferencias de acceso telefónico en Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="28cf0-171">[Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span></span>
  
