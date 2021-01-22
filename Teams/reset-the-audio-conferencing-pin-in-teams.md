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
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Aprenda a restablecer el PIN de Audioconferencia de un usuario en Microsoft Teams y a conocer datos importantes sobre los PIN.
ms.openlocfilehash: cf660331bebfe32fe1809067570e316449c12a22
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918986"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Restablecer el PIN de Audioconferencia en Microsoft Teams

Un PIN es un código formado por números que se crea para cada usuario de Microsoft Teams que está habilitado para audioconferencias. El PIN de audioconferencia lo usa el organizador de la reunión para identificarse como tal y poder iniciar una por teléfono. Si la reunión se inicia con la aplicación de Microsoft Teams, no se necesitará el PIN. Si un usuario olvida su PIN y no lo puede encontrar en el correo electrónico que se le envió cuando se le habilitó para audioconferencias, el administrador podrá restablecer su PIN o podrá hacerlo el mismo usuario.
  
Las reuniones se pueden iniciar cuando un usuario autenticado se une mediante la aplicación de Microsoft Teams o cuando el organizador se une con su PIN a través del teléfono. Cuando una reunión necesita un PIN para empezar, los usuarios que se unan a la reunión por teléfono se colocarán en la sala de espera y escucharán música en espera hasta que se inicie la reunión. Si el organizador de la reunión no necesita un PIN para iniciar la reunión por teléfono, a los autores de la llamada no se les pedirá un PIN cuando se unan a la reunión.

## <a name="reset-a-users-pin"></a>Restablecer el PIN de un usuario

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, **haga clic en Usuarios** y, a continuación, seleccione el usuario en la lista de usuarios disponibles.

2. Haga clic **en Editar.**

3. En **Audioconferencia,** haga clic **en Restablecer PIN.**

4. Haga clic **en Restablecer.**
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-their-own-pin"></a>Hacer que un usuario restablezca su propio PIN

1. Hacer que el usuario vaya a [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) .
2. Haga clic **en Restablecer PIN.** 


## <a name="what-else-should-you-know-about-pins"></a>¿Qué más tiene que saber sobre los códigos PIN?

- Por motivos de seguridad, el PIN solo se muestra a un administrador una vez, cuando se restablece el PIN. Después de que un administrador restablezca el PIN, aparecerá como ***********.
    
- El envío automático de correos electrónicos a los usuarios está habilitado de forma predeterminada, y los usuarios recibirán un correo electrónico con su PIN cuando están habilitados para la audioconferencia o cuando se restablece el PIN. Pero si deshabilitó el envío automático de correos electrónicos, no se enviará un correo electrónico de restablecimiento de PIN al usuario y tendrá que enviar manualmente la información del PIN al usuario.
    
- Cuando se inicia una reunión, todos los usuarios de la sala de espera se unirán automáticamente. Por ejemplo, si dos participantes intentan unirse a una reunión antes de que se haya iniciado, se colocarán en la sala de espera y escucharán música en espera, y cuando el organizador de la reunión se una con su PIN a través del teléfono, la reunión se iniciará y los participantes de la sala de espera se unirán a la reunión.
    
- La configuración predeterminada es no permitir que autores de llamadas anónimos puedan iniciar una reunión.
    
- Cuando se habilita a un usuario para las audioconferencias, de forma predeterminada se envían correos electrónicos con información sobre la conferencia y su PIN. El usuario debe tener un buzón de Microsoft 365 u Office 365, porque cuando se restablece un PIN, se enviará un nuevo PIN al usuario por correo electrónico a su dirección SMTP principal (alias) configurada para el usuario.
    
- Al configurar la audioconferencia, establezca los dígitos necesarios para los NÚMEROS PIN de su organización. Los códigos PIN pueden tener de 4 a 12 dígitos (el valor predeterminado es 5). Si cambia la configuración de longitud del PIN, la configuración solo se aplicará en los nuevos PIN y no se aplicará a la configuración de PIN de los usuarios existentes habilitados para audioconferencia. Vea [Establecer la longitud del PIN para las reuniones de Audioconferencia.](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)
    
- El correo electrónico se establecerá de forma predeterminada en la dirección SMTP principal de Microsoft 365 u Office 365 del usuario. Puede enviar un correo electrónico a una dirección que no sea de Microsoft 365 o que no sea de Office 365, como una dirección de Hotmail o MSN. Puede reemplazar la dirección de correo electrónico predeterminada usando Windows PowerShell. Esto es útil si los usuarios no tienen un buzón de Exchange en Microsoft 365 u Office 365.

    

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tenga que realizar varias tareas. To get started with Windows PowerShell, see these topics:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Temas relacionados

[Restablecer un Id. de conferencia para un usuario](reset-a-conference-id-for-a-user-in-teams.md)
