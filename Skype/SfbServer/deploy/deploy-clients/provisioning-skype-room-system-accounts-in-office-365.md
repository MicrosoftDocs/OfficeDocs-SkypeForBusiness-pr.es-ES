---
title: Aprovisionamiento de cuentas del Sistema de salas de Skype en Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Lea este tema para obtener información acerca del aprovisionamiento de cuentas de Sistema de salas de Skype en Office 365.
ms.openlocfilehash: b248168870366db8f685db48197badb3bacf935f
ms.sourcegitcommit: 4660539cf0a6f7fde5de0a68bc4866089962ce80
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2018
ms.locfileid: "22102056"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a><span data-ttu-id="d7f12-103">Aprovisionamiento de cuentas del Sistema de salas de Skype en Office 365</span><span class="sxs-lookup"><span data-stu-id="d7f12-103">Provisioning Skype Room System accounts in Office 365</span></span>
 
<span data-ttu-id="d7f12-104">Lea este tema para obtener información acerca del aprovisionamiento de cuentas de Sistema de salas de Skype en Office 365.</span><span class="sxs-lookup"><span data-stu-id="d7f12-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="d7f12-105">En la siguiente sección, se explica la cuenta del sistema de salas de Skype aprovisionamiento para un inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="d7f12-105">The following section covers Skype Room System account provisioning for an Office 365 tenant.</span></span>
  
## <a name="office-365-prerequisites"></a><span data-ttu-id="d7f12-106">Requisitos previos de Office 365</span><span class="sxs-lookup"><span data-stu-id="d7f12-106">Office 365 prerequisites</span></span>

<span data-ttu-id="d7f12-107">El inquilino en línea debe cumplir los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="d7f12-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="d7f12-108">El plan de Office 365 debe incluir Skype para Business Online Plan 2, 3 Plan, o Office 365 E1, E3 o E5.</span><span class="sxs-lookup"><span data-stu-id="d7f12-108">The Office 365 plan must include Skype for Business Online Plan 2, Plan 3, or Office 365 E1, E3 or E5.</span></span>
    
- <span data-ttu-id="d7f12-109">El inquilino debe tener la capacidad de conferencia de Skype para la empresa habilitado.</span><span class="sxs-lookup"><span data-stu-id="d7f12-109">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="d7f12-110">El inquilino debe tener Exchange Online habilitado.</span><span class="sxs-lookup"><span data-stu-id="d7f12-110">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="d7f12-111">El administrador remoto del inquilino debe tener el siguiente acceso a PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d7f12-111">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="d7f12-112">Acceso remoto a PowerShell de Exchange</span><span class="sxs-lookup"><span data-stu-id="d7f12-112">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="d7f12-113">Skype para el acceso de PowerShell remoto en línea de negocio</span><span class="sxs-lookup"><span data-stu-id="d7f12-113">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="d7f12-114">Windows Azure Active Directory módulo para Windows PowerShell para acceso al directorio de acceso a Office 365</span><span class="sxs-lookup"><span data-stu-id="d7f12-114">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="d7f12-115">Para la cuenta de Salas de Skype, se necesita la siguiente licencia:</span><span class="sxs-lookup"><span data-stu-id="d7f12-115">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="d7f12-116">Se requiere un Skype para profesionales Online Plan 2 o Office 365 E1 o E3 licencia para habilitar las reuniones de Skype.</span><span class="sxs-lookup"><span data-stu-id="d7f12-116">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="d7f12-117">Para dar derecho a la sala con la capacidad de Enterprise Voice, por lo que se puede habilitar la sala con un número de teléfono, un Skype para profesionales Online Plan 2 con el complemento de PBX de la nube o E5 de Office 365 es necesaria (1).</span><span class="sxs-lookup"><span data-stu-id="d7f12-117">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Cloud PBX Add-on or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="d7f12-118">La disponibilidad de autorización de las conferencias RTC en una reunión concreta se determina mediante la licencia del organizador de la reunión.</span><span class="sxs-lookup"><span data-stu-id="d7f12-118">The availability of PSTN Conferencing entitlement within any given meeting is determined by the license of the meeting organizer.</span></span>
    
- <span data-ttu-id="d7f12-119">No se necesita una licencia de Exchange Online para la cuenta de Salas de Skype porque la cuenta debería configurarse como una cuenta de buzón del recurso.</span><span class="sxs-lookup"><span data-stu-id="d7f12-119">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="d7f12-120">Información general de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="d7f12-120">Provisioning overview</span></span>

<span data-ttu-id="d7f12-121">En el siguiente diagrama proporciona una visión general de la cuenta del sistema de salas de Skype aprovisionamiento flujo en Office 365.</span><span class="sxs-lookup"><span data-stu-id="d7f12-121">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![Pasos de aprovisionamiento del sistema de salas de Skype para O365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="d7f12-123">Identificar una nueva sala de conferencias</span><span class="sxs-lookup"><span data-stu-id="d7f12-123">Identify a new conference room</span></span>

<span data-ttu-id="d7f12-124">Es posible que ya tiene un buzón de sala de recursos de Exchange que proporciona la característica de programación, o puede crear un buzón de recursos por primera vez facilitar la implementación del sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="d7f12-124">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="d7f12-125">En cualquier caso, debe identificar una cuenta de sala para que la use el inquilino.</span><span class="sxs-lookup"><span data-stu-id="d7f12-125">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="d7f12-126">El aprovisionamiento de Exchange Online y Skype para las secciones de aprovisionamiento de negocio proporcionan instrucciones para ambos tipos de cuentas.</span><span class="sxs-lookup"><span data-stu-id="d7f12-126">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="d7f12-127">Por ejemplo, supongamos que tiene los siguientes dos salas y que le gustaría implementar del sistema de sala de Skype para ambos tipos de ellos:</span><span class="sxs-lookup"><span data-stu-id="d7f12-127">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="d7f12-128">Cuenta existente de buzón de recursos: confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="d7f12-128">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="d7f12-129">Cuenta nueva de buzón de recursos: confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="d7f12-129">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="d7f12-130">Aprovisionamiento de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d7f12-130">Exchange Online provisioning</span></span>

<span data-ttu-id="d7f12-131">En primer lugar, se conecte a Exchange Online PowerShell siguiendo las instrucciones que aparecen en el tema, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="d7f12-131">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="d7f12-132">Para establecer una cuenta de buzón de sala de recurso existente de Skype salón de sistema, ejecute los siguientes comandos en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d7f12-132">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="d7f12-133">Para crear una nueva cuenta de buzón de recursos de Exchange para el sistema de sala de Skype, ejecute los siguientes comandos en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d7f12-133">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="d7f12-134">Los comandos anteriores configuración o creación una nueva cuenta de buzón de recursos de Exchange para uso del sistema de salas de Skype mediante la habilitación de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="d7f12-134">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="d7f12-135">Después de crear el buzón de correo, puede usar el cmdlet Set-CalendarProcessing en Exchange Online PowerShell para configurar el buzón de correo.</span><span class="sxs-lookup"><span data-stu-id="d7f12-135">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="d7f12-136">Haga referencia a los pasos 3 a 6 en implementaciones locales de bosque único para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="d7f12-136">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="d7f12-137">Asignar una licencia de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="d7f12-137">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="d7f12-138">Ahora puede asignar un Skype para profesionales Online (Plan 2) o de Skype para licencia empresarial en línea (planeación de 3) mediante el portal administrativo de Office 365, tal como se describe en [asignar o quitar licencias de Office 365 para profesionales](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) o en [Skype para el complemento de Business concesión de licencias](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span><span class="sxs-lookup"><span data-stu-id="d7f12-138">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="d7f12-139">Después de asignar una licencia de Skype para profesionales en línea, podrá iniciar sesión y validar que la cuenta está activa con cualquier Skype para clientes empresariales.</span><span class="sxs-lookup"><span data-stu-id="d7f12-139">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="d7f12-140">Aprovisionamiento de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="d7f12-140">Skype for Business Online provisioning</span></span>

<span data-ttu-id="d7f12-141">Después de una sala de recurso se ha creado y habilitado tal y como se ha mostrado anteriormente cuenta de buzón de correo y la cuenta tiene licencia para Skype para profesionales en línea la cuenta se sincronizarán desde el bosque de Exchange Online a Skype para el bosque en línea de negocio mediante la Bosque de Active Directory de Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="d7f12-141">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="d7f12-142">Los siguientes pasos son necesarios para aprovisionar la cuenta del sistema de salas de Skype en el Skype para un grupo de servidores en línea de negocio.</span><span class="sxs-lookup"><span data-stu-id="d7f12-142">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="d7f12-143">Estos pasos son los mismos para una cuenta de buzón de recursos existente o una cuenta recién creada (confrm1 o confrm2), porque una vez que están habilitados en Exchange Online, ambas cuentas se sincronizarán con Skype para profesionales en línea de la misma manera:</span><span class="sxs-lookup"><span data-stu-id="d7f12-143">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="d7f12-144">Cree una sesión remota de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d7f12-144">Create a Remote PowerShell session.</span></span> <span data-ttu-id="d7f12-145">Tenga en cuenta que necesitará descargar Skype para el módulo del conector de negocio en línea y Microsoft Asistente en línea de servicios de inicio de sesión y asegúrese de que el equipo está configurado.</span><span class="sxs-lookup"><span data-stu-id="d7f12-145">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="d7f12-146">Para obtener más información, vea [Configurar el equipo de Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="d7f12-146">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="d7f12-147">Para habilitar una cuenta de sistema de salas de Skype para Skype para la empresa, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="d7f12-147">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="d7f12-148">Puede obtener el RegistrarPool devuelve la dirección donde están hospedados su Skype para los usuarios empresariales de una de las cuentas existentes mediante el comando siguiente para esta propiedad:</span><span class="sxs-lookup"><span data-stu-id="d7f12-148">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

  
## <a name="password-expiration"></a><span data-ttu-id="d7f12-149">Caducidad de la contraseña</span><span class="sxs-lookup"><span data-stu-id="d7f12-149">Password expiration</span></span>

<span data-ttu-id="d7f12-150">En Office 365, la directiva de caducidad de la contraseña predeterminada de todas las cuentas de usuario es de 90 días a no ser que configure una directiva de caducidad de la contraseña diferente.</span><span class="sxs-lookup"><span data-stu-id="d7f12-150">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="d7f12-151">Para las cuentas del sistema de salas de Skype, puede seleccionar la contraseña nunca caduca configuración con los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="d7f12-151">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="d7f12-152">Cree una sesión en Windows Azure Active Directory mediante el uso de las credenciales de administrador global de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="d7f12-152">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="d7f12-153">Establecer la contraseña nunca caduca la configuración de la cuenta de sala del sistema de salas de Skype creada anteriormente mediante el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="d7f12-153">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="d7f12-154">Para obtener más información, vea [Configurar el equipo de Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="d7f12-154">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  

