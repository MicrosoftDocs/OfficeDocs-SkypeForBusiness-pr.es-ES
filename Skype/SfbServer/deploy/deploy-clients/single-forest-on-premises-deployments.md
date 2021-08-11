---
title: Skype Implementaciones locales de bosque único del sistema de sala
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
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: Lea este tema para obtener información sobre cómo implementar Skype room system en un único bosque entorno local.
ms.openlocfilehash: 9244ceca231142757a2a82f140b6d17613486117a86af6d6c9248e5a106a958f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "54312108"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a>Skype Implementaciones locales de bosque único del sistema de sala
 
Lea este tema para obtener información sobre cómo implementar Skype room system en un único bosque entorno local.
  
En esta sección se proporciona información general sobre los pasos para aprovisionar la cuenta del sistema de sala de Skype en Exchange Server y Skype Empresarial Server hospedados en una implementación local de un solo bosque.
  
## <a name="single-forest-on-premises-deployments"></a>Implementaciones locales de un solo bosque

Si ya tiene una cuenta de buzón de recursos para la sala de conferencias, puede usarla. De lo contrario, tendrá que crear uno nuevo. Puede usar el Shell Exchange administración (PowerShell) o Consola de administración de Exchange para crear una nueva cuenta de buzón de recursos. Se recomienda usar un buzón de recursos nuevo (eliminar buzón antiguo y volver a crear) para Skype room system. Asegúrese de hacer una copia de seguridad de los datos del buzón antes de eliminarlos y, a continuación, volver a exportarlos al buzón de correo creado de nuevo con el cliente de Outlook (vea Exportar o hacer una copia de seguridad de mensajes, calendario, tareas y contactos para obtener más información). Para restaurar las reuniones perdidas mediante la eliminación del buzón de correo, vea [Conectar o restaurar un buzón eliminado](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help). 
  
Para usar una cuenta de buzón de recursos existente (por ejemplo, LRS-01) siga los pasos siguientes:
  
1. Ejecute el siguiente comando Exchange PowerShell de administración:
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. Si tiene previsto crear un nuevo buzón, ejecute el siguiente comando para un único bosque local Exchange organización:
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   En el ejemplo anterior se crea una cuenta de usuario habilitada en Active Directory y un buzón de sala para una sala de conferencias en una organización Exchange local. El parámetro RoomMailboxPassword especifica la contraseña de la cuenta de usuario.
    
3. Configure la cuenta para resolver automáticamente conflictos aceptando o rechazando reuniones. Skype Las cuentas de salas de conferencias equipadas con el sistema en Exchange pueden ser administradas por individuos, pero tenga en cuenta que hasta que el individuo acepte una reunión no aparecerá en el calendario de la pantalla principal del sistema de salas de Skype.
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   Para obtener un conjunto completo de comandos disponibles, vea Set-CalendarProcessing.
    
   Para recordar a los organizadores de la reunión que hagan de la reunión una reunión Skype Empresarial en línea en Outlook, ejecute el siguiente comando para configurar una sugerencia de correo electrónico para la nueva cuenta: 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. Use los siguientes comandos para configurar cadenas localizadas. Si la organización lo requiere, también puede agregar traducciones personalizadas: 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. Opcional: configure el texto de aceptación de reuniones que proporciona a los usuarios información sobre Skype Empresarial Sala de reuniones y qué esperar cuando programan y se unen a reuniones. 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a>Comprobar cuenta de buzón de recursos en Active Directory

La cuenta de buzón de sala de conferencia creada Exchange en el paso 1 anterior puede ser un objeto de usuario deshabilitado en Active Directory. Skype El sistema de sala no puede iniciar sesión ni autenticarse mediante la autenticación Kerberos/NTLM si la cuenta está deshabilitada en Active Directory. El Skype del sistema de sala de Exchange debe poder autenticarse en Exchange Web Services para recuperar la configuración del calendario y también debe poder enviar correo electrónico con contenido de pizarra. 
  
Por lo tanto, si la cuenta está deshabilitada, debe habilitar esta cuenta en Active Directory haciendo lo siguiente: 
  
1. En Active Directory, ejecute el siguiente comando para habilitar el inicio de sesión de la cuenta: 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   Al ejecutar este comando, se le pedirá que escriba la contraseña actual y, a continuación, vuelva a escribir la contraseña dos veces para confirmarla.
    
2. Una vez establecida la contraseña, ejecute el siguiente comando para habilitar la cuenta: 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a>Habilitar Skype de sistema de sala para Skype Empresarial

En esta sección se proporciona información general sobre los pasos necesarios para habilitar Skype Empresarial la cuenta de la sala de conferencias, que se configurará en Skype room system. 
  
Después de crear una cuenta de buzón de recursos para las salas de conferencias, use el Shell de administración de Skype Empresarial Server para habilitar Skype del sistema de salas para Skype Empresarial servicios.
  
> [!NOTE]
> En el siguiente procedimiento se supone que ha habilitado la cuenta Skype room system en Active Directory. 
  
1. Ejecute el siguiente comando para habilitar la cuenta Skype sistema de sala en un grupo Skype Empresarial Server grupo de servidores:
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. Opcional: permitir que esta cuenta realice y reciba llamadas telefónicas RTC habilitando la cuenta para Telefonía IP empresarial. Telefonía IP empresarial no es necesario para Skype Room System, pero si no lo habilita para Telefonía IP empresarial, el cliente del sistema de sala de Skype no podrá proporcionar la funcionalidad de marcado RTC:
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> Si habilita la Telefonía IP empresarial para la cuenta de la sala de conferencias Skype room system, asegúrese de configurar una directiva de voz restringida adecuada para su organización. Si el Skype Empresarial Sala de reuniones es un recurso disponible públicamente, cualquiera podría usarlo para unirse a una reunión, ya sea programada o ad hoc. Después de unirse a una reunión, la persona podría llamar a cualquier número. En Skype Empresarial Server, la característica de acceso telefónico desde conferencias usa la directiva de voz del usuario, en este caso la cuenta del sistema de sala Skype usada para unirse a la reunión. En versiones anteriores de Lync Server, se usa la directiva de voz del organizador. Por lo tanto, si un usuario de una versión anterior de Lync Server programa una sala de reuniones e invita a la cuenta de sala del sistema de salas de Skype, cualquiera podría usar el Skype Empresarial Sala de reuniones para unirse a la reunión y podría marcar cualquier número de teléfono nacional, regional o internacional, siempre que el organizador pueda marcar esos números. 
