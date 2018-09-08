---
title: Iniciar una conferencia de Audio a través del teléfono sin un PIN en Microsoft Teams
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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtenga información sobre cómo habilitar o deshabilitar los autores de llamadas anónimas se unan a una reunión desde el centro de administración de equipos. '
ms.openlocfilehash: c68e3a0bd9992eb53811941113a30e9362c78227
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883002"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Iniciar una conferencia de Audio a través del teléfono sin un PIN en Microsoft Teams

Puede resultar frustrante para los usuarios que se conectan a una reunión a permanecer en la sala de espera de la reunión de escucha música debido a que el organizador de la reunión Teams Microsoft no ha comenzado la reunión. 
  
Si llama a un organizador de la reunión la reunión, de forma predeterminada, se requiere un PIN para iniciar una reunión. Se puede configurarla para que cualquier persona puede conectarse a una reunión y no se le pida un PIN iniciar la reunión. Puede usar el centro de administración para habilitar o deshabilitar a esta configuración para un único usuario.
  
Un PIN no es necesario para el organizador de la reunión si alguien ha iniciado la conferencia desde la aplicación Microsoft Teams. El PIN solo será necesario si el organizador de la reunión se une a ella desde un teléfono. El PIN para las reuniones se envía al usuario audio cuando se asignan a la licencia de **Conferencias de Audio** y están habilitados para conferencias de Audio. Vea [Enviar un correo electrónico a un usuario con su información de conferencia de Audio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) y [mensajes de correo electrónico que se envían automáticamente a los usuarios al cambia su configuración de conferencias de Audio](emails-sent-to-users-when-their-settings-change-in-teams.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Habilitar o deshabilitar la posibilidad de que los autores de llamada anónimos se unan a la reunión

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

1. En el panel de navegación izquierdo, haga clic en **usuarios**. 

2. Seleccione un usuario en la lista y, a continuación, haga clic en **Editar** en la parte superior de la página. 

3. Junto a **Conferencias de Audio**, haga clic en **Editar**.

4. En el panel de **Conferencia de Audio** , habilitar o deshabilitar **los autores de llamadas sin autenticar pueden ser la primera persona en una reunión**.
    
4. Haga clic en **Guardar**. 

**Uso de Windows Powershell**
  
Vea la [referencia de PowerShell de los equipos de Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.

## <a name="what-else-should-you-know"></a>¿Qué más tengo que saber?

- Si desea restablecer el PIN, consulte [Restablecer el PIN de conferencia de Audio](reset-the-audio-conferencing-pin-in-teams.md).
    
- Si está habilitado el acceso anónimo o que no requiere un PIN iniciar una reunión:
    
  - Si no ha comenzado la reunión (hay nadie en la reunión todavía): un autor de la llamada se preguntará si es el organizador; Si contesta Sí, se pedirá para su PIN y después de que escribe el NIP, se iniciará la reunión y el usuario se unirá a la reunión.
    
  - Si la reunión ya ha iniciado (otro usuario ya está en la reunión): un autor de la llamada no se le pida si es el organizador y nunca se solicitará el PIN; ya se ha iniciado la reunión, y el autor de la llamada se unirá a.
    
- Si se deshabilita el acceso anónimo o que no requiere un PIN iniciar una reunión:
    
  - Si no ha comenzado la reunión (hay nadie en la reunión todavía): un autor de la llamada no se le pida si es el organizador y nunca se pedirá el PIN. Debido a que la configuración del organizador se establece en off, se iniciará la reunión y los llamadores anónimos se unirá a la reunión.
    
  - Si la reunión ya ha iniciado (otro usuario ya está en la reunión): un autor de la llamada no se le pida si es el organizador y nunca se pedirá el PIN, ya se ha iniciado la reunión y el autor de la llamada se unirá a.
    
## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obtener más información acerca de Windows PowerShell, vea la [referencia de PowerShell de los equipos de Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.
  
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
