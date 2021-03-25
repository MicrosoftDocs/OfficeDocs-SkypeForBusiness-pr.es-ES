---
title: Permitir que los usuarios graben su nombre cuando se unan a una reunión en Skype Empresarial Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Obtenga información sobre cómo habilitar o deshabilitar si los usuarios pueden grabar sus nombres cuando se unan a una reunión en Skype Empresarial Online.
ms.openlocfilehash: 7fd8afb71ee524b20f24f9583ec847adbec2ff43
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114246"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a>Permitir que los usuarios graben su nombre cuando se unan a una reunión en Skype Empresarial Online

> [!Note]
> Si desea permitir a los usuarios registren sus nombres en Teams, consulte [Habilitar a los usuarios para registrar su nombre cuando se unen a una reunión en Microsoft Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).

Al configurar audioconferencias en Microsoft 365 u Office 365, recibirá números de teléfono y lo que se denomina un puente de audioconferencia. Un puente de conferencia puede contener uno o más números de teléfono que pueden ser un número de teléfono dedicado o compartido.
  
El puente de conferencia responde a la llamada de un usuario que llama a una reunión con un teléfono. Ese puente responde al autor de la llamada con avisos de voz de un operador automático y, luego, de acuerdo con su configuración, puede reproducir notificaciones, solicitar a los autores de las llamadas que graben sus nombres y configura la seguridad del PIN para los organizadores de reuniones. Los PIN se proporcionan al organizador de la reunión y con ellos se puede empezar una reunión, pero puede configurarlo de modo que no se necesite un PIN para comenzar una reunión.

## <a name="set-whether-callers-should-record-their-name"></a>Establecer si los autores de las llamadas tienen que grabar sus nombres
    
1. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.
    
2. En **Experiencia de unirse a la reunión**, vea que esté activa la casilla de verificación **Habilitar las notificaciones de entrada y salida de la reunión**.
    
   - **Activado**: se solicitará a los autores de las llamadas que graben sus nombres antes de unirse a la reunión. Esta opción está seleccionada de forma predeterminada.
    
   - **Desactivado**: no se solicitará a los autores de las llamadas que graben sus nombres antes de unirse a la reunión.
    
3. Después de realizar los cambios, haga clic en **Guardar**.
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings).
    
- Windows PowerShell se trata de administrar usuarios y lo que los usuarios pueden hacer. Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Por qué necesita usar Microsoft 365 u Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad en comparación con el uso del Centro de administración de Microsoft 365, por ejemplo, cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes: 
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar audioconferencias en Microsoft 365 u Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)