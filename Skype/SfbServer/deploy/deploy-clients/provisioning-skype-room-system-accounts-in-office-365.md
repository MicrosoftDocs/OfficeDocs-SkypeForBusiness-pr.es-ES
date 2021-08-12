---
title: Aprovisionamiento Skype del sistema de sala en Microsoft 365 y Office 365
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
description: Lea este tema para obtener información sobre el aprovisionamiento Skype del sistema de sala en Microsoft 365 o Office 365.
ms.openlocfilehash: e50d0df6b0ae3c03299756d9f917083fc2518cb64d7b049d0d7b23eb4f64b063
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307951"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a>Aprovisionamiento Skype del sistema de sala en Microsoft 365 y Office 365
 
Lea este tema para obtener información sobre el aprovisionamiento Skype del sistema de sala en Microsoft 365 o Office 365.
  
En la siguiente sección se Skype aprovisionamiento de cuentas del sistema de sala.
  
## <a name="microsoft-365-and-office-365-prerequisites"></a>Microsoft 365 y Office 365 requisitos previos

El inquilino en línea debe cumplir los siguientes requisitos:
  
- El Microsoft 365 o Office 365 debe incluir Skype Empresarial plan en línea 2 o Office 365 E1, E3 o E5. <br/>Para obtener más información Skype Empresarial planes en línea, consulte [el Skype Empresarial Online Service Description](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description).
    
- El espacio empresarial debe tener la capacidad de conferencia Skype Empresarial habilitada.
    
- El espacio empresarial debe tener Exchange Online habilitada. 
    
- El administrador remoto del inquilino debe tener el siguiente acceso de PowerShell:
    
  - Exchange Acceso remoto de PowerShell
    
  - Skype Empresarial Acceso remoto de PowerShell en línea
    
  - Windows Azure Active Directory módulo para Windows PowerShell acceso a Microsoft 365 o Office 365 de directorio
    
Para la Skype room, se requieren las siguientes licencias:
  
- Se Skype Empresarial una licencia de plan 2 o Office 365 E1 o E3 en línea para habilitar Skype reuniones.
    
- Para dar derecho a la sala con la funcionalidad Telefonía IP empresarial para que la sala se pueda habilitar con un número de teléfono, se requiere un plan en línea 2 de Skype Empresarial con la licencia Sistema telefónico o Office 365 E5 (1).
    
- Si necesita funcionalidades de acceso telefónico local de una reunión, necesitará una audioconferencia y una Sistema telefónico de acceso telefónico.  Si necesita funcionalidades de acceso telefónico local desde una reunión, necesitará un plan de llamadas nacionales o nacionales e internacionales. 
    
- No Exchange Online una licencia para la cuenta Skype Room porque la cuenta debe configurarse como una cuenta de buzón de recursos.
    
## <a name="provisioning-overview"></a>Introducción al aprovisionamiento

En el siguiente diagrama se proporciona información general sobre el flujo Skype de aprovisionamiento de cuentas del sistema de sala.
  
![Skype Pasos de aprovisionamiento del sistema de sala](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Identificar una nueva sala de conferencias

Es posible que ya tenga un buzón de sala de recursos en Exchange que proporciona la característica de programación, o puede que esté creando un buzón de recursos por primera vez para facilitar Skype implementación del sistema de sala. En cualquier caso, debe identificar una cuenta de sala que se usará en el espacio empresarial. Las Exchange Online Provision y Skype Empresarial Provision proporcionan instrucciones para ambos tipos de cuentas. Por ejemplo, supongamos que tiene las dos salas siguientes y le gustaría implementar Skype room system para ambas:
  
- Cuenta de buzón de recursos existente: confrm1@contoso.onmicrosoft.com
    
- Nueva cuenta de buzón de recursos: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Exchange Online aprovisionamiento

En primer lugar, conéctese Exchange Online PowerShell siguiendo las instrucciones del tema, Conectar [a Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).
  
Para establecer una cuenta de buzón de sala de recursos existente para Skype Room System, ejecute los siguientes comandos en Exchange Online PowerShell:
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Para crear una nueva cuenta Exchange buzón de recursos para Skype Room System, ejecute los siguientes comandos en Exchange Online PowerShell:To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Los comandos anteriores configuraron o crearon una nueva cuenta de buzón de Exchange de recursos para Skype de sala habilitando la cuenta.
  
Después de crear el buzón, puede usar el cmdlet Set-CalendarProcessing en Exchange Online PowerShell para configurar el buzón. Consulte los pasos del 3 al 6 en Implementaciones locales de bosque único para obtener más información

## <a name="assigning-a-skype-for-business-online-license"></a>Asignar una licencia Skype Empresarial Online

Ahora puede asignar una licencia de Skype Empresarial Online (Plan 2) o Skype Empresarial Online (Plan 3) mediante el portal administrativo de Microsoft 365, tal como se describe en Asignar o quitar licencias para [Microsoft 365](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) para empresas o en licencias de complementos de [Skype Empresarial.](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7) 
  
Después de asignar una licencia para Skype Empresarial Online, podrá iniciar sesión y validar que la cuenta está activa con cualquier Skype Empresarial cliente.
  
## <a name="skype-for-business-online-provisioning"></a>Skype Empresarial Aprovisionamiento en línea

Una vez que se haya creado y habilitado una cuenta de buzón de sala de recursos como se muestra anteriormente, y haya concedido una licencia a la cuenta para Skype For Business Online, la cuenta se sincronizará del bosque de Exchange Online al bosque de Skype Empresarial Online mediante el uso del bosque Windows Azure Active Directory. Los siguientes pasos son necesarios para aprovisionar la cuenta Skype sistema de sala en el grupo Skype Empresarial en línea. Estos pasos son los mismos para una cuenta de buzón de recursos existente o una cuenta recién creada (confrm1 o confrm2), ya que una vez habilitadas en Exchange Online, ambas cuentas se sincronizarán con Skype Empresarial Online de la misma manera:
  
1. Crear una sesión remota de PowerShell. Tenga en cuenta que tendrá que descargar Teams [módulo de PowerShell](/microsoftteams/teams-powershell-install).
    
  ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
  ```

2. Para habilitar una cuenta Skype sistema de sala para Skype Empresarial, ejecute el siguiente comando:
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Puede obtener la dirección RegistrarPool donde los usuarios de Skype Empresarial se encuentran en una de sus cuentas existentes mediante el siguiente comando para devolver esta propiedad:
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>La autenticación multifactor (MFA) no se admite para las Skype del sistema de sala. 

## <a name="password-expiration"></a>Expiración de contraseña

En Microsoft 365 o Office 365, la directiva de expiración de contraseña predeterminada para todas las cuentas de usuario es de 90 días, a menos que configure una directiva de expiración de contraseña diferente. Para Skype sistema de sala, puede seleccionar la configuración Contraseña nunca expira con los pasos siguientes.
  
1. Cree una sesión Windows Azure Active Directory con sus credenciales de administrador global de inquilinos.
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Establezca la configuración Contraseña nunca expira para la cuenta de sala Skype del sistema de sala creada anteriormente mediante el siguiente comando:
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Para obtener más información, vea [Configurar el equipo para Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).
  
## <a name="validate"></a>Validar

Para la validación, debe poder usar cualquier Skype Empresarial cliente para iniciar sesión en la cuenta que creó.