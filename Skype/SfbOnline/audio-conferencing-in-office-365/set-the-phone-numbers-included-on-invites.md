---
title: Establecer el teléfono los números incluidos en invitaciones en Skype para profesionales en línea
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: c78a3fb140431dd46b3850e1d01e7fb29fb29210
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32229418"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a><span data-ttu-id="0b3df-103">Establecer el teléfono los números incluidos en invitaciones en Skype para profesionales en línea</span><span class="sxs-lookup"><span data-stu-id="0b3df-103">Set the phone numbers included on invites in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="0b3df-104">Para obtener información acerca de la reunión invitar a los números de teléfono en Microsoft Teams, vea [establecer el teléfono los números incluidos en invitaciones en los equipos de Microsoft](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).</span><span class="sxs-lookup"><span data-stu-id="0b3df-104">For information about meeting invite phone numbers in Microsoft Teams, see [Set the phone numbers included on invites in Microsoft Teams](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).</span></span>

<span data-ttu-id="0b3df-105">Conferencias de audio en Office 365 permiten a los usuarios de la organización crear Skype para reuniones de negocios y, a continuación, permitir a los usuarios para conectarse a las reuniones utilizando un teléfono.</span><span class="sxs-lookup"><span data-stu-id="0b3df-105">Audio Conferencing in Office 365 enables users in your organization to create Skype for Business meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="0b3df-106">En Office 365, tendrá la opción de utilizar un puente de conferencia de audio de Microsoft o un puente de conferencia de audio de terceros que está hospedado en un proveedor de conferencias de audio aprobadas (ACP).</span><span class="sxs-lookup"><span data-stu-id="0b3df-106">In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0b3df-107">No existe un recurso que incluya un listado con todos los números de acceso telefónico local de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="0b3df-107">There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing.</span></span> <span data-ttu-id="0b3df-108">Si está buscando para ver si hay números de teléfono de acceso telefónico disponibles en su área o país o región, utilice la **Skype para el centro de administración de negocio** > **voz** > **Los números de teléfono**, haga clic en **Agregar** , a continuación, \*\*los nuevos números de servicio \*\*.</span><span class="sxs-lookup"><span data-stu-id="0b3df-108">If you are looking to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add** then **New Service Numbers**.</span></span> <span data-ttu-id="0b3df-109">Use las listas de **País o región**, provincia o región de \*\*\*\* y **Ciudad** para filtrar su search.> también, si busca los números de teléfono de pago servicio gratuito, seleccione **gratuito** de la provincia o región \*\*\*\* lista.</span><span class="sxs-lookup"><span data-stu-id="0b3df-109">Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.</span></span>
  
<span data-ttu-id="0b3df-110">Un puente de conferencia le proporciona un conjunto de números de teléfono de acceso telefónico para su organización.</span><span class="sxs-lookup"><span data-stu-id="0b3df-110">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="0b3df-111">Todos ellos se pueden usar para unirse a las reuniones que ha creado un organizador de la reunión, pero puede seleccionar cuáles se incluirá en sus invitaciones de reunión.</span><span class="sxs-lookup"><span data-stu-id="0b3df-111">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0b3df-112">Puede haber un máximo de un teléfono de pago y un número de teléfono gratuito en la invitación a la reunión para un organizador de la reunión, pero también hay un vínculo que se encuentra en la parte inferior de cada invitación a la reunión que se abre la lista completa de todos los números de teléfono de acceso telefónico que se pueden usar para unirse a una reunión.</span><span class="sxs-lookup"><span data-stu-id="0b3df-112">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a><span data-ttu-id="0b3df-113">Establecer el número de teléfono de marcado predeterminado para un organizador de la reunión</span><span class="sxs-lookup"><span data-stu-id="0b3df-113">Set the default dial-in phone number for a meeting organizer</span></span>

1. <span data-ttu-id="0b3df-114">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="0b3df-114">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="0b3df-115">Seleccione **Centros de administración** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="0b3df-115">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="0b3df-116">Seleccione **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="0b3df-116">Choose **Users**.</span></span>
    
    ![Selección de los usuarios en el Skype para el centro de administración de negocio de muestra](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. <span data-ttu-id="0b3df-118">Elija los usuarios que desea editar:</span><span class="sxs-lookup"><span data-stu-id="0b3df-118">Choose the users you want to edit:</span></span>
    
   - <span data-ttu-id="0b3df-119">Para seleccionar un único usuario, seleccione el nombre del usuario.</span><span class="sxs-lookup"><span data-stu-id="0b3df-119">To select a single user, select the user's name.</span></span>
    
   - <span data-ttu-id="0b3df-120">Para seleccionar todos los usuarios en la página, active la casilla situada junto al **nombre para mostrar** en la parte superior de la lista.</span><span class="sxs-lookup"><span data-stu-id="0b3df-120">To select all users on the page, select the box next to **Display name** at the top of the list.</span></span>
    
   - <span data-ttu-id="0b3df-121">Para seleccionar varios usuarios, active la casilla situada junto a cada nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="0b3df-121">To select multiple users, select the box next to each user's name.</span></span>
    
5. <span data-ttu-id="0b3df-122">En el panel derecho, elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0b3df-122">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="0b3df-124">Elija **conferencias de Audio**.</span><span class="sxs-lookup"><span data-stu-id="0b3df-124">Choose **Audio conferencing**.</span></span>
    
7. <span data-ttu-id="0b3df-125">En la página de **Propiedades** , en la lista **nombre del proveedor** , seleccione el proveedor para el usuario.</span><span class="sxs-lookup"><span data-stu-id="0b3df-125">On the **Properties** page, in the **Provider name** list, choose the provider for the user.</span></span> <span data-ttu-id="0b3df-126">Dependiendo del proveedor, complete los siguientes cuadros.</span><span class="sxs-lookup"><span data-stu-id="0b3df-126">Depending on the provider, complete the following boxes.</span></span>
    
   - <span data-ttu-id="0b3df-127">**Microsoft es el proveedor**: el **número de teléfono de pago predeterminado** y **número de teléfono gratuito predeterminada** listas para seleccionar los números de forma predeterminada para el usuario.</span><span class="sxs-lookup"><span data-stu-id="0b3df-127">**Microsoft is the provider**: Use the **Default toll number** and **Default toll-free number** lists to select the default numbers for the user.</span></span>
    
     > [!NOTE]
     > <span data-ttu-id="0b3df-128">Debe asignarse al menos un número de teléfono gratuito para el puente de conferencia antes de que se puede establecer como el número de teléfono gratuito predeterminado de un usuario.</span><span class="sxs-lookup"><span data-stu-id="0b3df-128">At least one toll-free number must be assigned to your conferencing bridge before it can be set as the default toll-free number of a user.</span></span> <span data-ttu-id="0b3df-129">Para obtener un número de teléfono gratuito, vea [números de teléfono de servicio de obtención de Skype para la empresa](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="0b3df-129">To get a toll-free number, see [Getting service phone numbers for Skype for Business](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span></span> 
  
   - <span data-ttu-id="0b3df-130">**Un tercero es el proveedor**: Use los campos de **número de teléfono de pago** y **número de teléfono gratuito** para escribir los números para el usuario.</span><span class="sxs-lookup"><span data-stu-id="0b3df-130">**A third-party is the provider**: Use the **Toll number** and **Toll-free number** fields to enter the numbers for the user.</span></span>


## <a name="reset-audio-conferencing-phone-numbers"></a><span data-ttu-id="0b3df-131">Restablecer los números de teléfono de conferencia de audio</span><span class="sxs-lookup"><span data-stu-id="0b3df-131">Reset audio conferencing phone numbers</span></span>

1. <span data-ttu-id="0b3df-132">En el **Skype para el centro de administración de negocio**, elija **conferencias de Audio**.</span><span class="sxs-lookup"><span data-stu-id="0b3df-132">In the **Skype for Business admin center**, choose **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="0b3df-133">En la parte superior de la página, elija **usuarios**.</span><span class="sxs-lookup"><span data-stu-id="0b3df-133">At the top of the page, choose **Users**.</span></span>
    
3. <span data-ttu-id="0b3df-134">Elija los usuarios que desea restablecer y, a continuación, en el panel de acciones, haga clic en **Borrar**.</span><span class="sxs-lookup"><span data-stu-id="0b3df-134">Choose the users you want to reset, and then in the Action pane, click **Clear**.</span></span>
    
<span data-ttu-id="0b3df-135">De forma predeterminada, cuando se cambia la configuración de conferencia de un usuario, se envía un correo electrónico al usuario.</span><span class="sxs-lookup"><span data-stu-id="0b3df-135">By default, when you change a user's conferencing settings, an email is sent to the user.</span></span> <span data-ttu-id="0b3df-136">Para cambiar esta configuración, vea [Habilitar o deshabilitar el envío por correo electrónico cuando cambie la configuración de conferencias de Audio](enable-or-disable-sending-emails-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="0b3df-136">To change this, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0b3df-137">Cuando se cambia la configuración de conferencia de audio de un usuario, periódica y futuro Skype para reuniones de negocios debe actualiza y se envía a los asistentes.</span><span class="sxs-lookup"><span data-stu-id="0b3df-137">When you change a user's audio conferencing settings, recurring and future Skype for Business meetings must be updated and sent to attendees.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="0b3df-138">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="0b3df-138">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="0b3df-139">Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688).</span><span class="sxs-lookup"><span data-stu-id="0b3df-139">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet.</span></span>
    
- <span data-ttu-id="0b3df-140">Use el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) para cambiar el número de pago o el número gratuito predeterminado para usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="0b3df-140">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>
    
    <span data-ttu-id="0b3df-141">Para cambiar el número gratuito predeterminado de un usuario, ejecute:</span><span class="sxs-lookup"><span data-stu-id="0b3df-141">To change the default toll-free number for a user, run:</span></span>
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- <span data-ttu-id="0b3df-142">Use el cmdlet de **Set-CsOnlineDialInConferencingUserDefaultNumber** para cambiar el número de pago o el número gratuito predeterminado de los usuarios, según el número predeterminado original o la ubicación.</span><span class="sxs-lookup"><span data-stu-id="0b3df-142">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0b3df-143">Para buscar el BridgeID, use el cmdlet **Get-CsOnlineDialInConferencingBridge** .</span><span class="sxs-lookup"><span data-stu-id="0b3df-143">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge** cmdlet.</span></span>
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - <span data-ttu-id="0b3df-144">Para establecer el número de teléfono gratuito de forma predeterminada para todos los usuarios sin uno a +18005551234, ejecute:</span><span class="sxs-lookup"><span data-stu-id="0b3df-144">To set the default toll-free number for all users without one to +18005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - <span data-ttu-id="0b3df-145">Para cambiar el número de teléfono gratuito predeterminado de todos los usuarios que tienen +18005551234 como su número de teléfono gratuito predeterminado a +18005551239, ejecute:</span><span class="sxs-lookup"><span data-stu-id="0b3df-145">To change the default toll-free number of all users that have +18005551234 as their default toll-free number to +18005551239, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="0b3df-146">Para establecer el número de teléfono gratuito predeterminado de todos los usuarios que se encuentra en los Estados Unidos a +18005551234, ejecute:</span><span class="sxs-lookup"><span data-stu-id="0b3df-146">To set the default toll-free number of all users located in the U.S. to +18005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
  ## <a name="want-to-learn-more-about-windows-powershell"></a><span data-ttu-id="0b3df-147">¿Desea obtener más información acerca de Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="0b3df-147">Want to learn more about Windows PowerShell?</span></span>
- <span data-ttu-id="0b3df-p107">En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="0b3df-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0b3df-151">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="0b3df-151">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="0b3df-152">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="0b3df-152">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="0b3df-p108">Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="0b3df-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="0b3df-155">Mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0b3df-155">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="0b3df-156">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="0b3df-156">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="0b3df-157">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="0b3df-157">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="0b3df-158">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="0b3df-158">Related topics</span></span>

[<span data-ttu-id="0b3df-159">Probar o comprar Audioconferencia en Office 365</span><span class="sxs-lookup"><span data-stu-id="0b3df-159">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
