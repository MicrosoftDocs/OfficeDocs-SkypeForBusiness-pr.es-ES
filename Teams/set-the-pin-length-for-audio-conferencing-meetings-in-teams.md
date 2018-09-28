---
title: Cambiar la longitud del PIN para las reuniones de Audioconferencia en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: Conozca cuáles son los parámetros de longitud y los requisitos de un PIN, y vea cómo se configura la duración de las reuniones en Microsoft Teams.
ms.openlocfilehash: 8e0be3a904f4172aa0f92c1632ad37992a36ab5f
ms.sourcegitcommit: 19fb0279985251c00cd507a8d13b8499b19e2808
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2018
ms.locfileid: "25347485"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>Cambiar la longitud del PIN para las reuniones de Audioconferencia en Microsoft Teams

Al establecer una conferencia de audio para Microsoft Teams, obtendrá un puente de conferencia de audio. Un puente de conferencia puede contener uno o más números de teléfono. Establece el número de teléfono se incluirá en la reunión de invitaciones para la aplicación Microsoft Teams.
  
El puente de conferencia de audio responde a una llamada para las personas que llaman a una reunión mediante un teléfono. Atiende el autor de la llamada con mensajes de voz de un operador automático y, a continuación, dependiendo de la configuración, puede reproducir las notificaciones y pida a los autores de llamadas para registrar su nombre. **Configuración de puente de Microsoft** le permiten cambiar la configuración de las notificaciones de la reunión y experiencia al unirse a la reunión y establecer la longitud de los ejes que se usan por los organizadores de reuniones. Los organizadores de reuniones Utilice PIN para iniciar reuniones si no puede unirse a la reunión mediante la aplicación de Microsoft Teams.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>Configurar la longitud del PIN

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) Uso del equipos de Microsoft y Skype para centro de administración de negocio

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página **Puentes de conferencia**, haga clic en **Configuración de puente**. 

3. En el panel **configuración de puente** , en **longitud PIN**, seleccione el número de dígitos que desee para el PIN.

4. Haga clic en **Guardar**.

> [!NOTE]
> Un PIN no es lo mismo que un identificador de conferencia. Los autores de llamada usan los identificadores de conferencia al unirse a la reunión. Se utilizan para identificar la reunión. El PIN se usa para autenticar un autor de llamada como organizador de la reunión. 

## <a name="want-to-know-more-about-pin-settings"></a>¿Desea saber más acerca de la configuración de NIP?

- PIN pueden contener de 4 a 12 dígitos; el valor predeterminado es 5. En la creación de un PIN solo pueden usarse números. Por lo tanto, no pueden usarse letras ni caracteres especiales.
    
- Un PIN sólo es necesario para el organizador de la reunión cuando un usuario de Microsoft Teams ya no ha iniciado la reunión. Si todas las personas llaman a la reunión, se necesita el PIN para que el organizador de la reunión inicie la reunión.
    
- La configuración de seguridad del PIN se aplica a todos los números de teléfono asociados a un puente de Microsoft, así como a todas las reuniones que usen los números de teléfono asociados a dicho puente. 
    
## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
