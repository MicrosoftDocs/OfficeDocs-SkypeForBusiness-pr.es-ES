---
title: Restablecer el PIN de Audioconferencia en Microsoft Teams
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Descubra qué debe saber sobre los PIN y cómo se restablecen en Microsoft Teams. '
ms.openlocfilehash: b88ab6ee2cd498a38026e1fe2bfde04344514901
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25014254"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Restablecer el PIN de Audioconferencia en Microsoft Teams

Un NIP es un código formado por los números que se crean para cada usuario de Microsoft Teams habilitados para conferencias de audio. PIN de conferencia de audio se usan por los organizadores de reuniones para identificar que son el organizador de la reunión y que puedan iniciar una reunión a través del teléfono. Si la aplicación de Microsoft Teams que utilizan para iniciar la reunión, un PIN no es necesario. Si los usuarios olvidan su PIN y no pueden encontrar en el correo electrónico que se envió a ellos cuando se han habilitado para conferencias de audio, un administrador puede restablecer su NIP, o pueden restablecer su propios NIP.
  
Las reuniones se pueden iniciar cuando se une a un usuario autenticado mediante la aplicación de Microsoft Teams o cuando se une el organizador con su PIN a través del teléfono. Cuando una reunión necesita un PIN para empezar, los usuarios que se unan a la reunión por teléfono se colocarán en la sala de espera y escucharán música en espera hasta que se inicie la reunión. Si el organizador de la reunión no necesita un PIN para iniciar la reunión por teléfono, a los autores de la llamada no se les pedirá un PIN cuando se unan a la reunión.

## <a name="reset-a-users-pin"></a>Restablecer el PIN de un usuario

1. En el panel de navegación izquierdo, haga clic en **Usuarios** y seleccione el usuario en la lista de usuarios disponibles.

2. En la parte superior de la página, haga clic en **Editar**.

3. En **Audioconferencia**, haga clic en **Restablecer PIN**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Pedir a un usuario que restablezca su propio PIN

1. Indique al usuario que vaya a [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).
2. Haga clic en **Restablecer PIN**. 


## <a name="what-else-should-you-know-about-pins"></a>¿Qué más tiene que saber sobre los códigos PIN?

- Por motivos de seguridad, el PIN solo se muestra a un administrador una vez, cuando se restablece el PIN. Después de restablece el PIN por un administrador, el NIP se mostrará como ***.
    
- Enviar automáticamente mensajes de correo electrónico a los usuarios está habilitado de forma predeterminada, y los usuarios recibirán un correo electrónico con su NIP cuando están habilitados para conferencias de audio o cuando se restablece el NIP. Pero si ha deshabilitado automáticamente enviar mensajes de correo electrónico, no se enviará un correo electrónico de restablecimiento PIN a un usuario y tendrá que enviar manualmente la información de PIN para el usuario.
    
- Cuando se inicia una reunión, todos los usuarios de la sala de espera se unirán automáticamente. Por ejemplo, si los dos participantes intentan unirse a una reunión antes de que se haya iniciado, se enviarán a la sala de espera y escucharán música en espera y, cuando el organizador de la reunión se una con su PIN a través del teléfono, la reunión se iniciará y los participantes de la sala de espera se unirán a la reunión.
    
- La configuración predeterminada no permite que se inicie una reunión con autores de llamada anónimos.
    
- Cuando se habilita un usuario para conferencias de audio, de forma predeterminada se envían mensajes de correo electrónico que incluyen información de conferencia y su PIN. El usuario debe tener un buzón de Office 365, porque cuando se restablece un NIP, un nuevo NIP se van a enviar al usuario por correo electrónico a su dirección SMTP principal (alias) que se establece para el usuario.
    
- Cuando se establece una conferencia con audio, establezca los dígitos que se requieren para el PIN en la organización. Los PIN pueden tener de 4 a 12 dígitos (el valor predeterminado es 5). Si cambia la configuración de longitud PIN, la configuración se aplica solo a los PIN generados recientemente y no se aplica a la configuración de PIN para los usuarios existentes que están habilitados para conferencias de audio. Vea [establecer la longitud del eje para las reuniones de conferencia de Audio](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).
    
- El correo electrónico de forma predeterminada se establecerá en la dirección SMTP principal de Office 365 del usuario. Puede enviar un correo electrónico a una dirección que no sean Office 365, como Hotmail o la dirección de correo electrónico MSN. Puede invalidar la dirección de correo electrónico predeterminada mediante el uso de Windows PowerShell. Esto es útil si los usuarios no tienen un buzón de Exchange en Office 365.

    

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Temas relacionados

[Restablecer un Id. de conferencia para un usuario](reset-a-conference-id-for-a-user-in-teams.md)
