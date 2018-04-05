---
title: Establecer idiomas del operador automático para conferencias de Audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: Vea cómo seleccionar los idiomas operador automático de conferencia de audio para un número de conferencia de audio.
ms.openlocfilehash: 4cd40a54c90559d3886b737b8e9f66f02346358f
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/05/2018
---
# <a name="set-auto-attendant-languages-for-audio-conferencing"></a>Establecer idiomas del operador automático para conferencias de Audio

El operador automático de conferencia de Audio de Skype para empresas y Teams de Microsoft puede saludar a los llamadores audio en varios idiomas diferentes cuando se unen a una reunión.
  
Elegir un idioma principal y hasta cuatro idiomas secundarias. Se utilizará el idioma principal que se establece en primer lugar y los idiomas secundarios se utilizará el operador automático que selecciona. 
  
> [!NOTE]
>  Puede configurar los idiomas en sólo números de teléfono de acceso interno de audio.
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Establecer la conferencia idiomas de operador automático

**Utilizando los equipos de Microsoft y Skype para el centro de administración de negocios**

1. En la exploración de la izquierda, vaya a **reuniones** > **Puentes de conferencia**.

2. Seleccione el número de teléfono de conferencia de audio de la lista y en la parte superior de la página, haga clic en **Editar**.

3. En el panel de la derecha, seleccione el idioma predeterminado que desee y los idiomas alternativos. 
 
    > [!NOTE]
    > Se muestran los predeterminados y los idiomas alternativos compatibles. El orden en el que los seleccione de las listas será el orden de los idiomas que se presenta a los llamadores. 

4. Haga clic en **Aplicar**.

**Usar Skype para el negocio en línea**

Debe ser un [administrador global de Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) o [Skype para la administración de negocios](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) para realizar este paso.
    
1. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.
    
2. Seleccione el número de teléfono de conferencia de audio de la lista y en el panel Acción, haga clic en **idiomas**. 
    
3. En la página **conjunto de idiomas** , haga clic en la lista **idioma principal** para ver la lista completa de idiomas disponibles. Si necesita, haga clic en cada una de las listas **secundarias idiomas** para seleccionar idioma secundario.
    
    > [!NOTE]
    > Se enumeran el idioma principal y los secundarios que son compatibles. El orden en el que los seleccione de las listas será el orden de los idiomas que se presenta a los llamadores. 
  
4. Haga clic en **Guardar**.
    
## <a name="want-else-should-i-know"></a>¿Qué más debo saber?

- Para ver la lista de idiomas admitidos para conferencias de Audio, vea [idiomas compatibles de conferencia de Audio](audio-conferencing-supported-languages.md).
    
- Idiomas pueden establecerse para dedicado pero no compartido para números de teléfono.
    
- Para ver una lista de países o regiones en que están disponibles las conferencias de Audio en Office 365 con Microsoft como proveedor, vea [números de teléfono de conferencia de Audio](phone-numbers-for-audio-conferencing.md).
    
## <a name="want-to-use-windows-powershell"></a>¿Desea usar Windows PowerShell?

Para automatizar este paso, puede usar los cmdlets [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) y de [CsOnlineDialInConferencingServiceNumber del conjunto](https://go.microsoft.com/fwlink/?LinkId=617689) .
  
Para obtener más información, consulte [Uso de Windows PowerShell hacer Skype común para tareas de administración de negocios en línea](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>See also

[Probar o comprar Audioconferencia en Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
