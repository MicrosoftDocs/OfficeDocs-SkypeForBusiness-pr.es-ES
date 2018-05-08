---
title: Establecer idiomas del operador automático para conferencias de Audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Vea cómo seleccionar los idiomas operador automático de conferencia de audio para un número de conferencia de audio.
ms.openlocfilehash: c4461f61ce05afedc2663a3e5b61d37370394cd4
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="set-auto-attendant-languages-for-audio-conferencing"></a>Establecer idiomas del operador automático para conferencias de Audio

El operador automático de conferencia de Audio de Skype para empresas y Microsoft Teams puede saludar a los autores de llamadas de audioconferencias en un número de diferentes idiomas unirse a una reunión.
  
Elegir un idioma principal y hasta cuatro idiomas secundarios. El idioma principal que ha configurado en primer lugar se va a usar y los idiomas secundarios utilizará el operador automático de forma que seleccione. 
  
> [!NOTE]
>  Puede configurar los idiomas en sólo los números de teléfono de acceso nacional de audio.
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Configurar la conferencia de idiomas de operador automático

![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

1. En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**.

2. Seleccione el número de teléfono de conferencia de audio de la lista y, en la parte superior de la página, haga clic en **Editar**.

3. En el panel de la derecha, seleccione el idioma predeterminado que desee y los idiomas alternativos. 
 
    > [!NOTE]
    > Se enumeran los predeterminados y los idiomas alternativos que se admiten. El orden en que los seleccione en las listas de será el orden de los idiomas que se presentan a los autores de llamadas. 

4. Haga clic en **Aplicar**.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **Uso de Skype para la empresa en línea**

Debe ser un [administrador global de Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) o [Skype para administración empresarial](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) para llevar a cabo este paso.
    
1. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.
    
2. Seleccione el número de teléfono de conferencia de audio de la lista y, en el panel de acciones, haga clic en **conjunto de idiomas**. 
    
3. En la página **conjunto de idiomas** , haga clic en la lista **idioma principal** para ver la lista completa de idiomas disponibles. Si necesita, haga clic en cada una de las listas de **idiomas secundarios** para seleccionar idioma secundario.
    
    > [!NOTE]
    > Se enumeran el idioma principal y los secundarios que son compatibles. El orden en que los seleccione en las listas de será el orden de los idiomas que se presentan a los autores de llamadas. 
  
4. Haga clic en **Guardar**.
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-else-should-i-know"></a>¿Qué más debo saber?

- Para ver la lista de idiomas admitidos para conferencias de Audio, vea [idiomas admitidos de conferencias de Audio](audio-conferencing-supported-languages.md).
    
- Idiomas se pueden establecer para dedicada, pero no para los números de teléfono compartida.
    
- Para ver una lista de países o regiones en la que está disponible en Office 365 con Microsoft como proveedor de conferencia, vea [los números de teléfono para conferencias de Audio](phone-numbers-for-audio-conferencing.md).
    
## <a name="want-to-use-windows-powershell"></a>¿Desea usar Windows PowerShell?

Para automatizar este paso, puede usar los cmdlets [Set-CsOnlineDialInConferencingServiceNumber](https://go.microsoft.com/fwlink/?LinkId=617689) y [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) .
  
Para obtener más información, vea [Uso de Windows PowerShell para hacer Skype comunes para las tareas de administración en línea de negocio](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>See also

[Probar o comprar Audioconferencia en Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
