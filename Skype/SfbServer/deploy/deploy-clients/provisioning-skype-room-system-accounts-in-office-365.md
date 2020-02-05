---
title: Aprovisionamiento de cuentas del Sistema de salas de Skype en Office 365
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
description: Lea este tema para obtener información acerca del aprovisionamiento de cuentas de Sistema de salas de Skype en Office 365.
ms.openlocfilehash: 33c3acf2f0fffc69da55468e8c16902ec7fa4f88
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768753"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a><span data-ttu-id="47980-103">Aprovisionamiento de cuentas del Sistema de salas de Skype en Office 365</span><span class="sxs-lookup"><span data-stu-id="47980-103">Provisioning Skype Room System accounts in Office 365</span></span>
 
<span data-ttu-id="47980-104">Lea este tema para obtener información acerca del aprovisionamiento de cuentas de Sistema de salas de Skype en Office 365.</span><span class="sxs-lookup"><span data-stu-id="47980-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="47980-105">La siguiente sección cubre el aprovisionamiento de la cuenta del sistema de salas de Skype para un inquilino de Office 365.</span><span class="sxs-lookup"><span data-stu-id="47980-105">The following section covers Skype Room System account provisioning for an Office 365 tenant.</span></span>
  
## <a name="office-365-prerequisites"></a><span data-ttu-id="47980-106">Requisitos previos de Office 365</span><span class="sxs-lookup"><span data-stu-id="47980-106">Office 365 prerequisites</span></span>

<span data-ttu-id="47980-107">El inquilino en línea debe cumplir los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="47980-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="47980-108">El plan de Office 365 debe incluir Skype empresarial online plan 2 u Office 365 E1, E3 o E5.</span><span class="sxs-lookup"><span data-stu-id="47980-108">The Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="47980-109">Para obtener más información sobre los planes de Skype empresarial online, consulte la [Descripción del servicio de Skype empresarial online](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="47980-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>
    
- <span data-ttu-id="47980-110">Su inquilino debe tener habilitada la función de conferencia de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="47980-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="47980-111">El inquilino debe tener Exchange Online habilitado.</span><span class="sxs-lookup"><span data-stu-id="47980-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="47980-112">El administrador remoto del inquilino debe tener el siguiente acceso a PowerShell:</span><span class="sxs-lookup"><span data-stu-id="47980-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="47980-113">Acceso remoto a PowerShell de Exchange</span><span class="sxs-lookup"><span data-stu-id="47980-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="47980-114">Acceso remoto a PowerShell de Skype empresarial online</span><span class="sxs-lookup"><span data-stu-id="47980-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="47980-115">Módulo Windows Azure Active Directory para Windows PowerShell para obtener acceso al directorio de Office 365</span><span class="sxs-lookup"><span data-stu-id="47980-115">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="47980-116">Para la cuenta de Salas de Skype, se necesita la siguiente licencia:</span><span class="sxs-lookup"><span data-stu-id="47980-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="47980-117">Para habilitar las reuniones de Skype, es necesario disponer de una licencia de Skype empresarial online plan 2 u Office 365 E1 o E3.</span><span class="sxs-lookup"><span data-stu-id="47980-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="47980-118">Para asignar un número de teléfono a la sala con la funcionalidad de telefonía IP empresarial de modo que se pueda habilitar la sala con un número de teléfono, se requiere un plan 2 de Skype empresarial online con la licencia de sistema telefónico u Office 365 E5 (1).</span><span class="sxs-lookup"><span data-stu-id="47980-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="47980-119">Si necesita capacidades de acceso telefónico desde una reunión, necesitará una licencia de audioconferencia y sistema telefónico.</span><span class="sxs-lookup"><span data-stu-id="47980-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="47980-120">Si necesita poder llamar desde una reunión, necesitará un plan de llamadas nacionales o nacionales e internacionales.</span><span class="sxs-lookup"><span data-stu-id="47980-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="47980-121">No se necesita una licencia de Exchange Online para la cuenta de Salas de Skype porque la cuenta debería configurarse como una cuenta de buzón del recurso.</span><span class="sxs-lookup"><span data-stu-id="47980-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="47980-122">Información general de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="47980-122">Provisioning overview</span></span>

<span data-ttu-id="47980-123">El siguiente diagrama ofrece una descripción general del flujo de aprovisionamiento de cuentas del sistema de salas de Skype en Office 365.</span><span class="sxs-lookup"><span data-stu-id="47980-123">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![Pasos de aprovisionamiento del sistema de salas de Skype para O365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="47980-125">Identificar una nueva sala de conferencias</span><span class="sxs-lookup"><span data-stu-id="47980-125">Identify a new conference room</span></span>

<span data-ttu-id="47980-126">Es posible que ya tenga un buzón de sala de recursos en Exchange que proporcione la característica de programación o que cree un buzón de recursos por primera vez para facilitar la implementación de sistemas de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="47980-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="47980-127">En cualquier caso, debe identificar una cuenta de sala para que la use el inquilino.</span><span class="sxs-lookup"><span data-stu-id="47980-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="47980-128">Las secciones de provisiones de Exchange Online y de Skype empresarial proporcionan orientación para ambos tipos de cuentas.</span><span class="sxs-lookup"><span data-stu-id="47980-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="47980-129">Por ejemplo, supongamos que tiene las dos salas siguientes y le gustaría implementar el sistema de salas de Skype para ambos:</span><span class="sxs-lookup"><span data-stu-id="47980-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="47980-130">Cuenta existente de buzón de recursos: confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="47980-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="47980-131">Cuenta nueva de buzón de recursos: confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="47980-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="47980-132">Aprovisionamiento de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="47980-132">Exchange Online provisioning</span></span>

<span data-ttu-id="47980-133">En primer lugar, conéctese a Exchange Online PowerShell siguiendo las instrucciones de este tema, [Conéctese a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="47980-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="47980-134">Para configurar una cuenta de buzón de sala de recursos existente para el sistema de salas de Skype, ejecute los siguientes comandos en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="47980-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="47980-135">Para crear una cuenta nueva de buzón de recursos de Exchange para el sistema de salas de Skype, ejecute los siguientes comandos en Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="47980-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="47980-136">Los comandos anteriores para configurar o crear una cuenta nueva de buzón de recursos de Exchange para el uso del sistema de salas de Skype habilitando la cuenta.</span><span class="sxs-lookup"><span data-stu-id="47980-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="47980-137">Después de crear el buzón de correo, puede usar el cmdlet Set-CalendarProcessing en Exchange Online PowerShell para configurarlo.</span><span class="sxs-lookup"><span data-stu-id="47980-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="47980-138">Haga referencia a los pasos 3 a 6 en implementaciones locales de bosque único para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="47980-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="47980-139">Asignar una licencia de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="47980-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="47980-140">Ahora puede asignar una licencia de Skype empresarial online (plan 2) o de Skype empresarial online (Plan 3) mediante el portal administrativo de Office 365 según se describe en [asignar o quitar licencias de office 365 para empresas](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) o en [licencias complementarias de Skype empresarial](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span><span class="sxs-lookup"><span data-stu-id="47980-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="47980-141">Después de asignar una licencia para Skype empresarial online, podrá iniciar sesión y validar que la cuenta esté activa con cualquier cliente de Skype empresarial.</span><span class="sxs-lookup"><span data-stu-id="47980-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="47980-142">Aprovisionamiento de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="47980-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="47980-143">Una vez que se ha creado y habilitado una cuenta de buzón de sala de recursos como se ha mostrado anteriormente, y se ha autorizado la cuenta para Skype empresarial online, la cuenta se sincronizará desde el bosque de Exchange Online a un bosque de Skype empresarial online con el Bosque de Windows Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="47980-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="47980-144">Para aprovisionar la cuenta del sistema de salas de Skype en el grupo de Skype empresarial online, debe seguir estos pasos.</span><span class="sxs-lookup"><span data-stu-id="47980-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="47980-145">Estos pasos son los mismos para una cuenta de buzón de recursos existente o una cuenta recién creada (confrm1 o confrm2), porque una vez que se habilitan en Exchange Online, estas dos cuentas se sincronizarán con Skype empresarial online de la misma manera:</span><span class="sxs-lookup"><span data-stu-id="47980-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="47980-146">Cree una sesión remota de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="47980-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="47980-147">Tenga en cuenta que tendrá que descargar el módulo del conector de Skype empresarial online y el ayudante para el inicio de sesión de Microsoft Online Services y asegurarse de que su equipo está configurado.</span><span class="sxs-lookup"><span data-stu-id="47980-147">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="47980-148">Para obtener más información, vea [configurar el equipo para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="47980-148">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="47980-149">Para habilitar una cuenta de sistema de Skype Room para Skype empresarial, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="47980-149">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="47980-150">Puede obtener la dirección de RegistrarPool en la que los usuarios de Skype empresarial estén alojados desde una de sus cuentas existentes con el siguiente comando para que devuelva esta propiedad:</span><span class="sxs-lookup"><span data-stu-id="47980-150">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
><span data-ttu-id="47980-151">La autenticación multifactor (MFA) no es compatible con las cuentas del sistema de salas de Skype.</span><span class="sxs-lookup"><span data-stu-id="47980-151">Multi-Factor Authentication (MFA) isn't supported for Skype Room System accounts.</span></span> 

## <a name="password-expiration"></a><span data-ttu-id="47980-152">Caducidad de la contraseña</span><span class="sxs-lookup"><span data-stu-id="47980-152">Password expiration</span></span>

<span data-ttu-id="47980-153">En Office 365, la directiva de caducidad de la contraseña predeterminada de todas las cuentas de usuario es de 90 días a no ser que configure una directiva de caducidad de la contraseña diferente.</span><span class="sxs-lookup"><span data-stu-id="47980-153">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="47980-154">Para las cuentas del sistema de salas de Skype, puede seleccionar la opción la contraseña nunca vence con los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="47980-154">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="47980-155">Cree una sesión en Windows Azure Active Directory mediante el uso de las credenciales de administrador global de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="47980-155">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="47980-156">Establezca la configuración de la contraseña nunca vence para la cuenta de sala del sistema de salas de Skype creada anteriormente con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="47980-156">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="47980-157">Para obtener más información, vea [configurar el equipo para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="47980-157">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="validate"></a><span data-ttu-id="47980-158">Valide</span><span class="sxs-lookup"><span data-stu-id="47980-158">Validate</span></span>

<span data-ttu-id="47980-159">Para la validación, debe poder usar cualquier cliente de Skype empresarial para iniciar sesión en la cuenta que ha creado.</span><span class="sxs-lookup"><span data-stu-id="47980-159">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

