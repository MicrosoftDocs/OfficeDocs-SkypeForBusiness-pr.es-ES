---
title: Aprovisionamiento de cuentas del Sistema de salas de Skype en Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Lea este tema para obtener información acerca del aprovisionamiento de cuentas de Sistema de salas de Skype en Office 365.
ms.openlocfilehash: be90831eba5f16f5a3b41f4c74c26333bf728926
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a><span data-ttu-id="61574-103">Aprovisionamiento de cuentas del Sistema de salas de Skype en Office 365</span><span class="sxs-lookup"><span data-stu-id="61574-103">Provisioning Skype Room System accounts in Office 365</span></span>
 
<span data-ttu-id="61574-104">Lea este tema para obtener información acerca del aprovisionamiento de cuentas de Sistema de salas de Skype en Office 365.</span><span class="sxs-lookup"><span data-stu-id="61574-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="61574-105">La sección siguiente trata la cuenta de sistema del sitio de Skype provisioning para un arrendatario de Office 365.</span><span class="sxs-lookup"><span data-stu-id="61574-105">The following section covers Skype Room System account provisioning for an Office 365 tenant.</span></span>
  
## <a name="office-365-prerequisites"></a><span data-ttu-id="61574-106">Requisitos previos de Office 365</span><span class="sxs-lookup"><span data-stu-id="61574-106">Office 365 prerequisites</span></span>

<span data-ttu-id="61574-107">El inquilino en línea debe cumplir los siguientes requisitos:</span><span class="sxs-lookup"><span data-stu-id="61574-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="61574-108">El plan de Office 365 debe incluir Skype negocio Online Plan 2, Plan 3, Office 365 E1, E3 o E5.</span><span class="sxs-lookup"><span data-stu-id="61574-108">The Office 365 plan must include Skype for Business Online Plan 2, Plan 3, or Office 365 E1, E3 or E5.</span></span>
    
- <span data-ttu-id="61574-109">El arrendatario debe tener la capacidad de conferencia de Skype para empresas habilitadas.</span><span class="sxs-lookup"><span data-stu-id="61574-109">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="61574-110">El inquilino debe tener Exchange Online habilitado.</span><span class="sxs-lookup"><span data-stu-id="61574-110">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="61574-111">El administrador remoto del inquilino debe tener el siguiente acceso a PowerShell:</span><span class="sxs-lookup"><span data-stu-id="61574-111">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="61574-112">Acceso remoto a PowerShell de Exchange</span><span class="sxs-lookup"><span data-stu-id="61574-112">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="61574-113">Skype para acceso de PowerShell remoto de negocios en línea</span><span class="sxs-lookup"><span data-stu-id="61574-113">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="61574-114">Windows Azure Active Directory módulo para Windows PowerShell para acceso al directorio de acceso a Office 365</span><span class="sxs-lookup"><span data-stu-id="61574-114">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="61574-115">Para la cuenta de Salas de Skype, se necesita la siguiente licencia:</span><span class="sxs-lookup"><span data-stu-id="61574-115">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="61574-116">Un Skype para negocios Online Plan 2 o Office 365 E1 o E3 licencia es necesaria para habilitar reuniones de Skype.</span><span class="sxs-lookup"><span data-stu-id="61574-116">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="61574-117">Para dar derecho a la sala, con la capacidad de Telefonía IP empresarial para que la sala se puede habilitar con un número de teléfono, un Skype para negocios Online Plan 2 con el complemento de PBX de nube o Office 365 E5 es necesaria (1).</span><span class="sxs-lookup"><span data-stu-id="61574-117">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Cloud PBX Add-on or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="61574-118">La disponibilidad de autorización de las conferencias RTC en una reunión concreta se determina mediante la licencia del organizador de la reunión.</span><span class="sxs-lookup"><span data-stu-id="61574-118">The availability of PSTN Conferencing entitlement within any given meeting is determined by the license of the meeting organizer.</span></span>
    
- <span data-ttu-id="61574-119">No se necesita una licencia de Exchange Online para la cuenta de Salas de Skype porque la cuenta debería configurarse como una cuenta de buzón del recurso.</span><span class="sxs-lookup"><span data-stu-id="61574-119">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="61574-120">Información general de aprovisionamiento</span><span class="sxs-lookup"><span data-stu-id="61574-120">Provisioning overview</span></span>

<span data-ttu-id="61574-121">El siguiente diagrama proporciona una visión general de la cuenta de sistema del sitio de Skype aprovisionamiento flujo en Office 365.</span><span class="sxs-lookup"><span data-stu-id="61574-121">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![Pasos de aprovisionamiento del sistema de salas de Skype para O365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="61574-123">Identificar una nueva sala de conferencias</span><span class="sxs-lookup"><span data-stu-id="61574-123">Identify a new conference room</span></span>

<span data-ttu-id="61574-124">Es posible que tenga un buzón de sala de recursos de Exchange que proporciona la función de programación, o que desee crear un buzón de recursos por primera vez facilitar la implementación de sistema de sala de Skype.</span><span class="sxs-lookup"><span data-stu-id="61574-124">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="61574-125">En cualquier caso, debe identificar una cuenta de sala para que la use el inquilino.</span><span class="sxs-lookup"><span data-stu-id="61574-125">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="61574-126">La provisión en línea de Exchange y Skype para secciones de provisión de negocios proporcionan orientación para ambos tipos de cuentas.</span><span class="sxs-lookup"><span data-stu-id="61574-126">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="61574-127">Por ejemplo, supongamos que tiene las siguientes dos salas, y que le gustaría implementar sistema de sala de Skype para ambos:</span><span class="sxs-lookup"><span data-stu-id="61574-127">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="61574-128">Cuenta existente de buzón de recursos: confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="61574-128">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="61574-129">Cuenta nueva de buzón de recursos: confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="61574-129">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="61574-130">Aprovisionamiento de Exchange Online</span><span class="sxs-lookup"><span data-stu-id="61574-130">Exchange Online provisioning</span></span>

<span data-ttu-id="61574-131">En primer lugar, conectarse a Exchange Online PowerShell siguiendo las instrucciones en el tema, [conectarse a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="61574-131">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="61574-132">Para establecer una cuenta de buzón de sala de recursos existente para el sistema del sitio de Skype, ejecute los siguientes comandos de PowerShell en línea de Exchange:</span><span class="sxs-lookup"><span data-stu-id="61574-132">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="61574-133">Para crear una nueva cuenta de buzón de recursos de Exchange para el sistema del sitio de Skype, ejecute los siguientes comandos de PowerShell en línea de Exchange:</span><span class="sxs-lookup"><span data-stu-id="61574-133">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="61574-134">Los comandos anteriores configurar o crean una nueva cuenta de buzón de recursos de Exchange para uso del sistema de sala de Skype habilitando la cuenta.</span><span class="sxs-lookup"><span data-stu-id="61574-134">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="61574-135">Después de crear el buzón, puede utilizar el cmdlet Set-CalendarProcessing de PowerShell en línea de Exchange para configurar el buzón.</span><span class="sxs-lookup"><span data-stu-id="61574-135">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="61574-136">Haga referencia a los pasos 3 a 6 en implementaciones locales de bosque único para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="61574-136">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="61574-137">Aprovisionamiento de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="61574-137">Skype for Business Online provisioning</span></span>

<span data-ttu-id="61574-138">Después de haber creado una cuenta de buzón de la sala de recurso y habilitado como se mostró anteriormente, la cuenta se sincronizará desde el bosque de Exchange Online a Skype para el bosque del negocio en línea utilizando el bosque de Active Directory de Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="61574-138">After a resource room mailbox account has been created and enabled as shown previously, the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="61574-139">Los pasos siguientes son necesarios para proporcionar la cuenta de sistema del sitio de Skype en el Skype para grupo de negocios en línea.</span><span class="sxs-lookup"><span data-stu-id="61574-139">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="61574-140">Estos pasos son los mismos para una cuenta de buzón de recursos existente o una cuenta recién creada (confrm1 o confrm2), porque una vez que están habilitados en Exchange Online, ambas cuentas se sincronizarán con Skype para los negocios en línea de la misma manera:</span><span class="sxs-lookup"><span data-stu-id="61574-140">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="61574-141">Cree una sesión remota de PowerShell.</span><span class="sxs-lookup"><span data-stu-id="61574-141">Create a Remote PowerShell session.</span></span> <span data-ttu-id="61574-142">Tenga en cuenta que necesitará descargar Skype para el módulo del conector de negocios en línea y Asistente Microsoft Online Services inicio de sesión y asegúrese de que su equipo está configurado.</span><span class="sxs-lookup"><span data-stu-id="61574-142">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="61574-143">Para obtener más información, consulte [Configuración del equipo para la administración de Lync Online](http://technet.microsoft.com/library/bca143e2-659a-4161-9220-59ffd9fc2874.aspx).</span><span class="sxs-lookup"><span data-stu-id="61574-143">For more information, see [Configuring Your Computer for Lync Online Management](http://technet.microsoft.com/library/bca143e2-659a-4161-9220-59ffd9fc2874.aspx).</span></span>
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="61574-144">Para habilitar una cuenta de sistema del sitio de Skype de Skype para empresas, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="61574-144">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="61574-145">Puede obtener el RegistrarPool devuelve la dirección donde están alojados su Skype para usuarios profesionales de una de las cuentas existentes mediante el comando siguiente para esta propiedad:</span><span class="sxs-lookup"><span data-stu-id="61574-145">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="61574-146">Asignar una licencia de Skype Empresarial Online</span><span class="sxs-lookup"><span data-stu-id="61574-146">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="61574-147">Después de habilitar una cuenta de sistema del sitio de Skype en Skype para el negocio, puede asignar un Skype para los negocios en línea (Plan 2) o Skype para licencia de negocios en línea (Plan 3) a través del portal de administración de Office 365 como se describe en [asignar o quitar licencias para Office 365 para el negocio](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) o en [Skype para Business licensing del complemento](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span><span class="sxs-lookup"><span data-stu-id="61574-147">After you enable a Skype Room System account in Skype for Business, you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="61574-148">Después de asignar una licencia de Skype para los negocios en línea, podrá iniciar sesión y validar que la cuenta está activa utilizando cualquier Skype para cliente de empresa.</span><span class="sxs-lookup"><span data-stu-id="61574-148">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="password-expiration"></a><span data-ttu-id="61574-149">Caducidad de la contraseña</span><span class="sxs-lookup"><span data-stu-id="61574-149">Password expiration</span></span>

<span data-ttu-id="61574-150">En Office 365, la directiva de caducidad de la contraseña predeterminada de todas las cuentas de usuario es de 90 días a no ser que configure una directiva de caducidad de la contraseña diferente.</span><span class="sxs-lookup"><span data-stu-id="61574-150">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="61574-151">Para las cuentas de sistema del sitio de Skype, puede seleccionar la contraseña nunca caduca opción con los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="61574-151">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="61574-152">Cree una sesión en Windows Azure Active Directory mediante el uso de las credenciales de administrador global de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="61574-152">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="61574-153">Establecer la contraseña nunca caduca la configuración de la cuenta de la sala de sistema de sala de Skype creada previamente mediante el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="61574-153">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="61574-154">Para obtener más información, consulte [Uso de Windows PowerShell para administrar Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).</span><span class="sxs-lookup"><span data-stu-id="61574-154">For more information, see [Using Windows PowerShell to Manage Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).</span></span>
  

