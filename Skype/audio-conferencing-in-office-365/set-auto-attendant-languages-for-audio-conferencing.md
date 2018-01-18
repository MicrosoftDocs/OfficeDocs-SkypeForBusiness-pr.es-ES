---
title: "Configurar idiomas de operador automático para conferencias de Audio"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 26d73dda-ab26-4af4-8aec-d17f3479ae50
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Vea cómo seleccionar los idiomas operador automático de conferencia de audio para un número de conferencia de audio."
ms.openlocfilehash: 1c6b5acda947b97d7bbfbd5888159b48bf5e95aa
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="set-auto-attendant-languages-for-audio-conferencing"></a>Configurar idiomas de operador automático para conferencias de Audio

El operador automático de conferencia de Audio de Skype para empresas y Teams de Microsoft puede saludar a los llamadores audio en varios idiomas diferentes cuando se unen a una reunión.
  
Elegir un idioma principal y hasta cuatro idiomas secundarias. Se utilizará el idioma principal que se establece en primer lugar y los idiomas secundarios se utilizará el operador automático que selecciona. 
  
> [!NOTE]
>  Puede configurar los idiomas en sólo números de teléfono de acceso interno de audio.
  
## <a name="set-the-conferencing-auto-attendant-languages"></a>Establecer la conferencia idiomas de operador automático

Debe ser un [administrador global de Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) o [Skype para la administración de negocios](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) para realizar este paso.
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio**y, a continuación, haga clic en **puente de Microsoft**.
    
4. Seleccione el número de teléfono de conferencia de audio de la lista y en el panel Acción, haga clic en **idiomas**. 
    
5. En la página **conjunto de idiomas** , haga clic en la lista **idioma principal** para ver la lista completa de idiomas disponibles. Si necesita, haga clic en cada una de las listas **secundarias idiomas** para seleccionar idioma secundario.
    
    > [!NOTE]
    > Se enumeran los idiomas primarios y secundarios que son compatibles. El orden en el que los seleccione de las listas será el orden de los idiomas que se presenta a los llamadores. 
  
6. Haga clic en **Guardar**.
    
## <a name="want-else-should-i-know"></a>¿Desea otra cosa que debo saber?

- Para ver la lista de idiomas admitidos para conferencias de Audio, vea [idiomas compatibles de conferencia de Audio](audio-conferencing-supported-languages.md).
    
- Idiomas pueden establecerse para dedicado pero no compartido para números de teléfono.
    
- Para ver una lista de países o regiones en que están disponibles las conferencias de Audio en Office 365 con Microsoft como proveedor, vea [números de teléfono de conferencia de Audio](phone-numbers-for-audio-conferencing.md).
    
## <a name="want-to-use-windows-powershell"></a>¿Desea usar Windows PowerShell?

Para automatizar este paso, puede usar los cmdlets [Get-CsOnlineDialInConferencingLanguagesSupported](https://go.microsoft.com/fwlink/?LinkId=617684) y de [CsOnlineDialInConferencingServiceNumber del conjunto](https://go.microsoft.com/fwlink/?LinkId=617689) .
  
Para obtener más información, consulte [Uso de Windows PowerShell hacer Skype común para tareas de administración de negocios en línea](https://go.microsoft.com/fwlink/?LinkId=525038)
  
## <a name="related-topics"></a>Temas relacionados

[Configurar Audioconferencia para Skype Empresarial y Microsoft Teams](set-up-audio-conferencing.md)

