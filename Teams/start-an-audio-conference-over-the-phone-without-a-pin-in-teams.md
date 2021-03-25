---
title: Iniciar audioconferencia por teléfono sin un PIN en Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Obtenga información sobre cómo habilitar o deshabilitar a los autores de llamadas anónimos para que no se unan a una reunión desde el Centro de administración de Teams. '
ms.openlocfilehash: 520bf720a01a686a103748cdbbf26cb8426e94f2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116968"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a>Iniciar una audioconferencia por teléfono sin PIN en Microsoft Teams

Puede ser frustrante que los usuarios que llamen a una reunión se celebre en la sala de espera de la reunión escuchando música porque el organizador de la reunión de Microsoft Teams no ha iniciado la reunión. 
  
Si un organizador de la reunión llama a la reunión, de forma predeterminada, se requiere un PIN para iniciar una reunión. Puede configurarlo para que cualquier persona pueda llamar a una reunión y no se le pida un PIN para iniciar la reunión. Puede usar el Centro de administración para habilitar o deshabilitar esta configuración para un solo usuario.
  
No se requiere un PIN para el organizador de la reunión si alguien ha iniciado la reunión desde la aplicación de Microsoft Teams. El PIN solo será necesario si el organizador de la reunión se une a ella desde un teléfono. El PIN de las reuniones se envía al usuario de audio cuando se les asigna la licencia de **conferencias** de audio y se habilitan para conferencias de audio. Vea [Enviar un correo electrónico a](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) un usuario con su información de audioconferencia y Correos electrónicos que se envían automáticamente a los usuarios cuando cambia la configuración de audioconferencia. [](emails-sent-to-users-when-their-settings-change-in-teams.md)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a>Habilitar o deshabilitar la posibilidad de que los autores de llamada anónimos se unan a la reunión

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**

1. En el panel de navegación izquierdo, haga clic en **Usuarios.** 

2. Seleccione un usuario en la lista y, a continuación, haga clic **en Editar** en la parte superior de la página. 

3. Junto a **Audioconferencia,** haga clic en **Editar.**

4. En el **panel Audioconferencia,** habilitar o deshabilitar las llamadas de acceso telefónico local puede ser la primera persona **de una reunión.**
    
4. Haga clic en **Aplicar**. 

Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.
  
Vea la [referencia de PowerShell de Microsoft Teams](/powershell/module/teams/?view=teams-ps) para obtener más información.

## <a name="what-else-should-you-know"></a>¿Qué más debe saber?

- Si desea restablecer el PIN, vea [Restablecer el PIN de audioconferencia.](reset-the-audio-conferencing-pin-in-teams.md)
    
- Si el acceso anónimo o no requiere un PIN para iniciar una reunión, está deshabilitado:
    
  - Si la reunión no se ha iniciado (todavía no hay nadie en la reunión): se le pedirá a un autor de la llamada si es el organizador; si dice que sí, se le pedirá su PIN y, después de introducir el PIN, se iniciará la reunión y el usuario se unirá a la reunión.
    
  - Si la reunión ya se ha iniciado (otra persona ya está en la reunión): no se le pedirá a un autor de la llamada si es el organizador y nunca se le pedirá el PIN; la reunión ya está iniciada y el autor de la llamada se unirá a ella.
    
- Si el acceso anónimo o no requiere un PIN para iniciar una reunión, está habilitado:
    
  - Si la reunión no se ha iniciado (todavía no hay nadie en la reunión): no se le pedirá a una persona que llame si es el organizador y nunca se le pedirá el PIN. Como la configuración del organizador está desactivada, la reunión se iniciará y los autores de llamadas anónimos se unirán a la reunión.
    
  - Si la reunión ya se ha iniciado (otra persona ya está en la reunión): no se le pedirá a una persona que llame si es el organizador y nunca se le pedirá el PIN; la reunión ya está iniciada y el autor de la llamada se unirá a ella.
    
## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 mediante un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer. To get started with Windows PowerShell, see these topics:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar audioconferencias en Microsoft 365 u Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)