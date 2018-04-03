---
title: Configurar el teléfono invita números incluidos en
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
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
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: 59ebd95f5b7f7ee546ab272596adf353b2a7adbc
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2018
---
# <a name="set-the-phone-numbers-included-on-invites"></a><span data-ttu-id="699dd-103">Configurar el teléfono invita números incluidos en</span><span class="sxs-lookup"><span data-stu-id="699dd-103">Set the phone numbers included on invites</span></span>

<span data-ttu-id="699dd-104">Conferencias de audio en Office 365 permite a los usuarios de su organización crear Skype para reuniones de negocios y Teams de Microsoft y, a continuación, permitir a los usuarios llamar a esas reuniones utilizando un teléfono.</span><span class="sxs-lookup"><span data-stu-id="699dd-104">Audio Conferencing in Office 365 enables users in your organization to create Skype for Business and Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span> <span data-ttu-id="699dd-105">En Office 365, tiene la opción de utilizar un puente de conferencia de audio de Microsoft o de un puente de conferencia de audio de terceros que está alojado en un proveedor aprobado de audioconferencias (ACP).</span><span class="sxs-lookup"><span data-stu-id="699dd-105">In Office 365, you have the option of using a Microsoft audio conferencing bridge or a third-party audio conferencing bridge that is hosted by an approved audio conferencing provider (ACP).</span></span>
  
> [!NOTE]
> <span data-ttu-id="699dd-106">No existe un recurso que incluya un listado con todos los números de acceso telefónico local de Audioconferencia.</span><span class="sxs-lookup"><span data-stu-id="699dd-106">There isn't a resource that contains a listing of all of the dial-in numbers for Audio Conferencing.</span></span> <span data-ttu-id="699dd-107">Si está buscando para ver si hay números de teléfono de marcado disponibles en su área o país o región, utilice el **Skype para el centro de administración de negocios** > **voz** > **Números de teléfono**, haga clic en **Agregar** nuevos números de servicio de ** **.</span><span class="sxs-lookup"><span data-stu-id="699dd-107">If you are looking to see if there are dial-in phone numbers available in your area or country/region, use the **Skype for Business admin center** > **Voice** > **Phone Numbers**, click **Add** then **New Service Numbers**.</span></span> <span data-ttu-id="699dd-108">Utilice las listas de **País o región**, estado o región de **** y **Ciudad** para filtrar su búsqueda. > también, si está buscando números de servicio gratuito de peaje, seleccione **número gratuito** desde el estado o región **** lista.</span><span class="sxs-lookup"><span data-stu-id="699dd-108">Use the lists for **Country/Region**, **State/Region** and **City** to filter your search.> Also, if you are looking for toll free service numbers, select **Toll-Free** from the **State/Region** list.</span></span>
  
<span data-ttu-id="699dd-109">Un puente de conferencia ofrece un conjunto de números de teléfono de acceso telefónico para su organización.</span><span class="sxs-lookup"><span data-stu-id="699dd-109">A conferencing bridge gives you a set of dial-in phone numbers for your organization.</span></span> <span data-ttu-id="699dd-110">Todos ellos pueden utilizarse para unirse a las reuniones que ha creado el organizador de una reunión, pero puede seleccionar cuáles se incluirán en sus invitaciones a la reunión.</span><span class="sxs-lookup"><span data-stu-id="699dd-110">All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="699dd-111">Puede haber un máximo de un teléfono y un número de teléfono gratuito en la invitación de reunión para el organizador de una reunión, pero también hay un vínculo que se encuentra en la parte inferior de cada invitación de reunión que se abre la lista completa de todos los números de teléfono de acceso telefónico que puede utilizarse para unirse a una reunión.</span><span class="sxs-lookup"><span data-stu-id="699dd-111">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 
  
## <a name="setting-the-default-dial-in-phone-number-for-a-meeting-organizer"></a><span data-ttu-id="699dd-112">Establecer el número de teléfono marcado predeterminado para el organizador de una reunión</span><span class="sxs-lookup"><span data-stu-id="699dd-112">Setting the default dial-in phone number for a meeting organizer</span></span>

1. <span data-ttu-id="699dd-113">Inicie sesión en Office 365 con su cuenta profesional o educativa.</span><span class="sxs-lookup"><span data-stu-id="699dd-113">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="699dd-114">Seleccione **Centros de administración** > **Skype Empresarial**.</span><span class="sxs-lookup"><span data-stu-id="699dd-114">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="699dd-115">Seleccione **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="699dd-115">Choose **Users**.</span></span>
    
    ![Seleccionar los usuarios en el Skype para el centro de administración de negocio de muestra](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. <span data-ttu-id="699dd-117">Seleccione los usuarios que desea editar:</span><span class="sxs-lookup"><span data-stu-id="699dd-117">Choose the users you want to edit:</span></span>
    
  - <span data-ttu-id="699dd-118">Para seleccionar un único usuario, seleccione el nombre del usuario.</span><span class="sxs-lookup"><span data-stu-id="699dd-118">To select a single user, select the user's name.</span></span>
    
  - <span data-ttu-id="699dd-119">Para seleccionar todos los usuarios de la página, active la casilla situada junto al **nombre para mostrar** en la parte superior de la lista.</span><span class="sxs-lookup"><span data-stu-id="699dd-119">To select all users on the page, select the box next to **Display name** at the top of the list.</span></span>
    
  - <span data-ttu-id="699dd-120">Para seleccionar varios usuarios, active la casilla situada junto a cada nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="699dd-120">To select multiple users, select the box next to each user's name.</span></span>
    
5. <span data-ttu-id="699dd-121">En el panel derecho, elija **Editar**.</span><span class="sxs-lookup"><span data-stu-id="699dd-121">In the right panel, choose **Edit**.</span></span>
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="699dd-123">Elija la **conferencia de Audio**.</span><span class="sxs-lookup"><span data-stu-id="699dd-123">Choose **Audio conferencing**.</span></span>
    
7. <span data-ttu-id="699dd-124">En la página de **Propiedades** , en la lista **nombre de proveedor** , seleccione el proveedor para el usuario.</span><span class="sxs-lookup"><span data-stu-id="699dd-124">On the **Properties** page, in the **Provider name** list, choose the provider for the user.</span></span> <span data-ttu-id="699dd-125">Dependiendo del proveedor, complete los siguientes cuadros.</span><span class="sxs-lookup"><span data-stu-id="699dd-125">Depending on the provider, complete the following boxes.</span></span>
    
  - <span data-ttu-id="699dd-126">**Microsoft es el proveedor**: **número gratuito predeterminada** listas para seleccionar los números predeterminados para el usuario y utilizar el **número de pago predeterminado** .</span><span class="sxs-lookup"><span data-stu-id="699dd-126">**Microsoft is the provider**: Use the **Default toll number** and **Default toll-free number** lists to select the default numbers for the user.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="699dd-127">Debe asignarse al menos un número gratuito para el puente de conferencia antes de que se puede establecer como el número gratuito de predeterminado de un usuario.</span><span class="sxs-lookup"><span data-stu-id="699dd-127">At least one toll-free number must be assigned to your conferencing bridge before it can be set as the default toll-free number of a user.</span></span> <span data-ttu-id="699dd-128">Para obtener un número de teléfono gratuito, vea [números de teléfono de servicio de obtención de Skype para empresas y equipos de Microsoft](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="699dd-128">To get a toll-free number, see [Getting service phone numbers for Skype for Business and Microsoft Teams](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span></span> 
  
  - <span data-ttu-id="699dd-129">**Un tercero es el proveedor**: utilice los campos de **número de teléfono** y **número de teléfono gratuito** para especificar los números para el usuario.</span><span class="sxs-lookup"><span data-stu-id="699dd-129">**A third-party is the provider**: Use the **Toll number** and **Toll-free number** fields to enter the numbers for the user.</span></span>
    
## <a name="reset-audio-conferencing-phone-numbers"></a><span data-ttu-id="699dd-130">Restablecer los números de teléfono de conferencia de audio</span><span class="sxs-lookup"><span data-stu-id="699dd-130">Reset audio conferencing phone numbers</span></span>

1. <span data-ttu-id="699dd-131">En el **Skype para el centro de administración de negocios**, elija **conferencias de Audio**.</span><span class="sxs-lookup"><span data-stu-id="699dd-131">In the **Skype for Business admin center**, choose **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="699dd-132">En la parte superior de la página, elija **los usuarios**.</span><span class="sxs-lookup"><span data-stu-id="699dd-132">At the top of the page, choose **Users**.</span></span>
    
3. <span data-ttu-id="699dd-133">Seleccionar los usuarios que desea restablecer y, a continuación, en el panel Acción, haga clic en **Borrar**.</span><span class="sxs-lookup"><span data-stu-id="699dd-133">Choose the users you want to reset, and then in the Action pane, click **Clear**.</span></span>
    
<span data-ttu-id="699dd-134">De forma predeterminada, al cambiar la configuración de conferencia de un usuario, se envía un correo electrónico al usuario.</span><span class="sxs-lookup"><span data-stu-id="699dd-134">By default, when you change a user's conferencing settings, an email is sent to the user.</span></span> <span data-ttu-id="699dd-135">Para cambiar esta configuración, vea [Habilitar o deshabilitar el envío correos electrónicos cuando cambie la configuración de conferencia de Audio](enable-or-disable-sending-emails-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="699dd-135">To change this, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="699dd-136">Cuando se cambia la configuración de conferencia de audio de un usuario, periódica y futuro Skype para reuniones de negocios y Teams de Microsoft debe actualiza y se envía a los asistentes.</span><span class="sxs-lookup"><span data-stu-id="699dd-136">When you change a user's audio conferencing settings, recurring and future Skype for Business and Microsoft Teams meetings must be updated and sent to attendees.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="699dd-137">¿Desea saber cómo administrar con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="699dd-137">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="699dd-138">Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688).</span><span class="sxs-lookup"><span data-stu-id="699dd-138">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet.</span></span>
    
- <span data-ttu-id="699dd-139">Use el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) para cambiar el número de pago o el número gratuito predeterminado para usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="699dd-139">Use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) cmdlet to change the default toll or toll-free number for specific users.</span></span>
    
    <span data-ttu-id="699dd-140">Para cambiar el número gratuito predeterminado de un usuario, ejecute:</span><span class="sxs-lookup"><span data-stu-id="699dd-140">To change the default toll-free number for a user, run:</span></span>
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- <span data-ttu-id="699dd-141">Use el cmdlet de **Set-CsOnlineDialInConferencingUserDefaultNumber** para cambiar el número de pago o el número gratuito predeterminado de los usuarios, según el número predeterminado original o la ubicación.</span><span class="sxs-lookup"><span data-stu-id="699dd-141">Use the **Set-CsOnlineDialInConferencingUserDefaultNumber** cmdlet to change the default toll or toll-free number of users based on their original default number or their location.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="699dd-142">Para encontrar el BridgeID, utilice el **Get-CsOnlineDialInConferencingBridge**.</span><span class="sxs-lookup"><span data-stu-id="699dd-142">To find the BridgeID, use the **Get-CsOnlineDialInConferencingBridge**.</span></span>
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - <span data-ttu-id="699dd-143">Para establecer el número de teléfono gratuito de forma predeterminada para todos los usuarios sin uno a +18005551234, ejecute:</span><span class="sxs-lookup"><span data-stu-id="699dd-143">To set the default toll-free number for all users without one to +18005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - <span data-ttu-id="699dd-144">Para cambiar el número gratuito por defecto de todos los usuarios que tienen +18005551234 como su número de llamada gratuita predeterminado a +18005551239, ejecute:</span><span class="sxs-lookup"><span data-stu-id="699dd-144">To change the default toll-free number of all users that have +18005551234 as their default toll-free number to +18005551239, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - <span data-ttu-id="699dd-145">Para establecer el número gratuito de forma predeterminada todos los usuarios ubicados en los Estados Unidos a +18005551234, ejecute:</span><span class="sxs-lookup"><span data-stu-id="699dd-145">To set the default toll-free number of all users located in the U.S. to +18005551234, run:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
## <a name="want-to-learn-more-about-windows-powershell"></a><span data-ttu-id="699dd-146">¿Desea obtener más información acerca de Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="699dd-146">Want to learn more about Windows PowerShell?</span></span>
- <span data-ttu-id="699dd-p107">En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:</span><span class="sxs-lookup"><span data-stu-id="699dd-p107">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="699dd-150">Una introducción a Windows PowerShell y Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="699dd-150">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="699dd-151">Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365</span><span class="sxs-lookup"><span data-stu-id="699dd-151">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="699dd-p108">Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:</span><span class="sxs-lookup"><span data-stu-id="699dd-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="699dd-154">Mejores formas de administrar Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="699dd-154">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="699dd-155">Usar Windows PowerShell para administrar Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="699dd-155">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="699dd-156">Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="699dd-156">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="699dd-157">See also</span><span class="sxs-lookup"><span data-stu-id="699dd-157">Related topics</span></span>

[<span data-ttu-id="699dd-158">Probar o comprar Audioconferencia en Office 365</span><span class="sxs-lookup"><span data-stu-id="699dd-158">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
