---
title: Cambiar la configuración de un puente de Audioconferencias.
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
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
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: Cambie la configuración del puente de audioconferencia, incluidas las notificaciones de entrada y salida, los nombres de reproducción o números de teléfono, los tonos y el aviso a los autores de las llamadas para que graben su nombre.
ms.openlocfilehash: d9853826d9a93c5794017185f561b9d6a6cd1ffb
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2022
ms.locfileid: "67641791"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Cambiar la configuración de un puente de Audioconferencias.

Al configurar Audioconferencia en Microsoft 365 o Office 365, recibirá números de teléfono para los usuarios de lo que se denomina un puente de audioconferencia. Un puente de conferencia puede contener uno o más números de teléfono. Estos números de teléfono se usan cuando las personas que llaman llaman a una reunión. El número de teléfono se incluye en la parte inferior de la invitación a la reunión de Teams.
  
El puente de conferencia responde una llamada y le pide al autor de la llamada que use un operador automático de la reunión y, después, según su configuración, puede reproducir notificaciones, pedir a los autores de las llamadas que graben su nombre y controlar la configuración del PIN. Los PIN se entregan a los organizadores de la reunión para permitirles iniciar una reunión cuando no estén usando una aplicación de Microsoft Teams.

  > [!IMPORTANT]
  > Solo se requiere un PIN para el organizador de la reunión cuando un usuario de la aplicación Teams aún no ha iniciado la reunión. Si todos llaman a la reunión, el PIN es necesario para que el organizador de la reunión inicie la reunión.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo, vaya a **Puentes** >  de **conferencia de** reuniones.

2. En la parte superior de la página **Puentes de conferencia** , haga clic en **Configuración del puente**.

3. En el panel **Configuración del puente** , seleccione:
   - **Notificaciones de entrada y salida de la reunión** Si desactiva esta opción, los usuarios que ya se hayan unido a la reunión no recibirán una notificación cuando alguien se una o abandone la reunión.

     Al activar **las notificaciones de entrada y salida** de la reunión, puede seleccionar estas opciones:

   - **Nombres o números de teléfono** Cuando los usuarios llaman a una reunión, se reproduce su número de teléfono cuando se unen a ella.

   - **Tonos** Cuando los usuarios llaman a una reunión, se reproduce un tono de audio cuando se unen a ella.

   - **Pedir a los autores de las llamadas que graben su nombre antes de unirse a la reunión** Si desactiva esta opción, no se pedirá a los autores de las llamadas que graben su nombre antes de unirse a una reunión.

4. Para establecer la longitud del PIN para las reuniones, seleccione el número de dígitos que desea para el PIN en la lista **de longitud del PIN** .

5. Para especificar si desea enviar correo electrónico a los usuarios, habilite o deshabilite **Enviar automáticamente correos electrónicos a los usuarios si cambia la configuración de las audioconferencias**.
    Vea [Correos electrónicos enviados automáticamente a los usuarios cuando cambia la configuración de Audioconferencia en Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) para obtener más información.

6. Haga clic en **Guardar**.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsDialinConferencingBridge](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) .

- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tenga que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:

  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - [Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))

- Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad con respecto solo al uso de los Centro de administración de Microsoft 365, como cuando se realizan cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:

  - [Introducción a Microsoft Teams PowerShell](teams-powershell-overview.md)

  - [Instalar módulo de PowerShell de Microsoft Teams](teams-powershell-install.md)
  
## <a name="related-topics"></a>Temas relacionados

[Configurar audioconferencias en Microsoft Teams](set-up-audio-conferencing-in-teams.md)
