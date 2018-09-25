---
title: Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de Audioconferencia en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Aprenda a habilitar o deshabilitar a Skype para enviar correos electrónicos a los usuarios cuando cambien opciones de configuración, como el PIN, o cambie el número de conferencia predeterminado en Microsoft Teams. '
ms.openlocfilehash: 2c082410f7acf000473e001f46587025edd6e9c7
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25015544"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de Audioconferencia en Microsoft Teams

Cuando están habilitados para conferencias de Audio, se notificación automáticamente a los usuarios por correo electrónico. Puede haber ocasiones, sin embargo, cuando desea reducir el número de mensajes de correo electrónico que se envían a los usuarios de Microsoft Teams. En estos casos, puede deshabilitar el envío de correo electrónico.
  
Si deshabilita el envío de correos electrónicos, no se enviará ningún correo de Audioconferencia a los usuarios, incluidos los correos electrónicos para cuando se habilite o deshabilite a los usuarios para participar en audioconferencias, cuando se restablezca su código PIN o cuando cambie el Id. de conferencia y el número de teléfono de conferencia predeterminado.
  
A continuación se muestra un ejemplo del correo electrónico que se envía a los usuarios cuando se les habilita para Audioconferencia:
  
![Correo electrónico de Audioconferencia](media/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>¿Cuándo se envían correos electrónicos a los usuarios?

- Existen diversos correos electrónicos que se envían a los usuarios de su organización una vez que se han habilitado para la audioconferencia:
    
  - Cuando se les asigna una licencia de **Audioconferencia**.
    
  - Al restablecer de forma manual el PIN de audioconferencia del usuario.
    
  - Al restablecer de forma manual el Id. de conferencia del usuario.
    
  - Cuando se elimina la licencia de **Audioconferencia** para el usuario.
    
  - Cuando el proveedor de servicios de audioconferencia de un usuario se cambia de Microsoft a otro proveedor o a **Ninguno**.
    
  - Cuando el proveedor de servicios de audioconferencia de un usuario se cambia a Microsoft.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Habilitar o deshabilitar que el correo electrónico se envíe a los usuarios

Para habilitar o deshabilitar el envío de correos electrónicos a los usuarios se utiliza Microsoft Teams o Windows PowerShell.

![teams-logo-30x30.png](media/teams-logo-30x30.png) **Mediante el Centro de administración de Skype for Business y Microsoft Teams:**
1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página **Puentes de conferencia**, haga clic en **Configuración de puente**. 

3. En el panel **Configuración de puente**, habilite o deshabilite **Enviar automáticamente correos electrónicos a los usuarios si se produce algún cambio en la configuración del acceso telefónico local**.

4. Haga clic en **Guardar**.

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Uso de Windows PowerShell**
  
Vea la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.

    
## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Temas relacionados

[Correos electrónicos que se envían a los usuarios cuando cambia la configuración de Audioconferencia](emails-sent-to-users-when-their-settings-change-in-teams.md)

[Enviar un correo electrónico a un usuario con su información de conferencias de Audio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


