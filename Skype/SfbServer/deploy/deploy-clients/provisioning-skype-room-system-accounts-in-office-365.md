---
title: Aprovisionamiento de cuentas del sistema de salón de Skype en Microsoft 365 y Office 365
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
description: Lea este tema para obtener información sobre el aprovisionamiento de cuentas del sistema de sala de Skype en Microsoft 365 u Office 365.
ms.openlocfilehash: 8e44e648e12ec4db1e8acf9617c02937f9418c41
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569382"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a>Aprovisionamiento de cuentas del sistema de salón de Skype en Microsoft 365 y Office 365
 
Lea este tema para obtener información sobre el aprovisionamiento de cuentas del sistema de sala de Skype en Microsoft 365 u Office 365.
  
En la siguiente sección se describe el aprovisionamiento de cuentas del sistema de salón de Skype.
  
## <a name="microsoft-365-and-office-365-prerequisites"></a>Requisitos previos de Microsoft 365 y Office 365

El inquilino en línea debe cumplir los siguientes requisitos:
  
- El plan de Microsoft 365 u Office 365 debe incluir el Plan 2 de Skype Empresarial Online u Office 365 E1, E3 o E5. <br/>Para obtener más información sobre los planes de Skype Empresarial Online, vea la Descripción del servicio [de Skype Empresarial Online](https://technet.microsoft.com/library/jj822172.aspx).
    
- El inquilino debe tener habilitada la funcionalidad de conferencia de Skype Empresarial.
    
- El inquilino debe tener Exchange Online habilitado. 
    
- El administrador remoto del inquilino debe tener el siguiente acceso de PowerShell:
    
  - Acceso remoto de PowerShell de Exchange
    
  - Acceso remoto de PowerShell de Skype Empresarial Online
    
  - Windows Azure módulo de Active Directory para Windows PowerShell acceso a directorios de Microsoft 365 u Office 365
    
Para la cuenta de salón de Skype, se requieren las siguientes licencias:
  
- Se requiere una licencia de Skype Empresarial Online Plan 2 u Office 365 E1 o E3 para habilitar las reuniones de Skype.
    
- Para dar derecho a la sala con la funcionalidad Telefonía IP empresarial para que la sala se pueda habilitar con un número de teléfono, se requiere un Plan 2 de Skype Empresarial Online con la licencia del sistema telefónico u Office 365 E5 (1).
    
- Si necesita funcionalidades de acceso telefónico local de una reunión, necesitará una audioconferencia y una licencia del sistema telefónico.  Si necesita funcionalidades de acceso telefónico local desde una reunión, necesitará un plan de llamadas nacionales o nacionales e internacionales. 
    
- No es necesaria una licencia de Exchange Online para la cuenta de salón de Skype porque la cuenta debe configurarse como una cuenta de buzón de recursos.
    
## <a name="provisioning-overview"></a>Introducción al aprovisionamiento

En el siguiente diagrama se proporciona información general sobre el flujo de aprovisionamiento de cuentas del sistema de salón de Skype.
  
![Pasos de aprovisionamiento del sistema de sala de Skype](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Identificar una nueva sala de conferencias

Es posible que ya tenga un buzón de sala de recursos en Exchange que proporciona la característica de programación, o puede que esté creando un buzón de recursos por primera vez para facilitar la implementación del sistema de sala de Skype. En cualquier caso, debe identificar una cuenta de sala que se usará en el espacio empresarial. Las secciones Aprovisionamiento de Exchange Online y Aprovisionamiento de Skype Empresarial proporcionan instrucciones para ambos tipos de cuentas. Por ejemplo, supongamos que tiene las dos salas siguientes y le gustaría implementar El sistema de salas de Skype para ambas:
  
- Cuenta de buzón de recursos existente: confrm1@contoso.onmicrosoft.com
    
- Nueva cuenta de buzón de recursos: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Aprovisionamiento de Exchange Online

En primer lugar, conéctese a Exchange Online PowerShell siguiendo las instrucciones del tema [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
  
Para establecer una cuenta de buzón de sala de recursos existente para El sistema de sala de Skype, ejecute los siguientes comandos en Exchange Online PowerShell:
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Para crear una nueva cuenta de buzón de recursos de Exchange para Skype Room System, ejecute los siguientes comandos en Exchange Online PowerShell:
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Los comandos anteriores configuraron o crearon una nueva cuenta de buzón de recursos de Exchange para el uso del sistema de salón de Skype habilitando la cuenta.
  
Después de crear el buzón, puede usar el cmdlet Set-CalendarProcessing exchange Online PowerShell para configurar el buzón. Consulte los pasos del 3 al 6 en Implementaciones locales de bosque único para obtener más información

## <a name="assigning-a-skype-for-business-online-license"></a>Asignar una licencia de Skype Empresarial Online

Ahora puede asignar una licencia de Skype Empresarial Online (Plan 2) o Skype Empresarial Online (Plan 3) mediante el portal administrativo de Microsoft 365, tal como se describe en Asignar o quitar licencias para [Microsoft 365](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) para empresas o en licencias de complementos de [Skype](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)Empresarial. 
  
Después de asignar una licencia para Skype Empresarial Online, podrá iniciar sesión y validar que la cuenta está activa con cualquier cliente de Skype Empresarial.
  
## <a name="skype-for-business-online-provisioning"></a>Aprovisionamiento de Skype Empresarial Online

Después de crear y habilitar una cuenta de buzón de sala de recursos como se muestra anteriormente, y de haber concedido una licencia a la cuenta para Skype Empresarial Online, la cuenta se sincronizará desde el bosque de Exchange Online con el bosque de Skype Empresarial Online mediante el bosque de Active Directory Windows Azure. Los pasos siguientes son necesarios para aprovisionar la cuenta sistema de salón de Skype en el grupo de Skype Empresarial Online. Estos pasos son los mismos para una cuenta de buzón de recursos existente o una cuenta recién creada (confrm1 o confrm2), ya que una vez habilitadas en Exchange Online, ambas cuentas se sincronizarán con Skype Empresarial Online de la misma manera:
  
1. Crear una sesión remota de PowerShell. Tenga en cuenta que tendrá que descargar el [módulo de PowerShell de Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-install).
    
  ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
  ```

2. Para habilitar una cuenta del sistema de salón de Skype Empresarial, ejecute el siguiente comando:
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Puede obtener la dirección RegistrarPool donde los usuarios de Skype Empresarial se encuentran en una de sus cuentas existentes mediante el siguiente comando para devolver esta propiedad:
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>La autenticación multifactor (MFA) no es compatible con las cuentas del sistema de salón de Skype. 

## <a name="password-expiration"></a>Expiración de contraseña

En Microsoft 365 u Office 365, la directiva de expiración de contraseña predeterminada para todas las cuentas de usuario es de 90 días, a menos que configure una directiva de expiración de contraseña diferente. Para las cuentas del sistema de salón de Skype, puede seleccionar la configuración Contraseña nunca expira con los pasos siguientes.
  
1. Cree una sesión Windows Azure Active Directory mediante las credenciales de administrador global de inquilinos.
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Establezca la configuración Contraseña nunca expira para la cuenta de salón del sistema de salón de Skype creada anteriormente mediante el siguiente comando:
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Para obtener más información, [vea Configurar el equipo para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
## <a name="validate"></a>Validar

Para la validación, debe poder usar cualquier cliente de Skype Empresarial para iniciar sesión en la cuenta que creó.

