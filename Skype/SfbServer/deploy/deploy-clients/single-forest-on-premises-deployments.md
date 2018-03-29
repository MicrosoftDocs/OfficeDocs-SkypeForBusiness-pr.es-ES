---
title: Implementaciones locales de bosque único de Sistema de salas de Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/4/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: Lea este tema para obtener información sobre cómo implementar Sistema de salas de Skype en un entorno local de un único bosque.
ms.openlocfilehash: b998c0b1e139951297eca8a963536dd59dcd4b39
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Implementaciones locales de bosque único de Sistema de salas de Skype
 
Lea este tema para obtener información sobre cómo implementar Sistema de salas de Skype en un entorno local de un único bosque.
  
Esta sección proporciona una visión general de los pasos para el aprovisionamiento de la cuenta de sistema del sitio de Skype en Exchange Server y Skype para Business Server alojado en una implementación local de bosque único.
  
## <a name="single-forest-on-premises-deployments"></a>Implementaciones locales de un solo bosque

Si ya tiene una cuenta de buzón de recursos para la sala de conferencias, puede usarla. Si no es así, necesitará crear una. Puede usar el Shell de administración de Exchange (PowerShell) o la consola de administración de Exchange para crear una cuenta de buzón de recursos. Se recomienda usar un nuevo (eliminar el buzón antiguo y volver a crear) el buzón de recursos para el sistema de sala de Skype. Asegúrese de realizar una copia de seguridad de todos los datos del buzón antes de eliminarlo y de exportarlos de nuevo al buzón recién creado con el cliente de Outlook (consulte Exportar o realizar copias de seguridad de mensajes, calendario, tareas y contactos para obtener más información). Para restaurar las reuniones perdidas por eliminar el buzón, consulte [Conectar o restaurar un buzón eliminado](https://technet.microsoft.com/en-us/library/jj863438%28v=exchg.150%29.aspx). 
  
Para usar una cuenta de buzón de recursos (por ejemplo, LRS-01), siga los siguientes pasos:
  
1. Ejecute el siguiente comando de PowerShell de administración de Exchange:
    
  ```
  Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
  ```

2. Si planea crear un nuevo buzón para una organización de Exchange local de un solo bosque, ejecute el siguiente comando:
    
  ```
  New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
  ```

  En el ejemplo anterior se crea una cuenta de usuario habilitada en Active Directory y un buzón de sala para una sala de conferencia en una organización de Exchange local. El parámetro RoomMailboxPassword especifica la contraseña para la cuenta de usuario.
    
3. Configure la cuenta para resolver automáticamente conflictos aceptando o rechazando reuniones. Sala de conferencias de equipado con sistema de sala de cuentas de Exchange pueden administrarse por individuos, pero tenga en cuenta que hasta que la persona acepta una reunión no aparecerá en el calendario de la pantalla de inicio de sistema de sala de Skype de Skype.
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   Para ver un conjunto completo de comandos disponibles, consulte Set-CalendarProcessing.
    
   Para recordar a los organizadores de la reunión para realizar la reunión un Skype en línea para la reunión de negocios en Outlook, ejecute el siguiente comando para configurar un sugerencias de correo electrónico para la nueva cuenta: 
    
   ```
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. Use los siguientes comandos para configurar las cadenas localizadas. Si su organización lo requiere, también puede agregar traducciones personalizadas: 
   ```
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. Opcional: Configurar reunión, aceptación que proporciona a los usuarios información acerca de Skype para salas de reuniones de negocios y lo que puede esperar al programar y unirse a reuniones. 
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Comprobar la cuenta de buzón de recursos en Active Directory

La cuenta de buzón de la sala de conferencias que creó Exchange en el paso 1 anterior puede ser un objeto de usuario deshabilitado en Active Directory. Sistema de sala de Skype no puede iniciar sesión o autenticar mediante la autenticación Kerberos o NTLM si la cuenta está deshabilitada en Active Directory. El cliente del sistema de sala de Skype debe ser capaz de autenticarse en servicios Web de Exchange para recuperar la configuración de calendario y también debe ser capaz de enviar correo electrónico con el contenido de la Pizarra. 
  
Por lo tanto, si la cuenta está deshabilitada, debe habilitarla en Active Directory siguiendo estos pasos: 
  
1. En Active Directory, ejecute el siguiente comando para habilitar el inicio de sesión de la cuenta: 
    
   ```
   Set-ADAccountPassword -Identity LRS01
   ```

   Cuando ejecute este comando, se le solicitará que escriba la contraseña actual y que vuelva a escribirla una segunda vez para confirmarla.
    
2. Una vez que haya establecido la contraseña, ejecute el siguiente comando para habilitar la cuenta: 
    
   ```
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>Habilitar sistema de sala de Skype cuentas de Skype para empresas

Esta sección proporciona una visión general de los pasos necesarios para habilitar Skype para empresas para su cuenta de sala de conferencia, que estará configurada en el sistema del sitio de Skype. 
  
Después de crear una cuenta de buzón de recursos para las salas de conferencias, usar Skype para negocios de Shell de administración de servidor para habilitar cuentas de sistema del sitio de Skype para Skype para servicios de negocios.
  
> [!NOTE]
> El procedimiento siguiente asume que ha habilitado la cuenta de sistema del sitio de Skype en Active Directory. 
  
1. Ejecute el siguiente comando para habilitar la cuenta de sistema del sitio de Skype en un Skype para grupo Business Server:
    
   ```
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. Opcional: permita que esta cuenta realice y reciba llamadas RTC habilitando la cuenta para telefonía IP empresarial. No es necesario para el sistema de sala de Skype de Telefonía IP empresarial, pero si no se habilita para Telefonía IP empresarial, no podrá el cliente del sistema de sala de Skype proporcionar la funcionalidad de marcado PSTN:
    
   ```
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true

   ```

> [!NOTE]
> Si habilita la Telefonía IP empresarial para la cuenta de sistema del sitio de Skype conferencias sala, asegúrese de configurar una directiva de voz restringido adecuado para su organización. Si el Skype para salas de reuniones de negocios es un recurso disponible públicamente, cualquier persona podría utilizar para unirse a una reunión, programada o ad hoc. Después de unirse a una reunión, la persona podría aceptar la llamada para unirse a una conferencia de cualquier número. En Skype para Business Server, el acceso telefónico de salida de la función de conferencias utiliza la voz del usuario, en este caso utiliza la cuenta de sistema del sitio de Skype para unirse a la reunión. En versiones anteriores de Lync Server, se usaba la directiva de voz del organizador. Por lo tanto, si un usuario de una versión anterior de Lync Server programa una sala de reuniones y se invita a la cuenta de sistema del sitio de Skype sala, cualquier persona podría utilizar el Skype para salas de reuniones de negocios para unirse a la reunión y puede marcar cualquier número de teléfono nacionales, regionales o internacional número, siempre que el organizador puede marcar esos números. 
  

