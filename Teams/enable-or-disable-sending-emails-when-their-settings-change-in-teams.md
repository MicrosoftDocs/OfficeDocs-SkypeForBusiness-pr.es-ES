---
title: Email opciones cuando cambia la configuración de Audioconferencia
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Obtenga información sobre cómo habilitar o deshabilitar el envío de correos electrónicos a los usuarios por parte de Microsoft Teams cuando la configuración, como anclar cambios o los cambios de número de conferencia predeterminados en Teams. '
ms.openlocfilehash: a5119d6f612ed083ac4e72ab52f6bb189af4c9d1
ms.sourcegitcommit: 5abfb6f1abe10b6d32cf6eb97a890cf3138ed0e6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2022
ms.locfileid: "67642111"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a>Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de Audioconferencia en Microsoft Teams

Los usuarios reciben automáticamente una notificación por correo electrónico cuando están habilitados para audioconferencia. Sin embargo, puede haber ocasiones en que desee reducir el número de correos electrónicos que se envían a los usuarios de Microsoft Teams. En estos casos, puede deshabilitar el envío de correo electrónico.
  
Si deshabilita el envío de correos electrónicos, los correos electrónicos de Audioconferencia no se enviarán a los usuarios, incluidos los correos electrónicos para cuando los usuarios estén habilitados o deshabilitados para las audioconferencias, cuando se restablezca su PIN y cuando cambien el Id. de conferencia y el número de teléfono de conferencia predeterminado.
  
Este es un ejemplo del correo electrónico que se envía a los usuarios cuando están habilitados para audioconferencia:
  
![Ejemplo de un mensaje de correo electrónico de Audioconferencia.](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>¿Cuándo se envían correos electrónicos a los usuarios?

- Hay varios correos electrónicos que se envían a los usuarios de su organización después de que estén habilitados para audioconferencia:

  - Cuando se les asigna una licencia **de Audioconferencia** .

  - Al restablecer manualmente el PIN de audioconferencia del usuario.

  - Al restablecer de forma manual el id. de conferencia del usuario.

  - Cuando se les quita la licencia **de Audioconferencia** .

  - Cuando se cambia el proveedor de servicios de audioconferencia de un usuario de Microsoft a otro proveedor o **a Ninguno**.

  - Cuando se cambia el proveedor de servicios de audioconferencia de un usuario a Microsoft.

## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Habilitar o deshabilitar el envío de correo electrónico a los usuarios

Puede usar Microsoft Teams o Windows PowerShell para habilitar o deshabilitar el correo electrónico enviado a los usuarios.

### <a name="using-the-microsoft-teams-admin-center"></a>Usar el Centro de administración de Microsoft Teams

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.

2. En la parte superior de la página **Puentes de conferencia** , haga clic en **Configuración del puente**.

3. En el panel **Configuración del puente** , habilite o deshabilite **Enviar automáticamente correos electrónicos a los usuarios si cambia la configuración de acceso telefónico local**.

4. Haga clic en **Guardar**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

### <a name="using-windows-powershell"></a>Usar Windows PowerShell

También puede usar el módulo Microsoft Teams PowerShell y ejecutar:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

You can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) to manage other settings for your organization, including email.

Consulte la [referencia de Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obtener más información.

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tenga que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:

- [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Las mejores formas de administrar Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](/powershell/module/teams/?view=teams-ps).

## <a name="related-topics"></a>Temas relacionados

[Correos electrónicos enviados a los usuarios cuando cambia la configuración de Audioconferencia](emails-sent-to-users-when-their-settings-change-in-teams.md)

[Enviar un correo electrónico a un usuario con su información de Audioconferencia](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
