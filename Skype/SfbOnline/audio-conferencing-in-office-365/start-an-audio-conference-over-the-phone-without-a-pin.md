---
title: Iniciar una conferencia de audio a través del teléfono sin un PIN en Skype empresarial online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. '
ms.openlocfilehash: cfc15835906fbc400830783777027ed7ca1f4e59
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962498"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a>Iniciar una conferencia de audio a través del teléfono sin un PIN en Skype empresarial online

> [!Note]
> Para obtener información sobre cómo iniciar una conferencia de audio sin un PIN en Microsoft Teams, consulte [iniciar una conferencia de audio a través del teléfono sin un PIN en Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).

Es posible que sea frustrante para los usuarios que llaman a una reunión en la sala de espera de la reunión escuchando música porque el organizador de la reunión de Skype empresarial no ha iniciado la reunión. 
  
Si un organizador de la reunión llama a la reunión, de forma predeterminada, se necesita un PIN para iniciar una reunión. Puede configurarlo para que cualquier persona pueda llamar a una reunión y no se le pida un PIN para iniciar la reunión. Puede usar el Centro de administración de Skype Empresarial para habilitar o deshabilitar este parámetro para un solo usuario.
  
Si alguien ha iniciado la reunión desde la aplicación Skype empresarial, no es necesario un PIN para el organizador de la reunión. Un PIN solo es necesario cuando un organizador de la reunión se une a su reunión a través de un teléfono. El PIN para las reuniones se envía al usuario de audio cuando se le asigna la licencia de **audioconferencias** y está habilitado para las conferencias de audio. Consulte [Enviar un correo electrónico a un usuario con la información de la audioconferencia y los](send-an-email-to-a-user-with-their-dial-in-information.md) [correos electrónicos que se envían de forma automática a los usuarios cuando cambia la configuración de audioconferencia](emails-sent-to-users-when-their-settings-change.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Habilitar o deshabilitar la posibilidad de que los autores de llamada anónimos se unan a la reunión
    
1. En el **centro de administración de Skype empresarial**, en el navegación de la izquierda, vaya a**usuarios**de **conferencias** > de audio. 
    
2. En la lista, seleccione el usuario y, en el panel de acciones, haga clic en **Editar**. 
    
3. En la página de propiedades del usuario, en **Opciones de reunión**, Active o desactive permitir que **los autores de llamadas no autenticados sean las primeras personas de una reunión. En caso contrario, esperarán en la sala de espera hasta que se unan un usuario autenticado**.
    
4. Haga clic en **Guardar **. 


    
 **Usar Windows PowerShell**
  
- Ejecute lo siguiente: 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>¿Qué más debe saber?

- Si desea restablecer el PIN, consulte [restablecer el PIN de audioconferencia](reset-the-audio-conferencing-pin.md).
    
- Si el acceso anónimo, o si no necesita un PIN para iniciar una reunión, está deshabilitado:
    
  - Si la reunión no se ha iniciado (todavía no hay nadie en la reunión): se preguntará a una persona que llame si es el organizador. Si dice sí, se le solicitará su PIN y, después de especificar el PIN, la reunión se iniciará y el usuario se unirá a la reunión.
    
  - Si la reunión ya ha comenzado (otra persona ya está en la reunión): no se le pedirá la llamada si es el organizador y nunca se le solicitará el PIN. la reunión ya se ha iniciado y la persona que llama se une.
    
- Si el acceso anónimo, o si no necesita un PIN para iniciar una reunión, está habilitado:
    
  - Si la reunión no se ha iniciado (todavía no hay nadie en la reunión): no se le solicitará al autor de la llamada si es el organizador, y nunca se le pedirá el PIN. Puesto que la configuración del organizador está deshabilitada, la reunión se iniciará y los autores de llamadas anónimos se unirán a la reunión.
    
  - Si la reunión ya ha comenzado (otra persona ya está en la reunión): no se le solicitará una llamada si es el organizador, y nunca se le pedirá el PIN; la reunión ya se ha iniciado, y el autor de la llamada se unirá a ella.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso para más de un usuario, puede usar el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
- Cuando se trata de Windows PowerShell, Skype Empresarial Online se centra en la administración de usuarios y en determinar qué pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tiene varias tareas que realizar. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad en lugar de usar únicamente el centro de administración de Microsoft 365, por ejemplo, cuando está realizando cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes: 
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
