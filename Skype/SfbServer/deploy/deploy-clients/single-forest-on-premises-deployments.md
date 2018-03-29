---
title: Implementaciones locales de bosque único de Sistema de salas de Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: Lea este tema para obtener información sobre cómo implementar Sistema de salas de Skype en un entorno local de un único bosque.
ms.openlocfilehash: b998c0b1e139951297eca8a963536dd59dcd4b39
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a><span data-ttu-id="78afd-103">Implementaciones locales de bosque único de Sistema de salas de Skype</span><span class="sxs-lookup"><span data-stu-id="78afd-103">Skype Room System single forest on-premises deployments</span></span>
 
<span data-ttu-id="78afd-104">Lea este tema para obtener información sobre cómo implementar Sistema de salas de Skype en un entorno local de un único bosque.</span><span class="sxs-lookup"><span data-stu-id="78afd-104">Read this topic to learn how to deploy Skype Room System in a single forest on-premises environment.</span></span>
  
<span data-ttu-id="78afd-105">Esta sección proporciona una visión general de los pasos para el aprovisionamiento de la cuenta de sistema del sitio de Skype en Exchange Server y Skype para Business Server alojado en una implementación local de bosque único.</span><span class="sxs-lookup"><span data-stu-id="78afd-105">This section provides an overview of the steps for provisioning the Skype Room System account on Exchange Server and Skype for Business Server hosted in a single forest on-premises deployment.</span></span>
  
## <a name="single-forest-on-premises-deployments"></a><span data-ttu-id="78afd-106">Implementaciones locales de un solo bosque</span><span class="sxs-lookup"><span data-stu-id="78afd-106">Single forest on-premises deployments</span></span>

<span data-ttu-id="78afd-107">Si ya tiene una cuenta de buzón de recursos para la sala de conferencias, puede usarla.</span><span class="sxs-lookup"><span data-stu-id="78afd-107">If you already have a resource mailbox account for the conferencing room, you can use it.</span></span> <span data-ttu-id="78afd-108">Si no es así, necesitará crear una.</span><span class="sxs-lookup"><span data-stu-id="78afd-108">Otherwise, you will need to create a new one.</span></span> <span data-ttu-id="78afd-109">Puede usar el Shell de administración de Exchange (PowerShell) o la consola de administración de Exchange para crear una cuenta de buzón de recursos.</span><span class="sxs-lookup"><span data-stu-id="78afd-109">You can use either Exchange Management Shell (PowerShell) or Exchange Management Console to create a new resource mailbox account.</span></span> <span data-ttu-id="78afd-110">Se recomienda usar un nuevo (eliminar el buzón antiguo y volver a crear) el buzón de recursos para el sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="78afd-110">We recommend using a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="78afd-111">Asegúrese de realizar una copia de seguridad de todos los datos del buzón antes de eliminarlo y de exportarlos de nuevo al buzón recién creado con el cliente de Outlook (consulte Exportar o realizar copias de seguridad de mensajes, calendario, tareas y contactos para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="78afd-111">Make sure to back up mailbox data before deleting and then export it back to the re-created mailbox using the Outlook client (see Export or back up messages, calendar, tasks, and contacts for more information).</span></span> <span data-ttu-id="78afd-112">Para restaurar las reuniones perdidas por eliminar el buzón, consulte [Conectar o restaurar un buzón eliminado](https://technet.microsoft.com/en-us/library/jj863438%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="78afd-112">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/en-us/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="78afd-113">Para usar una cuenta de buzón de recursos (por ejemplo, LRS-01), siga los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="78afd-113">To use an existing resource mailbox account (for example, LRS-01) follow the steps below:</span></span>
  
1. <span data-ttu-id="78afd-114">Ejecute el siguiente comando de PowerShell de administración de Exchange:</span><span class="sxs-lookup"><span data-stu-id="78afd-114">Run the following Exchange Management PowerShell command:</span></span>
    
  ```
  Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
  ```

2. <span data-ttu-id="78afd-115">Si planea crear un nuevo buzón para una organización de Exchange local de un solo bosque, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="78afd-115">If you plan to create a new mailbox, then, for a single forest on-premises Exchange organization, run the following command:</span></span>
    
  ```
  New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
  ```

  <span data-ttu-id="78afd-p102">En el ejemplo anterior se crea una cuenta de usuario habilitada en Active Directory y un buzón de sala para una sala de conferencia en una organización de Exchange local. El parámetro RoomMailboxPassword especifica la contraseña para la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="78afd-p102">The above example creates an enabled user account in Active Directory and a room mailbox for a conference room in an on-premises Exchange organization. The RoomMailboxPassword parameter specifies the password for the user account.</span></span>
    
3. <span data-ttu-id="78afd-118">Configure la cuenta para resolver automáticamente conflictos aceptando o rechazando reuniones.</span><span class="sxs-lookup"><span data-stu-id="78afd-118">Configure the account to automatically resolve conflicts by accepting/rejecting meetings.</span></span> <span data-ttu-id="78afd-119">Sala de conferencias de equipado con sistema de sala de cuentas de Exchange pueden administrarse por individuos, pero tenga en cuenta que hasta que la persona acepta una reunión no aparecerá en el calendario de la pantalla de inicio de sistema de sala de Skype de Skype.</span><span class="sxs-lookup"><span data-stu-id="78afd-119">Skype Room System-equipped conference room accounts in Exchange can be managed by individuals, but note that until the individual accepts a meeting it will not appear on the Skype Room System home screen calendar.</span></span>
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   <span data-ttu-id="78afd-120">Para ver un conjunto completo de comandos disponibles, consulte Set-CalendarProcessing.</span><span class="sxs-lookup"><span data-stu-id="78afd-120">For a complete set of commands available, see Set-CalendarProcessing.</span></span>
    
   <span data-ttu-id="78afd-121">Para recordar a los organizadores de la reunión para realizar la reunión un Skype en línea para la reunión de negocios en Outlook, ejecute el siguiente comando para configurar un sugerencias de correo electrónico para la nueva cuenta:</span><span class="sxs-lookup"><span data-stu-id="78afd-121">To remind meeting organizers to make the meeting an online Skype for Business meeting in Outlook, run the following command to set up a MailTip for the new account:</span></span> 
    
   ```
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. <span data-ttu-id="78afd-p104">Use los siguientes comandos para configurar las cadenas localizadas. Si su organización lo requiere, también puede agregar traducciones personalizadas:</span><span class="sxs-lookup"><span data-stu-id="78afd-p104">Use the following commands to configure localized strings. If required by your organization, you can also add custom translations:</span></span> 
   ```
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. <span data-ttu-id="78afd-124">Opcional: Configurar reunión, aceptación que proporciona a los usuarios información acerca de Skype para salas de reuniones de negocios y lo que puede esperar al programar y unirse a reuniones.</span><span class="sxs-lookup"><span data-stu-id="78afd-124">Optional: Configure meeting acceptance text that provides users with information about Skype for Business Meeting Room, and what to expect when they schedule and join meetings.</span></span> 
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a><span data-ttu-id="78afd-125">Comprobar la cuenta de buzón de recursos en Active Directory</span><span class="sxs-lookup"><span data-stu-id="78afd-125">Check Resource Mailbox Account in Active Directory</span></span>

<span data-ttu-id="78afd-126">La cuenta de buzón de la sala de conferencias que creó Exchange en el paso 1 anterior puede ser un objeto de usuario deshabilitado en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="78afd-126">The conference room mailbox account created by Exchange in step 1 above might be a disabled user object in Active Directory.</span></span> <span data-ttu-id="78afd-127">Sistema de sala de Skype no puede iniciar sesión o autenticar mediante la autenticación Kerberos o NTLM si la cuenta está deshabilitada en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="78afd-127">Skype Room System cannot sign in or authenticate by using Kerberos/NTLM authentication if the account is disabled in Active Directory.</span></span> <span data-ttu-id="78afd-128">El cliente del sistema de sala de Skype debe ser capaz de autenticarse en servicios Web de Exchange para recuperar la configuración de calendario y también debe ser capaz de enviar correo electrónico con el contenido de la Pizarra.</span><span class="sxs-lookup"><span data-stu-id="78afd-128">The Skype Room System client must be able to authenticate against Exchange Web Services to retrieve calendar settings, and must also be able to send email with whiteboard contents.</span></span> 
  
<span data-ttu-id="78afd-129">Por lo tanto, si la cuenta está deshabilitada, debe habilitarla en Active Directory siguiendo estos pasos:</span><span class="sxs-lookup"><span data-stu-id="78afd-129">Therefore, if the account is disabled, you must enable this account in Active Directory by doing the following:</span></span> 
  
1. <span data-ttu-id="78afd-130">En Active Directory, ejecute el siguiente comando para habilitar el inicio de sesión de la cuenta:</span><span class="sxs-lookup"><span data-stu-id="78afd-130">In Active Directory, run the following command to enable account log on:</span></span> 
    
   ```
   Set-ADAccountPassword -Identity LRS01
   ```

   <span data-ttu-id="78afd-131">Cuando ejecute este comando, se le solicitará que escriba la contraseña actual y que vuelva a escribirla una segunda vez para confirmarla.</span><span class="sxs-lookup"><span data-stu-id="78afd-131">Running this command will prompt you to enter the current password, and then to re-enter the password twice for confirmation.</span></span>
    
2. <span data-ttu-id="78afd-132">Una vez que haya establecido la contraseña, ejecute el siguiente comando para habilitar la cuenta:</span><span class="sxs-lookup"><span data-stu-id="78afd-132">Once the password is set, run the following command to enable the account:</span></span> 
    
   ```
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a><span data-ttu-id="78afd-133">Habilitar sistema de sala de Skype cuentas de Skype para empresas</span><span class="sxs-lookup"><span data-stu-id="78afd-133">Enabling Skype Room System Accounts for Skype for Business</span></span>

<span data-ttu-id="78afd-134">Esta sección proporciona una visión general de los pasos necesarios para habilitar Skype para empresas para su cuenta de sala de conferencia, que estará configurada en el sistema del sitio de Skype.</span><span class="sxs-lookup"><span data-stu-id="78afd-134">This section provides an overview of the steps required to enable Skype for Business for your conference room account, which will be configured on Skype Room System.</span></span> 
  
<span data-ttu-id="78afd-135">Después de crear una cuenta de buzón de recursos para las salas de conferencias, usar Skype para negocios de Shell de administración de servidor para habilitar cuentas de sistema del sitio de Skype para Skype para servicios de negocios.</span><span class="sxs-lookup"><span data-stu-id="78afd-135">After you create a resource mailbox account for the conferencing rooms, use Skype for Business Server Management Shell to enable Skype Room System accounts for Skype for Business services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="78afd-136">El procedimiento siguiente asume que ha habilitado la cuenta de sistema del sitio de Skype en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="78afd-136">The following procedure assumes that you have enabled the Skype Room System account in Active Directory.</span></span> 
  
1. <span data-ttu-id="78afd-137">Ejecute el siguiente comando para habilitar la cuenta de sistema del sitio de Skype en un Skype para grupo Business Server:</span><span class="sxs-lookup"><span data-stu-id="78afd-137">Run the following command to enable the Skype Room System account on a Skype for Business Server pool:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. <span data-ttu-id="78afd-138">Opcional: permita que esta cuenta realice y reciba llamadas RTC habilitando la cuenta para telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="78afd-138">Optional: Allow this account to make and receive PSTN phone calls by enabling the account for Enterprise Voice.</span></span> <span data-ttu-id="78afd-139">No es necesario para el sistema de sala de Skype de Telefonía IP empresarial, pero si no se habilita para Telefonía IP empresarial, no podrá el cliente del sistema de sala de Skype proporcionar la funcionalidad de marcado PSTN:</span><span class="sxs-lookup"><span data-stu-id="78afd-139">Enterprise Voice is not required for Skype Room System, but if you do not enable it for Enterprise Voice, the Skype Room System client won't be able to provide PSTN dialing functionality:</span></span>
    
   ```
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true

   ```

> [!NOTE]
> <span data-ttu-id="78afd-140">Si habilita la Telefonía IP empresarial para la cuenta de sistema del sitio de Skype conferencias sala, asegúrese de configurar una directiva de voz restringido adecuado para su organización.</span><span class="sxs-lookup"><span data-stu-id="78afd-140">If you enable Enterprise Voice for the Skype Room System conference room account, make sure to configure a restricted Voice Policy suitable for your organization.</span></span> <span data-ttu-id="78afd-141">Si el Skype para salas de reuniones de negocios es un recurso disponible públicamente, cualquier persona podría utilizar para unirse a una reunión, programada o ad hoc.</span><span class="sxs-lookup"><span data-stu-id="78afd-141">If the Skype for Business Meeting Room is a publicly available resource, anyone could use it to join a meeting, either scheduled or ad hoc.</span></span> <span data-ttu-id="78afd-142">Después de unirse a una reunión, la persona podría aceptar la llamada para unirse a una conferencia de cualquier número.</span><span class="sxs-lookup"><span data-stu-id="78afd-142">After joining a meeting, the person could dial out to any number.</span></span> <span data-ttu-id="78afd-143">En Skype para Business Server, el acceso telefónico de salida de la función de conferencias utiliza la voz del usuario, en este caso utiliza la cuenta de sistema del sitio de Skype para unirse a la reunión.</span><span class="sxs-lookup"><span data-stu-id="78afd-143">In Skype for Business Server, the dial-out from conferences feature uses the voice policy of the user, in this case the Skype Room System account used to join the meeting.</span></span> <span data-ttu-id="78afd-144">En versiones anteriores de Lync Server, se usaba la directiva de voz del organizador.</span><span class="sxs-lookup"><span data-stu-id="78afd-144">In earlier versions of Lync Server, the voice policy of the organizer is used.</span></span> <span data-ttu-id="78afd-145">Por lo tanto, si un usuario de una versión anterior de Lync Server programa una sala de reuniones y se invita a la cuenta de sistema del sitio de Skype sala, cualquier persona podría utilizar el Skype para salas de reuniones de negocios para unirse a la reunión y puede marcar cualquier número de teléfono nacionales, regionales o internacional número, siempre que el organizador puede marcar esos números.</span><span class="sxs-lookup"><span data-stu-id="78afd-145">Therefore, if a user of an earlier version of Lync Server schedules a meeting room and invites the Skype Room System room account, anyone could use the Skype for Business Meeting Room to join the meeting and could dial any national/regional or international phone number, as long as the organizer is allowed to dial those numbers.</span></span> 
  

