---
title: Iniciar una audioconferencia por teléfono sin PIN en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Aprenda a habilitar o deshabilitar la posibilidad de que los autores de llamada anónimos puedan unirse a una reunión desde el Centro de administración de Teams. '
ms.openlocfilehash: 5f2dbd84b71058e75b710f37994e41c9adb488ef
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32227098"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Iniciar una audioconferencia por teléfono sin PIN en Microsoft Teams

Puede resultar frustrante para los usuarios que la llamada local a una reunión se mantenga en espera en la sala de espera de la reunión mientras se reproduce música, porque el organizador de la reunión de Microsoft Teams no haya iniciado la reunión. 
  
Si un organizador de la reunión llama a la reunión, de manera predeterminada, se le pedirá un PIN para iniciarla. Pero puede configurarla para que cualquier usuario pueda entrar en la reunión con una llamada sin que se le pida el PIN para iniciarla. Puede usar el centro de administración para habilitar o deshabilitar este parámetro para un solo usuario.
  
El organizador de la reunión no necesita el PIN si otra persona ha iniciado la reunión desde la aplicación de Microsoft Teams. Solo será necesario si el organizador de la reunión se une a ella a través de un teléfono. El PIN para reuniones se envía al usuarios de audioconferencias cuando se le asigna la licencia de **Audioconferencia** o cuando se habilita para estas. Consulte [Enviar un correo electrónico a un usuario con su información de audioconferencia](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) y [Correos electrónicos que se envían de forma automática a los usuarios cuando cambia la configuración de Audioconferencia](emails-sent-to-users-when-their-settings-change-in-teams.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Habilitar o deshabilitar la posibilidad de que los autores de llamada anónimos se unan a una reunión

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **desde el centro de administración de equipos de Microsoft**

1. En el panel de navegación izquierdo, haga clic en **Usuarios**. 

2. Seleccione un usuario de la lista y haga clic en **Editar** en la parte superior de la página. 

3. Junto a **Audioconferencia**, haga clic en **Editar**.

4. En el panel **Audioconferencia**, habilite o deshabilite **Los autores de llamada sin autenticar pueden ser los primeros en unirse a una reunión**.
    
4. Haga clic en **Guardar**. 

**Uso de Windows PowerShell**
  
Vea la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.

## <a name="what-else-should-you-know"></a>¿Qué más debe saber?

- Si desea restablecer el PIN, consulte [Restablecer el PIN de Audioconferencia](reset-the-audio-conferencing-pin-in-teams.md).
    
- Si se ha habilitado el acceso anónimo o la posibilidad de iniciar una reunión sin PIN:
    
  - Si la reunión no ha empezado (no hay nadie todavía en la reunión): se le preguntará al autor de la llamada si es el organizador. Si indica que lo es, se le solicitará el PIN. La reunión se iniciará cuando lo especifique y el usuario se unirá a ella.
    
  - Si la reunión ha empezado (ya hay personas en la reunión): no se le preguntará al autor de la llamada si es el organizador y en ningún momento se le solicitará el PIN. La reunión ya ha empezado y el autor de la llamada se unirá a ella.
    
- Si se ha deshabilitado el acceso anónimo o no se solicita el PIN para iniciar una reunión:
    
  - Si la reunión no ha empezado (no hay nadie todavía en la reunión): no se le preguntará al autor de la llamada si es el organizador y en ningún momento se le solicitará el PIN. Como la configuración del organizador estará desactivada, la reunión se iniciará y los autores de llamada anónimos se unirán a ella.
    
  - Si la reunión ha empezado (ya hay personas en la reunión): no se le preguntará al autor de la llamada si es el organizador y en ningún momento se le solicitará el PIN. La reunión ya ha empezado y el autor de la llamada se unirá a ella.
    
## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
