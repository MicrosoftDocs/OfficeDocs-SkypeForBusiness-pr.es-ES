---
title: Iniciar audioconferencia por teléfono sin un PIN en Teams
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
- seo-marvel-mar2020
description: 'Obtenga información sobre cómo habilitar o deshabilitar que los autores de llamadas anónimos se unan a una reunión desde el Centro de administración de Teams. '
ms.openlocfilehash: a858c95527d09e24004d025787bee52c0de84705
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641951"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Iniciar una audioconferencia por teléfono sin PIN en Microsoft Teams

Puede resultar frustrante para los usuarios que llaman a una reunión que se celebre en la sala de espera de la reunión escuchando música porque el organizador de la reunión de Microsoft Teams no ha iniciado la reunión.
  
Si un organizador de la reunión llama a la reunión, de forma predeterminada, se requiere un PIN para iniciarla. Puede configurarlo para que cualquier persona pueda llamar a una reunión y no se le pida un PIN para iniciar la reunión. Puede usar el centro de administración para habilitar o deshabilitar esta configuración para un solo usuario.
  
No es necesario un PIN para el organizador de la reunión si alguien ha iniciado la reunión desde la aplicación Microsoft Teams. El PIN solo será necesario si el organizador de la reunión se une a ella desde un teléfono. El PIN para las reuniones se envía al usuario de audio cuando se le asigna la licencia **de Audioconferencia** y se habilita para Audioconferencia. Vea [Enviar un correo electrónico a un usuario con su información de Audioconferencia](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) y [Correos electrónicos que se envían automáticamente a los usuarios cuando cambia la configuración de Audioconferencia](emails-sent-to-users-when-their-settings-change-in-teams.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Habilitar o deshabilitar la posibilidad de que los autores de llamada anónimos se unan a la reunión

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo, haga clic en **Usuarios**.

2. Seleccione un usuario de la lista y, a continuación, haga clic en **Editar** en la parte superior de la página.

3. Junto a **Audioconferencia**, haga clic en **Editar**.

4. En el panel **Audioconferencia** , habilitar o deshabilitar los **autores de llamadas de acceso telefónico local pueden ser la primera persona de una reunión**.

5. Haga clic en **Aplicar**.

### <a name="using-windows-powershell"></a>Usar Windows PowerShell

Consulte la [referencia de Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obtener más información.

## <a name="what-else-should-you-know"></a>¿Qué más debe saber?

- Si desea restablecer el PIN, consulte [Restablecer el PIN de Audioconferencia](reset-the-audio-conferencing-pin-in-teams.md).

- Si el acceso anónimo o no requiere un PIN para iniciar una reunión está deshabilitado:

  - Si la reunión no ha comenzado (todavía no hay nadie en la reunión): se le preguntará si es el organizador; si dice sí, se le pedirá su PIN y, después de introducir el PIN, se iniciará la reunión y el usuario se unirá a ella.

  - Si la reunión ya se ha iniciado (otra persona ya está en la reunión): no se le preguntará al autor de la llamada si es el organizador y nunca se le pedirá el PIN; la reunión ya se ha iniciado y el autor de la llamada se unirá a ella.

- Si se habilita el acceso anónimo o no requiere un PIN para iniciar una reunión:

  - Si la reunión no ha comenzado (todavía no hay nadie en la reunión): no se le preguntará al autor de la llamada si es la organizadora y nunca se le pedirá el PIN. Dado que la configuración del organizador está desactivada, la reunión se iniciará y los autores de llamada anónimos se unirán a la reunión.

  - Si la reunión ya se ha iniciado (otra persona ya está en la reunión): no se le preguntará al autor de la llamada si es la organizadora y nunca se le pedirá el PIN; la reunión ya se ha iniciado y el autor de la llamada se unirá a ella.

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tenga que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:

- [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Microsoft 365 para Microsoft Teams](try-or-purchase-audio-conferencing-in-office-365-for-teams.md)
