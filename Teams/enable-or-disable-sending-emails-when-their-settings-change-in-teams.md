---
title: Opciones de correo electrónico cuando cambia la configuración de conferencias de audio
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
description: 'Obtenga información sobre cómo habilitar o deshabilitar Skype enviar correos electrónicos a los usuarios cuando la configuración, como los cambios de anclar o el número de conferencia predeterminado, cambie en Microsoft Teams. '
ms.openlocfilehash: 17c2864703eafa2c70709da0381f870abba58ad0
ms.sourcegitcommit: 8c2093f7a048a9a56b36e4a3b4c48ae1206c52f6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2021
ms.locfileid: "53004172"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de Audioconferencia en Microsoft Teams

Los usuarios se notifican automáticamente por correo electrónico cuando están habilitados para las audioconferencias. Sin embargo, puede haber ocasiones en las que quiera reducir el número de correos electrónicos que se envían a Microsoft Teams usuarios. En estos casos, puede deshabilitar el envío de correo electrónico.
  
Si deshabilita el envío de correos electrónicos, los correos electrónicos de audioconferencia no se enviarán a los usuarios, incluidos los correos electrónicos para cuando los usuarios estén habilitados o deshabilitados para las audioconferencias, cuando se restablezca su PIN y cuando cambie el id. de conferencia y el número de teléfono de conferencia predeterminado.
  
Este es un ejemplo del correo electrónico que se envía a los usuarios cuando están habilitados para las audioconferencias:
  
![Ejemplo de un mensaje de correo electrónico de audioconferencia](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>¿Cuándo se envían correos electrónicos a los usuarios?

- Hay varios correos electrónicos que se envían a los usuarios de su organización después de que estén habilitados para las audioconferencias:
    
  - Cuando se les asigna una licencia **de** audioconferencia.
    
  - Cuando restablezca manualmente el PIN de audioconferencia del usuario.
    
  - Al restablecer de forma manual el id. de conferencia del usuario.
    
  - Cuando se **quita la licencia de conferencias** de audio.
    
  - Cuando el proveedor de audioconferencias de un usuario se cambia de Microsoft a otro proveedor o **Ninguno.**
    
  - Cuando el proveedor de audioconferencias de un usuario se cambia a Microsoft.


## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Habilitar o deshabilitar el correo electrónico para que no se envíe a los usuarios

Puede usar Microsoft Teams o Windows PowerShell para habilitar o deshabilitar el correo electrónico enviado a los usuarios.

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la **página Puentes de** conferencia, haga clic en **Configuración de puente.** 

3. En el **panel Configuración de puente,** habilite o deshabilite Enviar mensajes de correo electrónico automáticamente a los usuarios si cambia la configuración **de acceso telefónico.**

4. Haga clic en **Guardar**.

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.
  
También puede usar el módulo Microsoft Teams PowerShell y ejecutar:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

You can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) to manage other settings for your organization, including email.

Vea la [Microsoft Teams referencia de PowerShell](/powershell/module/teams/?view=teams-ps) para obtener más información.

    
## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer. To get started with Windows PowerShell, see these topics:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Temas relacionados

[Correos electrónicos enviados a los usuarios cuando cambian sus opciones de audioconferencia](emails-sent-to-users-when-their-settings-change-in-teams.md)

[Enviar un correo electrónico a un usuario con su información de conferencias de Audio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
