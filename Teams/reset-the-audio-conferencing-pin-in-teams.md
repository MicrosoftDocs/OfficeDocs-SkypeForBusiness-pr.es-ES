---
title: Restablecer el PIN de Audioconferencia en Microsoft Teams
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Obtenga información sobre cómo restablecer el PIN de Audioconferencia de un usuario en Microsoft Teams y obtenga información importante sobre los CÓDIGOS PIN.
ms.openlocfilehash: 51c936580010899355db539a45477afd932fb53d
ms.sourcegitcommit: d3eb876e58c9e4a0a11a21b9292d3a6177508d81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/03/2022
ms.locfileid: "68329034"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a>Restablecer el PIN de Audioconferencia en Microsoft Teams

Un PIN es un código formado por números que se crea para cada usuario de Microsoft Teams habilitado para audioconferencia. Los pin de audioconferencia los usan los organizadores de la reunión para identificar que son el organizador de la reunión y permitirles iniciar una reunión por teléfono. Si usan la aplicación Microsoft Teams para iniciar la reunión, no es necesario un PIN. Si los usuarios olvidan su PIN y no lo encuentran en el correo electrónico que se les envió cuando se habilitaron para audioconferencia, un administrador puede restablecer su PIN o pueden restablecer su propio PIN.
  
Las reuniones se pueden iniciar cuando un usuario autenticado se une con la aplicación de Microsoft Teams o cuando el organizador se une con su PIN por teléfono. Cuando una reunión requiere un PIN para iniciarse, los usuarios que se unan por teléfono se colocarán en la sala de espera y escucharán música en espera hasta que el organizador los admita. Si el organizador de la reunión no necesita un PIN para iniciar la reunión por teléfono, a los autores de la llamada no se les pedirá un PIN cuando se unan a la reunión.

## <a name="reset-a-users-pin"></a>Restablecer el PIN de un usuario

Con el Centro de administración de Microsoft Teams:

1. En el panel de navegación izquierdo, haga clic en **Usuarios** y, a continuación, seleccione el usuario en la lista de usuarios disponibles.

2. Haga clic en **Editar**.

3. En **Audioconferencia**, haga clic en **Restablecer PIN**.

4. Haga clic en **Restablecer**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="have-a-user-reset-their-own-pin"></a>Hacer que un usuario restablezca su propio PIN

1. Haz que el usuario vaya a [https://dialin.teams.microsoft.com/usp](https://dialin.teams.microsoft.com/usp).
2. Haga clic en **Restablecer PIN**.

> [!NOTE]
> Para GCCH, ve a: [https://dialin.cpc.gov.teams.microsoft.us/usp](https://dialin.cpc.gov.teams.microsoft.us/usp).
> Para DoD, vaya a: [https://dialin.cpc.dod.teams.microsoft.us/usp](https://dialin.cpc.dod.teams.microsoft.us/usp).

> [!NOTE]
> No se enviará un correo electrónico de restablecimiento de PIN al usuario si usa este método.

## <a name="what-else-should-you-know-about-pins"></a>¿Qué más tiene que saber sobre los códigos PIN?

- Por motivos de seguridad, el PIN solo se muestra a un administrador una vez, cuando se restablece el PIN. Después de que un administrador restablezca el PIN, este se mostrará como **********.

- El envío automático de correos electrónicos a los usuarios está habilitado de forma predeterminada, y los usuarios recibirán un correo electrónico con su PIN cuando estén habilitados para audioconferencia o cuando se restablezca el PIN. Pero si deshabilitó el envío automático de correos electrónicos, no se enviará un correo electrónico de restablecimiento de PIN a un usuario y tendrá que enviar manualmente la información del PIN al usuario.

- Cuando se inicia una reunión, el organizador debe admitir a todos los usuarios de RTC de la sala de espera para unirse a la reunión. Por ejemplo, si dos participantes de RTC intentan unirse a una reunión antes de que se haya iniciado, se enviarán a la sala de espera y escucharán música en espera y, cuando el organizador de la reunión se una con su PIN por teléfono, se iniciará la reunión y el organizador podrá usar el comando Dentro de la reunión (presione *21) para admitir a todos los usuarios de RTC de la sala de espera.

- La configuración predeterminada es no permitir que los autores de llamada anónimos inicien una reunión.

- Al habilitar a un usuario para las audioconferencias, de forma predeterminada se le envían correos electrónicos que incluyen información de conferencia y su PIN. El usuario debe tener un buzón de Microsoft 365 o Office 365, ya que, cuando se restablece un PIN, se enviará un nuevo PIN al usuario por correo electrónico a su dirección SMTP principal (alias) establecida para el usuario.

- Al configurar la audioconferencia, establezca los dígitos necesarios para los CÓDIGOS PIN de su organización. Los códigos PIN pueden tener de 4 a 12 dígitos (el valor predeterminado es 5). Si cambia la configuración de longitud del PIN, la configuración solo se aplica en los códigos PIN recién generados y no se aplica a la configuración de PIN para los usuarios existentes que están habilitados para audioconferencia. Vea [Establecer la longitud del PIN para las reuniones de Audioconferencia](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).

- De forma predeterminada, el correo electrónico se establecerá en microsoft 365 o Office 365 dirección SMTP principal del usuario. Puede enviar un correo electrónico a una dirección que no sea de Microsoft 365 o que no sea Office 365, como una dirección de correo electrónico de Hotmail o MSN. Puede reemplazar la dirección de correo electrónico predeterminada con Windows PowerShell. Esto es útil si los usuarios no tienen un buzón de Exchange en Microsoft 365 o Office 365.

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tenga que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:

- [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Temas relacionados

[Restablecer un Id. de conferencia para un usuario](reset-a-conference-id-for-a-user-in-teams.md)
