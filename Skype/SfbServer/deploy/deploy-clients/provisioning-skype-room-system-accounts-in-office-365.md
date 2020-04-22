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
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a>Aprovisionamiento de cuentas del sistema de salas de Skype en Microsoft 365 y Office 365
 
Lea este tema para obtener información sobre el aprovisionamiento de cuentas del sistema de salas de Skype en Office 365.
  
En la siguiente sección se describe el aprovisionamiento de cuentas de sistemas de salas de Skype para una organización de Office 365.
  
## <a name="microsoft-365-and-office-365-prerequisites"></a>Requisitos previos de Microsoft 365 y Office 365

El inquilino en línea debe cumplir los siguientes requisitos:
  
- El plan Microsoft 365 o Office 365 debe incluir Skype empresarial online (plan 2) o Office 365 E1, E3 o E5. <br/>Para obtener más información sobre los planes de Skype empresarial online, consulte la [Descripción del servicio Skype empresarial online](https://technet.microsoft.com/library/jj822172.aspx).
    
- El inquilino debe tener habilitada la función de conferencias de Skype empresarial.
    
- El inquilino debe tener Exchange Online habilitado. 
    
- El administrador remoto del inquilino debe tener el siguiente acceso de PowerShell:
    
  - Acceso remoto a PowerShell de Exchange
    
  - Acceso remoto a PowerShell de Skype empresarial online
    
  - Módulo Windows Azure Active Directory para Windows PowerShell para obtener acceso al directorio de Office 365
    
Para la cuenta de sala de Skype, se necesita la siguiente licencia:
  
- Se necesita una licencia de Skype empresarial online (plan 2) o de Office 365 E1 o E3 para habilitar las reuniones de Skype.
    
- Para cambiar el título de la sala con la funcionalidad de Enterprise Voice de modo que el salón pueda habilitarse con un número de teléfono, se requiere un plan 2 de Skype empresarial online con la licencia de sistema telefónico o Office 365 E5 (1).
    
- Si necesita capacidades de acceso telefónico desde una reunión, necesitará una licencia de sistema telefónico y Conferencia de audio.  Si necesita capacidades de acceso telefónico desde una reunión, necesitará un plan de llamadas nacionales o nacionales e internacionales. 
    
- No se necesita una licencia de Exchange Online para la cuenta de sala de Skype, ya que la cuenta debe estar configurada como una cuenta de buzón de recursos.
    
## <a name="provisioning-overview"></a>Información general sobre el aprovisionamiento

En el siguiente diagrama se proporciona información general sobre el flujo de aprovisionamiento de cuentas del sistema de salas de Skype en Office 365.
  
![Pasos de aprovisionamiento del sistema de salas de Skype para O365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Identificar una nueva sala de conferencias

Es posible que ya tenga un buzón de sala de recursos en Exchange que proporcione la característica de programación o que cree un buzón de recursos por primera vez para facilitar la implementación de sistemas de salas de Skype. En cualquier caso, debe identificar una cuenta de sala que se utilizará en el espacio empresarial. Las secciones de aprovisionamiento de Exchange Online y de Skype empresarial proporcionan orientación para ambos tipos de cuentas. Por ejemplo, supongamos que tiene las dos salas siguientes y desea implementar el sistema de salas de Skype para ambas:
  
- Cuenta de buzón de recursos existente: confrm1@contoso.onmicrosoft.com
    
- Nueva cuenta de buzón de recursos: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Aprovisionamiento de Exchange Online

En primer lugar, conéctese a Exchange Online PowerShell siguiendo las instrucciones que se indican en el tema [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
  
Para establecer una cuenta de buzón de sala de recursos existente para el sistema de salas de Skype, ejecute los siguientes comandos en Exchange Online PowerShell:
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Para crear una cuenta de buzón de recursos de Exchange nueva para el sistema de salas de Skype, ejecute los siguientes comandos en Exchange Online PowerShell:
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Los comandos anteriores configuran o crean una nueva cuenta de buzón de recursos de Exchange para el uso del sistema de salas de Skype mediante la habilitación de la cuenta.
  
Después de crear el buzón, puede usar el cmdlet Set-CalendarProcessing en Exchange Online PowerShell para configurar el buzón. Consulte los pasos 3 a 6 en implementaciones locales de bosque único para obtener más información.

## <a name="assigning-a-skype-for-business-online-license"></a>Asignar una licencia de Skype empresarial online

Ahora puede asignar una licencia de Skype empresarial online (plan 2) o Skype empresarial online (Plan 3) mediante el portal administrativo de Office 365, tal como se describe en [asignar o quitar licencias para office 365 para empresas](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) o en [licencias complementarias de Skype](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)empresarial. 
  
Después de asignar una licencia para Skype empresarial online, podrá iniciar sesión y validar que la cuenta está activa mediante cualquier cliente de Skype empresarial.
  
## <a name="skype-for-business-online-provisioning"></a>Aprovisionamiento de Skype empresarial online

Una vez que se haya creado y habilitado una cuenta de buzón de sala de recursos, tal y como se mostró anteriormente, y haya configurado la cuenta de Skype empresarial online, la cuenta se sincronizará desde el bosque de Exchange Online al bosque de Skype empresarial online mediante el bosque de Windows Azure Active Directory. Los siguientes pasos son necesarios para aprovisionar la cuenta del sistema de salas de Skype en el grupo de Skype empresarial online. Estos pasos son los mismos para una cuenta de buzón de recursos existente o para una cuenta recién creada (confrm1 o confrm2), ya que una vez que están habilitados en Exchange Online, ambas cuentas se sincronizarán con Skype empresarial online de la misma manera:
  
1. Cree una sesión remota de PowerShell. Tenga en cuenta que tendrá que descargar el módulo del conector de Skype empresarial online y el Asistente para el inicio de sesión de Microsoft Online Services y asegurarse de que el equipo está configurado. Para obtener más información, consulte [configurar el equipo para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. Para habilitar una cuenta de sistema de salas de Skype para Skype empresarial, ejecute el siguiente comando:
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Puede obtener la dirección RegistrarPool donde sus usuarios de Skype empresarial están hospedados de una de sus cuentas existentes mediante el siguiente comando para devolver esta propiedad:
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
>La autenticación multifactor (MFA) no es compatible con las cuentas del sistema de salas de Skype. 

## <a name="password-expiration"></a>Expiración de contraseña

En Office 365, la Directiva de expiración de contraseña predeterminada para todas las cuentas de usuario es de 90 días a menos que configure una directiva de expiración de contraseña diferente. Para las cuentas del sistema de salas de Skype, puede seleccionar la opción la contraseña nunca expira con los siguientes pasos.
  
1. Cree una sesión de Windows Azure Active Directory con sus credenciales de administrador global de inquilinos.
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Establezca la configuración de la contraseña nunca expira para la cuenta de sala del sistema de salas de Skype creada anteriormente mediante el siguiente comando:
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Para obtener más información, consulte [configurar el equipo para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
## <a name="validate"></a>Validar

Para la validación, debe poder usar cualquier cliente de Skype empresarial para iniciar sesión en la cuenta que ha creado.

