---
title: Implementaciones locales de bosque único de Sistema de salas de Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: Lea este tema para obtener información sobre cómo implementar Sistema de salas de Skype en un entorno local de un único bosque.
ms.openlocfilehash: 2d73ee2313088c653f4362139cb431e55d92015b
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775269"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Implementaciones locales de bosque único de Sistema de salas de Skype
 
Lea este tema para obtener información sobre cómo implementar Sistema de salas de Skype en un entorno local de un único bosque.
  
Esta sección proporciona una descripción general de los pasos para aprovisionar la cuenta del sistema de salas de Skype en Exchange Server y en Skype empresarial Server hospedada en una implementación local de bosque único.
  
## <a name="single-forest-on-premises-deployments"></a>Implementaciones locales de un solo bosque

Si ya tiene una cuenta de buzón de recursos para la sala de conferencias, puede usarla. Si no es así, necesitará crear una. Puede usar el Shell de administración de Exchange (PowerShell) o la consola de administración de Exchange para crear una cuenta de buzón de recursos. Le recomendamos que use un buzón de recursos nuevo (eliminar el buzón antiguo y recrear) para el sistema de salas de Skype. Asegúrese de realizar una copia de seguridad de todos los datos del buzón antes de eliminarlo y de exportarlos de nuevo al buzón recién creado con el cliente de Outlook (consulte Exportar o realizar copias de seguridad de mensajes, calendario, tareas y contactos para obtener más información). Para restaurar las reuniones perdidas eliminando el buzón de correo, vea [conectar o restaurar un buzón eliminado](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx). 
  
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
    
3. Configure la cuenta para resolver automáticamente conflictos aceptando o rechazando reuniones. Los usuarios pueden administrar las cuentas de sala de conferencias equipadas con sistemas de salas de Skype, pero ten en cuenta que hasta que la persona acepte una reunión, no aparecerá en el calendario de la pantalla de inicio del sistema de Skype Room.
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   Para ver un conjunto completo de comandos disponibles, consulte Set-CalendarProcessing.
    
   Para recordar a los organizadores de reuniones que hagan una reunión de Skype empresarial en línea en Outlook, ejecute el siguiente comando para configurar una sugerencia para la nueva cuenta: 
    
   ```
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. Use los siguientes comandos para configurar las cadenas localizadas. Si su organización lo requiere, también puede agregar traducciones personalizadas: 
   ```
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. Opcional: configure el texto de aceptación de la reunión que proporciona a los usuarios información sobre el salón de reunión de Skype empresarial y qué puede esperar cuando programe y únase a reuniones. 
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Comprobar la cuenta de buzón de recursos en Active Directory

La cuenta de buzón de la sala de conferencias que creó Exchange en el paso 1 anterior puede ser un objeto de usuario deshabilitado en Active Directory. El sistema de salas de Skype no puede iniciar sesión ni autenticarse mediante la autenticación Kerberos/NTLM si la cuenta está deshabilitada en Active Directory. El cliente del sistema de salas de Skype debe poder autenticarse con los servicios Web de Exchange para recuperar la configuración del calendario y también debe poder enviar correo electrónico con el contenido de la pizarra. 
  
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

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>Habilitar cuentas del sistema de salas de Skype para Skype empresarial

Esta sección proporciona una descripción general de los pasos necesarios para habilitar Skype empresarial en su cuenta de sala de conferencias, que se configurará en el sistema de salas de Skype. 
  
Después de crear una cuenta de buzón de recursos para las salas de conferencias, use el shell de administración de Skype empresarial Server para habilitar las cuentas del sistema de Skype Room para los servicios de Skype empresarial.
  
> [!NOTE]
> En el procedimiento siguiente se supone que ha habilitado la cuenta del sistema de salas de Skype en Active Directory. 
  
1. Ejecute el siguiente comando para habilitar la cuenta del sistema de salas de Skype en un grupo de servidores de Skype empresarial:
    
   ```
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. Opcional: permita que esta cuenta realice y reciba llamadas RTC habilitando la cuenta para telefonía IP empresarial. La telefonía IP empresarial no es necesaria para el sistema de salas de Skype, pero si no lo habilita para telefonía IP empresarial, el cliente del sistema de salas de Skype no podrá proporcionar la función de marcado RTC:
    
   ```
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Si habilita la telefonía IP empresarial para la cuenta de sala de conferencias de sistemas de salas de Skype, asegúrese de configurar una directiva de voz restringida adecuada para su organización. Si el salón de reunión de Skype empresarial es un recurso disponible públicamente, cualquier persona podría usarlo para unirse a una reunión, ya sea programada o ad-hoc. Después de unirse a una reunión, la persona podría aceptar la llamada para unirse a una conferencia de cualquier número. En Skype empresarial Server, la característica de acceso telefónico de las conferencias usa la Directiva de voz del usuario, en este caso, la cuenta de sistema de Skype Room que se usa para unirse a la reunión. En versiones anteriores de Lync Server, se usaba la directiva de voz del organizador. Por lo tanto, si un usuario de una versión anterior de Lync Server programa una sala de reuniones e invita a la sala de reuniones del sistema de salas de Skype, cualquier persona podría usar la sala de reuniones de Skype empresarial para unirse a la reunión y llamar a cualquier teléfono nacional o regional o internacional. número, siempre que el organizador pueda marcar esos números. 
  

