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
ms.openlocfilehash: 93b6ea917c7f79747273366893efc47a22b89bb2
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163912"
---
# <a name="set-auto-attendant-languages-for-audio-conferencing-in-skype-for-business-online"></a>Establecer los idiomas de operador automático para audioconferencias en Skype for Business Online

> [!Note]
> Para obtener información acerca de cómo establecer el idioma de operador automático en Microsoft Teams, vea [Establecer idiomas de operador automático para audioconferencias en Microsoft Teams](/MicrosoftTeams/set-auto-attendant-languages-for-audio-conferencing-in-teams).

El operador automático de audioconferencias de Skype for Business puede saludar a los autores de llamadas de audioconferencias en un número de diferentes idiomas cuando se unan a una reunión.
  
Choose one primary language and up to four secondary languages. The primary language that you set will be used first and the secondary languages will be used by the auto-attendant in order that you select. 
  
> [!NOTE]
>  Solo puede cambiar los idiomas de los números de audioconferencia que son de la categoría Dedicado. Los idiomas del número de audioconferencia compartida no se pueden cambiar.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Configurar la conferencia de idiomas de operador automático

Debe ser administrador [global o administrador](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) de Skype [Empresarial](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) para realizar este paso.
    
1. En el **Centro de administración de Skype Empresarial,** en el panel de navegación izquierdo, vaya al portal **heredado.** Una vez en el portal heredado, **seleccione Audioconferencia** y, a continuación, haga clic en **puente de Microsoft.**
    
2. Seleccione el número de teléfono de audioconferencia de la lista y, en el panel de acciones, haga clic **en Establecer idiomas.** Solo es posible cambiar los idiomas de los números de audioconferencia dedicados.  
    
3. En la **página Establecer idiomas,** haga clic en la **lista Idioma** principal para ver la lista completa de idiomas disponibles. Si es necesario, haga clic en cada una de las listas de **idiomas** secundarios para seleccionar un idioma secundario.
    
    > [!NOTE]
    > Se enumeran el idioma principal y los secundarios que son compatibles. El orden en que los seleccione en las listas será el orden de los idiomas que se presentan a los autores de llamadas. 
  
4. Haga clic en **Guardar**.
    
## <a name="want-else-should-i-know"></a>¿Qué más debo saber?

- Para ver la lista de los idiomas admitidos para audioconferencia, vea [Idiomas admitidos en audioconferencia](/MicrosoftTeams/audio-conferencing-supported-languages).
    
- Los idiomas se pueden establecer para números de teléfono dedicados, pero no para compartidos.
    
- Para ver una lista de países o regiones en los que Audioconferencia en Microsoft 365 [](phone-numbers-for-audio-conferencing.md)u Office 365 mediante Microsoft como el proveedor está disponible, consulte Números de teléfono para Audioconferencia.
    
## <a name="want-to-use-windows-powershell"></a>¿Desea usar Windows PowerShell?

Para automatizar este paso, puede usar los [cmdlets Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) y [Get-CsOnlineDialInConferencingLanguagesSupported.](https://go.microsoft.com/fwlink/?LinkId=617684)
  
Para obtener más información, consulte [Uso de Windows PowerShell para realizar tareas](https://go.microsoft.com/fwlink/?LinkId=525038) de administración comunes de Skype Empresarial Online
  
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Microsoft 365 u Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
