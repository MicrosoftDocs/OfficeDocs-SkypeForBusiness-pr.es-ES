---
title: Permitir que los usuarios de Telefonía IP empresarial en línea y sistema de teléfono en el correo de voz de Office 365
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 9/25/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 28daebcb-c2dc-4338-b2d1-04345ece9c19
description: Aprenda a habilitar sistema de teléfono de servicios de voz de Office 365 para su Skype para usuarios de negocios.
ms.openlocfilehash: 72c3ea49394fd1b7d25b041a0f4423639753b523
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="enable-users-for-enterprise-voice-online-and-phone-system-in-office-365-voicemail"></a>Permitir que los usuarios de Telefonía IP empresarial en línea y sistema de teléfono en el correo de voz de Office 365
 
Aprenda a habilitar sistema de teléfono de servicios de voz de Office 365 para su Skype para usuarios de negocios.
  
El último paso en la implementación de sistema de teléfono en Office 365 con conectividad de RTC local es permitir a los usuarios para el sistema de teléfono en Office 365 y correo de voz. Para habilitar estas funciones, tiene que ser un usuario con el rol de administrador global de Office 365 y ser capaz de ejecutar PowerShell remoto. Solo tiene que seguir los pasos que se indican en este tema para las cuentas de usuario que no tengan habilitada la telefonía IP empresarial para Skype Empresarial Online.
  
## <a name="enable-phone-system-in-office-365-voice-services"></a>Habilitar sistema de teléfono de servicios de voz de Office 365

Para habilitar a un usuario para el sistema de teléfono de voz de Office 365 y correo de voz, deberá realizar algunos pasos iniciales, como comprobar para ver de la Skype para Business Connector en línea se implementa en los servidores y permitir a los usuarios de correo de voz hospedado.
  
### <a name="to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail"></a>Para permitir a los usuarios para el sistema de teléfono en el correo de voz y voz de Office 365

1. Antes de comenzar, compruebe que se ha implementado el Skype para Business Connector en línea (módulo de Windows PowerShell) en los servidores frontales. Si no es así, puede descargarlo desde [el centro de descarga](https://www.microsoft.com/en-us/download/details.aspx?id=39366). Puede encontrar más información acerca del uso de este módulo en [Configurar el equipo para Skype para la administración de negocios en línea](https://technet.microsoft.com/en-us/library/dn362839%28v=ocs.15%29.aspx).
    
2. Inicie Windows PowerShell como un administrador.
    
3. Escriba lo siguiente y presione Entrar:
    
  ```
  Import-Module skypeonlineconnector
  ```

4. Escriba lo siguiente y presione Entrar:
    
  ```
  $cred = Get-Credential
  ```

    Después de presionar ENTRAR, verá el cuadro de diálogo Credenciales de Windows PowerShell.
    
5. Escriba el nombre de usuario y la contraseña del administrador del inquilino y, después, haga clic en **Aceptar**.
    
6. En la ventana de la PowerShell, escriba lo siguiente y presione Entrar:
    
  ```
  $Session = New-CsOnlineSession -Credential $cred -Verbose
  ```

7. Escriba el siguiente cmdlet para importar la sesión:
    
  ```
  Import-PSSession $Session -AllowClobber
  ```

    Al ejecutar PowerShell en un Skype para Business Server, el local Skype para cmdlets de negocio ya se cargan al abrir PowerShell. Debe especificar el parámetro - AllowClobber para permitir que los cmdlets en línea sobrescribir los cmdlets local con el mismo nombre.
    
8. Use el cmdlet Set-CsUser para asignar las propiedades $EnterpriseVoiceEnabled y $HostedVoiceMail a su usuario del siguiente modo:
    
  ```
  Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
  ```

    Por ejemplo:
    
  ```
  Set-CsUser -Identity "Bob Kelly" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
  ```

    > [!NOTE]
    > También puede especificar un usuario por su dirección SIP, nombre principal de usuario (UPN), nombre de dominio y nombre de usuario (dominio\nombre de usuario), y nombre para mostrar en Active Directory ("Guillermo Rodarte"). 
  
## <a name="update-the-line-uri-and-dial-plan-for-users-enabled-for-phone-system-in-office-365"></a>Actualizar el URI de la línea y marcar el plan para los usuarios habilitados para el sistema telefónico en Office 365

En esta sección se describe cómo actualizar el URI de la línea y marcar el plan para los usuarios habilitados para el sistema telefónico en Office 365. 
  
### <a name="to-update-the-line-uri"></a>Para actualizar el URI de línea

1. Desde una cuenta de usuario que se asigne al rol CsUserAdministrator o CsAdministrator, inicie sesión en cualquier equipo en la implementación interna.
    
2. Use el menú Inicio o un acceso directo en el escritorio para abrir el Panel de control de Skype Empresarial Server.
    
    > [!NOTE]
    > También puede abrir una ventana del explorador y, después, escribir la URL del administrador para abrir el Panel de control de Skype Empresarial Server. 
  
3. En la barra de navegación izquierda, haga clic en **Usuarios**.
    
4. En el cuadro **Buscar usuarios**, escriba la primera parte del nombre para mostrar, el nombre, los apellidos, el nombre de la cuenta del Administrador de cuentas de seguridad (SAM), la dirección SIP o el identificador uniforme de recursos (URI) de línea de la cuenta de usuario que desee habilitar y, a continuación, haga clic en **Buscar**.
    
5. En la tabla, haga clic en la cuenta de usuario de Skype Empresarial cuyo URI de línea quiera cambiar.
    
6. Haga clic en **URI de línea** y escriba un número de teléfono único y normalizado (por ejemplo, tel:+14255550200). Después, haga clic en **Confirmar**.
    
## <a name="update-the-dial-plan-using-on-premises-windows-powershell-cmdlets"></a>Actualizar el plan de marcado con cmdlets locales de Windows PowerShell

Puede asignar planes de marcado con Windows PowerShell y el cmdlet [CsDialPlan de concesión](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) por usuario. Este cmdlet se puede ejecutar desde el Skype para Business Server 2015 o desde una sesión remota de Windows PowerShell.
  
### <a name="to-assign-a-per-user-dial-plan-to-a-single-user"></a>Para asignar un plan de marcado por usuario a un único usuario

- Utilice el cmdlet [Grant CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para asignar el plan de marcado por el usuario RedmondDialPlan al usuario Ken Myer:
    
  ```
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName "RedmondDialPlan"
  ```

### <a name="to-assign-a-per-user-dial-plan-to-multiple-users"></a>Para asignar un plan de marcado por usuario a varios usuarios

- El siguiente comando asigna el plan de marcado por usuario RedmondDialPlan a todos los usuarios que trabajen en la ciudad de Redmond. Para obtener más información sobre el parámetro filtroLDAP utilizado en este comando, consulte la documentación para el cmdlet [Get-CsUser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) :
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsDialPlan -PolicyName "RedmondDialPlan"

  ```

> [!NOTE]
> Puede utilizar planes de marcado globales o por usuario para los usuarios en línea. Los planes de marcado de sitio no se pueden usar ya que solo se aplican a los usuarios hospedados en una implementación local y se asignan a un sitio local. 
  
### <a name="to-unassign-a-per-user-dial-plan"></a>Para quitar la asignación de un plan de marcado por usuario

- Use el cmdlet de [Concesión CsDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-csdialplan?view=skype-ps) para desasignar cualquier plan de acceso telefónico por usuario asignado previamente a Ken Myer. Una vez que se ha cancelado la asignación del plan de marcado por usuario, el usuario Ken Myer se administrará automáticamente mediante el plan de marcado global o el plan de marcado de ámbito de servicio asignado a su registrador o a su puerta de enlace RTC. Los planes de marcado de ámbito de servicio tienen prioridad sobre el plan de marcado global:
    
  ```
  Grant-CsDialPlan -Identity "Ken Myer" -PolicyName $Null
  ```

## <a name="update-the-voice-routing-policies-using-on-premises-windows-powershell-cmdlets"></a>Actualizar las directivas de enrutamiento de voz con cmdlets locales de Windows PowerShell

En esta sección se describe cómo actualizar las directivas de enrutamiento de voz para los usuarios habilitados para el sistema telefónico en Office 365.
  
Sistema de teléfono de los usuarios de Office 365 debe tener una directiva de enrutamiento de voz asignados para enrutar correctamente las llamadas. Esto difiere de los usuarios de telefonía empresarial local que deben tener una directiva de voz asignada para permitir que las llamadas se enruten correctamente. La directiva de enrutamiento de voz debe contener usos PSTN que definen llamadas autorizadas y rutas para el sistema telefónico de los usuarios de Office 365. Puede copiar estos usos de RTC de las directivas de voz existentes a las nuevas directivas de enrutamiento de voz. Para obtener más información, consulte [CsVoiceRoutingPolicy de nuevo](https://docs.microsoft.com/powershell/module/skype/new-csvoiceroutingpolicy?view=skype-ps).
  
> [!NOTE]
> Todos los sistema de teléfono de los usuarios de Office 365 se asignan la misma directiva de voz en línea denominado BusinessVoice que define las características de llamada permitidas; Por ejemplo, permitir llamadas simultáneas. 
  
### <a name="to-assign-a-per-user-voice-routing-policy-to-a-single-user"></a>Para asignar una directiva de enrutamiento de voz por usuario a un solo usuario

- Utilice el cmdlet [Grant CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps) para asignar la directiva de enrutamiento de voz RedmondVoiceRoutingPolicy por el usuario para el usuario Ken Myer:
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName "RedmondVoiceRoutingPolicy"
  ```

### <a name="to-assign-a-per-user-voice-routing-policy-to-multiple-users"></a>Para asignar una directiva de enrutamiento de voz por usuario a varios usuarios

- El siguiente comando permite asignar la directiva de enrutamiento de voz por usuario RedmondVoiceRoutingPolicy a todos los usuarios que trabajan en la ciudad de Redmond. Para obtener más información sobre el parámetro filtroLDAP utilizado en este comando, consulte [Get-Csusuario](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps).
    
  ```
  Get-CsUser -LdapFilter "l=Redmond" | Grant-CsVoiceRoutingPolicy -PolicyName "RedmondVoiceRoutingPolicy"
  ```

    > [!NOTE]
    > Puede utilizar directivas de enrutamiento de voz globales o por usuario para usuarios en línea. Las directivas de enrutamiento de voz de sitio no se pueden usar, ya que solo se aplican a los usuarios hospedados en una implementación local y se asignan a un sitio local. 
  
### <a name="to-unassign-a-per-user-voice-routing-policy"></a>Para desasignar una directiva de enrutamiento de voz por usuario

- Utilice la CsVoiceRoutingPolicy de concesión para desasignar cualquier directiva de enrutamiento de voz por usuario asignado previamente a Ken Myer. Después de cancelar la asignación de la directiva de enrutamiento de voz por usuario, el usuario Ken Myer se administrará automáticamente mediante la directiva de enrutamiento de voz global.
    
  ```
  Grant-CsVoiceRoutingPolicy -Identity "Ken Myer" -PolicyName $Null
  ```

    Para obtener más información, consulte [CsVoiceRoutingPolicy en la concesión](https://docs.microsoft.com/powershell/module/skype/grant-csvoiceroutingpolicy?view=skype-ps).
    

