---
title: "Enviar un correo electrónico a un usuario con su información de acceso telefónico"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Enviar un correo electrónico con su información de conferencia de audio de los usuarios."
ms.openlocfilehash: 70533de9fbf942a6ff7bd00f3998ede9f43ff96a
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2018
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information"></a><span data-ttu-id="99400-103">Enviar un correo electrónico a un usuario con su información de conferencias de Audio</span><span class="sxs-lookup"><span data-stu-id="99400-103">Send an email to a user with their Audio Conferencing information</span></span>

<span data-ttu-id="99400-104">A veces quizá tenga Skype para usuarios de negocios o Teams de Microsoft le envíe su información de conferencia de Audio.</span><span class="sxs-lookup"><span data-stu-id="99400-104">Sometimes Skype for Business or Microsoft Teams users may need you to send them their Audio Conferencing information.</span></span> <span data-ttu-id="99400-105">Puede hacerlo utilizando el **Skype para el centro de administración de negocios** y hacer clic en **Enviar información de conferencia a través de correo electrónico** en las propiedades de un usuario.</span><span class="sxs-lookup"><span data-stu-id="99400-105">You can do this by using the **Skype for Business admin center** and clicking **Send conference info via email** under the properties for a user.</span></span> <span data-ttu-id="99400-106">Al enviar este correo electrónico, contendrá toda la información de conferencia de audio, incluyendo:</span><span class="sxs-lookup"><span data-stu-id="99400-106">When you send this email, it will contain all of the audio conferencing information, including:</span></span>
  
- <span data-ttu-id="99400-107">El número de teléfono de la conferencia o el número de teléfono de acceso telefónico local del usuario.</span><span class="sxs-lookup"><span data-stu-id="99400-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="99400-108">El id. de conferencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="99400-108">The user's conference ID.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="99400-109">Identificadores estáticos se utilizan cuando las personas de la organización no desean recordar un número aleatorio; Puede seleccionar un determinado número o utilizar uno que sea fácil de recordar.</span><span class="sxs-lookup"><span data-stu-id="99400-109">Static IDs are used when people in your organization don't want to remember a random number; they can select a certain number or use one that's easy to remember.</span></span> <span data-ttu-id="99400-110">Cuando se utilizan identificadores de conferencia dinámico, cada reunión programaciones de un usuario obtener asignará un identificador único conferencia.</span><span class="sxs-lookup"><span data-stu-id="99400-110">When dynamic conference IDs are used, each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="99400-111">Si desea asignar el dinámico en lugar de conferencia estática IDs, [vaya aquí](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="99400-111">If you want to assign dynamic rather than static conference IDs, [go here](using-audio-conferencing-dynamic-ids-in-your-organization.md).</span></span> 
  
<span data-ttu-id="99400-112">Aquí es un ejemplo del correo electrónico que se envía:</span><span class="sxs-lookup"><span data-stu-id="99400-112">Here is an example of the email that is sent:</span></span>
  
![Correo electrónico de conferencia de acceso telefónico](../images/audio-conferencing-info.png)
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="99400-114">Enviar un correo electrónico con información de conferencia de audio a un usuario</span><span class="sxs-lookup"><span data-stu-id="99400-114">Send an email with audio conferencing information to a user</span></span>

1. <span data-ttu-id="99400-115">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="99400-115">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="99400-116">Ir al **Centro de administración de Office 365** > **Skype para el negocio**y la exploración de la izquierda, haga clic en **conferencias de Audio**.</span><span class="sxs-lookup"><span data-stu-id="99400-116">Go to the **Office 365 admin center** > **Skype for Business**, and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="99400-117">Haga clic en **usuarios**y, a continuación, seleccione el usuario.</span><span class="sxs-lookup"><span data-stu-id="99400-117">Click **Users**, and then select the user.</span></span>
    
4. <span data-ttu-id="99400-118">En el panel de acciones, haga clic en **Enviar información de conferencia por correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="99400-118">In the Action pane, click **Send conference info via email**.</span></span>
    
> [!TIP]
> <span data-ttu-id="99400-119">También puede enviar correo electrónico al usuario con la configuración de conferencia de audio editando las propiedades del usuario y, a continuación, haga clic en **conferencias de Audio** > **Enviar información de conferencia a través de correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="99400-119">You can also send email to the user with the audio conferencing settings by editing the user's properties and then clicking **Audio conferencing** > **Send conference info via email**.</span></span> 
  
## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="99400-120">¿Qué más debe saber sobre este correo electrónico?</span><span class="sxs-lookup"><span data-stu-id="99400-120">What else should you know about this email?</span></span>

- <span data-ttu-id="99400-121">Hay varios correos electrónicos que se envían a los usuarios de la organización después de que se hayan habilitado para conferencias de audio:</span><span class="sxs-lookup"><span data-stu-id="99400-121">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="99400-122">Cuando se asigna una licencia de **Conferencia de Audio** a ellos.</span><span class="sxs-lookup"><span data-stu-id="99400-122">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="99400-123">Cuando restablece manualmente conferencias de audio PIN del usuario.</span><span class="sxs-lookup"><span data-stu-id="99400-123">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="99400-124">Al restablecer de forma manual el id. de conferencia del usuario.</span><span class="sxs-lookup"><span data-stu-id="99400-124">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="99400-125">Cuando se quita una licencia de **Conferencia de Audio** de ellos.</span><span class="sxs-lookup"><span data-stu-id="99400-125">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="99400-126">Cuando se cambia el proveedor de conferencia de audio para un usuario de Microsoft a otro proveedor, o **Ninguno**.</span><span class="sxs-lookup"><span data-stu-id="99400-126">When the audio conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="99400-127">Cuando se cambia el proveedor de conferencia de audio de un usuario a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="99400-127">When the audio conferencing provider for a user is changed to Microsoft.</span></span>
    
- <span data-ttu-id="99400-128">De forma predeterminada, será el remitente de los mensajes de correo electrónico de Office 365, pero puede cambiar la dirección de correo electrónico y nombre para mostrar mediante el uso de Windows PowerShell y el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) .</span><span class="sxs-lookup"><span data-stu-id="99400-128">By default, the sender of the emails will be from Office 365, but you can change the email address and display name by using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) cmdlet.</span></span> <span data-ttu-id="99400-129">Para realizar cambios en la dirección de correo electrónico que está enviando el correo electrónico a los usuarios, debe:</span><span class="sxs-lookup"><span data-stu-id="99400-129">To make changes to the email address that is sending the email to users, you must:</span></span>
    
  - <span data-ttu-id="99400-130">Escriba la dirección de correo electrónico en el parámetro SendEmailFromAddress.</span><span class="sxs-lookup"><span data-stu-id="99400-130">Enter the email address in the SendEmailFromAddress parameter.</span></span>
    
  - <span data-ttu-id="99400-131">Establezca el parámetro SendEmailOverride en True.</span><span class="sxs-lookup"><span data-stu-id="99400-131">Set the SendEmailOverride parameter to True.</span></span>
    
  - <span data-ttu-id="99400-132">Escriba el nombre de pantalla de correo electrónico en el parámetro SendEmailFromDisplayName.</span><span class="sxs-lookup"><span data-stu-id="99400-132">Enter the email display name in the SendEmailFromDisplayName parameter.</span></span>
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > <span data-ttu-id="99400-133">Si quiere cambiar la información de la dirección de correo electrónico, asegúrese de que las directivas de correo electrónico de entrada de su organización permitan la recepción de mensajes enviados por la dirección de correo electrónico personalizada configurada.</span><span class="sxs-lookup"><span data-stu-id="99400-133">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address that is set.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="99400-134">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="99400-134">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="99400-135">Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="99400-135">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
    <span data-ttu-id="99400-136">Para enviar un correo electrónico al usuario con su información de conferencia de audio, ejecute lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="99400-136">To send an email to the user with their audio conferencing information, run the following:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

-  <span data-ttu-id="99400-p104">Cuando se trata de Windows PowerShell, Skype Empresarial Online se centra en la administración de usuarios y en determinar qué pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tiene varias tareas que realizar. Para empezar a usar Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="99400-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="99400-140">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="99400-140">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="99400-141">Las mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="99400-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="99400-p105">Windows PowerShell cuenta con muchas ventajas en velocidad, simplicidad y productividad en comparación con solo usar el centro de administración de Office 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="99400-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="99400-144">Introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="99400-144">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="99400-145">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="99400-145">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="99400-146">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="99400-146">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="99400-p106">El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="99400-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="99400-149">See also</span><span class="sxs-lookup"><span data-stu-id="99400-149">Related topics</span></span>

[<span data-ttu-id="99400-150">Conferencias de acceso telefónico en Office 365</span><span class="sxs-lookup"><span data-stu-id="99400-150">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)
