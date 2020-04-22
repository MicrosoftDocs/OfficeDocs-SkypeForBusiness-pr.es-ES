---
title: Aprovisionamiento de cuentas del sistema de salas de Skype en Microsoft 365 y Office 365
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Lea este tema para obtener información sobre el aprovisionamiento de cuentas del sistema de salas de Skype en Microsoft 365 u Office 365.
ms.openlocfilehash: e2796d9a81f918c0503382e23aad5ead711240e7
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779716"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a><span data-ttu-id="bfb87-103">Aprovisionamiento de cuentas del sistema de salas de Skype en Microsoft 365 y Office 365</span><span class="sxs-lookup"><span data-stu-id="bfb87-103">Provisioning Skype Room System accounts in Microsoft 365 and Office 365</span></span>
 
<span data-ttu-id="bfb87-104">Lea este tema para obtener información sobre el aprovisionamiento de cuentas del sistema de salas de Skype en Office 365.</span><span class="sxs-lookup"><span data-stu-id="bfb87-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="bfb87-105">En la siguiente sección se describe el aprovisionamiento de cuentas de sistemas de salas de Skype para una organización de Office 365.</span><span class="sxs-lookup"><span data-stu-id="bfb87-105">The following section covers Skype Room System account provisioning for an Office 365 organization.</span></span>
  
## <a name="microsoft-365-and-office-365-prerequisites"></a><span data-ttu-id="bfb87-106">Requisitos previos de Microsoft 365 y Office 365</span><span class="sxs-lookup"><span data-stu-id="bfb87-106">Microsoft 365 and Office 365 prerequisites</span></span>

<span data-ttu-id="bfb87-107">El inquilino en línea debe cumplir los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="bfb87-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="bfb87-108">El plan Microsoft 365 o Office 365 debe incluir Skype empresarial online (plan 2) o Office 365 E1, E3 o E5.</span><span class="sxs-lookup"><span data-stu-id="bfb87-108">The Microsoft 365 or Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="bfb87-109">Para obtener más información sobre los planes de Skype empresarial online, consulte la [Descripción del servicio Skype empresarial online](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="bfb87-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>
    
- <span data-ttu-id="bfb87-110">El inquilino debe tener habilitada la función de conferencias de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="bfb87-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="bfb87-111">El inquilino debe tener Exchange Online habilitado.</span><span class="sxs-lookup"><span data-stu-id="bfb87-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="bfb87-112">El administrador remoto del inquilino debe tener el siguiente acceso de PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bfb87-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="bfb87-113">Acceso remoto a PowerShell de Exchange</span><span class="sxs-lookup"><span data-stu-id="bfb87-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="bfb87-114">Acceso remoto a PowerShell de Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="bfb87-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="bfb87-115">Módulo Windows Azure Active Directory para Windows PowerShell para obtener acceso al directorio de Office 365</span><span class="sxs-lookup"><span data-stu-id="bfb87-115">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="bfb87-116">Para la cuenta de sala de Skype, se necesita la siguiente licencia:</span><span class="sxs-lookup"><span data-stu-id="bfb87-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="bfb87-117">Se necesita una licencia de Skype empresarial online (plan 2) o de Office 365 E1 o E3 para habilitar las reuniones de Skype.</span><span class="sxs-lookup"><span data-stu-id="bfb87-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="bfb87-118">Para cambiar el título de la sala con la funcionalidad de Enterprise Voice de modo que el salón pueda habilitarse con un número de teléfono, se requiere un plan 2 de Skype empresarial online con la licencia de sistema telefónico o Office 365 E5 (1).</span><span class="sxs-lookup"><span data-stu-id="bfb87-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="bfb87-119">Si necesita capacidades de acceso telefónico desde una reunión, necesitará una licencia de sistema telefónico y Conferencia de audio.</span><span class="sxs-lookup"><span data-stu-id="bfb87-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="bfb87-120">Si necesita capacidades de acceso telefónico desde una reunión, necesitará un plan de llamadas nacionales o nacionales e internacionales.</span><span class="sxs-lookup"><span data-stu-id="bfb87-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="bfb87-121">No se necesita una licencia de Exchange Online para la cuenta de sala de Skype, ya que la cuenta debe estar configurada como una cuenta de buzón de recursos.</span><span class="sxs-lookup"><span data-stu-id="bfb87-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="bfb87-122">Información general sobre el aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="bfb87-122">Provisioning overview</span></span>

<span data-ttu-id="bfb87-123">En el siguiente diagrama se proporciona información general sobre el flujo de aprovisionamiento de cuentas del sistema de salas de Skype en Office 365.</span><span class="sxs-lookup"><span data-stu-id="bfb87-123">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![Pasos de aprovisionamiento del sistema de salas de Skype para O365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="bfb87-125">Identificar una nueva sala de conferencias</span><span class="sxs-lookup"><span data-stu-id="bfb87-125">Identify a new conference room</span></span>

<span data-ttu-id="bfb87-126">Es posible que ya tenga un buzón de sala de recursos en Exchange que proporcione la característica de programación o que cree un buzón de recursos por primera vez para facilitar la implementación de sistemas de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="bfb87-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="bfb87-127">En cualquier caso, debe identificar una cuenta de sala que se utilizará en el espacio empresarial.</span><span class="sxs-lookup"><span data-stu-id="bfb87-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="bfb87-128">Las secciones de aprovisionamiento de Exchange Online y de Skype empresarial proporcionan orientación para ambos tipos de cuentas.</span><span class="sxs-lookup"><span data-stu-id="bfb87-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="bfb87-129">Por ejemplo, supongamos que tiene las dos salas siguientes y desea implementar el sistema de salas de Skype para ambas:</span><span class="sxs-lookup"><span data-stu-id="bfb87-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="bfb87-130">Cuenta de buzón de recursos existente: confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="bfb87-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="bfb87-131">Nueva cuenta de buzón de recursos: confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="bfb87-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="bfb87-132">Aprovisionamiento de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="bfb87-132">Exchange Online provisioning</span></span>

<span data-ttu-id="bfb87-133">En primer lugar, conéctese a Exchange Online PowerShell siguiendo las instrucciones que se indican en el tema [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="bfb87-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="bfb87-134">Para establecer una cuenta de buzón de sala de recursos existente para el sistema de salas de Skype, ejecute los siguientes comandos en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bfb87-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="bfb87-135">Para crear una cuenta de buzón de recursos de Exchange nueva para el sistema de salas de Skype, ejecute los siguientes comandos en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="bfb87-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="bfb87-136">Los comandos anteriores configuran o crean una nueva cuenta de buzón de recursos de Exchange para el uso del sistema de salas de Skype mediante la habilitación de la cuenta.</span><span class="sxs-lookup"><span data-stu-id="bfb87-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="bfb87-137">Después de crear el buzón, puede usar el cmdlet Set-CalendarProcessing en Exchange Online PowerShell para configurar el buzón.</span><span class="sxs-lookup"><span data-stu-id="bfb87-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="bfb87-138">Consulte los pasos 3 a 6 en implementaciones locales de bosque único para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="bfb87-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="bfb87-139">Asignar una licencia de Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="bfb87-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="bfb87-140">Ahora puede asignar una licencia de Skype empresarial online (plan 2) o Skype empresarial online (Plan 3) mediante el portal administrativo de Office 365, tal como se describe en [asignar o quitar licencias para office 365 para empresas](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) o en [licencias complementarias de Skype](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)empresarial.</span><span class="sxs-lookup"><span data-stu-id="bfb87-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="bfb87-141">Después de asignar una licencia para Skype empresarial online, podrá iniciar sesión y validar que la cuenta está activa mediante cualquier cliente de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="bfb87-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="bfb87-142">Aprovisionamiento de Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="bfb87-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="bfb87-143">Una vez que se haya creado y habilitado una cuenta de buzón de sala de recursos, tal y como se mostró anteriormente, y haya configurado la cuenta de Skype empresarial online, la cuenta se sincronizará desde el bosque de Exchange Online al bosque de Skype empresarial online mediante el bosque de Windows Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bfb87-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="bfb87-144">Los siguientes pasos son necesarios para aprovisionar la cuenta del sistema de salas de Skype en el grupo de Skype empresarial online.</span><span class="sxs-lookup"><span data-stu-id="bfb87-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="bfb87-145">Estos pasos son los mismos para una cuenta de buzón de recursos existente o para una cuenta recién creada (confrm1 o confrm2), ya que una vez que están habilitados en Exchange Online, ambas cuentas se sincronizarán con Skype empresarial online de la misma manera:</span><span class="sxs-lookup"><span data-stu-id="bfb87-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="bfb87-146">Cree una sesión remota de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bfb87-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="bfb87-147">Tenga en cuenta que tendrá que descargar el módulo del conector de Skype empresarial online y el Asistente para el inicio de sesión de Microsoft Online Services y asegurarse de que el equipo está configurado.</span><span class="sxs-lookup"><span data-stu-id="bfb87-147">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="bfb87-148">Para obtener más información, consulte [configurar el equipo para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="bfb87-148">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="bfb87-149">Para habilitar una cuenta de sistema de salas de Skype para Skype empresarial, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="bfb87-149">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="bfb87-150">Puede obtener la dirección RegistrarPool donde sus usuarios de Skype empresarial están hospedados de una de sus cuentas existentes mediante el siguiente comando para devolver esta propiedad:</span><span class="sxs-lookup"><span data-stu-id="bfb87-150">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
><span data-ttu-id="bfb87-151">La autenticación multifactor (MFA) no es compatible con las cuentas del sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="bfb87-151">Multi-Factor Authentication (MFA) isn't supported for Skype Room System accounts.</span></span> 

## <a name="password-expiration"></a><span data-ttu-id="bfb87-152">Expiración de contraseña</span><span class="sxs-lookup"><span data-stu-id="bfb87-152">Password expiration</span></span>

<span data-ttu-id="bfb87-153">En Office 365, la Directiva de expiración de contraseña predeterminada para todas las cuentas de usuario es de 90 días a menos que configure una directiva de expiración de contraseña diferente.</span><span class="sxs-lookup"><span data-stu-id="bfb87-153">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="bfb87-154">Para las cuentas del sistema de salas de Skype, puede seleccionar la opción la contraseña nunca expira con los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="bfb87-154">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="bfb87-155">Cree una sesión de Windows Azure Active Directory con sus credenciales de administrador global de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="bfb87-155">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="bfb87-156">Establezca la configuración de la contraseña nunca expira para la cuenta de sala del sistema de salas de Skype creada anteriormente mediante el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="bfb87-156">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="bfb87-157">Para obtener más información, consulte [configurar el equipo para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="bfb87-157">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="validate"></a><span data-ttu-id="bfb87-158">Validar</span><span class="sxs-lookup"><span data-stu-id="bfb87-158">Validate</span></span>

<span data-ttu-id="bfb87-159">Para la validación, debe poder usar cualquier cliente de Skype empresarial para iniciar sesión en la cuenta que ha creado.</span><span class="sxs-lookup"><span data-stu-id="bfb87-159">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

