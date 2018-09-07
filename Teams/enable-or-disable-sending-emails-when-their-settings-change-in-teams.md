---
title: Habilitar o deshabilitar el envío de los correos electrónicos al cambia configuración de conferencia de Audio en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtenga información sobre cómo habilitar o deshabilitar Skype de envío de mensajes de correo electrónico a los usuarios cuando cambie la configuración como pin o los cambios de número de conferencia de forma predeterminada en Microsoft Teams. '
ms.openlocfilehash: 5d18d039c379bb56a861ba6f6a36d23f301150b4
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861894"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Habilitar o deshabilitar el envío de los correos electrónicos al cambia configuración de conferencia de Audio en Microsoft Teams

Cuando están habilitados para conferencias de Audio, se notificación automáticamente a los usuarios por correo electrónico. Puede haber ocasiones, sin embargo, cuando desea reducir el número de mensajes de correo electrónico que se envían a los usuarios de Microsoft Teams. En estos casos, puede deshabilitar el envío de correo electrónico.
  
Si se deshabilitación el envío de los correos electrónicos, mensajes de correo electrónico de conferencia de Audio no se enviará a los usuarios, incluidos los correos electrónicos para cuando los usuarios se habilitan o deshabilitan para conferencias de audio, cuando se restablezca su NIP y cuando el identificador de conferencia y la conferencia predeterminado cambios del número de teléfono .
  
Este es un ejemplo del correo electrónico que se envía a los usuarios cuando están habilitados para conferencias de Audio:
  
![Correo electrónico de conferencia audio](media/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>¿Cuándo se envían correos electrónicos a los usuarios?

- Hay varios correos electrónicos que se envían a los usuarios de su organización después de que están habilitados para conferencias de audio:
    
  - Cuando se asigna una licencia de **Conferencias de Audio** a ellos.
    
  - Al restablecer manualmente PIN de conferencia de audio del usuario.
    
  - Al restablecer de forma manual el id. de conferencia del usuario.
    
  - Cuando la licencia de **Conferencias de Audio** se quita de ellos.
    
  - Cuando se cambia el proveedor de conferencia de audio de un usuario de Microsoft a otro proveedor o **Ninguno**.
    
  - Cuando se cambia el proveedor de conferencia de audio de un usuario a Microsoft.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Habilitar o deshabilitar el correo electrónico no se envía a los usuarios

Puede usar Microsoft Teams o Windows PowerShell para habilitar o deshabilitar el correo electrónico enviado a los usuarios.

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**
1. En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página de **Puentes de conferencia** , haga clic en **configuración de puente**. 

3. En el panel **configuración de puente** , habilitar o deshabilitar **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de acceso telefónico**.

4. Haga clic en **Guardar**.

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.**
  
Vea la [referencia de PowerShell de los equipos de Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.

    
## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obtener más información acerca de Windows PowerShell, vea la [referencia de PowerShell de los equipos de Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.
    
  
## <a name="related-topics"></a>Temas relacionados

[Correos electrónicos enviados a los usuarios cuando cambie su configuración de conferencias de Audio](emails-sent-to-users-when-their-settings-change-in-teams.md)

[Enviar un correo electrónico a un usuario con su información de conferencias de Audio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


