---
title: Cambiar la longitud del PIN para las reuniones de Audioconferencia
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Obtenga información sobre los parámetros de la longitud y los requisitos de un PIN y vea cómo establecer la longitud de las reuniones en Microsoft Teams.
ms.openlocfilehash: 68297e437bdf0f3be9affa4d5e5518295dd05ab7
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2021
ms.locfileid: "58608787"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a>Cambiar la longitud del PIN para las reuniones de Audioconferencia en Microsoft Teams

Al configurar las audioconferencias para Microsoft Teams, recibirá un puente de audioconferencia. Un puente de conferencia puede contener uno o más números de teléfono. El número de teléfono que establezca se incluirá en las invitaciones de reunión para la Microsoft Teams aplicación.
  
El puente de audio conferencia responde a una llamada de personas que están llamando a una reunión usando un teléfono. Responde al autor de la llamada con mensajes de voz de un operador automático y, después, según la configuración, puede reproducir notificaciones y pedir a los autores de llamadas que graben su nombre. **La configuración del** puente de Microsoft le permite cambiar la configuración de las notificaciones de reunión y la experiencia de unirse a la reunión, y establecer la longitud de los PIN que usan los organizadores de la reunión. Los organizadores de reuniones usan los PINs para iniciar reuniones si no pueden unirse a la reunión con la aplicación Microsoft Teams reunión.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>Configurar la longitud del PIN

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página **Puentes de conferencia**, haga clic en **Configuración de puente**. 

3. En el **panel Configuración de puente,** en Longitud **del PIN,** seleccione el número de dígitos que desea para el PIN.

4. Haga clic en **Guardar**.

> [!NOTE]
> Un PIN no es lo mismo que un identificador de conferencia. Los autores de llamada usan los identificadores de conferencia al unirse a la reunión. Se utilizan para identificar la reunión. El PIN se usa para autenticar un autor de llamada como organizador de la reunión. 

## <a name="want-to-know-more-about-pin-settings"></a>¿Desea obtener más información sobre la configuración de PIN?

- Los PIN pueden ser de 4 a 12 dígitos; el valor predeterminado es 5. En la creación de un PIN solo pueden usarse números. Por lo tanto, no pueden usarse letras ni caracteres especiales.
    
- Solo se requiere un PIN para el organizador de la reunión cuando un Microsoft Teams usuario aún no ha iniciado la reunión. Si todas las personas llaman a la reunión, se necesita el PIN para que el organizador de la reunión inicie la reunión.
    
- La configuración de seguridad del PIN se aplica a todos los números de teléfono asociados a un puente de Microsoft, así como a todas las reuniones que usen los números de teléfono asociados a dicho puente. 
    
## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 mediante un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer. To get started with Windows PowerShell, see these topics:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Temas relacionados

[Pruebe o compre Audioconferencia en Microsoft 365 o Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)