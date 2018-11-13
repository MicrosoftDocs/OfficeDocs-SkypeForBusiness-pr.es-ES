---
title: Aprovisionamiento de cuentas del Sistema de salas de Skype en Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Lea este tema para obtener información acerca del aprovisionamiento de cuentas de Sistema de salas de Skype en Office 365.
ms.openlocfilehash: 74512be2d097ca5f43fbd6a22ff17bba8040dd36
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295452"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a>Aprovisionamiento de cuentas del Sistema de salas de Skype en Office 365
 
Lea este tema para obtener información acerca del aprovisionamiento de cuentas de Sistema de salas de Skype en Office 365.
  
En la siguiente sección, se explica la cuenta del sistema de salas de Skype aprovisionamiento para un inquilino de Office 365.
  
## <a name="office-365-prerequisites"></a>Requisitos previos de Office 365

El inquilino en línea debe cumplir los siguientes requisitos:
  
- El plan de Office 365 debe incluir Skype para 2 Plan en línea de negocio, o Office 365 E1, E3 o E5. <br/>Para obtener información detallada en Skype para planes de negocios de en línea, vea la [Skype para la descripción de servicio en línea de negocio](https://technet.microsoft.com/library/jj822172.aspx).
    
- El inquilino debe tener la capacidad de conferencia de Skype para la empresa habilitado.
    
- El inquilino debe tener Exchange Online habilitado. 
    
- El administrador remoto del inquilino debe tener el siguiente acceso a PowerShell:
    
  - Acceso remoto a PowerShell de Exchange
    
  - Skype para el acceso de PowerShell remoto en línea de negocio
    
  - Windows Azure Active Directory módulo para Windows PowerShell para acceso al directorio de acceso a Office 365
    
Para la cuenta de Salas de Skype, se necesita la siguiente licencia:
  
- Se requiere un Skype para profesionales Online Plan 2 o Office 365 E1 o E3 licencia para habilitar las reuniones de Skype.
    
- Para dar derecho a la sala con la capacidad de Enterprise Voice, por lo que se puede habilitar la sala con un número de teléfono, un Skype para Online Plan 2 de negocio con la licencia del sistema de teléfono o E5 de Office 365 es necesaria (1).
    
- Si necesita capacidades de marcado de una reunión, necesitará una conferencia de audio y la licencia del sistema telefónico.  Si necesita las capacidades de acceso telefónico de salida de una reunión, necesitará un nacionales o nacional e internacional de llamada Plan. 
    
- No se necesita una licencia de Exchange Online para la cuenta de Salas de Skype porque la cuenta debería configurarse como una cuenta de buzón del recurso.
    
## <a name="provisioning-overview"></a>Información general de aprovisionamiento

En el siguiente diagrama proporciona una visión general de la cuenta del sistema de salas de Skype aprovisionamiento flujo en Office 365.
  
![Pasos de aprovisionamiento del sistema de salas de Skype para O365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a>Identificar una nueva sala de conferencias

Es posible que ya tiene un buzón de sala de recursos de Exchange que proporciona la característica de programación, o puede crear un buzón de recursos por primera vez facilitar la implementación del sistema de salas de Skype. En cualquier caso, debe identificar una cuenta de sala para que la use el inquilino. El aprovisionamiento de Exchange Online y Skype para las secciones de aprovisionamiento de negocio proporcionan instrucciones para ambos tipos de cuentas. Por ejemplo, supongamos que tiene los siguientes dos salas y que le gustaría implementar del sistema de sala de Skype para ambos tipos de ellos:
  
- Cuenta existente de buzón de recursos: confrm1@contoso.onmicrosoft.com
    
- Cuenta nueva de buzón de recursos: confrm2@contoso.onmicrosoft.com
    
## <a name="exchange-online-provisioning"></a>Aprovisionamiento de Exchange Online

En primer lugar, se conecte a Exchange Online PowerShell siguiendo las instrucciones que aparecen en el tema, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).
  
Para establecer una cuenta de buzón de sala de recurso existente de Skype salón de sistema, ejecute los siguientes comandos en Exchange Online PowerShell:
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Para crear una nueva cuenta de buzón de recursos de Exchange para el sistema de sala de Skype, ejecute los siguientes comandos en Exchange Online PowerShell:
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

Los comandos anteriores configuración o creación una nueva cuenta de buzón de recursos de Exchange para uso del sistema de salas de Skype mediante la habilitación de la cuenta.
  
Después de crear el buzón de correo, puede usar el cmdlet Set-CalendarProcessing en Exchange Online PowerShell para configurar el buzón de correo. Haga referencia a los pasos 3 a 6 en implementaciones locales de bosque único para obtener más información.

## <a name="assigning-a-skype-for-business-online-license"></a>Asignar una licencia de Skype Empresarial Online

Ahora puede asignar un Skype para profesionales Online (Plan 2) o de Skype para licencia empresarial en línea (planeación de 3) mediante el portal administrativo de Office 365, tal como se describe en [asignar o quitar licencias de Office 365 para profesionales](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) o en [Skype para el complemento de Business concesión de licencias](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7). 
  
Después de asignar una licencia de Skype para profesionales en línea, podrá iniciar sesión y validar que la cuenta está activa con cualquier Skype para clientes empresariales.
  
## <a name="skype-for-business-online-provisioning"></a>Aprovisionamiento de Skype Empresarial Online

Después de una sala de recurso se ha creado y habilitado tal y como se ha mostrado anteriormente cuenta de buzón de correo y la cuenta tiene licencia para Skype para profesionales en línea la cuenta se sincronizarán desde el bosque de Exchange Online a Skype para el bosque en línea de negocio mediante la Bosque de Active Directory de Windows Azure. Los siguientes pasos son necesarios para aprovisionar la cuenta del sistema de salas de Skype en el Skype para un grupo de servidores en línea de negocio. Estos pasos son los mismos para una cuenta de buzón de recursos existente o una cuenta recién creada (confrm1 o confrm2), porque una vez que están habilitados en Exchange Online, ambas cuentas se sincronizarán con Skype para profesionales en línea de la misma manera:
  
1. Cree una sesión remota de PowerShell. Tenga en cuenta que necesitará descargar Skype para el módulo del conector de negocio en línea y Microsoft Asistente en línea de servicios de inicio de sesión y asegúrese de que el equipo está configurado. Para obtener más información, vea [Configurar el equipo de Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. Para habilitar una cuenta de sistema de salas de Skype para Skype para la empresa, ejecute el siguiente comando:
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    Puede obtener el RegistrarPool devuelve la dirección donde están hospedados su Skype para los usuarios empresariales de una de las cuentas existentes mediante el comando siguiente para esta propiedad:
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

  
## <a name="password-expiration"></a>Caducidad de la contraseña

En Office 365, la directiva de caducidad de la contraseña predeterminada de todas las cuentas de usuario es de 90 días a no ser que configure una directiva de caducidad de la contraseña diferente. Para las cuentas del sistema de salas de Skype, puede seleccionar la contraseña nunca caduca configuración con los siguientes pasos.
  
1. Cree una sesión en Windows Azure Active Directory mediante el uso de las credenciales de administrador global de inquilinos.
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. Establecer la contraseña nunca caduca la configuración de la cuenta de sala del sistema de salas de Skype creada anteriormente mediante el comando siguiente:
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

Para obtener más información, vea [Configurar el equipo de Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
## <a name="validate"></a>Validar

Para la validación, debe usar cualquier Skype para clientes empresariales para iniciar sesión en la cuenta que creó.

