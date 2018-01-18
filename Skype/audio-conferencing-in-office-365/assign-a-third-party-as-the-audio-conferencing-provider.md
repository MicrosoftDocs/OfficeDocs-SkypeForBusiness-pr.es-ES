---
title: Asignar a un tercero como el proveedor de conferencia de audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 77f68ca7-c1cf-40d9-9c23-87a6b2abe9de
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords:
- ms.lync.lac.DialInExportImport
- ms.lync.lac.DialInProvider
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Aprenda a configurar un tercero como proveedor de conferencia de acceso telefónico con Skype para el negocio. "
ms.openlocfilehash: a53a2e63f15aa40eb6a88ab13daba2022b35e3b6
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="assign-a-third-party-as-the-audio-conferencing-provider"></a><span data-ttu-id="38fee-103">Asignar a un tercero como el proveedor de conferencia de audio</span><span class="sxs-lookup"><span data-stu-id="38fee-103">Assign a third-party as the audio conferencing provider</span></span>

<span data-ttu-id="38fee-104">Un proveedor de conferencia de audio proporciona el *puente de conferencia*.</span><span class="sxs-lookup"><span data-stu-id="38fee-104">An audio conferencing provider supplies the *conference bridge*.</span></span> <span data-ttu-id="38fee-105">El puente de conferencia proporciona el número de teléfono de acceso telefónico, pasadores y conferencia identificadores para las reuniones que se crean.</span><span class="sxs-lookup"><span data-stu-id="38fee-105">The conference bridge provides the dial-in phone number, PINs, and conference IDs for meetings that are created.</span></span> <span data-ttu-id="38fee-106">Sólo debe asignar a un proveedor de conferencia de audio para las personas que se van a programar o plomo Skype para reuniones de negocios o Teams de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="38fee-106">You only need to assign an audio conferencing provider to people who are going to schedule or lead Skype for Business or Microsoft Teams meetings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="38fee-107">Para Teams de Microsoft, un usuario no puede utilizar un proveedor de conferencia de audio de terceros, deben utilizar audioconferencia en Office 365, que establece el proveedor de conferencia de audio en Microsoft.</span><span class="sxs-lookup"><span data-stu-id="38fee-107">For Microsoft Teams, a user can't use a third-party audio conferencing provider, they must use Audio Conferencing in Office 365, which sets the audio conferencing provider to Microsoft.</span></span> 
  
## <a name="steps-to-do-before-you-can-assign-a-third-party-audio-conferencing-provider"></a><span data-ttu-id="38fee-108">Pasos a realizar antes de que se puede asignar a un proveedor de conferencia de audio de terceros</span><span class="sxs-lookup"><span data-stu-id="38fee-108">Steps to do BEFORE you can assign a third-party audio conferencing provider</span></span>

1. <span data-ttu-id="38fee-109">Dependiendo del plan de Office 365, debe comprar licencias adicionales de **Conferencia de Audio** para las personas de la organización que se va a programar o plomo Skype para reuniones de negocios o Teams de Microsoft mediante conferencias de Audio.</span><span class="sxs-lookup"><span data-stu-id="38fee-109">Depending on your Office 365 plan, you might need to buy **Audio Conferencing** add-on licenses for the people in your organization who are going to schedule or lead Skype for Business or Microsoft Teams meetings using Audio Conferencing.</span></span> <span data-ttu-id="38fee-110">Para obtener más información, vea [Skype para negocios y equipos de Microsoft licencias adicionales](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="38fee-110">To learn more, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="38fee-111">Si ha adquirido licencias adicionales de **Conferencias de Audio** , asignarlos a las personas de la organización que se va a programar o llevar las reuniones que se utilizan en conferencias de Audio.</span><span class="sxs-lookup"><span data-stu-id="38fee-111">If you purchased **Audio Conferencing** add-on licenses, assign them to the people in your organization who are going to schedule or lead meetings that use Audio Conferencing.</span></span> <span data-ttu-id="38fee-112">Consulte [Asignar Skype para licencias de negocio y equipos de Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="38fee-112">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="38fee-113">Si asigna una licencia de **Conferencias de Audio** a otra persona **después** que se les asigne a un proveedor de conferencia de audio de terceros, esa persona se establecerá automáticamente para utilizar en su lugar Microsoft como su proveedor de conferencia de audio!</span><span class="sxs-lookup"><span data-stu-id="38fee-113">If you assign an **Audio Conferencing** license to someone **AFTER** you assign them a third-party audio conferencing provider, that person will automatically be set to use Microsoft as their audio conferencing provider instead!</span></span> <span data-ttu-id="38fee-114">Si esto ocurre, debe quitar Microsoft como proveedor de conferencia de audio antes de poder asignar a un proveedor de conferencia de audio de terceros a ellos.</span><span class="sxs-lookup"><span data-stu-id="38fee-114">If this happens, you will need to first remove Microsoft as the audio conferencing provider before you can assign a third-party audio conferencing provider to them.</span></span>
  
3. <span data-ttu-id="38fee-115">Encontrar un proveedor de conferencia de audio de terceros en [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530).</span><span class="sxs-lookup"><span data-stu-id="38fee-115">Find a third-party audio conferencing provider at [Microsoft PinPoint](https://go.microsoft.com/fwlink/?LinkId=797530).</span></span> <span data-ttu-id="38fee-116">Póngase en contacto con ellos y descubra cómo conseguir cosas con ellos.</span><span class="sxs-lookup"><span data-stu-id="38fee-116">Contact them and find out how to get things set up with them.</span></span>
    
    <span data-ttu-id="38fee-117">Le proporcionará:</span><span class="sxs-lookup"><span data-stu-id="38fee-117">They will give you:</span></span>
    
  - <span data-ttu-id="38fee-118">**Números de acceso telefónico (de pago)** y números de teléfono gratuitos si están disponibles.</span><span class="sxs-lookup"><span data-stu-id="38fee-118">**Dial-in numbers (toll)** and toll-free numbers if they are available.</span></span>
    
  - <span data-ttu-id="38fee-119">**Conferencia de identificadores** que se utilizan para cada persona que programa reuniones.</span><span class="sxs-lookup"><span data-stu-id="38fee-119">**Conference IDs** that are used for each person who schedules meetings.</span></span> <span data-ttu-id="38fee-120">Algunos ACP llame a estos códigos de acceso de la conferencia.</span><span class="sxs-lookup"><span data-stu-id="38fee-120">Some ACPs call these conference passcodes.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="38fee-121">Si ha hecho la inicial configurada para un ACP de terceros pero ahora necesita realizar cambios, en la parte inferior de la página de **Puente de Microsoft** **haga clic aquí para configurar un proveedor de conferencia de audio de terceros**.</span><span class="sxs-lookup"><span data-stu-id="38fee-121">If you have done the initial set up for an third-party ACP but you now need to make changes, at the bottom of the **Microsoft Bridge** page **Click here to configure a third-party audio conferencing provider**.</span></span> 
  
    > [!NOTE]
    > <span data-ttu-id="38fee-122">Cuando habilita a una persona para conferencias de audio y asignarles a un proveedor de conferencia de audio de otros fabricantes, los números de audio y los identificadores de conferencia (contraseñas) se agregan automáticamente a cualquier **nuevo** Skype para reuniones de negocios en línea creados por ellos mismos.</span><span class="sxs-lookup"><span data-stu-id="38fee-122">When you enable a person for audio conferencing, and assign them a third-party audio conferencing provider, the audio numbers and conference IDs (passcodes) are automatically added to any **new** Skype for Business Online meetings that they create.</span></span>
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-a-user"></a><span data-ttu-id="38fee-123">Cómo asignar a un proveedor de conferencia de audio de terceros a un usuario</span><span class="sxs-lookup"><span data-stu-id="38fee-123">How to assign a third-party audio conferencing provider to a user</span></span>

1. <span data-ttu-id="38fee-124">En el **Skype para el centro de administración de negocios**, elegir **los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="38fee-124">In the **Skype for Business admin center**, choose **Users**.</span></span> <span data-ttu-id="38fee-125">Seleccione el usuario de la lista y haga clic en **Editar** en el panel de acción.</span><span class="sxs-lookup"><span data-stu-id="38fee-125">Select the user from the list and click **Edit** in the action pane.</span></span>
    
2. <span data-ttu-id="38fee-126">En la página de propiedades del usuario, haga clic en **conferencias de Audio** y escriba esta información:</span><span class="sxs-lookup"><span data-stu-id="38fee-126">On the user's properties page, click **Audio conferencing** and enter this information:</span></span>
    
  - <span data-ttu-id="38fee-127">**Nombre del proveedor** Seleccione el proveedor de la lista.</span><span class="sxs-lookup"><span data-stu-id="38fee-127">**Provider name** Select the third-party provider from the list.</span></span>
    
  - <span data-ttu-id="38fee-128">**Número de peaje predeterminado** Esto es necesario.</span><span class="sxs-lookup"><span data-stu-id="38fee-128">**Default toll number** This is required.</span></span>
    
  - <span data-ttu-id="38fee-129">**Predeterminado el número de teléfono gratuito** Esto no es necesario.</span><span class="sxs-lookup"><span data-stu-id="38fee-129">**Default toll-free number** This not required.</span></span>
    
  - <span data-ttu-id="38fee-130">**Id. de conferencia** Esto es proporcionada por su proveedor de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="38fee-130">**Conference ID** This is provided by your audio conferencing provider.</span></span>
    
3. <span data-ttu-id="38fee-131">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="38fee-131">Click **Save**.</span></span>
    
4. <span data-ttu-id="38fee-132">Envíe el NIP que recibió del proveedor de conferencia de audio de cada persona.</span><span class="sxs-lookup"><span data-stu-id="38fee-132">Send each person the PIN you received from the audio conferencing provider.</span></span> <span data-ttu-id="38fee-133">El NIP se requiera para llamar en que el organizador de la conferencia o el líder.</span><span class="sxs-lookup"><span data-stu-id="38fee-133">The PIN may be required to call in as the conference call organizer or leader.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="38fee-134">Cuando se utiliza un proveedor de conferencia de audio de otros fabricantes, no hay una manera de ver o configurar el PIN en nombre de los organizadores de la reunión.</span><span class="sxs-lookup"><span data-stu-id="38fee-134">When you use a third-party audio conferencing provider, there isn't a way for you to see or set PINs on behalf of meeting organizers.</span></span> 
  
## <a name="how-to-assign-a-third-party-audio-conferencing-provider-to-many-people-at-the-same-time"></a><span data-ttu-id="38fee-135">Cómo asignar a un proveedor de conferencia de audio de terceros a varias personas al mismo tiempo</span><span class="sxs-lookup"><span data-stu-id="38fee-135">How to assign a third-party audio conferencing provider to many people at the same time</span></span>

1. <span data-ttu-id="38fee-136">En el **Skype para el centro de administración de negocios**, elija **conferencias de Audio** > **puente de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="38fee-136">In the **Skype for Business admin center**, choose **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="38fee-137">En la parte inferior de la página, haga clic en el vínculo de **Si desea configurar un proveedor de conferencia de audio de terceros en su lugar, haga clic aquí**.</span><span class="sxs-lookup"><span data-stu-id="38fee-137">At the bottom of the page, click the link in **If you would like to configure a third-party audio conferencing provider instead, click here**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="38fee-138">Si ha hecho la inicial configurada para un ACP de terceros pero ahora necesita realizar cambios, en la parte inferior de la página de **Puente de Microsoft** , **haga clic aquí para configurar un proveedor de conferencia de audio de terceros**.</span><span class="sxs-lookup"><span data-stu-id="38fee-138">If you have done the initial set up for an third-party ACP but you now need to make changes, at the bottom of the **Microsoft Bridge** page, **Click here to configure a third-party audio conferencing provider**.</span></span> 
  
2. <span data-ttu-id="38fee-139">En la página **configurar un tercero proveedor de conferencia de audio** , en **Importar y exportar usuarios**, haga clic en **Asistente para exportar**y, a continuación, siga los pasos del **Asistente para exportar usuarios**.</span><span class="sxs-lookup"><span data-stu-id="38fee-139">On the **Configure a third party audio conferencing provider** page, under **Import and export users**, click **Export wizard**, and then follow the steps in the **Export Users wizard**.</span></span> <span data-ttu-id="38fee-140">Cuando termine, tendrá un archivo que enumere las personas que desea configurar para conferencias de audio.</span><span class="sxs-lookup"><span data-stu-id="38fee-140">When you finish, you'll have a file that lists the people you want to set up for audio conferencing.</span></span>
    
3. <span data-ttu-id="38fee-141">Enviar el archivo creado con el proveedor de conferencia de audio de terceros.</span><span class="sxs-lookup"><span data-stu-id="38fee-141">Send the file you created to your third-party audio conferencing provider.</span></span> <span data-ttu-id="38fee-142">Se agrega información de conferencia de audio para las personas incluidas en el archivo y, a continuación, devuelva el archivo.</span><span class="sxs-lookup"><span data-stu-id="38fee-142">They will add audio conferencing information for the people listed in the file, and then return the file to you.</span></span>
    
4. <span data-ttu-id="38fee-143">Compruebe que el archivo devuelto contiene la información correcta.</span><span class="sxs-lookup"><span data-stu-id="38fee-143">Double-check that the returned file has the right information in it.</span></span> <span data-ttu-id="38fee-144">Hemos oído de instancias donde no todos los usuarios enumerados en el archivo tiene la información correcta.</span><span class="sxs-lookup"><span data-stu-id="38fee-144">We've heard of instances where not everyone listed in the file got the right information.</span></span>
    
5. <span data-ttu-id="38fee-145">En **Configurar una página de proveedor de conferencia de audio de terceros**, en **los usuarios importar y exportar**, haga clic en **Asistente para importar**y, a continuación, siga los pasos del **Asistente para importar usuarios**</span><span class="sxs-lookup"><span data-stu-id="38fee-145">On the **Configure a third-party audio conferencing provider page**, under **Import and export users**, click **Import wizard**, and then follow the steps in the **Import Users wizard**</span></span>
    
6. <span data-ttu-id="38fee-146">Envíe el NIP que recibió del proveedor de conferencia de audio de cada persona.</span><span class="sxs-lookup"><span data-stu-id="38fee-146">Send each person the PIN you received from the audio conferencing provider.</span></span> <span data-ttu-id="38fee-147">El NIP se requiera para llamar en que el organizador de la conferencia o el líder.</span><span class="sxs-lookup"><span data-stu-id="38fee-147">The PIN may be required to call in as the conference call organizer, or leader.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="38fee-148">Cuando se utiliza un proveedor de conferencia de audio de otros fabricantes, no hay una manera de ver o configurar el PIN en nombre de los organizadores de la reunión.</span><span class="sxs-lookup"><span data-stu-id="38fee-148">When you use a third-party audio conferencing provider, there isn't a way for you to see or set PINs on behalf of meeting organizers.</span></span> 
  
## <a name="when-to-use-a-third-party-audio-conferencing-provider"></a><span data-ttu-id="38fee-149">Cuándo utilizar un proveedor de conferencia de audio de terceros</span><span class="sxs-lookup"><span data-stu-id="38fee-149">When to use a third-party audio conferencing provider</span></span>

<span data-ttu-id="38fee-150">Si estás en un país o región donde no está disponible en Office 365 conferencias de Audio, la calidad de servicio no es gran cosa debido a su ubicación o tiene un contrato existente con un proveedor de conferencia de audio de terceros, se recomienda utilizar un audio de otros fabricantes proveedor de conferencia.</span><span class="sxs-lookup"><span data-stu-id="38fee-150">If you are in a country or region where Audio Conferencing in Office 365 isn't available, the service quality isn't great because of its location, or you have an existing contract with a third-party audio conferencing provider, we recommend using a third-party audio conferencing provider.</span></span> <span data-ttu-id="38fee-151">De lo contrario, se recomienda utilizar Microsoft como proveedor de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="38fee-151">Otherwise, we recommend using Microsoft as your audio conferencing provider.</span></span>
  
## <a name="automate-assigning-the-third-party-audio-conferencing-provider-by-using-windows-powershell"></a><span data-ttu-id="38fee-152">Automatizar la asignación de proveedor de conferencia de audio de terceros mediante Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="38fee-152">Automate assigning the third-party audio conferencing provider by using Windows PowerShell</span></span>

- <span data-ttu-id="38fee-153">Para ahorrar tiempo o automatizar esta tarea, puede utilizar el cmdlet [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851) .</span><span class="sxs-lookup"><span data-stu-id="38fee-153">To save time or automate this, you can use the [Set-CsUserAcp](https://go.microsoft.com/fwlink/?LinkId=716851) cmdlet.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="38fee-154">Para cambiar el proveedor de audio de Microsoft a un proveedor de conferencia de audio de terceros, debe quitar Microsoft como proveedor de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="38fee-154">To change the audio provider from Microsoft to a third-party audio conferencing provider, you must remove Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="38fee-155">Para ello, use el cmdlet [Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ) .</span><span class="sxs-lookup"><span data-stu-id="38fee-155">To do this, use the [Disable-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617692 ) cmdlet.</span></span>
  
- <span data-ttu-id="38fee-156">Para obtener más información sobre el uso de Windows PowerShell, vea [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038).</span><span class="sxs-lookup"><span data-stu-id="38fee-156">For more information about using Windows PowerShell, see [Using Windows PowerShell to do common Skype for Business Online management tasks](https://go.microsoft.com/fwlink/?LinkId=525038).</span></span>
    
## <a name="what-else-do-i-need-to-know"></a><span data-ttu-id="38fee-157">Más información de utilidad</span><span class="sxs-lookup"><span data-stu-id="38fee-157">What else do I need to know?</span></span>

<span data-ttu-id="38fee-158">Una persona de su organización sólo puede utilizar un proveedor de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="38fee-158">A person in your organization can only use one audio conferencing provider.</span></span> <span data-ttu-id="38fee-159">Para cambiar el proveedor de conferencia de audio de una persona a Microsoft, consulte [mover el proveedor de conferencia de audio de un usuario a Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md) o [Asignar Microsoft como proveedor de conferencia de audio](assign-microsoft-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="38fee-159">To change a person's audio conferencing provider to Microsoft, see [Moving a user's audio conferencing provider to Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md) or [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="38fee-160">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="38fee-160">Related Topics</span></span>

[<span data-ttu-id="38fee-161">Configurar conferencias de Audio de Skype para la empresa y Teams de Microsoft</span><span class="sxs-lookup"><span data-stu-id="38fee-161">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  
[<span data-ttu-id="38fee-162">Configurar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="38fee-162">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  

