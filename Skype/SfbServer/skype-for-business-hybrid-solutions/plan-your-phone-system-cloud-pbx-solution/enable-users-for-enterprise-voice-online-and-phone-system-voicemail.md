---
title: Habilitación de usuarios para telefonía IP empresarial en línea y sistemas telefónicos en el correo de voz de Office 365
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Obtenga información sobre cómo habilitar el sistema telefónico en los servicios de voz de Office 365 para sus usuarios de Skype empresarial.
ms.openlocfilehash: 8ed04e3926adfecb2f0022d12c783f6c3e83d763
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780729"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a>Habilitación de usuarios para telefonía IP empresarial en línea y sistemas telefónicos en el correo de voz de Office 365
 
Obtenga información sobre cómo habilitar el sistema telefónico en los servicios de voz de Office 365 para sus usuarios de Skype empresarial.
  
El último paso de la implementación del sistema telefónico en Office 365 con la conectividad RTC local es habilitar a los usuarios para el sistema telefónico en Office 365 y el correo de voz. Para habilitar estas funciones, debe ser un usuario con el rol de administrador global y poder ejecutar PowerShell remoto. Debe seguir los pasos de este tema para todas las cuentas de usuario que todavía no tienen habilitada la telefonía IP empresarial para Skype empresarial online.
  
## <a name="enable-phone-system-in-office-365-voice-services"></a>Habilitar sistema telefónico en los servicios de voz de Office 365

Para habilitar un usuario para el sistema telefónico en Office 365 Voice y el correo de voz, necesitará realizar algunos pasos iniciales, como comprobar si el conector de Skype empresarial online se ha implementado en los servidores y habilitar a los usuarios para el correo de voz hospedado.
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a>Para habilitar a los usuarios para el sistema telefónico en Office 365 voz y correo de voz

1. Antes de empezar, compruebe que el conector de Skype empresarial online (módulo Windows PowerShell) esté implementado en los servidores front-end. Si no lo está, puede descargarlo desde [el centro de descarga](https://www.microsoft.com/download/details.aspx?id=39366). Puede encontrar más información sobre el uso de este módulo en [configurar el equipo para la administración de Skype empresarial online](https://technet.microsoft.com/library/dn362839%28v=ocs.15%29.aspx).
    
2. Inicie Windows PowerShell como administrador.
    
3. Escriba lo siguiente y presione ENTRAR:
    
   ```powershell
   Import-Module skypeonlineconnector
   ```

4. Escriba lo siguiente y presione ENTRAR:
    
   ```powershell
   $cred = Get-Credential
   ```

    Después de presionar entrar, verá el cuadro de diálogo credenciales de Windows PowerShell.
    
5. Escriba su nombre de usuario y contraseña de administrador de inquilinos y haga clic en **Aceptar**.
    
6. En la ventana de PowerShell, escriba lo siguiente y presione ENTRAR:
    
   ```powershell
   $Session = New-CsOnlineSession -Credential $cred -Verbose
   ```

7. Para importar la sesión, escriba el siguiente cmdlet:
    
   ```powershell
   Import-PSSession $Session -AllowClobber
   ```

    Al ejecutar PowerShell en un servidor de Skype empresarial, los cmdlets de Skype empresarial local ya están cargados cuando abre PowerShell. Debe especificar el parámetro-AllowClobber para permitir que los cmdlets en línea sobrescriban los cmdlets locales con el mismo nombre.
    
8. Use el cmdlet Set-CsUser para asignar las propiedades $EnterpriseVoiceEnabled y $HostedVoiceMail a su usuario de la siguiente manera:
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    Por ejemplo:
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > También puede especificar un usuario por su dirección SIP, nombre principal de usuario (UPN), nombre de dominio y nombre de usuario (dominio\nombre de usuario), y nombre para mostrar en Active Directory ("Bob Kelly"). 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a>Actualizar el URI de línea y el plan de marcado para los usuarios habilitados para sistema telefónico en Office 365

En esta sección se describe cómo actualizar el URI de línea y el plan de marcado para los usuarios habilitados para el sistema telefónico en Office 365. 
  
### <a name="to-update-the-line-uri"></a>Para actualizar el URI de línea

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Use el menú Inicio o el acceso directo del escritorio para abrir el panel de control de Skype empresarial Server.
    
    > [!NOTE]
    > También puede abrir una ventana del explorador y, a continuación, escribir la URL del administrador para abrir el panel de control de Skype empresarial Server. 
  
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.
    
5. En la tabla, haga clic en la cuenta de usuario de Skype empresarial cuyo URI de línea desea cambiar.
    
6. Haga clic en **URI de línea**y escriba un número de teléfono único y normalizado (por ejemplo, Tel: + 14255550200). A continuación, haga clic en **confirmar**.
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>Actualizar el plan de marcado con cmdlets locales de Windows PowerShell

Puede asignar planes de marcado por usuario con Windows PowerShell y el cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) . Puede ejecutar este cmdlet desde Skype empresarial Server 2015 o desde una sesión remota de Windows PowerShell.
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>Para asignar un plan de marcado por usuario a un solo usuario

- Use el cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para asignar el plan de marcado por usuario RedmondDialPlan al usuario Ken Myer:
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>Para asignar un plan de marcado por usuario a varios usuarios

- El comando siguiente asigna el plan de marcado por usuario RedmondDialPlan a todos los usuarios que trabajan en la ciudad de Redmond. Para obtener más información sobre el parámetro LdapFilter usado en este comando, consulte la documentación del cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> Puede usar planes de marcado globales o de usuario para usuarios en línea. Los planes de marcado de sitio no se pueden usar porque solo se aplican a los usuarios que están hospedados de forma local y que están asignados a un sitio local. 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>Para cancelar la asignación de un plan de marcado por usuario

- Use el cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para desasignar cualquier plan de marcado por usuario asignado previamente a Ken Myer. Una vez sin asignar el plan de marcado por usuario, Ken Myer se administrará automáticamente mediante el plan de marcado global o el plan de marcado de ámbito de servicio asignado a su registrador o puerta de enlace RTC. Un plan de marcado de ámbito de servicio tiene prioridad sobre el plan de marcado global:
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>Actualizar las directivas de enrutamiento de voz mediante los cmdlets locales de Windows PowerShell

En esta sección se describe cómo actualizar las directivas de enrutamiento de voz para los usuarios habilitados para sistema telefónico en Office 365.
  
Sistema telefónico en Office 365 los usuarios deben tener asignada una directiva de enrutamiento de voz para que las llamadas se enruten correctamente. Esto difiere de los usuarios de voz de empresa locales que requieren que se les asigne una directiva de voz para permitir que las llamadas se enruten correctamente. La Directiva de enrutamiento de voz debe contener usos de RTC que definen las llamadas y rutas autorizadas para sistema telefónico en los usuarios de Office 365. Puede copiar estos usos de RTC de las directivas de voz existentes a las nuevas directivas de enrutamiento de voz. Para obtener más información, vea [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).
  
> [!NOTE]
> Todos los sistemas telefónicos de Office 365 usuarios tienen asignada la misma directiva de voz en línea llamada Businessvoice, que define las características de llamada permitidas; por ejemplo, permitir llamadas simultáneas. 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>Para asignar una directiva de enrutamiento de voz por usuario a un solo usuario

- Use el cmdlet [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) para asignar la Directiva de enrutamiento de voz por usuario RedmondVoiceRoutingPolicy al usuario Ken Myer:
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>Para asignar una directiva de enrutamiento de voz por usuario a varios usuarios

- El comando siguiente asigna la Directiva de enrutamiento de voz por usuario RedmondVoiceRoutingPolicy a todos los usuarios que trabajan en la ciudad de Redmond. Para obtener más información sobre el parámetro LdapFilter usado en este comando, consulte [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > Puede usar directivas de enrutamiento de voz globales o de usuario para los usuarios en línea. No se pueden usar las directivas de enrutamiento de voz del sitio, ya que solo se aplican a los usuarios hospedados de forma local y que están asignados a un sitio local. 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>Para quitar la asignación de una directiva de enrutamiento de voz por usuario

- Use Grant-CsVoiceRoutingPolicy para desasignar cualquier directiva de enrutamiento de voz por usuario asignada previamente a Ken Myer. Una vez no asignada la Directiva de enrutamiento de voz por usuario, Ken Myer se administrará automáticamente mediante la Directiva de enrutamiento de voz global.
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    Para obtener más información, consulte [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).
    

