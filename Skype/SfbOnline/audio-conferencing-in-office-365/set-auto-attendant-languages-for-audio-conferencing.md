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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Vea cómo seleccionar los idiomas operador automático de audio conferencia para un número de audioconferencia en Skype for Business Online.
ms.openlocfilehash: 70313648f04b05e622ddb34e871ff1b303ac02a7
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23864989"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Establecer los idiomas de operador automático para audioconferencias en Skype for Business Online

> [!Note]
> Para obtener información acerca de cómo establecer el idioma de operador automático en Microsoft Teams, vea [Establecer idiomas de operador automático para audioconferencias en Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).

El operador automático de audioconferencias de Skype for Business puede saludar a los autores de llamadas de audioconferencias en un número de diferentes idiomas cuando se unan a una reunión.
  
Elija un idioma principal y hasta cuatro idiomas secundarios. El idioma principal que configure se usará en primer lugar y los idiomas secundarios se usarán por el operador automático en el orden que seleccione. 
  
> [!NOTE]
>  Puede configurar los idiomas en solo los números de teléfono de acceso nacional de audio.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Configurar la conferencia de idiomas de operador automático

Debe ser un [administrador global de Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) o [administrador de Skype for Business](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) para llevar a cabo este paso.
    
1. En el **centro de administración de Skype for Business**, en la navegación izquierda, vaya a **Audioconferencia** y a continuación haga clic en **Puente de Microsoft**.
    
2. Seleccione el número de teléfono de audioconferencia de la lista y, en el panel de acciones, haga clic en **Establecer idiomas**. 
    
3. En la página **Establecer idiomas**, haga clic en **Idioma principal** para ver la lista completa de idiomas disponibles. Si lo necesita, haga clic en cada una de las listas de **Idiomas secundarios** para seleccionar idiomas secundarios.
    
    > [!NOTE]
    > Se enumeran el idioma principal y los secundarios que son compatibles. El orden en que los seleccione en las listas será el orden de los idiomas presentados a los autores de llamadas. 
  
4. Haga clic en **Guardar**.
    
## <a name="want-else-should-i-know"></a>¿Qué más debo saber?

- Para ver la lista de los idiomas admitidos para audioconferencia, vea [Idiomas admitidos en audioconferencia](/MicrosoftTeams/audio-conferencing-supported-languages).
    
- Los idiomas se pueden establecer para números de teléfono dedicados, pero no para compartidos.
    
- Para ver una lista de países o regiones en la que está disponible la audioconferencia en Office 365 con Microsoft como proveedor, vea [Números de teléfono para audioconferencias](phone-numbers-for-audio-conferencing.md).
    
## <a name="want-to-use-windows-powershell"></a>¿Desea usar Windows PowerShell?

Para automatizar este paso, puede usar los cmdlets [Set-CsOnlineDialInConferencingServiceNumber ](https://go.microsoft.com/fwlink/?LinkId=617689) y [Get-CsOnlineDialInConferencingLanguagesSupported ](https://go.microsoft.com/fwlink/?LinkId=617684).
  
Para obtener más información, consulte [Usar Windows PowerShell para realizar tareas de administración comunes de Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
