---
title: Iniciar una audioconferencia por teléfono sin un PIN en Skype Empresarial Online
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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. '
ms.openlocfilehash: 655f61c449554a9044095a5b8ef8bd8ef2940bc4
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237596"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a>Iniciar una audioconferencia por teléfono sin un PIN en Skype Empresarial Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Para obtener información sobre cómo iniciar una conferencia de audio sin un PIN en Microsoft Teams, vea Iniciar una conferencia de audio por teléfono sin [un PIN](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams)en Microsoft Teams .

Puede ser frustrante que los usuarios que llamen a una reunión se celebre en la sala de espera de la reunión escuchando música porque el organizador de la reunión de Skype Empresarial no ha iniciado la reunión. 
  
Si un organizador de la reunión llama a la reunión, de forma predeterminada, se requiere un PIN para iniciar una reunión. Puede configurarlo para que cualquier persona pueda llamar a una reunión y no se le pida un PIN para iniciar la reunión. Puede usar el Centro de administración de Skype Empresarial para habilitar o deshabilitar este parámetro para un solo usuario.
  
No es necesario un PIN para el organizador de la reunión si alguien ha iniciado la reunión desde la aplicación Skype Empresarial reunión. El PIN solo será necesario si el organizador de la reunión se une a ella desde un teléfono. El PIN de las reuniones se envía al usuario de audio cuando se les asigna la licencia de **conferencias** de audio y se habilitan para conferencias de audio. Vea [Enviar un correo electrónico a](send-an-email-to-a-user-with-their-dial-in-information.md) un usuario con su información de audioconferencia y Correos electrónicos que se envían automáticamente a los usuarios cuando cambia la configuración de audioconferencia. [](emails-sent-to-users-when-their-settings-change.md)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Habilitar o deshabilitar la posibilidad de que los autores de llamada anónimos se unan a la reunión
    
1. En el **Skype Empresarial de administración**, en el panel de navegación izquierdo, vaya a Usuarios de **audioconferencia.**  >   
    
2. En la lista, seleccione el usuario y, en el panel de acciones, haga clic **en Editar.** 
    
3. En la página de propiedades del usuario, en Opciones de **reunión,** seleccione o desactive Permitir que los autores de llamadas no autenticados sean los primeros en **una reunión. Si no es así, esperarán en** la sala de espera hasta que se una un usuario autenticado.
    
4. Haga clic en **Guardar**. 


    
 **Usar Windows Powershell**
  
- Ejecute lo siguiente: 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>¿Qué más debe saber?

- Si desea restablecer el PIN, vea [Restablecer el PIN de audioconferencia.](reset-the-audio-conferencing-pin.md)
    
- Si el acceso anónimo o no requiere un PIN para iniciar una reunión, está deshabilitado:
    
  - Si la reunión no se ha iniciado (todavía no hay nadie en la reunión): se le pedirá a un autor de la llamada si es el organizador; si dice que sí, se le pedirá su PIN y, después de introducir el PIN, se iniciará la reunión y el usuario se unirá a la reunión.
    
  - Si la reunión ya se ha iniciado (otra persona ya está en la reunión): no se le pedirá a un autor de la llamada si es el organizador y nunca se le pedirá el PIN; la reunión ya está iniciada y el autor de la llamada se unirá a ella.
    
- Si el acceso anónimo o no requiere un PIN para iniciar una reunión, está habilitado:
    
  - Si la reunión no se ha iniciado (todavía no hay nadie en la reunión): no se le pedirá a una persona que llame si es el organizador y nunca se le pedirá el PIN. Como la configuración del organizador está desactivada, la reunión se iniciará y los autores de llamadas anónimos se unirán a la reunión.
    
  - Si la reunión ya se ha iniciado (otra persona ya está en la reunión): no se le pedirá a una persona que llame si es el organizador y nunca se le pedirá el PIN; la reunión ya está iniciada y el autor de la llamada se unirá a ella.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso para más de un usuario, puede usar el cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).
    
- Cuando se trata de Windows PowerShell, Skype Empresarial Online se centra en la administración de usuarios y en determinar qué pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer. Para empezar con Windows PowerShell, vea estos temas:
    
  - [¿Por qué necesita usar Microsoft 365 o Office 365 PowerShell?](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad en comparación con el uso del centro de administración de Microsoft 365, por ejemplo, cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes: 
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [Usar Windows PowerShell para administrar Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Temas relacionados

[Pruebe o compre Audioconferencia en Microsoft 365 o Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
