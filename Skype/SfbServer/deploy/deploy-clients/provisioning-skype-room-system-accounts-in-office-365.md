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
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a>Aprovisionamiento de cuentas del Sistema de salas de Skype en Office 365
 
Lea este tema para obtener información acerca del aprovisionamiento de cuentas de Sistema de salas de Skype en Office 365.
  
La siguiente sección cubre el aprovisionamiento de la cuenta del sistema de salas de Skype para un inquilino de Office 365.
  
## <a name="office-365-prerequisites"></a>Requisitos previos de Office 365

El inquilino en línea debe cumplir los siguientes requisitos:
  
- El plan de Office 365 debe incluir Skype empresarial online plan 2 u Office 365 E1, E3 o E5. <br/>Para obtener más información sobre los planes de Skype empresarial online, consulte la [Descripción del servicio de Skype empresarial online](https://technet.microsoft.com/library/jj822172.aspx).
    
- Su inquilino debe tener habilitada la función de conferencia de Skype empresarial.
    
- El inquilino debe tener Exchange Online habilitado. 
    
- El administrador remoto del inquilino debe tener el siguiente acceso a PowerShell:
    
  - Acceso remoto a PowerShell de Exchange
    
  - Acceso remoto a PowerShell de Skype empresarial online
    
  - Módulo Windows Azure Active Directory para Windows PowerShell para obtener acceso al directorio de Office 365
    
Para la cuenta de Salas de Skype, se necesita la siguiente licencia:
  
- Para habilitar las reuniones de Skype, es necesario disponer de una licencia de Skype empresarial online plan 2 u Office 365 E1 o E3.
    
- Para asignar un número de teléfono a la sala con la funcionalidad de telefonía IP empresarial de modo que se pueda habilitar la sala con un número de teléfono, se requiere un plan 2 de Skype empresarial online con la licencia de sistema telefónico u Office 365 E5 (1).
    
- Si necesita capacidades de acceso telefónico desde una reunión, necesitará una licencia de audioconferencia y sistema telefónico.  Si necesita poder llamar desde una reunión, necesitará un plan de llamadas nacionales o nacionales e internacionales. 
    
- No se necesita una licencia de Exchange Online para la cuenta de Salas de Skype porque la cuenta debería configurarse como una cuenta de buzón del recurso.
    
## <a name="provisioning-overview"></a>Información general de aprovisionamiento

El siguiente diagrama ofrece una descripción general del flujo de aprovisionamiento de cuentas del sistema de salas de Skype en Office 365.
  
![Pasos de aprovisionamiento del sistema de salas de Skype para O365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Identificar una nueva sala de conferencias

Es posible que ya tenga un buzón de sala de recursos en Exchange que proporcione la característica de programación o que cree un buzón de recursos por primera vez para facilitar la implementación de sistemas de salas de Skype. En cualquier caso, debe identificar una cuenta de sala para que la use el inquilino. Las secciones de provisiones de Exchange Online y de Skype empresarial proporcionan orientación para ambos tipos de cuentas. Por ejemplo, supongamos que tiene las dos salas siguientes y le gustaría implementar el sistema de salas de Skype para ambos:
  
- Cuenta existente de buzón de recursos: confrm1@contoso.onmicrosoft.com
    
- Cuenta nueva de buzón de recursos: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Aprovisionamiento de Exchange Online

En primer lugar, conéctese a Exchange Online PowerShell siguiendo las instrucciones de este tema, [Conéctese a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
  
Para configurar una cuenta de buzón de sala de recursos existente para el sistema de salas de Skype, ejecute los siguientes comandos en Exchange Online PowerShell:
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Para crear una cuenta nueva de buzón de recursos de Exchange para el sistema de salas de Skype, ejecute los siguientes comandos en Exchange Online PowerShell:
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Los comandos anteriores para configurar o crear una cuenta nueva de buzón de recursos de Exchange para el uso del sistema de salas de Skype habilitando la cuenta.
  
Después de crear el buzón de correo, puede usar el cmdlet Set-CalendarProcessing en Exchange Online PowerShell para configurarlo. Haga referencia a los pasos 3 a 6 en implementaciones locales de bosque único para obtener más información.

## <a name="assigning-a-skype-for-business-online-license"></a>Asignar una licencia de Skype Empresarial Online

Ahora puede asignar una licencia de Skype empresarial online (plan 2) o de Skype empresarial online (Plan 3) mediante el portal administrativo de Office 365 según se describe en [asignar o quitar licencias de office 365 para empresas](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) o en [licencias complementarias de Skype empresarial](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7). 
  
Después de asignar una licencia para Skype empresarial online, podrá iniciar sesión y validar que la cuenta esté activa con cualquier cliente de Skype empresarial.
  
## <a name="skype-for-business-online-provisioning"></a>Aprovisionamiento de Skype Empresarial Online

Una vez que se ha creado y habilitado una cuenta de buzón de sala de recursos como se ha mostrado anteriormente, y se ha autorizado la cuenta para Skype empresarial online, la cuenta se sincronizará desde el bosque de Exchange Online a un bosque de Skype empresarial online con el Bosque de Windows Azure Active Directory. Para aprovisionar la cuenta del sistema de salas de Skype en el grupo de Skype empresarial online, debe seguir estos pasos. Estos pasos son los mismos para una cuenta de buzón de recursos existente o una cuenta recién creada (confrm1 o confrm2), porque una vez que se habilitan en Exchange Online, estas dos cuentas se sincronizarán con Skype empresarial online de la misma manera:
  
1. Cree una sesión remota de PowerShell. Tenga en cuenta que tendrá que descargar el módulo del conector de Skype empresarial online y el ayudante para el inicio de sesión de Microsoft Online Services y asegurarse de que su equipo está configurado. Para obtener más información, vea [configurar el equipo para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. Para habilitar una cuenta de sistema de Skype Room para Skype empresarial, ejecute el siguiente comando:
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Puede obtener la dirección de RegistrarPool en la que los usuarios de Skype empresarial estén alojados desde una de sus cuentas existentes con el siguiente comando para que devuelva esta propiedad:
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>La autenticación multifactor (MFA) no es compatible con las cuentas del sistema de salas de Skype. 

## <a name="password-expiration"></a>Caducidad de la contraseña

En Office 365, la directiva de caducidad de la contraseña predeterminada de todas las cuentas de usuario es de 90 días a no ser que configure una directiva de caducidad de la contraseña diferente. Para las cuentas del sistema de salas de Skype, puede seleccionar la opción la contraseña nunca vence con los pasos siguientes.
  
1. Cree una sesión en Windows Azure Active Directory mediante el uso de las credenciales de administrador global de inquilinos.
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Establezca la configuración de la contraseña nunca vence para la cuenta de sala del sistema de salas de Skype creada anteriormente con el siguiente comando:
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Para obtener más información, vea [configurar el equipo para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
## <a name="validate"></a>Valide

Para la validación, debe poder usar cualquier cliente de Skype empresarial para iniciar sesión en la cuenta que ha creado.

