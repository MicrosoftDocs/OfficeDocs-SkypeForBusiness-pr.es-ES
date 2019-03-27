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
ms.openlocfilehash: 5c9bb7cfddb496a5b3bdb0b28ea050d5958a8147
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885766"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="1dfff-103">Administradores: Configurar Skype Empresarial para usuarios individuales</span><span class="sxs-lookup"><span data-stu-id="1dfff-103">Admins: Configure Skype for Business settings for individual users</span></span>

<span data-ttu-id="1dfff-104">En este artículo se explica cómo los administradores configuran Skype Empresarial para un pequeño número de usuarios.</span><span class="sxs-lookup"><span data-stu-id="1dfff-104">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="1dfff-105">Para llevar a cabo estos pasos de forma masiva, hemos incluido vínculos a los cmdlets de Windows PowerShell que puede usar.</span><span class="sxs-lookup"><span data-stu-id="1dfff-105">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="1dfff-106">Para permitir (o impedir) que todos en la empresa puedan comunicarse con personas ajenas a esta, consulte:</span><span class="sxs-lookup"><span data-stu-id="1dfff-106">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="1dfff-107">[Permitir a los usuarios ponerse en contacto con Skype externo para usuarios profesionales](allow-users-to-contact-external-skype-for-business-users.md): puede permitir que la organización utilice avanzada Skype para las características de Business (recurso compartido de escritorios, aspecto para quién está en línea, etc.) para comunicarse con personas en una determinada de confianza empresarial (federado).</span><span class="sxs-lookup"><span data-stu-id="1dfff-107">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="1dfff-108">El artículo también explica cómo bloquear la comunicación con los dominios específicos.</span><span class="sxs-lookup"><span data-stu-id="1dfff-108">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="1dfff-109">[Permiten Skype para usuarios profesionales agregar contactos de Skype](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="1dfff-109">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="1dfff-110">Puede permitir que su organización use Skype Empresarial para buscar personas que usen la aplicación gratuita Skype y comunicarse con ellas con mensajería instantánea.</span><span class="sxs-lookup"><span data-stu-id="1dfff-110">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="1dfff-111">Establecer la configuración general de un usuario</span><span class="sxs-lookup"><span data-stu-id="1dfff-111">Configure general settings for one user</span></span>
<span data-ttu-id="1dfff-112"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="1dfff-112"></span></span>

<span data-ttu-id="1dfff-113">Debe tener [permisos de administrador](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) para llevar a cabo estos pasos.</span><span class="sxs-lookup"><span data-stu-id="1dfff-113">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>

<span data-ttu-id="1dfff-114">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**</span><span class="sxs-lookup"><span data-stu-id="1dfff-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="1dfff-115">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="1dfff-115">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="1dfff-116">Seleccione **Centros de administración** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="1dfff-116">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="1dfff-117">Seleccione **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="1dfff-117">Choose **Users**.</span></span>
    
    ![In the Skype for Business admin center, choose Users.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="1dfff-119">Elija los usuarios que desea editar:</span><span class="sxs-lookup"><span data-stu-id="1dfff-119">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="1dfff-120">En el panel derecho, elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="1dfff-120">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="1dfff-122">En la página de opciones **General**, active o desactive las casillas correspondientes a las características que quiera cambiar y luego elija **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1dfff-122">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="1dfff-123">**Opción**</span><span class="sxs-lookup"><span data-stu-id="1dfff-123">**Option**</span></span>|<span data-ttu-id="1dfff-124">**Detalles**</span><span class="sxs-lookup"><span data-stu-id="1dfff-124">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1dfff-125">Audio y vídeo HD</span><span class="sxs-lookup"><span data-stu-id="1dfff-125">Audio and HD video</span></span>  <br/> |<span data-ttu-id="1dfff-126">Permitir que esta persona grabar las reuniones de audio, las reuniones de audio y vídeos, o no permitir que ellos programar las reuniones (ninguno).</span><span class="sxs-lookup"><span data-stu-id="1dfff-126">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meetings (none).</span></span>  <br/> |
|<span data-ttu-id="1dfff-127">Registrar conversaciones y reuniones</span><span class="sxs-lookup"><span data-stu-id="1dfff-127">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="1dfff-128">Elija lo que puede grabar esta persona.</span><span class="sxs-lookup"><span data-stu-id="1dfff-128">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="1dfff-129">Esta opción no está disponible con Skype para empresarial básica.</span><span class="sxs-lookup"><span data-stu-id="1dfff-129">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="1dfff-130">Para cumplir con las normativas, desactive las características no archivadas</span><span class="sxs-lookup"><span data-stu-id="1dfff-130">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="1dfff-131">Elija esta opción si tiene la obligación legal de conservar la información almacenada por medios electrónicos.</span><span class="sxs-lookup"><span data-stu-id="1dfff-131">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="1dfff-132">Si selecciona esta opción, se desactiva las características que no se capturan cuando haya una [Conservación local](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) configurado en el centro de administración de Exchange.</span><span class="sxs-lookup"><span data-stu-id="1dfff-132">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) set up in the Exchange admin center.</span></span> <span data-ttu-id="1dfff-133">Desactiva las siguientes características:</span><span class="sxs-lookup"><span data-stu-id="1dfff-133">It turns off the following features:</span></span> <br/>  <span data-ttu-id="1dfff-134">Transferencia de archivos por mensajería instantánea</span><span class="sxs-lookup"><span data-stu-id="1dfff-134">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="1dfff-135">Páginas de OneNote compartidas</span><span class="sxs-lookup"><span data-stu-id="1dfff-135">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="1dfff-136">Anotaciones de PowerPoint</span><span class="sxs-lookup"><span data-stu-id="1dfff-136">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="1dfff-137">Para configurar estas opciones de configuración de forma masiva, use PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1dfff-137">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="1dfff-138">Consulte [configurar un equipo de Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="1dfff-138">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="1dfff-139">Bloquear comunicaciones externas</span><span class="sxs-lookup"><span data-stu-id="1dfff-139">Block external communications</span></span>
<span data-ttu-id="1dfff-140"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="1dfff-140"></span></span>

<span data-ttu-id="1dfff-141">Después de [Permitir que los usuarios de Skype Empresarial agreguen contactos de Skype](let-skype-for-business-users-add-skype-contacts.md) para todas las personas de su empresa, puede bloquear de manera selectiva las comunicaciones externas de personas específicas con estos pasos.</span><span class="sxs-lookup"><span data-stu-id="1dfff-141">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="1dfff-142">Elija **los usuarios**, seleccione los usuarios cuya configuración desea deshabilitar y, a continuación, elija **Editar** ![editar](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="1dfff-142">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="1dfff-143">Elija **Comunicaciones externas** y después desactive las opciones correspondientes:</span><span class="sxs-lookup"><span data-stu-id="1dfff-143">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
   - <span data-ttu-id="1dfff-144">**Usuarios externos de Skype Empresarial**: desactive esta casilla si no desea que el usuario pueda comunicarse con los usuarios de Skype Empresarial en dominios federados.</span><span class="sxs-lookup"><span data-stu-id="1dfff-144">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
   - <span data-ttu-id="1dfff-145">**Usuarios externos de Skype**: desactive esta casilla si no desea que el usuario pueda comunicarse con personas que usan la aplicación gratuita Skype.</span><span class="sxs-lookup"><span data-stu-id="1dfff-145">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="1dfff-146">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1dfff-146">Click **Save**.</span></span>
    
<span data-ttu-id="1dfff-147">Para configurar estas opciones de configuración de forma masiva, use PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1dfff-147">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="1dfff-148">Consulte [configurar un equipo de Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="1dfff-148">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="1dfff-149">Editar configuración de conferencia de audio de un usuario</span><span class="sxs-lookup"><span data-stu-id="1dfff-149">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="1dfff-150"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="1dfff-150"></span></span>

1. <span data-ttu-id="1dfff-151">Seleccione **los usuarios**, seleccione el usuario cuya configuración de conferencias de audio wan para editar, y, a continuación, elija **Editar** ![editar](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="1dfff-151">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="1dfff-152">Elija **conferencias de Audio**, seleccione el proveedor de conferencias de audio, escriba o cambiar la información solicitada y, a continuación, haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="1dfff-152">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="1dfff-153">**Configuración de Audioconferencia**</span><span class="sxs-lookup"><span data-stu-id="1dfff-153">**Audio conferencing setting**</span></span>|<span data-ttu-id="1dfff-154">**Descripción**</span><span class="sxs-lookup"><span data-stu-id="1dfff-154">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1dfff-155">**Nombre del proveedor**</span><span class="sxs-lookup"><span data-stu-id="1dfff-155">**Provider name**</span></span> <br/> |<span data-ttu-id="1dfff-156">Elija su proveedor de la lista.</span><span class="sxs-lookup"><span data-stu-id="1dfff-156">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="1dfff-157">**Número gratuito** (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="1dfff-157">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="1dfff-158">Un ACP de terceros, estos números de teléfono son los que le proporcionó el proveedor de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="1dfff-158">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="1dfff-159">Si el usuario utiliza Microsoft como proveedor de audioconferencia, estos serán los números establecidos en el puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="1dfff-159">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="1dfff-160">Dar formato a los números tal como desea que aparezca en Skype para las convocatorias de reunión de Microsoft Teams y profesionales.</span><span class="sxs-lookup"><span data-stu-id="1dfff-160">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="1dfff-161">**Número gratuito**</span><span class="sxs-lookup"><span data-stu-id="1dfff-161">**Toll-free number**</span></span> <br/> |<span data-ttu-id="1dfff-162">Un ACP de terceros, estos números de teléfono son los que le proporcionó el proveedor de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="1dfff-162">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="1dfff-163">Si el usuario utiliza Microsoft como proveedor de audioconferencia, estos serán los números establecidos en el puente de audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="1dfff-163">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="1dfff-164">Dar formato a los números tal como desea que aparezca en Skype para las convocatorias de reunión de Microsoft Teams y profesionales.</span><span class="sxs-lookup"><span data-stu-id="1dfff-164">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="1dfff-165">**PIN y el identificador de conferencia** (obligatorio)</span><span class="sxs-lookup"><span data-stu-id="1dfff-165">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="1dfff-166">El participante PIN o conferencia código, utilizado para unirse a reuniones que son programadas por este usuario y se proporcionan desde un proveedor de conferencia de audio de terceros.</span><span class="sxs-lookup"><span data-stu-id="1dfff-166">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="1dfff-167">Si el usuario está utilizando Microsoft como proveedor de conferencias de audio, esto no sea necesario.</span><span class="sxs-lookup"><span data-stu-id="1dfff-167">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="1dfff-168">Para configurar estas opciones de configuración de forma masiva, use PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1dfff-168">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="1dfff-169">Vea [el teléfono invita los números incluidos en](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Configurar el equipo de Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="1dfff-169">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="1dfff-170">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="1dfff-170">Related topics</span></span> 

[<span data-ttu-id="1dfff-171">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="1dfff-171">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="1dfff-172">Licencias complementarias de Skype Empresarial y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1dfff-172">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 
