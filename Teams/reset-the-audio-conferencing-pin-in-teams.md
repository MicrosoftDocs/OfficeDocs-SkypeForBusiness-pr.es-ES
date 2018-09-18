---
title: Restablecer el PIN de Audioconferencia en Microsoft Teams
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Descubra qué debe saber sobre los PIN y cómo se restablecen en Microsoft Teams. '
ms.openlocfilehash: 9c63df504150dce7ba1d46329fc86a27c75ced8d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892957"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Restablecer el PIN de Audioconferencia en Microsoft Teams

Un PIN es un código formado por números que se crea para cada usuario de Microsoft Teams que está habilitado para audioconferencias. El PIN de audioconferencia lo usa el organizador de la reunión para identificarse como tal y poder iniciar una por teléfono. Si la reunión se inicia con la aplicación de Microsoft Teams, no se necesitará el PIN. Si un usuario olvida su PIN y no lo puede encontrar en el correo electrónico que se le envió cuando se le habilitó para audioconferencias, el administrador podrá restablecer su PIN o podrá hacerlo el mismo usuario.
  
Las reuniones se pueden iniciar cuando un usuario autenticado se une con la aplicación de Microsoft Teams o cuando el organizador se une con su código PIN por teléfono. Cuando una reunión necesita un PIN para empezar, los usuarios que se unan a la reunión por teléfono se colocarán en la sala de espera y escucharán música en espera hasta que se inicie la reunión. Si el organizador de la reunión no necesita un PIN para iniciar la reunión por teléfono, a los autores de la llamada no se les pedirá un PIN cuando se unan a la reunión.

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

- Por motivos de seguridad, cuando se restablece el PIN, solo se muestra a un administrador una vez. Una vez que el administrador ha restablecido el PIN, este aparecerá como ***********.
    
- El envío automático de correos electrónicos a los usuarios está habilitado de manera predeterminada, de manera que los usuarios recibirán un correo electrónico con su PIN cuando estén habilitados para audioconferencias o cuando se restablezca el PIN. No obstante, si ha deshabilitado el envío automático de correos electrónicos, no se enviará el correo electrónico por el restablecimiento de PIN al usuario y habrá que enviarle esta información manualmente.
    
- Cuando se inicia una reunión, todos los usuarios de la sala de espera se unirán automáticamente. Por ejemplo, si los dos participantes intentan unirse a una reunión antes de que se haya iniciado, se enviarán a la sala de espera y escucharán música en espera y, cuando el organizador de la reunión se una con su PIN a través del teléfono, la reunión se iniciará y los participantes de la sala de espera se unirán a la reunión.
    
- La configuración predeterminada no permite que se inicie una reunión con autores de llamada anónimos.
    
- Al habilitar a un usuario para audioconferencias, de manera predeterminada se le envían correos electrónicos con información sobre la conferencia y con su PIN. Es necesario que el usuario tenga un buzón de Office 365 ya que, cuando se restablece un PIN, se enviará un nuevo PIN al usuario por correo electrónico a la dirección SMTP principal (alias) que se haya configurado para el usuario.
    
- Al configurar audioconferencias, establecerá los dígitos necesarios para los códigos PIN en su organización. Los PIN pueden tener de 4 a 12 dígitos (el valor predeterminado es 5). Si cambia la configuración de longitud del PIN, la configuración solo se aplicará en los códigos PIN nuevos que se generen, pero no se aplicará en la configuración de PIN de los usuarios existentes que tengan habilitada la audioconferencia. Vea [Establecer la longitud del PIN para reuniones de Audioconferencia](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)
    
- De manera predeterminada, el correo electrónico se establecerá en la dirección SMTP principal de Office 365 del usuario, aunque también se puede enviar un correo electrónico a una dirección que no sea de Office 365, como una dirección de Hotmail o MSN. La dirección de correo electrónico predeterminada se puede reemplazar con Windows PowerShell. Esto resulta muy útil si los usuarios no tienen un buzón de Exchange en Office 365.

    

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Temas relacionados

[Restablecer un Id. de conferencia para un usuario](reset-a-conference-id-for-a-user-in-teams.md)
