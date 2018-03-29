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
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a>Aprovisionamiento de cuentas del Sistema de salas de Skype en Office 365
 
Lea este tema para obtener información acerca del aprovisionamiento de cuentas de Sistema de salas de Skype en Office 365.
  
La sección siguiente trata la cuenta de sistema del sitio de Skype provisioning para un arrendatario de Office 365.
  
## <a name="office-365-prerequisites"></a>Requisitos previos de Office 365

El inquilino en línea debe cumplir los siguientes requisitos:
  
- El plan de Office 365 debe incluir Skype negocio Online Plan 2, Plan 3, Office 365 E1, E3 o E5.
    
- El arrendatario debe tener la capacidad de conferencia de Skype para empresas habilitadas.
    
- El inquilino debe tener Exchange Online habilitado. 
    
- El administrador remoto del inquilino debe tener el siguiente acceso a PowerShell:
    
  - Acceso remoto a PowerShell de Exchange
    
  - Skype para acceso de PowerShell remoto de negocios en línea
    
  - Windows Azure Active Directory módulo para Windows PowerShell para acceso al directorio de acceso a Office 365
    
Para la cuenta de Salas de Skype, se necesita la siguiente licencia:
  
- Un Skype para negocios Online Plan 2 o Office 365 E1 o E3 licencia es necesaria para habilitar reuniones de Skype.
    
- Para dar derecho a la sala, con la capacidad de Telefonía IP empresarial para que la sala se puede habilitar con un número de teléfono, un Skype para negocios Online Plan 2 con el complemento de PBX de nube o Office 365 E5 es necesaria (1).
    
- La disponibilidad de autorización de las conferencias RTC en una reunión concreta se determina mediante la licencia del organizador de la reunión.
    
- No se necesita una licencia de Exchange Online para la cuenta de Salas de Skype porque la cuenta debería configurarse como una cuenta de buzón del recurso.
    
## <a name="provisioning-overview"></a>Información general de aprovisionamiento

El siguiente diagrama proporciona una visión general de la cuenta de sistema del sitio de Skype aprovisionamiento flujo en Office 365.
  
![Pasos de aprovisionamiento del sistema de salas de Skype para O365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Identificar una nueva sala de conferencias

Es posible que tenga un buzón de sala de recursos de Exchange que proporciona la función de programación, o que desee crear un buzón de recursos por primera vez facilitar la implementación de sistema de sala de Skype. En cualquier caso, debe identificar una cuenta de sala para que la use el inquilino. La provisión en línea de Exchange y Skype para secciones de provisión de negocios proporcionan orientación para ambos tipos de cuentas. Por ejemplo, supongamos que tiene las siguientes dos salas, y que le gustaría implementar sistema de sala de Skype para ambos:
  
- Cuenta existente de buzón de recursos: confrm1@contoso.onmicrosoft.com
    
- Cuenta nueva de buzón de recursos: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Aprovisionamiento de Exchange Online

En primer lugar, conectarse a Exchange Online PowerShell siguiendo las instrucciones en el tema, [conectarse a Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
  
Para establecer una cuenta de buzón de sala de recursos existente para el sistema del sitio de Skype, ejecute los siguientes comandos de PowerShell en línea de Exchange:
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Para crear una nueva cuenta de buzón de recursos de Exchange para el sistema del sitio de Skype, ejecute los siguientes comandos de PowerShell en línea de Exchange:
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Los comandos anteriores configurar o crean una nueva cuenta de buzón de recursos de Exchange para uso del sistema de sala de Skype habilitando la cuenta.
  
Después de crear el buzón, puede utilizar el cmdlet Set-CalendarProcessing de PowerShell en línea de Exchange para configurar el buzón. Haga referencia a los pasos 3 a 6 en implementaciones locales de bosque único para obtener más información.
  
## <a name="skype-for-business-online-provisioning"></a>Aprovisionamiento de Skype Empresarial Online

Después de haber creado una cuenta de buzón de la sala de recurso y habilitado como se mostró anteriormente, la cuenta se sincronizará desde el bosque de Exchange Online a Skype para el bosque del negocio en línea utilizando el bosque de Active Directory de Windows Azure. Los pasos siguientes son necesarios para proporcionar la cuenta de sistema del sitio de Skype en el Skype para grupo de negocios en línea. Estos pasos son los mismos para una cuenta de buzón de recursos existente o una cuenta recién creada (confrm1 o confrm2), porque una vez que están habilitados en Exchange Online, ambas cuentas se sincronizarán con Skype para los negocios en línea de la misma manera:
  
1. Cree una sesión remota de PowerShell. Tenga en cuenta que necesitará descargar Skype para el módulo del conector de negocios en línea y Asistente Microsoft Online Services inicio de sesión y asegúrese de que su equipo está configurado. Para obtener más información, consulte [Configuración del equipo para la administración de Lync Online](http://technet.microsoft.com/library/bca143e2-659a-4161-9220-59ffd9fc2874.aspx).
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. Para habilitar una cuenta de sistema del sitio de Skype de Skype para empresas, ejecute el siguiente comando:
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Puede obtener el RegistrarPool devuelve la dirección donde están alojados su Skype para usuarios profesionales de una de las cuentas existentes mediante el comando siguiente para esta propiedad:
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

## <a name="assigning-a-skype-for-business-online-license"></a>Asignar una licencia de Skype Empresarial Online

Después de habilitar una cuenta de sistema del sitio de Skype en Skype para el negocio, puede asignar un Skype para los negocios en línea (Plan 2) o Skype para licencia de negocios en línea (Plan 3) a través del portal de administración de Office 365 como se describe en [asignar o quitar licencias para Office 365 para el negocio](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) o en [Skype para Business licensing del complemento](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7). 
  
Después de asignar una licencia de Skype para los negocios en línea, podrá iniciar sesión y validar que la cuenta está activa utilizando cualquier Skype para cliente de empresa.
  
## <a name="password-expiration"></a>Caducidad de la contraseña

En Office 365, la directiva de caducidad de la contraseña predeterminada de todas las cuentas de usuario es de 90 días a no ser que configure una directiva de caducidad de la contraseña diferente. Para las cuentas de sistema del sitio de Skype, puede seleccionar la contraseña nunca caduca opción con los pasos siguientes.
  
1. Cree una sesión en Windows Azure Active Directory mediante el uso de las credenciales de administrador global de inquilinos.
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Establecer la contraseña nunca caduca la configuración de la cuenta de la sala de sistema de sala de Skype creada previamente mediante el comando siguiente:
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Para obtener más información, consulte [Uso de Windows PowerShell para administrar Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).
  

