---
title: Establecer los idiomas de operador automático para audioconferencias en Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
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
description: Vea cómo seleccionar los idiomas operador automático de audio conferencia para un número de audioconferencia en Skype for Business Online.
ms.openlocfilehash: d2b4c0d9be666a6ee7de9c2bd36b8dd06cccdf32
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51110006"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Establecer los idiomas de operador automático para audioconferencias en Skype for Business Online

> [!Note]
> Para obtener información acerca de cómo establecer el idioma de operador automático en Microsoft Teams, vea [Establecer idiomas de operador automático para audioconferencias en Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).

El operador automático de audioconferencias de Skype for Business puede saludar a los autores de llamadas de audioconferencias en un número de diferentes idiomas cuando se unan a una reunión.
  
Elija un idioma principal y hasta cuatro idiomas secundarios. El idioma principal que establezca se usará primero y los idiomas secundarios los usará el operador automático en el orden que seleccione. 
  
> [!NOTE]
>  Solo puede cambiar los idiomas de los números de audioconferencia que son de la categoría Dedicado. Los idiomas del número de audioconferencia compartida no se pueden cambiar.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Configurar la conferencia de idiomas de operador automático

Para realizar este [paso, debe](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) ser administrador global o administrador de [Skype](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) Empresarial.
    
1. En el **Centro de administración de Skype Empresarial,** en el panel de navegación izquierdo, vaya a Portal **heredado.** Una vez en el portal heredado, seleccione **Audioconferencia y,** a continuación, haga clic en **Puente de Microsoft.**
    
2. Seleccione el número de teléfono de audioconferencia de la lista y, en el panel Acción, haga clic **en Establecer idiomas.** Solo es posible cambiar los idiomas de los números de audioconferencia dedicados.  
    
3. En la **página Establecer idiomas,** haga clic en **la lista Idioma** principal para ver la lista completa de idiomas disponibles. Si es necesario, haga clic en cada una de las listas **idiomas secundarios** para seleccionar el idioma secundario.
    
    > [!NOTE]
    > Se enumeran el idioma principal y los secundarios que son compatibles. El orden en que los seleccione en las listas será el orden de los idiomas presentados a los autores de llamadas. 
  
4. Haga clic en **Guardar**.
    
## <a name="want-else-should-i-know"></a>¿Qué más debo saber?

- Para ver la lista de los idiomas admitidos para audioconferencia, vea [Idiomas admitidos en audioconferencia](/MicrosoftTeams/audio-conferencing-supported-languages).
    
- Los idiomas se pueden establecer para números de teléfono dedicados, pero no para compartidos.
    
- Para ver una lista de países o regiones en los que las audioconferencias en Microsoft 365 u Office 365 con Microsoft como proveedor están disponibles, vea Números de teléfono para audioconferencias. [](phone-numbers-for-audio-conferencing.md)
    
## <a name="want-to-use-windows-powershell"></a>¿Desea usar Windows PowerShell?

Para automatizar este paso, puede usar los [cmdlets Set-CsOnlineDialInConferencingServiceNumber](/powershell/module/skype/Set-CsOnlineDialInConferencingServiceNumber) y [Get-CsOnlineDialInConferencingLanguagesSupported.](/powershell/module/skype/Get-CsOnlineDialInConferencingLanguagesSupported)
  
Para obtener más información, vea [Usar Windows PowerShell tareas comunes de](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) administración de Skype Empresarial Online
  
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar audioconferencias en Microsoft 365 u Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)