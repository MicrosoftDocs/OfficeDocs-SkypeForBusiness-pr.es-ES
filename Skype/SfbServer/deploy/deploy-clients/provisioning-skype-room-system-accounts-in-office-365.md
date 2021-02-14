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
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a>Aprovisionamiento de cuentas del Sistema de sala de Skype en Microsoft 365 y Office 365
 
Lea este tema para obtener información sobre el aprovisionamiento de cuentas del Sistema de sala de Skype en Microsoft 365 u Office 365.
  
En la siguiente sección se describe el aprovisionamiento de cuentas del Sistema de sala de Skype.
  
## <a name="microsoft-365-and-office-365-prerequisites"></a>Requisitos previos de Microsoft 365 y Office 365

El inquilino en línea debe cumplir los siguientes requisitos:
  
- El plan de Microsoft 365 u Office 365 debe incluir Skype Empresarial Online Plan 2 u Office 365 E1, E3 o E5. <br/>Para obtener más información sobre los planes de Skype Empresarial Online, consulte la descripción del servicio [skype empresarial online.](https://technet.microsoft.com/library/jj822172.aspx)
    
- Su espacio empresarial debe tener habilitada la funcionalidad de conferencia de Skype Empresarial.
    
- Su espacio empresarial debe tener Exchange Online habilitado. 
    
- El administrador remoto del espacio empresarial debe tener el siguiente acceso a PowerShell:
    
  - Acceso remoto de PowerShell de Exchange
    
  - Acceso remoto de PowerShell de Skype Empresarial Online
    
  - Windows Azure módulo de Active Directory para Windows PowerShell acceso al directorio de Microsoft 365 u Office 365
    
Para la cuenta de la sala de Skype, se requiere la siguiente licencia:
  
- Se necesita una licencia de Skype Empresarial Online plan 2 u Office 365 E1 o E3 para habilitar reuniones de Skype.
    
- Para habilitar la sala con la funcionalidad Telefonía IP empresarial para que la sala pueda habilitarse con un número de teléfono, se requiere un plan 2 de Skype Empresarial Online con la licencia del sistema telefónico u Office 365 E5 (1).
    
- Si necesita funcionalidades de acceso telefónico local de una reunión, necesitará una licencia de audioconferencia y sistema telefónico.  Si necesita funcionalidades de acceso telefónico de una reunión, necesitará un plan de llamadas nacionales, nacionales e internacionales. 
    
- No se necesita una licencia de Exchange Online para la cuenta de sala de Skype porque la cuenta debe configurarse como una cuenta de buzón de recursos.
    
## <a name="provisioning-overview"></a>Información general sobre el aprovisionamiento

En el siguiente diagrama se proporciona información general sobre el flujo de aprovisionamiento de cuentas del Sistema de sala de Skype.
  
![Pasos de aprovisionamiento del sistema de sala de Skype](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Identificar una nueva sala de conferencias

You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment. En cualquier caso, debe identificar una cuenta de sala que se usará en su espacio empresarial. Las secciones Aprovisionamiento de Exchange Online y Aprovisionamiento de Skype Empresarial proporcionan instrucciones para ambos tipos de cuentas. Por ejemplo, supongamos que tiene las dos salas siguientes y que le gustaría implementar el Sistema de salas de Skype para ambas:
  
- Cuenta de buzón de recursos existente: confrm1@contoso.onmicrosoft.com
    
- Nueva cuenta de buzón de recursos: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Aprovisionamiento de Exchange Online

En primer lugar, conéctese a Exchange Online PowerShell siguiendo las instrucciones del tema [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
  
Para establecer una cuenta de buzón de sala de recursos existente para el Sistema de sala de Skype, ejecute los siguientes comandos en Exchange Online PowerShell:
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Para crear una nueva cuenta de buzón de recursos de Exchange para el Sistema de sala de Skype, ejecute los siguientes comandos en Exchange Online PowerShell:
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Los comandos anteriores configuraron o crearon una nueva cuenta de buzón de recursos de Exchange para el uso del Sistema de sala de Skype habilitando la cuenta.
  
Después de crear el buzón, puede usar el cmdlet Set-CalendarProcessing en Exchange Online PowerShell para configurar el buzón. Consulte los pasos del 3 al 6 en Implementaciones locales de bosque único para obtener más información

## <a name="assigning-a-skype-for-business-online-license"></a>Asignar una licencia de Skype Empresarial Online

Ahora puede asignar una licencia de Skype Empresarial Online (Plan 2) o Skype Empresarial Online (Plan 3) mediante el portal administrativo de Microsoft 365, como se describe en Asignar o quitar licencias de [Microsoft 365](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) para empresas o en licencias de complementos de [Skype](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)Empresarial. 
  
Después de asignar una licencia para Skype Empresarial Online, podrá iniciar sesión y validar que la cuenta está activa con cualquier cliente de Skype Empresarial.
  
## <a name="skype-for-business-online-provisioning"></a>Aprovisionamiento de Skype Empresarial Online

Una vez que se haya creado y habilitado una cuenta de buzón de sala de recursos como se ha mostrado anteriormente, y haya concedido una licencia a la cuenta para Skype Empresarial Online, la cuenta se sincronizará desde el bosque de Exchange Online con el bosque de Skype Empresarial Online mediante el bosque de Active Directory de Windows Azure. Los siguientes pasos son necesarios para aprovisionar la cuenta del Sistema de sala de Skype en el grupo de Skype Empresarial Online. Estos pasos son los mismos para una cuenta de buzón de recursos existente o una cuenta recién creada (confrm1 o confrm2), ya que una vez habilitadas en Exchange Online, ambas cuentas se sincronizarán con Skype Empresarial Online de la misma manera:
  
1. Crear una sesión de PowerShell remoto. Tenga en cuenta que tendrá que descargar el Módulo de conector de Skype Empresarial Online y el Asistente para Microsoft Online Services Sign-In y asegurarse de que el equipo está configurado. Para obtener más información, [vea Configurar el equipo para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. Para habilitar una cuenta del Sistema de sala de Skype para Skype Empresarial, ejecute el siguiente comando:
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Puede obtener la dirección RegistrarPool en la que los usuarios de Skype Empresarial se encuentran en una de sus cuentas existentes mediante el siguiente comando para devolver esta propiedad:
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>La autenticación multifactor (MFA) no es compatible con las cuentas del sistema de sala de Skype. 

## <a name="password-expiration"></a>Expiración de contraseña

En Microsoft 365 u Office 365, la directiva de expiración de contraseña predeterminada para todas las cuentas de usuario es de 90 días, a menos que configure una directiva de expiración de contraseña diferente. Para las cuentas del sistema de sala de Skype, puede seleccionar la configuración contraseña nunca expira con los siguientes pasos.
  
1. Cree una sesión Windows Azure Active Directory con sus credenciales de administrador global de inquilinos.
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Establecer la configuración De contraseña nunca expira para la cuenta de sala del Sistema de sala de Skype creada anteriormente mediante el siguiente comando:
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Para obtener más información, [vea Configurar el equipo para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
## <a name="validate"></a>Validar

Para la validación, debería poder usar cualquier cliente de Skype Empresarial para iniciar sesión en la cuenta que creó.

