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
description: Obtenga información sobre cómo restablecer el PIN de audioconferencia de un usuario en Microsoft Teams y obtenga información importante sobre los PIN.
ms.openlocfilehash: ece69ec231408cc860f2fad803d92d22feaca781
ms.sourcegitcommit: cae94cd5761baafde51aea1137e6d164722eead9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/23/2021
ms.locfileid: "53075383"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Restablecer el PIN de Audioconferencia en Microsoft Teams

Un PIN es un código integrado por números que se crea para cada usuario Microsoft Teams que está habilitado para las audioconferencias. Los organizadores de la reunión usan los PIN de audioconferencia para identificar que son el organizador de la reunión y permitirles iniciar una reunión por teléfono. Si usan la aplicación Microsoft Teams para iniciar la reunión, no se requiere un PIN. Si los usuarios olvidan su PIN y no pueden encontrarlo en el correo electrónico que se les envió cuando se habilitaron para las audioconferencias, un administrador puede restablecer su PIN o puede restablecer su propio PIN.
  
Las reuniones se pueden iniciar cuando un usuario autenticado se une con la aplicación Microsoft Teams o cuando el organizador se une con su PIN por teléfono. Cuando una reunión requiere un PIN para iniciarse, los usuarios que se unan por teléfono se colocarán en la sala de espera y escucharán música en espera hasta que el organizador los admita. Si el organizador de la reunión no necesita un PIN para iniciar la reunión por teléfono, a los autores de la llamada no se les pedirá un PIN cuando se unan a la reunión.

## <a name="reset-a-users-pin"></a>Restablecer el PIN de un usuario

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**

1. En el panel de navegación izquierdo, haga clic **en Usuarios** y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. Haga clic **en Editar.**

3. En **Audioconferencia,** haga clic **en Restablecer PIN.**

4. Haga clic **en Restablecer**.
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-their-own-pin"></a>Hacer que un usuario restablezca su propio PIN

1. Hacer que el usuario vaya a [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing) .
2. Haga clic **en Restablecer PIN.** 

> [!NOTE]
> Para GCCH, vaya a: https://webdir2g.online.gov.skypeforbusiness.us/lscp/usp/pstnconferencing .

## <a name="what-else-should-you-know-about-pins"></a>¿Qué más tiene que saber sobre los códigos PIN?

- Por motivos de seguridad, el PIN solo se muestra a un administrador una vez, cuando se restablece el PIN. Una vez que un administrador restablezca el PIN, el PIN se mostrará como ***********.
    
- El envío automático de correos electrónicos a los usuarios está habilitado de forma predeterminada y los usuarios recibirán un correo electrónico con su PIN cuando se habiliten para audioconferencias o cuando se restablezca el PIN. Pero si ha deshabilitado el envío automático de correos electrónicos, no se enviará un correo electrónico de restablecimiento de PIN a un usuario y tendrá que enviar manualmente la información del PIN al usuario.
    
- Cuando se inicia una reunión, todos los usuarios de la sala de espera se unirán automáticamente. Por ejemplo, si dos participantes intentan unirse a una reunión antes de que se haya iniciado, se colocarán en la sala de espera y escucharán música en espera, y cuando el organizador de la reunión se una con su PIN por teléfono, se iniciará la reunión y los participantes de la sala de espera se unirán a la reunión.
    
- La configuración predeterminada es no permitir que los autores de llamadas anónimos puedan iniciar una reunión.
    
- Cuando habilita a un usuario para las audioconferencias, de forma predeterminada se envían correos electrónicos que incluyen información de conferencias y su PIN. El usuario debe tener un buzón de Microsoft 365 o Office 365, ya que cuando se restablece un PIN, se enviará un nuevo PIN al usuario por correo electrónico a su dirección SMTP principal (alias) establecida para el usuario.
    
- Al configurar las audioconferencias, se establecen los dígitos necesarios para los PIN de su organización. Los códigos PIN pueden tener de 4 a 12 dígitos (el valor predeterminado es 5). Si cambia la configuración de longitud del PIN, la configuración solo se aplica a los PIN generados recientemente y no se aplica a la configuración de PIN para los usuarios existentes habilitados para las audioconferencias. Vea Establecer la longitud del PIN para las reuniones [de audioconferencia.](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md)
    
- De forma predeterminada, el correo electrónico se establecerá en Microsoft 365 o Office 365 dirección SMTP principal del usuario. Puede enviar un correo electrónico a una dirección no Microsoft 365 o no Office 365 como una dirección de correo electrónico Hotmail MSN. Puede invalidar la dirección de correo electrónico predeterminada mediante Windows PowerShell. Esto es útil si los usuarios no tienen un buzón Exchange en Microsoft 365 o Office 365.

    

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 mediante un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer. To get started with Windows PowerShell, see these topics:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Temas relacionados

[Restablecer un Id. de conferencia para un usuario](reset-a-conference-id-for-a-user-in-teams.md)
