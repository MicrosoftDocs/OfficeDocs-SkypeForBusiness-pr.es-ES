---
title: Aprovisionamiento de cuentas del Sistema de sala de Skype en Microsoft 365 y Office 365
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
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Lea este tema para obtener información sobre el aprovisionamiento de cuentas del Sistema de sala de Skype en Microsoft 365 u Office 365.
ms.openlocfilehash: 115dd83751e0da837d9d88351d57a769b7e313da
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820850"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a><span data-ttu-id="5d77a-103">Aprovisionamiento de cuentas del Sistema de sala de Skype en Microsoft 365 y Office 365</span><span class="sxs-lookup"><span data-stu-id="5d77a-103">Provisioning Skype Room System accounts in Microsoft 365 and Office 365</span></span>
 
<span data-ttu-id="5d77a-104">Lea este tema para obtener información sobre el aprovisionamiento de cuentas del Sistema de sala de Skype en Microsoft 365 u Office 365.</span><span class="sxs-lookup"><span data-stu-id="5d77a-104">Read this topic to learn about provisioning Skype Room System accounts in Microsoft 365 or Office 365.</span></span>
  
<span data-ttu-id="5d77a-105">En la siguiente sección se describe el aprovisionamiento de cuentas del Sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="5d77a-105">The following section covers Skype Room System account provisioning.</span></span>
  
## <a name="microsoft-365-and-office-365-prerequisites"></a><span data-ttu-id="5d77a-106">Requisitos previos de Microsoft 365 y Office 365</span><span class="sxs-lookup"><span data-stu-id="5d77a-106">Microsoft 365 and Office 365 prerequisites</span></span>

<span data-ttu-id="5d77a-107">El inquilino en línea debe cumplir los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="5d77a-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="5d77a-108">El plan de Microsoft 365 u Office 365 debe incluir Skype Empresarial Online Plan 2 u Office 365 E1, E3 o E5.</span><span class="sxs-lookup"><span data-stu-id="5d77a-108">The Microsoft 365 or Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="5d77a-109">Para obtener más información sobre los planes de Skype Empresarial Online, consulte la descripción del servicio [skype empresarial online.](https://technet.microsoft.com/library/jj822172.aspx)</span><span class="sxs-lookup"><span data-stu-id="5d77a-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>
    
- <span data-ttu-id="5d77a-110">Su espacio empresarial debe tener habilitada la funcionalidad de conferencia de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="5d77a-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="5d77a-111">Su espacio empresarial debe tener Exchange Online habilitado.</span><span class="sxs-lookup"><span data-stu-id="5d77a-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="5d77a-112">El administrador remoto del espacio empresarial debe tener el siguiente acceso a PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5d77a-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="5d77a-113">Acceso remoto de PowerShell de Exchange</span><span class="sxs-lookup"><span data-stu-id="5d77a-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="5d77a-114">Acceso remoto de PowerShell de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="5d77a-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="5d77a-115">Windows Azure módulo de Active Directory para Windows PowerShell acceso al directorio de Microsoft 365 u Office 365</span><span class="sxs-lookup"><span data-stu-id="5d77a-115">Windows Azure Active Directory Module for Windows PowerShell to access Microsoft 365 or Office 365 directory access</span></span>
    
<span data-ttu-id="5d77a-116">Para la cuenta de la sala de Skype, se requiere la siguiente licencia:</span><span class="sxs-lookup"><span data-stu-id="5d77a-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="5d77a-117">Se necesita una licencia de Skype Empresarial Online plan 2 u Office 365 E1 o E3 para habilitar reuniones de Skype.</span><span class="sxs-lookup"><span data-stu-id="5d77a-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="5d77a-118">Para habilitar la sala con la funcionalidad Telefonía IP empresarial para que la sala pueda habilitarse con un número de teléfono, se requiere un plan 2 de Skype Empresarial Online con la licencia del sistema telefónico u Office 365 E5 (1).</span><span class="sxs-lookup"><span data-stu-id="5d77a-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="5d77a-119">Si necesita funcionalidades de acceso telefónico local de una reunión, necesitará una licencia de audioconferencia y sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="5d77a-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="5d77a-120">Si necesita funcionalidades de acceso telefónico de una reunión, necesitará un plan de llamadas nacionales, nacionales e internacionales.</span><span class="sxs-lookup"><span data-stu-id="5d77a-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="5d77a-121">No se necesita una licencia de Exchange Online para la cuenta de sala de Skype porque la cuenta debe configurarse como una cuenta de buzón de recursos.</span><span class="sxs-lookup"><span data-stu-id="5d77a-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="5d77a-122">Información general sobre el aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="5d77a-122">Provisioning overview</span></span>

<span data-ttu-id="5d77a-123">En el siguiente diagrama se proporciona información general sobre el flujo de aprovisionamiento de cuentas del Sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="5d77a-123">The following diagram provides an overview of the Skype Room System account provisioning flow.</span></span>
  
![Pasos de aprovisionamiento del sistema de sala de Skype](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="5d77a-125">Identificar una nueva sala de conferencias</span><span class="sxs-lookup"><span data-stu-id="5d77a-125">Identify a new conference room</span></span>

<span data-ttu-id="5d77a-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span><span class="sxs-lookup"><span data-stu-id="5d77a-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="5d77a-127">En cualquier caso, debe identificar una cuenta de sala que se usará en su espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="5d77a-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="5d77a-128">Las secciones Aprovisionamiento de Exchange Online y Aprovisionamiento de Skype Empresarial proporcionan instrucciones para ambos tipos de cuentas.</span><span class="sxs-lookup"><span data-stu-id="5d77a-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="5d77a-129">Por ejemplo, supongamos que tiene las dos salas siguientes y que le gustaría implementar el Sistema de salas de Skype para ambas:</span><span class="sxs-lookup"><span data-stu-id="5d77a-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="5d77a-130">Cuenta de buzón de recursos existente: confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="5d77a-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="5d77a-131">Nueva cuenta de buzón de recursos: confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="5d77a-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="5d77a-132">Aprovisionamiento de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="5d77a-132">Exchange Online provisioning</span></span>

<span data-ttu-id="5d77a-133">En primer lugar, conéctese a Exchange Online PowerShell siguiendo las instrucciones del tema [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="5d77a-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="5d77a-134">Para establecer una cuenta de buzón de sala de recursos existente para el Sistema de sala de Skype, ejecute los siguientes comandos en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5d77a-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="5d77a-135">Para crear una nueva cuenta de buzón de recursos de Exchange para el Sistema de sala de Skype, ejecute los siguientes comandos en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="5d77a-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="5d77a-136">Los comandos anteriores configuraron o crearon una nueva cuenta de buzón de recursos de Exchange para el uso del Sistema de sala de Skype habilitando la cuenta.</span><span class="sxs-lookup"><span data-stu-id="5d77a-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="5d77a-137">Después de crear el buzón, puede usar el cmdlet Set-CalendarProcessing en Exchange Online PowerShell para configurar el buzón.</span><span class="sxs-lookup"><span data-stu-id="5d77a-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="5d77a-138">Consulte los pasos del 3 al 6 en Implementaciones locales de bosque único para obtener más información</span><span class="sxs-lookup"><span data-stu-id="5d77a-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="5d77a-139">Asignar una licencia de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="5d77a-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="5d77a-140">Ahora puede asignar una licencia de Skype Empresarial Online (Plan 2) o Skype Empresarial Online (Plan 3) mediante el portal administrativo de Microsoft 365, como se describe en Asignar o quitar licencias de [Microsoft 365](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) para empresas o en licencias de complementos de [Skype](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)Empresarial.</span><span class="sxs-lookup"><span data-stu-id="5d77a-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Microsoft 365 administrative portal as described in [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="5d77a-141">Después de asignar una licencia para Skype Empresarial Online, podrá iniciar sesión y validar que la cuenta está activa con cualquier cliente de Skype Empresarial.</span><span class="sxs-lookup"><span data-stu-id="5d77a-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="5d77a-142">Aprovisionamiento de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="5d77a-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="5d77a-143">Una vez que se haya creado y habilitado una cuenta de buzón de sala de recursos como se ha mostrado anteriormente, y haya concedido una licencia a la cuenta para Skype Empresarial Online, la cuenta se sincronizará desde el bosque de Exchange Online con el bosque de Skype Empresarial Online mediante el bosque de Active Directory de Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="5d77a-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="5d77a-144">Los siguientes pasos son necesarios para aprovisionar la cuenta del Sistema de sala de Skype en el grupo de Skype Empresarial Online.</span><span class="sxs-lookup"><span data-stu-id="5d77a-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="5d77a-145">Estos pasos son los mismos para una cuenta de buzón de recursos existente o una cuenta recién creada (confrm1 o confrm2), ya que una vez habilitadas en Exchange Online, ambas cuentas se sincronizarán con Skype Empresarial Online de la misma manera:</span><span class="sxs-lookup"><span data-stu-id="5d77a-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="5d77a-146">Crear una sesión de PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="5d77a-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="5d77a-147">Tenga en cuenta que tendrá que descargar el Módulo de conector de Skype Empresarial Online y el Asistente para Microsoft Online Services Sign-In y asegurarse de que el equipo está configurado.</span><span class="sxs-lookup"><span data-stu-id="5d77a-147">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="5d77a-148">Para obtener más información, [vea Configurar el equipo para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="5d77a-148">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="5d77a-149">Para habilitar una cuenta del Sistema de sala de Skype para Skype Empresarial, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="5d77a-149">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="5d77a-150">Puede obtener la dirección RegistrarPool en la que los usuarios de Skype Empresarial se encuentran en una de sus cuentas existentes mediante el siguiente comando para devolver esta propiedad:</span><span class="sxs-lookup"><span data-stu-id="5d77a-150">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
><span data-ttu-id="5d77a-151">La autenticación multifactor (MFA) no es compatible con las cuentas del sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="5d77a-151">Multi-Factor Authentication (MFA) isn't supported for Skype Room System accounts.</span></span> 

## <a name="password-expiration"></a><span data-ttu-id="5d77a-152">Expiración de contraseña</span><span class="sxs-lookup"><span data-stu-id="5d77a-152">Password expiration</span></span>

<span data-ttu-id="5d77a-153">En Microsoft 365 u Office 365, la directiva de expiración de contraseña predeterminada para todas las cuentas de usuario es de 90 días, a menos que configure una directiva de expiración de contraseña diferente.</span><span class="sxs-lookup"><span data-stu-id="5d77a-153">In Microsoft 365 or Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="5d77a-154">Para las cuentas del sistema de sala de Skype, puede seleccionar la configuración contraseña nunca expira con los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="5d77a-154">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="5d77a-155">Cree una sesión Windows Azure Active Directory con sus credenciales de administrador global de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="5d77a-155">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="5d77a-156">Establecer la configuración De contraseña nunca expira para la cuenta de sala del Sistema de sala de Skype creada anteriormente mediante el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="5d77a-156">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="5d77a-157">Para obtener más información, [vea Configurar el equipo para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="5d77a-157">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="validate"></a><span data-ttu-id="5d77a-158">Validar</span><span class="sxs-lookup"><span data-stu-id="5d77a-158">Validate</span></span>

<span data-ttu-id="5d77a-159">Para la validación, debería poder usar cualquier cliente de Skype Empresarial para iniciar sesión en la cuenta que creó.</span><span class="sxs-lookup"><span data-stu-id="5d77a-159">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

