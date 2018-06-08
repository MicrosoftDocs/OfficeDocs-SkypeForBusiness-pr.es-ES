---
title: Iniciar una conferencia de Audio a través del teléfono sin un PIN
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
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
description: 'Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. '
ms.openlocfilehash: 8abdd9bcd61c55c7d55d896feef36afed22b312f
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703478"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin"></a>Iniciar una conferencia de Audio a través del teléfono sin un PIN

Puede resultar frustrante para los usuarios que se conectan a una reunión a permanecer en la sala de espera de la reunión de escucha música porque la Skype para el organizador de la reunión empresarial o Teams de Microsoft no ha comenzado la reunión. 
  
Si llama a un organizador de la reunión la reunión, de forma predeterminada, se requiere un PIN para iniciar una reunión. Se puede configurarla para que cualquier persona puede conectarse a una reunión y no se le pida un PIN iniciar la reunión. Puede usar el Centro de administración de Skype Empresarial para habilitar o deshabilitar este parámetro para un solo usuario.
  
Un PIN no es necesario para el organizador de la reunión si alguien ha iniciado la conferencia desde una Skype para aplicación empresarial o Teams de Microsoft. El PIN solo será necesario si el organizador de la reunión se une a ella desde un teléfono. El PIN para las reuniones se envía al usuario audio cuando se asignan a la licencia de **Conferencias de Audio** y están habilitados para conferencias de Audio. Vea [Enviar un correo electrónico a un usuario con su información de conferencia de Audio](send-an-email-to-a-user-with-their-dial-in-information.md) y [mensajes de correo electrónico que se envían automáticamente a los usuarios al cambia su configuración de conferencias de Audio](emails-sent-to-users-when-their-settings-change.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Habilitar o deshabilitar la posibilidad de que los autores de llamada anónimos se unan a la reunión

![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

1. En el panel de navegación izquierdo, haga clic en **usuarios**. 

2. Seleccione un usuario en la lista y, a continuación, haga clic en **Editar** en la parte superior de la página. 

3. Haga clic en el menú situado junto a **Puentes de conferencia**y, a continuación, haga clic en **Editar**.

4. En el panel de **proveedor de puente de conferencia** , habilitar o deshabilitar los autores de llamadas de **Permitir no autenticado para que sea el primer personas en una reunión. Si no, a continuación, esperará en la sala de espera hasta que un usuario autenticado se une a**.
    
4. Haga clic en **Aplicar**. 

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**
    
1. En el **Skype para el centro de administración de negocio**, en el panel de navegación izquierdo, vaya a la **conferencia de Audio** > **a los usuarios**. 
    
2. En la lista, seleccione el usuario y en el panel de acciones, haga clic en **Editar**. 
    
3. En la página de propiedades del usuario, en **Opciones de reunión**, active o desactive los autores de llamadas de **Permitir no autenticado para que sea el primer personas en una reunión. Si no, a continuación, esperará en la sala de espera hasta que un usuario autenticado se une a**.
    
4. Haga clic en **Guardar**. 


    
 **Uso de Windows Powershell**
  
- Ejecute lo siguiente: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a>¿Qué más debe saber?

- Si desea restablecer el PIN, consulte [Restablecer el PIN de conferencia de Audio](reset-the-audio-conferencing-pin.md).
    
- Si está habilitado el acceso anónimo o que no requiere un PIN iniciar una reunión:
    
  - Si no ha comenzado la reunión (hay nadie en la reunión todavía): un autor de la llamada se preguntará si es el organizador; Si contesta Sí, se pedirá para su PIN y después de que escribe el NIP, se iniciará la reunión y el usuario se unirá a la reunión.
    
  - Si la reunión ya ha iniciado (otro usuario ya está en la reunión): un autor de la llamada no se le pida si es el organizador y nunca se solicitará el PIN; ya se ha iniciado la reunión, y el autor de la llamada se unirá a.
    
- Si se deshabilita el acceso anónimo o que no requiere un PIN iniciar una reunión:
    
  - Si no ha comenzado la reunión (hay nadie en la reunión todavía): un autor de la llamada no se le pida si es el organizador y nunca se pedirá el PIN. Debido a que la configuración del organizador se establece en off, se iniciará la reunión y los llamadores anónimos se unirá a la reunión.
    
  - Si la reunión ya ha iniciado (otro usuario ya está en la reunión): un autor de la llamada no se le pida si es el organizador y nunca se pedirá el PIN, ya se ha iniciado la reunión y el autor de la llamada se unirá a.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Para ahorrar tiempo o automatizar este proceso para más de un usuario, puede usar el cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
-  Cuando se trata de Windows PowerShell, Skype Empresarial Online se centra en la administración de usuarios y en determinar qué pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tiene varias tareas que realizar. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics: 
    
  - [Introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>See also

[Probar o comprar Audioconferencia en Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
