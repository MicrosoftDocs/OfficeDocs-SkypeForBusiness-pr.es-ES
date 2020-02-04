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
description: Obtenga información sobre los parámetros para la duración y los requisitos de un PIN y vea cómo establecer la duración de las reuniones en Microsoft Teams.
ms.openlocfilehash: 7f7f477d14556baa7d2a47e5062aacd5de5796fd
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "41694005"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>Cambiar la longitud del PIN para las reuniones de Audioconferencia en Microsoft Teams

Cuando vaya a configurar una audioconferencia para Microsoft Teams, recibirá un puente de audioconferencia. Un puente de conferencia puede contener uno o varios números de teléfono. El que defina se incluirá en las invitaciones a la reunión para la aplicación de Microsoft Teams.
  
El puente de audioconferencia responderá a las llamadas de las personas que llamen a una reunión con un teléfono. Responde a la persona que llama con avisos de voz de un operador automático y, luego, según cuál sea su configuración, puede reproducir notificaciones y solicitar a los autores de las llamadas que registren sus nombres. En **Configuración de puente de Microsoft**, puede cambiar la configuración de las notificaciones de reunión y de la experiencia de unirse a esta, así como establecer la longitud de los PIN que usan los organizadores de la reunión. Los organizadores de la reunión usan números PIN para iniciar reuniones si no pueden unirse a la reunión con la aplicación de Microsoft Teams.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>Configurar la longitud del PIN

![Un icono que muestra el logotipo](media/teams-logo-30x30.png) de Microsoft Teams **con el centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página **Puentes de conferencia**, haga clic en **Configuración de puente**. 

3. En el panel **configuración de puente** , en longitud del **PIN**, seleccione el número de dígitos que desee para el PIN.

4. Haga clic en **Guardar **.

> [!NOTE]
> Un PIN no es lo mismo que un identificador de conferencia. Los autores de llamada usan los identificadores de conferencia al unirse a la reunión. Se utilizan para identificar la reunión. El PIN se usa para autenticar un autor de llamada como organizador de la reunión. 

## <a name="want-to-know-more-about-pin-settings"></a>¿Desea saber más sobre la configuración de PIN?

- Los pin pueden estar entre 4 y 12 dígitos; el valor predeterminado es 5. En la creación de un PIN solo pueden usarse números. Por lo tanto, no pueden usarse letras ni caracteres especiales.
    
- Un PIN solo es necesario para el organizador de la reunión cuando un usuario de Microsoft Teams ya no ha iniciado la reunión. Si todas las personas llaman a la reunión, se necesita el PIN para que el organizador de la reunión inicie la reunión.
    
- La configuración de seguridad del PIN se aplica a todos los números de teléfono asociados a un puente de Microsoft, así como a todas las reuniones que usen los números de teléfono asociados a dicho puente. 
    
## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
