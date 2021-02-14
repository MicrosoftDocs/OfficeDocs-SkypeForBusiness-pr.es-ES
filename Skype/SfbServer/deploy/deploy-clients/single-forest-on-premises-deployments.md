---
title: Implementaciones locales de bosque único del Sistema de sala de Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: Lea este tema para obtener información sobre cómo implementar el Sistema de sala de Skype en un entorno local de un solo bosque.
ms.openlocfilehash: 0449a5e909fa044df12766aec0a036bf97315386
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820760"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a><span data-ttu-id="80745-103">Implementaciones locales de bosque único del Sistema de sala de Skype</span><span class="sxs-lookup"><span data-stu-id="80745-103">Skype Room System single forest on-premises deployments</span></span>
 
<span data-ttu-id="80745-104">Lea este tema para obtener información sobre cómo implementar el Sistema de sala de Skype en un entorno local de un solo bosque.</span><span class="sxs-lookup"><span data-stu-id="80745-104">Read this topic to learn how to deploy Skype Room System in a single forest on-premises environment.</span></span>
  
<span data-ttu-id="80745-105">En esta sección se proporciona información general sobre los pasos para aprovisionar la cuenta del Sistema de sala de Skype en Exchange Server y Skype Empresarial Server hospedados en una implementación local de un solo bosque.</span><span class="sxs-lookup"><span data-stu-id="80745-105">This section provides an overview of the steps for provisioning the Skype Room System account on Exchange Server and Skype for Business Server hosted in a single forest on-premises deployment.</span></span>
  
## <a name="single-forest-on-premises-deployments"></a><span data-ttu-id="80745-106">Implementaciones locales de un solo bosque</span><span class="sxs-lookup"><span data-stu-id="80745-106">Single forest on-premises deployments</span></span>

<span data-ttu-id="80745-107">Si ya tiene una cuenta de buzón de recursos para la sala de conferencias, puede usarla.</span><span class="sxs-lookup"><span data-stu-id="80745-107">If you already have a resource mailbox account for the conferencing room, you can use it.</span></span> <span data-ttu-id="80745-108">De lo contrario, tendrá que crear uno nuevo.</span><span class="sxs-lookup"><span data-stu-id="80745-108">Otherwise, you will need to create a new one.</span></span> <span data-ttu-id="80745-109">Puede usar shell de administración de Exchange (PowerShell) o Consola de administración de Exchange para crear una nueva cuenta de buzón de recursos.</span><span class="sxs-lookup"><span data-stu-id="80745-109">You can use either Exchange Management Shell (PowerShell) or Exchange Management Console to create a new resource mailbox account.</span></span> <span data-ttu-id="80745-110">Se recomienda usar un nuevo buzón de recursos (eliminar el buzón antiguo y volver a crear) para el Sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="80745-110">We recommend using a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="80745-111">Asegúrese de hacer una copia de seguridad de los datos del buzón antes de eliminarlos y, a continuación, exportarlos de nuevo al buzón de correo creado de nuevo mediante el cliente de Outlook (vea Exportar o hacer una copia de seguridad de los mensajes, el calendario, las tareas y los contactos para obtener más información).</span><span class="sxs-lookup"><span data-stu-id="80745-111">Make sure to back up mailbox data before deleting and then export it back to the re-created mailbox using the Outlook client (see Export or back up messages, calendar, tasks, and contacts for more information).</span></span> <span data-ttu-id="80745-112">Para restaurar las reuniones perdidas eliminando el buzón, consulte [Conectar o restaurar un buzón eliminado.](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="80745-112">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="80745-113">Para usar una cuenta de buzón de recursos existente (por ejemplo, LRS-01), siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="80745-113">To use an existing resource mailbox account (for example, LRS-01) follow the steps below:</span></span>
  
1. <span data-ttu-id="80745-114">Ejecute el siguiente comando de PowerShell de administración de Exchange:</span><span class="sxs-lookup"><span data-stu-id="80745-114">Run the following Exchange Management PowerShell command:</span></span>
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. <span data-ttu-id="80745-115">Si planea crear un nuevo buzón, ejecute el siguiente comando para una organización de Exchange local de un solo bosque:</span><span class="sxs-lookup"><span data-stu-id="80745-115">If you plan to create a new mailbox, then, for a single forest on-premises Exchange organization, run the following command:</span></span>
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="80745-116">En el ejemplo anterior se crea una cuenta de usuario habilitada en Active Directory y un buzón de sala para una sala de conferencias en una organización de Exchange local.</span><span class="sxs-lookup"><span data-stu-id="80745-116">The above example creates an enabled user account in Active Directory and a room mailbox for a conference room in an on-premises Exchange organization.</span></span> <span data-ttu-id="80745-117">El parámetro RoomMailboxPassword especifica la contraseña de la cuenta de usuario.</span><span class="sxs-lookup"><span data-stu-id="80745-117">The RoomMailboxPassword parameter specifies the password for the user account.</span></span>
    
3. <span data-ttu-id="80745-118">Configure la cuenta para que resuelva automáticamente los conflictos aceptando o rechazando reuniones.</span><span class="sxs-lookup"><span data-stu-id="80745-118">Configure the account to automatically resolve conflicts by accepting/rejecting meetings.</span></span> <span data-ttu-id="80745-119">Las cuentas de salas de conferencias de Exchange que están equipados con el Sistema de salas de Skype pueden ser administradas por usuarios individuales, pero tenga en cuenta que hasta que la persona acepte una reunión, no aparecerá en el calendario de la pantalla principal del Sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="80745-119">Skype Room System-equipped conference room accounts in Exchange can be managed by individuals, but note that until the individual accepts a meeting it will not appear on the Skype Room System home screen calendar.</span></span>
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   <span data-ttu-id="80745-120">Para obtener un conjunto completo de comandos disponibles, vea Set-CalendarProcessing.</span><span class="sxs-lookup"><span data-stu-id="80745-120">For a complete set of commands available, see Set-CalendarProcessing.</span></span>
    
   <span data-ttu-id="80745-121">Para recordar a los organizadores de la reunión que hagan de la reunión una reunión en línea de Skype Empresarial en Outlook, ejecute el siguiente comando para configurar una sugerencia de correo electrónico para la nueva cuenta:</span><span class="sxs-lookup"><span data-stu-id="80745-121">To remind meeting organizers to make the meeting an online Skype for Business meeting in Outlook, run the following command to set up a MailTip for the new account:</span></span> 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. <span data-ttu-id="80745-122">Use los siguientes comandos para configurar cadenas localizadas.</span><span class="sxs-lookup"><span data-stu-id="80745-122">Use the following commands to configure localized strings.</span></span> <span data-ttu-id="80745-123">Si la organización lo requiere, también puede agregar traducciones personalizadas:</span><span class="sxs-lookup"><span data-stu-id="80745-123">If required by your organization, you can also add custom translations:</span></span> 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. <span data-ttu-id="80745-124">Opcional: configure el texto de aceptación de la reunión que proporciona a los usuarios información sobre la sala de reuniones de Skype Empresarial y qué esperar cuando programen y se unan a las reuniones.</span><span class="sxs-lookup"><span data-stu-id="80745-124">Optional: Configure meeting acceptance text that provides users with information about Skype for Business Meeting Room, and what to expect when they schedule and join meetings.</span></span> 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a><span data-ttu-id="80745-125">Comprobar la cuenta de buzón de recursos en Active Directory</span><span class="sxs-lookup"><span data-stu-id="80745-125">Check Resource Mailbox Account in Active Directory</span></span>

<span data-ttu-id="80745-126">La cuenta de buzón de sala de conferencias creada por Exchange en el paso 1 anterior podría ser un objeto de usuario deshabilitado en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="80745-126">The conference room mailbox account created by Exchange in step 1 above might be a disabled user object in Active Directory.</span></span> <span data-ttu-id="80745-127">El Sistema de sala de Skype no puede iniciar sesión ni autenticarse mediante la autenticación Kerberos/NTLM si la cuenta está deshabilitada en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="80745-127">Skype Room System cannot sign in or authenticate by using Kerberos/NTLM authentication if the account is disabled in Active Directory.</span></span> <span data-ttu-id="80745-128">El cliente del Sistema de sala de Skype debe ser capaz de autenticarse en los servicios Web Exchange para recuperar la configuración del calendario y también debe poder enviar correo electrónico con contenido de la pizarra.</span><span class="sxs-lookup"><span data-stu-id="80745-128">The Skype Room System client must be able to authenticate against Exchange Web Services to retrieve calendar settings, and must also be able to send email with whiteboard contents.</span></span> 
  
<span data-ttu-id="80745-129">Por lo tanto, si la cuenta está deshabilitada, debe habilitar esta cuenta en Active Directory haciendo lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="80745-129">Therefore, if the account is disabled, you must enable this account in Active Directory by doing the following:</span></span> 
  
1. <span data-ttu-id="80745-130">En Active Directory, ejecute el siguiente comando para habilitar el inicio de sesión de la cuenta:</span><span class="sxs-lookup"><span data-stu-id="80745-130">In Active Directory, run the following command to enable account log on:</span></span> 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   <span data-ttu-id="80745-131">Al ejecutar este comando se le pedirá que escriba la contraseña actual y, a continuación, vuelva a escribir la contraseña dos veces para confirmarla.</span><span class="sxs-lookup"><span data-stu-id="80745-131">Running this command will prompt you to enter the current password, and then to re-enter the password twice for confirmation.</span></span>
    
2. <span data-ttu-id="80745-132">Una vez establecida la contraseña, ejecute el siguiente comando para habilitar la cuenta:</span><span class="sxs-lookup"><span data-stu-id="80745-132">Once the password is set, run the following command to enable the account:</span></span> 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a><span data-ttu-id="80745-133">Habilitar cuentas del sistema de sala de Skype para Skype Empresarial</span><span class="sxs-lookup"><span data-stu-id="80745-133">Enabling Skype Room System Accounts for Skype for Business</span></span>

<span data-ttu-id="80745-134">En esta sección se proporciona información general sobre los pasos necesarios para habilitar Skype Empresarial para su cuenta de sala de conferencias, que se configurará en el Sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="80745-134">This section provides an overview of the steps required to enable Skype for Business for your conference room account, which will be configured on Skype Room System.</span></span> 
  
<span data-ttu-id="80745-135">Después de crear una cuenta de buzón de recursos para las salas de conferencias, use el Shell de administración de Skype Empresarial Server para habilitar las cuentas del Sistema de salas de Skype para los servicios de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="80745-135">After you create a resource mailbox account for the conferencing rooms, use Skype for Business Server Management Shell to enable Skype Room System accounts for Skype for Business services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="80745-136">En el siguiente procedimiento se supone que ha habilitado la cuenta sistema de sala de Skype en Active Directory.</span><span class="sxs-lookup"><span data-stu-id="80745-136">The following procedure assumes that you have enabled the Skype Room System account in Active Directory.</span></span> 
  
1. <span data-ttu-id="80745-137">Ejecute el siguiente comando para habilitar la cuenta del Sistema de sala de Skype en un grupo de servidores de Skype Empresarial Server:</span><span class="sxs-lookup"><span data-stu-id="80745-137">Run the following command to enable the Skype Room System account on a Skype for Business Server pool:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. <span data-ttu-id="80745-138">Opcional: permitir que esta cuenta realice y reciba llamadas telefónicas RTC habilitando la cuenta para Telefonía IP empresarial.</span><span class="sxs-lookup"><span data-stu-id="80745-138">Optional: Allow this account to make and receive PSTN phone calls by enabling the account for Enterprise Voice.</span></span> <span data-ttu-id="80745-139">Telefonía IP empresarial no es necesario para el Sistema de sala de Skype, pero si no lo habilita para Telefonía IP empresarial, el cliente del Sistema de sala de Skype no podrá proporcionar la funcionalidad de marcado RTC:</span><span class="sxs-lookup"><span data-stu-id="80745-139">Enterprise Voice is not required for Skype Room System, but if you do not enable it for Enterprise Voice, the Skype Room System client won't be able to provide PSTN dialing functionality:</span></span>
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="80745-140">Si habilita la Telefonía IP empresarial cuenta de la sala de conferencias del Sistema de salas de Skype, asegúrese de configurar una directiva de voz restringida adecuada para su organización.</span><span class="sxs-lookup"><span data-stu-id="80745-140">If you enable Enterprise Voice for the Skype Room System conference room account, make sure to configure a restricted Voice Policy suitable for your organization.</span></span> <span data-ttu-id="80745-141">Si la sala de reuniones de Skype Empresarial es un recurso disponible públicamente, cualquiera podría usarlo para unirse a una reunión, ya sea programada o ad hoc.</span><span class="sxs-lookup"><span data-stu-id="80745-141">If the Skype for Business Meeting Room is a publicly available resource, anyone could use it to join a meeting, either scheduled or ad hoc.</span></span> <span data-ttu-id="80745-142">Después de unirse a una reunión, la persona podría llamar a cualquier número.</span><span class="sxs-lookup"><span data-stu-id="80745-142">After joining a meeting, the person could dial out to any number.</span></span> <span data-ttu-id="80745-143">En Skype Empresarial Server, la característica de acceso telefónico desde conferencias usa la directiva de voz del usuario, en este caso la cuenta del Sistema de salas de Skype usada para unirse a la reunión.</span><span class="sxs-lookup"><span data-stu-id="80745-143">In Skype for Business Server, the dial-out from conferences feature uses the voice policy of the user, in this case the Skype Room System account used to join the meeting.</span></span> <span data-ttu-id="80745-144">En versiones anteriores de Lync Server, se usa la directiva de voz del organizador.</span><span class="sxs-lookup"><span data-stu-id="80745-144">In earlier versions of Lync Server, the voice policy of the organizer is used.</span></span> <span data-ttu-id="80745-145">Por lo tanto, si un usuario de una versión anterior de Lync Server programa una sala de reuniones e invita a la cuenta de sala del Sistema de salas de Skype, cualquiera podría usar la sala de reuniones de Skype Empresarial para unirse a la reunión y podría marcar cualquier número de teléfono nacional, regional o internacional, siempre y cuando el organizador pueda marcar esos números.</span><span class="sxs-lookup"><span data-stu-id="80745-145">Therefore, if a user of an earlier version of Lync Server schedules a meeting room and invites the Skype Room System room account, anyone could use the Skype for Business Meeting Room to join the meeting and could dial any national/regional or international phone number, as long as the organizer is allowed to dial those numbers.</span></span> 
  

