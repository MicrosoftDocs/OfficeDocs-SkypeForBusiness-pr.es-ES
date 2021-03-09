---
title: Habilitar a los usuarios para telefonía IP empresarial en línea y Sistema telefónico en correo de voz
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
description: Obtenga información sobre cómo habilitar los servicios de voz del sistema telefónico para los usuarios de Skype Empresarial.
ms.openlocfilehash: bbcf8b35d91015067943eec2cbe43525e952a7f7
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569362"
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-voicemail"></a>Habilitar a los usuarios para telefonía IP empresarial en línea y Sistema telefónico en correo de voz
 
> [!Important]
> Skype Empresarial Online se retirará el 31 de julio de 2021 después de lo cual el servicio ya no será accesible.  Además, la conectividad RTC entre el entorno local ya no se admite a través de Skype Empresarial Server o Cloud Connector Edition y Skype Empresarial Online.  Obtenga información sobre cómo conectar la red de telefonía local a Teams mediante [enrutamiento directo.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

Obtenga información sobre cómo habilitar los servicios de voz del sistema telefónico para los usuarios de Skype Empresarial.
  
El último paso para implementar el sistema telefónico con conectividad RTC local es habilitar a los usuarios para el sistema telefónico y el correo de voz. Para habilitar estas funcionalidades, debe ser un usuario con el rol Administrador global y poder ejecutar PowerShell remoto. Debe seguir los pasos descritos en este tema para todas las cuentas de usuario que aún no tienen Telefonía IP empresarial para Skype Empresarial Online.
  
## <a name="enable-phone-system-voice-services"></a>Habilitar servicios de voz del sistema telefónico

Para habilitar un usuario para voz del sistema telefónico y correo de voz, deberá realizar algunos pasos iniciales, como comprobar si Skype Empresarial Online Connector se implementa en los servidores y habilitar a los usuarios para el correo de voz hospedado.
  
### <a name="to-enable-your-users-for-phone-system-voice-and-voicemail"></a>Para habilitar a los usuarios para voz y correo de voz del sistema telefónico

> [!NOTE]
> Skype Empresarial Online Connector forma parte actualmente del último módulo de PowerShell de Teams.
> Si usa la versión pública más reciente de PowerShell de [Teams,](https://www.powershellgallery.com/packages/MicrosoftTeams/)no es necesario instalar Skype Empresarial Online Connector.

1. Antes de empezar, compruebe que el módulo de PowerShell de Teams está instalado en los servidores front-end. Si no es así, instale con las instrucciones de Instalación del módulo [de PowerShell de Teams](https://docs.microsoft.com/microsoftteams/teams-powershell-install).
    
2. Inicie Windows PowerShell como administrador.
    
3. Escriba lo siguiente y presione ENTRAR:
    
 ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

  
4. Use el cmdlet Set-CsUser para asignar las propiedades $EnterpriseVoiceEnabled y $HostedVoiceMail a su usuario de la siguiente manera:
    
   ```powershell
   Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    Por ejemplo:
    
   ```powershell
   Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
   ```

    > [!NOTE]
    > También puede especificar un usuario por su dirección SIP, nombre principal de usuario (UPN), nombre de dominio y nombre de usuario (dominio\nombredeusuario) y nombre para mostrar en Active Directory ("Bob Kelly"). 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system"></a>Actualizar el URI de línea y el plan de marcado para los usuarios habilitados para el sistema telefónico

En esta sección se describe cómo actualizar el URI de línea y el plan de marcado para los usuarios habilitados para sistema telefónico. 
  
### <a name="to-update-the-line-uri"></a>Para actualizar el URI de línea

1. Desde una cuenta de usuario asignada al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo de su implementación interna.
    
2. Use el menú Inicio o el acceso directo de escritorio para abrir el Panel de control de Skype Empresarial Server.
    
    > [!NOTE]
    > También puede abrir una ventana del explorador y, a continuación, escribir la dirección URL del administrador para abrir el Panel de control de Skype Empresarial Server. 
  
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.
    
5. En la tabla, haga clic en la cuenta de usuario de Skype Empresarial que desea cambiar el URI de línea.
    
6. Haga **clic en URI** de línea y escriba un número de teléfono único normalizado (por ejemplo, tel:+14255550200). A continuación, haga clic **en Confirmar**.
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>Actualizar el plan de marcado con cmdlets de Windows PowerShell locales

Puede asignar planes de marcado por usuario con Windows PowerShell y el cmdlet [Grant-CsDialPlan.](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) Puede ejecutar este cmdlet desde Skype Empresarial Server 2015 o desde una sesión remota de Windows PowerShell.
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>Para asignar un plan de marcado por usuario a un solo usuario

- Use el cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para asignar el plan de marcado por usuario RedmondDialPlan al usuario Ken Myer:
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>Para asignar un plan de marcado por usuario a varios usuarios

- El siguiente comando asigna el plan de marcado por usuario RedmondDialPlan a todos los usuarios que trabajan en la ciudad de Redmond. Para obtener más información sobre el parámetro LdapFilter usado en este comando, consulte la documentación del cmdlet [Get-CsUser:](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps)
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"
  ```

> [!NOTE]
> Puede usar planes de marcado global o de usuario para los usuarios en línea. Los planes de marcado de sitio no se pueden usar, ya que solo se aplican a usuarios hospedados localmente y asignados a un sitio local. 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>Para desasignación de un plan de marcado por usuario

- Use el cmdlet [Grant-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para desasociar cualquier plan de marcado por usuario asignado anteriormente a Ken Myer. Una vez que el plan de marcado por usuario no está asignado, Ken Myer se administrará automáticamente mediante el plan de marcado global o el plan de marcado de ámbito de servicio asignado a su registrador o puerta de enlace RTC. Un plan de marcado de ámbito de servicio tiene prioridad sobre el plan de marcado global:
    
  ```powershell
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>Actualizar las directivas de enrutamiento de voz con cmdlets Windows PowerShell locales

En esta sección se describe cómo actualizar las directivas de enrutamiento de voz para los usuarios habilitados para el sistema telefónico.
  
Los usuarios del sistema telefónico deben tener asignada una directiva de enrutamiento de voz para que las llamadas se enruten correctamente. Esto difiere de los usuarios locales de voz empresarial que requieren que se les asigne una directiva de voz para permitir que las llamadas se enruten correctamente. La directiva de enrutamiento de voz debe contener usos de RTC que definan las llamadas y rutas autorizadas para los usuarios del sistema telefónico. Puede copiar estos usos de RTC de directivas de voz existentes a nuevas directivas de enrutamiento de voz. Para obtener más información, [vea New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).
  
> [!NOTE]
> A todos los usuarios del sistema telefónico se les asigna la misma directiva de voz en línea denominada BusinessVoice que define las características de llamada permitidas; por ejemplo, Permitir anillo simultáneo. 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>Para asignar una directiva de enrutamiento de voz por usuario a un solo usuario

- Use el cmdlet [Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) para asignar la directiva de enrutamiento de voz por usuario RedmondVoiceRoutingPolicy al usuario Ken Myer:
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>Para asignar una directiva de enrutamiento de voz por usuario a varios usuarios

- El siguiente comando asigna la directiva de enrutamiento de voz por usuario RedmondVoiceRoutingPolicy a todos los usuarios que trabajan en la ciudad de Redmond. Para obtener más información sobre el parámetro LdapFilter usado en este comando, vea [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```powershell
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > Puede usar directivas de enrutamiento de voz global o de usuario para los usuarios en línea. Las directivas de enrutamiento de voz del sitio no se pueden usar, ya que solo se aplican a usuarios hospedados localmente y asignados a un sitio local. 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>Para desasignar una directiva de enrutamiento de voz por usuario

- Use el Grant-CsVoiceRoutingPolicy para desasignar cualquier directiva de enrutamiento de voz por usuario asignada anteriormente a Ken Myer. Una vez que la directiva de enrutamiento de voz por usuario no se asigna, Ken Myer se administrará automáticamente mediante la directiva de enrutamiento de voz global.
    
  ```powershell
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    Para obtener más información, [vea Grant-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).
    

