---
title: Restablecer el PIN de Audioconferencia en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Descubra qué debe saber sobre los PIN y cómo se restablecen en Microsoft Teams. '
ms.openlocfilehash: 6d0d986789fb987494ded16bb8d6f6d7c3bf58a4
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41693835"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Restablecer el PIN de Audioconferencia en Microsoft Teams

Un PIN es un código formado por números que se crea para cada usuario de Microsoft Teams que está habilitado para audioconferencias. El PIN de audioconferencia lo usa el organizador de la reunión para identificarse como tal y poder iniciar una por teléfono. Si la reunión se inicia con la aplicación de Microsoft Teams, no se necesitará el PIN. Si un usuario olvida su PIN y no lo puede encontrar en el correo electrónico que se le envió cuando se le habilitó para audioconferencias, el administrador podrá restablecer su PIN o podrá hacerlo el mismo usuario.
  
Las reuniones se pueden iniciar cuando un usuario autenticado se une con la aplicación de Microsoft Teams o cuando el organizador se une con su código PIN por teléfono. Cuando una reunión necesita un PIN para empezar, los usuarios que se unan a la reunión por teléfono se colocarán en la sala de espera y escucharán música en espera hasta que se inicie la reunión. Si el organizador de la reunión no necesita un PIN para iniciar la reunión por teléfono, a los autores de la llamada no se les pedirá un PIN cuando se unan a la reunión.

## <a name="reset-a-users-pin"></a>Restablecer el PIN de un usuario

![Un icono que muestra el logotipo](media/teams-logo-30x30.png) de Microsoft Teams **con el centro de administración de Microsoft Teams**

1. En el navegación de la izquierda, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. Haga clic en **Editar**.

3. En **audioconferencia**, haga clic en **restablecer PIN**.

4. Haga clic en **restablecer**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a>Hacer que un usuario restablezca su propio PIN

1. Hacer que el usuario vaya [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing)a.
2. Haga clic en **restablecer PIN**. 


## <a name="what-else-should-you-know-about-pins"></a>¿Qué más tiene que saber sobre los códigos PIN?

- Por motivos de seguridad, el PIN solo se muestra a un administrador una vez, cuando se restablece el PIN. Una vez que un administrador restablezca el PIN, el PIN aparecerá como * * * * * * * * * * *.
    
- El envío automático de correos electrónicos a los usuarios está habilitado de forma predeterminada y los usuarios recibirán un correo electrónico con su PIN cuando estén habilitados para conferencias de audio o cuando se restablezca el PIN. Pero si deshabilitaste el envío automático de correos electrónicos, no se enviará un mensaje de correo electrónico de restablecimiento de PIN a un usuario y tendrá que enviar manualmente la información del PIN al usuario.
    
- Cuando se inicia una reunión, todos los usuarios de la sala de espera se unirán automáticamente. Por ejemplo, si los dos participantes intentan unirse a una reunión antes de que se haya iniciado, se enviarán a la sala de espera y escucharán música en espera y, cuando el organizador de la reunión se una con su PIN a través del teléfono, la reunión se iniciará y los participantes de la sala de espera se unirán a la reunión.
    
- La configuración predeterminada es no permitir que los autores de llamadas anónimos inicien una reunión.
    
- Cuando habilita a un usuario para las conferencias de audio, se le envían mensajes de correo electrónico que incluyen información sobre conferencias y su PIN de forma predeterminada. El usuario debe tener un buzón de Office 365, porque cuando se restablece un PIN, se envía un PIN nuevo al usuario por correo electrónico a su dirección SMTP principal (alias) que está configurada para el usuario.
    
- Al configurar las conferencias de audio, se establecen los dígitos necesarios para los pin de la organización. Los códigos PIN pueden tener de 4 a 12 dígitos (el valor predeterminado es 5). Si cambia el valor de longitud del PIN, la configuración solo se aplicará a los pin recién generados y no se aplicará a la configuración de PIN de los usuarios existentes que estén habilitados para las conferencias de audio. Consulte [establecer la longitud del PIN para las reuniones de audioconferencia](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).
    
- De forma predeterminada, el correo electrónico se establecerá en la dirección SMTP principal de Office 365 del usuario. Puede enviar un correo electrónico a una dirección que no sea de Office 365, como una dirección de correo electrónico de hotmail o MSN. Puede omitir la dirección de correo electrónico predeterminada mediante Windows PowerShell. Esto es útil si los usuarios no tienen un buzón de Exchange en Office 365.

    

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Temas relacionados

[Restablecer un Id. de conferencia para un usuario](reset-a-conference-id-for-a-user-in-teams.md)
