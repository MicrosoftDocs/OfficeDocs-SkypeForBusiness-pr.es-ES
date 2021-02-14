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
ms.openlocfilehash: f02d458450f07b64f3daf4d23b1c56aa2bb846a3
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163879"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a>Iniciar una audioconferencia por teléfono sin un PIN en Skype Empresarial Online

> [!Note]
> Para obtener información sobre cómo iniciar una audioconferencia sin un PIN en Microsoft Teams, consulte Iniciar una audioconferencia por teléfono sin [un PIN en Microsoft Teams.](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams)

Puede resultar frustrante para los usuarios que la llamada a una reunión se celebre en la sala de espera de la reunión escuchando música porque el organizador de la reunión de Skype Empresarial no ha iniciado la reunión. 
  
Si un organizador de la reunión llama a la reunión, de forma predeterminada, se necesita un PIN para iniciarla. Puede configurarlo para que cualquiera pueda llamar a una reunión y no se le pida un PIN para iniciarla. Puede usar el Centro de administración de Skype Empresarial para habilitar o deshabilitar este parámetro para un solo usuario.
  
No es necesario un PIN para el organizador de la reunión si alguien ha iniciado la reunión desde la aplicación skype empresarial. Solo es necesario un PIN cuando un organizador de la reunión se une a la reunión por teléfono. El PIN para las reuniones se envía al usuario de audio cuando se le asigna la licencia de **Audioconferencia** y se habilita para Audioconferencia. Vea Enviar un correo electrónico a un usuario con su información de [Audioconferencia](send-an-email-to-a-user-with-their-dial-in-information.md) y correos electrónicos que se envían automáticamente a los usuarios cuando cambia su configuración [de Audioconferencia.](emails-sent-to-users-when-their-settings-change.md)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Habilitar o deshabilitar la posibilidad de que los autores de llamada anónimos se unan a la reunión
    
1. En el **Centro de administración de Skype Empresarial,** en el panel de navegación izquierdo, vaya a Usuarios de **Audioconferencia.**  >   
    
2. En la lista, seleccione el usuario y, en el panel de acciones, haga clic en **Editar.** 
    
3. En la página de propiedades del usuario, en Opciones de **reunión,** active o desactive Permitir que los autores de llamadas no autenticados sean las primeras personas **de una reunión. Si no es así, esperarán en la sala de espera hasta** que se una un usuario autenticado.
    
4. Haga clic en **Guardar**. 


    
 **Usar Windows PowerShell**
  
- Ejecute lo siguiente: 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>¿Qué más debe saber?

- Si desea restablecer el PIN, consulte Restablecer el PIN de [Audioconferencia.](reset-the-audio-conferencing-pin.md)
    
- Si el acceso anónimo, o no requerir un PIN para iniciar una reunión, está deshabilitado:
    
  - Si la reunión no ha empezado (aún no hay ningún usuario en la reunión): se le preguntará al autor de la llamada si es el organizador; si dice que sí, se le pedirá su PIN y, después de introducir el PIN, la reunión se iniciará y el usuario se unirá a la reunión.
    
  - Si la reunión ya se ha iniciado (otra persona ya está en la reunión): no se le preguntará al autor de la llamada si es el organizador y nunca se le solicitará el PIN. la reunión ya está iniciada y el autor de la llamada se unirá a ella.
    
- Si el acceso anónimo, o no requerir un PIN para iniciar una reunión, está habilitado:
    
  - Si la reunión no ha empezado (todavía no hay ningún usuario en la reunión): no se le preguntará al autor de la llamada si es el organizador y nunca se le solicitará el PIN. Como la configuración del organizador está desactivada, la reunión se iniciará y los autores de llamadas anónimos se unirán a ella.
    
  - Si la reunión ya se ha iniciado (otra persona ya está en la reunión): no se le preguntará al autor de la llamada si es el organizador y nunca se le solicitará el PIN; la reunión ya se ha iniciado y la persona que llama se unirá a ella.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso para más de un usuario, puede usar el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
- Cuando se trata de Windows PowerShell, Skype Empresarial Online se centra en la administración de usuarios y en determinar qué pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tenga que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [¿Por qué necesita usar Microsoft 365 u Office 365 PowerShell?](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell cuenta con muchas ventajas en velocidad, simplicidad y productividad con respecto al uso solo del Centro de administración de Microsoft 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes: 
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Microsoft 365 u Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
