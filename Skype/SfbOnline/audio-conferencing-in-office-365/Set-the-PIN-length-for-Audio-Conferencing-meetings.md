---
title: Establecer la longitud del perno para las reuniones de conferencia de Audio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: Learn the parameters for the length and requirements of a PIN and see how to set the length for meetings in Skype for Business.
ms.openlocfilehash: d8e6073bd60612131e54e10be6498370d8dfe3bb
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/05/2018
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings"></a>Establecer la longitud del perno para las reuniones de conferencia de Audio

Cuando se configure conferencias de audio por Skype para negocios o Teams de Microsoft, obtendrá un puente de conferencia de audio. Un puente de conferencia puede contener uno o más números de teléfono. Establece el número de teléfono se incluyen en las invitaciones de la reunión de Skype para aplicaciones de negocios y Teams de Microsoft.
  
El puente de conferencia de audio responde a una llamada para las personas que llaman a una reunión mediante un teléfono. Responde al llamador con indicaciones de voz de un operador automático y a continuación, dependiendo de la configuración, puede reproducir las notificaciones y solicitar los llamadores para registrar su nombre. **Configuración de puente de Microsoft** le permiten cambiar la configuración de notificaciones de la reunión y unirse a la experiencia de la reunión y establecer la longitud de las clavijas que son utilizados por los organizadores de la reunión. Organizadores de reuniones Utilice pines para iniciar reuniones si ellos no pueden unirse a la reunión mediante el Skype para la aplicación de negocios o Teams de Microsoft.
  
## <a name="setting-the-pin-length"></a>Configurar la longitud del PIN

**Utilizando los equipos de Microsoft y Skype para el centro de administración de negocios**

1. En la exploración de la izquierda, vaya a **reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página **Puentes de conferencia** , haga clic en **Configuración de puente**. 

3. En el panel de **configuración de puente** , en **longitud PIN**, seleccione el número de dígitos que desee para el PIN.

4. Haga clic en **Aplicar**.

Puede usar el Centro de administración de Skype Empresarial o Windows PowerShell para habilitar o deshabilitar el envío de correos electrónicos a los usuarios.
 
1. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.
    
2. En **seguridad** > **longitud PIN**, seleccione el número de dígitos que desee para el PIN y, a continuación, haga clic en **Guardar**.
    
> [!NOTE]
> Un PIN no es lo mismo que un identificador de conferencia. Los autores de llamada usan los identificadores de conferencia al unirse a la reunión. Se utilizan para identificar la reunión. El PIN se usa para autenticar un autor de llamada como organizador de la reunión. 
  
## <a name="want-to-know-more-about-pin-settings"></a>¿Desea saber más acerca de la configuración de PIN?

- Pines pueden oscilar entre 4 y 12 dígitos; el valor predeterminado es 5. En la creación de un PIN solo pueden usarse números. Por lo tanto, no pueden usarse letras ni caracteres especiales.
    
- Un PIN sólo es necesario para el organizador de la reunión cuando un Skype para usuarios de negocios o Teams de Microsoft ya no ha iniciado la conferencia. Si todas las personas llaman a la reunión, se necesita el PIN para que el organizador de la reunión inicie la reunión.
    
- La configuración de seguridad del PIN se aplica a todos los números de teléfono asociados a un puente de Microsoft, así como a todas las reuniones que usen los números de teléfono asociados a dicho puente. 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso, puede usar el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).
    
- Para establecer el número de dígitos del PIN en 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics: 
    
  - [Introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="see-also"></a>Vea también

[Probar o comprar Audioconferencia en Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
