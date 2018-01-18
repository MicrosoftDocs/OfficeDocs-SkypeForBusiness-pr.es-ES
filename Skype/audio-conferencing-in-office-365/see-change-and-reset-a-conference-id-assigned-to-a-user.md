---
title: Ver, cambiar y restablecer un ID de conferencia asignado a un usuario
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Aprenda a asignar un ID de conferencia a un usuario de Skype para el negocio y qué la conferencia ID deben ser parámetros. "
ms.openlocfilehash: 46edf684a835984524ce988da532b6b9a14931da
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="see-change-and-reset-a-conference-id-assigned-to-a-user"></a><span data-ttu-id="cb293-103">Ver, cambiar y restablecer un ID de conferencia asignado a un usuario</span><span class="sxs-lookup"><span data-stu-id="cb293-103">See, change, and reset a conference ID assigned to a user</span></span>

<span data-ttu-id="cb293-104">Un ID de conferencia se asigna automáticamente a un Skype para usuarios de negocios o Teams de Microsoft cuando se configuran para conferencias de Audio en Office 365 y usar Microsoft como proveedor de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="cb293-104">A conferencing ID is automatically assigned to a Skype for Business or Microsoft Teams user when they are set up for Audio Conferencing in Office 365 and use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="cb293-105">El ID de conferencia puede ser estáticas o dinámicas y se envía la invitación a la reunión cuando se programa la reunión.</span><span class="sxs-lookup"><span data-stu-id="cb293-105">The conference ID assigned can be either static or dynamic and is sent in the meeting invite when the meeting is scheduled.</span></span>
  
<span data-ttu-id="cb293-106">Identificadores estáticos se utilizan cuando las personas de la organización no desean recordar un número aleatorio; Puede seleccionar un determinado número o utilizar uno que sea fácil de recordar.</span><span class="sxs-lookup"><span data-stu-id="cb293-106">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="cb293-107">Cuando se utilizan identificadores de conferencia dinámico, cada reunión programaciones de un usuario obtener asignará un identificador único conferencia.</span><span class="sxs-lookup"><span data-stu-id="cb293-107">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="cb293-108">Si desea asignar el dinámico en lugar de conferencia estática IDs, [vaya aquí](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="cb293-108">If you want to assign dynamic rather than static conference IDs, [go here](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span>
  
<span data-ttu-id="cb293-109">Aunque crea automáticamente un ID de conferencia estática y se asigna a un usuario, puede haber ocasiones cuando un usuario no desea utilizar esta y desea establecerla en un número determinado, o cuando los usuarios no recuerdan o han perdido su ID de conferencia.</span><span class="sxs-lookup"><span data-stu-id="cb293-109">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or when your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="cb293-110">Puede utilizar el **Skype para el centro de administración de negocios** y de Windows PowerShell para ver, cambiar y restablecer su ID de conferencia.</span><span class="sxs-lookup"><span data-stu-id="cb293-110">You can use the **Skype for Business admin center** and Windows PowerShell to view, change, and reset their conference ID.</span></span>
  
<span data-ttu-id="cb293-111">Se enviará un correo electrónico al usuario con el identificador de la conferencia y los números de teléfono de conferencia de audio predeterminada o si restablece el ID de la conferencia se enviará otro correo electrónico que incluirá el identificador de la conferencia, pero no un PIN.</span><span class="sxs-lookup"><span data-stu-id="cb293-111">An email will be sent to the user with the conference ID and the default audio conferencing phone numbers, or if you reset the conference ID a different email will be sent that will include the conference ID but not a PIN.</span></span>
  
## <a name="view-and-change-conference-ids"></a><span data-ttu-id="cb293-112">Ver y cambiar los identificadores de la conferencia</span><span class="sxs-lookup"><span data-stu-id="cb293-112">View and change conference IDs</span></span>

### <a name="to-view-the-conference-id"></a><span data-ttu-id="cb293-113">Para ver el identificador de la conferencia</span><span class="sxs-lookup"><span data-stu-id="cb293-113">To view the conference ID</span></span>

<span data-ttu-id="cb293-114">Puede ver su ID de conferencia y enviarla a los usuarios.</span><span class="sxs-lookup"><span data-stu-id="cb293-114">You can view their conference ID and send it to users.</span></span>
  
1. <span data-ttu-id="cb293-115">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="cb293-115">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="cb293-116">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="cb293-116">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="cb293-117">En el **Skype para el centro de administración de negocios**> **conferencias de Audio** > **usuarios**, seleccione el usuario que necesita la conferencia Id.</span><span class="sxs-lookup"><span data-stu-id="cb293-117">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, select the user who needs the conference ID.</span></span>
    
4. <span data-ttu-id="cb293-118">En la página acción, busque bajo **Id. de conferencia**.</span><span class="sxs-lookup"><span data-stu-id="cb293-118">In the Action page, look under **Conference ID**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="cb293-119">Toda la información de la conferencia puede enviar al usuario en un correo electrónico que incluye el Id. de conferencia y números de teléfono de audio haciendo clic en el vínculo **Enviar información de conferencia a través de correo electrónico** después de seleccionar el usuario en la página **usuarios** .</span><span class="sxs-lookup"><span data-stu-id="cb293-119">You can send all of the conferencing information to the user in an email that includes the conference ID and audio phone numbers by clicking the **Send conference info via email** link after you select the user on the **Users** page.</span></span>
  
    <span data-ttu-id="cb293-120">Puede utilizar Windows PowerShell para ver el Id. de conferencia para un usuario.</span><span class="sxs-lookup"><span data-stu-id="cb293-120">You can use Windows PowerShell to view the conference ID for a user.</span></span> <span data-ttu-id="cb293-121">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="cb293-121">To do so, run:</span></span>
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    <span data-ttu-id="cb293-122">Consulte [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) para obtener más información acerca del cmdlet.</span><span class="sxs-lookup"><span data-stu-id="cb293-122">See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.</span></span>
    
### <a name="to-assign-or-change-the-conference-id"></a><span data-ttu-id="cb293-123">Para asignar o cambiar el ID de la conferencia</span><span class="sxs-lookup"><span data-stu-id="cb293-123">To assign or change the conference ID</span></span>

<span data-ttu-id="cb293-124">Puede asignar o cambiar un ID de conferencia para un usuario si, por ejemplo, alguien quiere un ID de conferencia que sea fácil de recordar.</span><span class="sxs-lookup"><span data-stu-id="cb293-124">You can assign or change a conference ID for a user if, for example, someone wants a conference ID that's easy to remember.</span></span>

  > [!NOTE]
  > <span data-ttu-id="cb293-125">No se puede utilizar el Skype para el centro de administración de negocios para modificar un ID de conferencia que se ha creado automáticamente, pero puede utilizar Windows PowerShell para modificar o cambiar el ID de conferencia que ha establecido.</span><span class="sxs-lookup"><span data-stu-id="cb293-125">The Skype for Business admin center can't be used to edit a conference ID that has been automatically created, but you can use Windows PowerShell to edit or change a conference ID that you have set.</span></span> 
     
<span data-ttu-id="cb293-126">Para modificar o cambiar el ID de conferencia para un usuario, ejecute:</span><span class="sxs-lookup"><span data-stu-id="cb293-126">To edit or change the conference ID for a user, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964
  ```

  > [!TIP]
  > <span data-ttu-id="cb293-127">Para establecer el id. de conferencia de un usuario, ejecute:</span><span class="sxs-lookup"><span data-stu-id="cb293-127">A conference ID must contain 7 digits, and you can't change it in the Skype for Business admin center or by using Windows PowerShell.</span></span> 
  
### <a name="to-reset-the-conference-id"></a><span data-ttu-id="cb293-128">Para restablecer el identificador de la conferencia</span><span class="sxs-lookup"><span data-stu-id="cb293-128">To reset the conference ID</span></span>

<span data-ttu-id="cb293-129">Puede restablecer un Id. de conferencia para un usuario si, por ejemplo, si olvida.</span><span class="sxs-lookup"><span data-stu-id="cb293-129">You can reset a conference ID for a user if, for example, if they forget it.</span></span>
  
1. <span data-ttu-id="cb293-130">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="cb293-130">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="cb293-131">Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="cb293-131">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="cb293-132">En el **Skype para el centro de administración de negocios**> **conferencias de Audio** > **los usuarios**, en el panel de acción en el **Id. de conferencia**, haga clic en **Restablecer**.</span><span class="sxs-lookup"><span data-stu-id="cb293-132">In the **Skype for Business admin center**> **Audio conferencing** > **Users**, in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="cb293-133">En el **Restablecer Id. de conferencia?** ventana, haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="cb293-133">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="cb293-134">Una conferencia que se creará automáticamente el ID y el correo electrónico enviado al usuario con el nuevo ID de conferencia.</span><span class="sxs-lookup"><span data-stu-id="cb293-134">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span>
    
    <span data-ttu-id="cb293-135">Puede restablecer el Id. de conferencia para un usuario mediante el de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cb293-135">You can reset the conference ID for a user by using the Windows PowerShell.</span></span> <span data-ttu-id="cb293-136">Para ello, ejecute:</span><span class="sxs-lookup"><span data-stu-id="cb293-136">To do this, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetLeaderPIN 8271964
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="cb293-137">¿Qué más tengo que saber?</span><span class="sxs-lookup"><span data-stu-id="cb293-137">What else should you know?</span></span>

   > [!IMPORTANT]
   >  <span data-ttu-id="cb293-138">Después se crea un nuevo ID de conferencia o uno se restablece, no se puede utilizar el ID de conferencia antigua los llamadores.</span><span class="sxs-lookup"><span data-stu-id="cb293-138">After a new conference ID is created or one is reset, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="cb293-139">Debe notificar a los usuarios a programar sus invitaciones para asegurarse de que la nueva conferencia que ID se agrega a las invitaciones para reuniones existentes.</span><span class="sxs-lookup"><span data-stu-id="cb293-139">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="cb293-140">Los usuarios pueden utilizar el Skype para la herramienta de migración de reuniones de negocios para actualizar sus reuniones existentes.</span><span class="sxs-lookup"><span data-stu-id="cb293-140">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="cb293-141">Para ver cómo descargar, instalar y ejecutar la herramienta, vea: [Herramienta de actualización de la reunión para Skype para empresas y Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype para los negocios en línea, herramienta de migración de reunión (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)y [Skype para los negocios en línea, herramienta de migración de reunión (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="cb293-141">To see how to download, install, and run the tool, see: [Meeting Update Tool for Skype for Business and Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
- <span data-ttu-id="cb293-142">El id. de conferencia tiene que contener siete dígitos y no se puede cambiar en el Centro de administración de Skype Empresarial ni con Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="cb293-142">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
    
- <span data-ttu-id="cb293-143">El identificador de la conferencia debe cumplir la longitud en dígitos establecido en el puente de conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="cb293-143">The conference ID must meet the length in digits set on the audio conferencing bridge.</span></span> <span data-ttu-id="cb293-144">No puede utilizar caracteres especiales o alfabéticos en conferencia identificadores; pueden utilizarse sólo números.</span><span class="sxs-lookup"><span data-stu-id="cb293-144">You can't use alphabetic or special characters in conference IDs; only numbers can be used.</span></span>
    
- <span data-ttu-id="cb293-145">El ID de conferencia para todos los usuarios de conferencia de audio será 7 dígitos de forma predeterminada y no se puede cambiar el número de dígitos.</span><span class="sxs-lookup"><span data-stu-id="cb293-145">The conference ID for all of your audio conferencing users will be 7 digits by default, and the number of digits can't be changed.</span></span>
    
- <span data-ttu-id="cb293-146">Si el usuario se mueve de Microsoft como proveedor de conferencia de audio a un proveedor de conferencia de audio de terceros o el proveedor de conferencia de audio se establece en **Ninguno**, el identificador de la conferencia ya no funcionará.</span><span class="sxs-lookup"><span data-stu-id="cb293-146">If the user is moved from Microsoft as the audio conferencing provider to a third-party audio conferencing provider or the audio conferencing provider is set to **None**, the conference ID will no longer work.</span></span> <span data-ttu-id="cb293-147">Consulte [asignar un tercero como el proveedor de conferencia de audio](assign-a-third-party-as-the-audio-conferencing-provider.md) o [mover el proveedor de conferencia de audio de un usuario a Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="cb293-147">See [Assign a third-party as the audio conferencing provider](assign-a-third-party-as-the-audio-conferencing-provider.md) or [Moving a user's audio conferencing provider to Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md).</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="cb293-148">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="cb293-148">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="cb293-p110">En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="cb293-p110">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="cb293-152">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="cb293-152">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - <span data-ttu-id="cb293-153">Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="cb293-153">[Why you need to use Office 365 PowerShell](https://go.microsoft.com/fwlink/?LinkId=525041)</span></span>
    
- <span data-ttu-id="cb293-p111">Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="cb293-p111">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="cb293-156">Mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="cb293-156">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="cb293-157">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="cb293-157">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="cb293-158">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="cb293-158">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="cb293-159">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="cb293-159">Related topics</span></span>

[<span data-ttu-id="cb293-160">Configurar Audioconferencia para Skype Empresarial y Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cb293-160">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
  

