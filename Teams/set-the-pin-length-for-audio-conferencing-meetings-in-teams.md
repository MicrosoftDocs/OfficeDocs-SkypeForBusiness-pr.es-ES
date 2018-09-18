---
title: Cambiar la longitud del PIN para las reuniones de Audioconferencia en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: Conozca cuáles son los parámetros de longitud y los requisitos de un PIN, y vea cómo se configura la duración de las reuniones en Microsoft Teams.
ms.openlocfilehash: 0300bba9139bdf98315b8af4200dd729ff6e70a1
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882994"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>Cambiar la longitud del PIN para las reuniones de Audioconferencia en Microsoft Teams

Cuando vaya a configurar una audioconferencia para Microsoft Teams, recibirá un puente de audioconferencia. Un puente de conferencia puede contener uno o varios números de teléfono. El que defina se incluirá en las invitaciones a la reunión para la aplicación de Microsoft Teams.
  
El puente de audioconferencia responderá a las llamadas de las personas que llamen a una reunión con un teléfono. Responde a la persona que llama con avisos de voz de un operador automático y, luego, según cuál sea su configuración, puede reproducir notificaciones y solicitar a los autores de las llamadas que registren sus nombres. En **Configuración de puente de Microsoft**, puede cambiar la configuración de las notificaciones de reunión y de la experiencia de unirse a esta, así como establecer la longitud de los PIN que usan los organizadores de la reunión. Los organizadores de la reunión usan números PIN para iniciar reuniones si no pueden unirse a la reunión con la aplicación de Microsoft Teams.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>Configurar la longitud del PIN

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página **Puentes de conferencia**, haga clic en **Configuración de puente**. 

3. En el panel **Configuración de puente**, en **Longitud del PIN**, seleccione el número de dígitos que quiere que tenga el PIN.

4. Haga clic en **Guardar**.

> [!NOTE]
> Un PIN no es lo mismo que un identificador de conferencia. Los autores de llamada usan los identificadores de conferencia al unirse a la reunión. Se utilizan para identificar la reunión. El PIN se usa para autenticar un autor de llamada como organizador de la reunión. 

## <a name="want-to-know-more-about-pin-settings"></a>¿Quiere saber más sobre la configuración del PIN?

- Los PIN pueden tener de 4 a 12 dígitos (el valor predeterminado es 5). Al crear un PIN solo pueden usarse números, por lo que no pueden usarse letras ni caracteres especiales.
    
- El PIN solo lo necesita el organizador de la reunión cuando un usuario de Microsoft Teams aún no ha iniciado la reunión. Si todos los participantes llaman a la reunión, se necesitará el PIN para que este pueda iniciarla.
    
- La configuración de seguridad del PIN se aplica a todos los números de teléfono asociados a un puente de Microsoft, así como a todas las reuniones que usen los números de teléfono asociados a dicho puente. 
    
## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
