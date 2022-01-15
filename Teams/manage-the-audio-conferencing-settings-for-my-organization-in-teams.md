---
title: Administrar la configuración de audioconferencia
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
- m365initiative-meetings
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Consulte Microsoft Teams pasos para asignar una licencia de conferencia de acceso telefónico local e id. de conferencia a un usuario y muchas otras opciones de configuración de conferencias de acceso telefónico local. '
ms.openlocfilehash: d6dccb2afc18f5497b08df583cde31fe249654bc
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2022
ms.locfileid: "62056070"
---
# <a name="manage-the-audio-conferencing-settings-for-your-organization-in-microsoft-teams"></a>Administrar la configuración de Audioconferencia para su organización en Microsoft Teams

Es posible que le resulte más fácil ver todas las opciones de configuración de audioconferencia Microsoft Teams en un solo lugar.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="assign-an-audio-conferencing-license"></a>Asignar una licencia de conferencia de acceso telefónico local

> [!NOTE]
> No puede asignar licencias con Teams. Debe usar el Centro de administración de Microsoft 365. Vea [Asignar Microsoft Teams de complementos.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

### <a name="to-assign-a-license-for-a-user"></a>To assign a license for a user

1. Inicie sesión en Microsoft 365 con su cuenta de trabajo o escuela.

2. En la navegación izquierda de la  **Centro de administración de Microsoft 365**, vaya a Usuarios usuarios activos y, a continuación, seleccione el usuario o los usuarios de  >  la lista de usuarios disponibles.

    > [!NOTE]
    > Si va a asignar licencias a un máximo de 20 usuarios al mismo tiempo, puede usar el menú desplegable **Seleccionar una vista** y elegir una de las opciones o crear su propia vista. Luego, haga clic en **Editar**, haga clic dos veces en **Siguiente**, seleccione la licencia y haga clic en **Enviar**.  
  
3. En el panel de acciones, en **Licencias de productos**, haga clic en **Editar**.

4. En la página **Asignar licencia**, active **Conferencias RTC de Skype Empresarial** y haga clic en **Guardar**. Para obtener más información sobre las [licencias, vea Microsoft Teams de complementos.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

   > [!NOTE]
   > Después de asignar la licencia, puede que Microsoft no aparezca en el menú desplegable como un proveedor de servicios de conferencia de acceso telefónico local. Si esto sucede, cierre sesión en el centro de administración o presione CTRL+F5 para actualizar la ventana del explorador.
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Enable or disable emails sent to audio conferencing users

### <a name="enable-or-disable-using-the-microsoft-teams-admin-center"></a>Habilitar o deshabilitar el uso del Microsoft Teams de administración

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.

2. En la parte superior de la **página Puentes de** conferencia, haga clic en **Configuración de puente.**

3. En el **panel Configuración de puente,** habilite o deshabilite Enviar mensajes de correo electrónico automáticamente a los usuarios si cambia la configuración **de acceso telefónico.**

4. Haga clic en **Guardar**.

### <a name="enable-or-disable-using-windows-powershell"></a>Habilitar o deshabilitar el uso de Windows PowerShell

Vea la [Microsoft Teams referencia de PowerShell](/powershell/module/teams/?view=teams-ps) para obtener más información.
  
## <a name="reset-the-meeting-conference-id"></a>Reset the meeting conference ID

### <a name="reset-the-meeting-conference-id-using-the-microsoft-teams-admin-center"></a>Restablecer el id. de conferencia de la reunión con el Microsoft Teams de administración

1. En el panel de navegación izquierdo, haga clic **en Usuarios** y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En **Audioconferencia, haga** clic **en Restablecer id. de conferencia.**  

3. En la ventana **¿Restablecer id. de conferencia?,** haga clic en **Restablecer**. Se creará automáticamente un id. de conferencia y se enviará un correo electrónico al usuario con el nuevo id. de conferencia si el envío de correo electrónico a los usuarios está habilitado. Está habilitada de forma predeterminada.

See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).

## <a name="reset-a-conference-organizers-pin"></a>Reset a conference organizer's PIN

Se asignará un id. de conferencia único a cada reunión que programe un usuario. Aunque un id. de conferencia se creará automáticamente y se asignará a un usuario, es posible que haya ocasiones en las que un usuario no quiera usar este y quiera establecerlo en un número determinado, o los usuarios no puedan recordar o haber perdido su id. de conferencia.

### <a name="reset-a-conference-organizers-pin-using-the-microsoft-teams-admin-center"></a>Restablecer el PIN de un organizador de conferencias con el centro Microsoft Teams de administración

1. En el panel de navegación izquierdo, haga clic **en Usuarios** y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En **Audioconferencia,** haga clic **en Restablecer PIN** y, a continuación, haga clic en **Restablecer**.
  
Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, ***** will be shown.
  
Vea [Restablecer el PIN de audioconferencia.](reset-the-audio-conferencing-pin-in-teams.md)
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Send an email with Audio Conferencing information to a user

### <a name="send-an-email-using-the-microsoft-teams-admin-center"></a>Enviar un correo electrónico con el centro Microsoft Teams administración

1. En el panel de navegación izquierdo, haga clic **en Usuarios** y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En **Audioconferencia,** haga clic **en Enviar información de conferencia por correo electrónico.**

    > [!NOTE]
    > When you do this, the audio conferencing PIN isn't sent to the user.

See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).
  
## <a name="set-the-phone-numbers-included-on-invites"></a>Establecer los números de teléfono incluidos en las invitaciones

### <a name="set-invite-phone-numbers-using-the-microsoft-teams-admin-center"></a>Establecer números de teléfono de invitación con el centro de Microsoft Teams de administración

1. En el panel de navegación izquierdo, haga clic **en Usuarios** y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. Junto a **Audioconferencia,** haga clic en **Editar.**

3. En el **panel Audioconferencia,** puede  establecer el número de pago y, si se permite, el **número gratuito**.

4. Haga clic en **Guardar**.

Vea [Establecer los números de teléfono incluidos en las invitaciones.](set-the-phone-numbers-included-on-invites-in-teams.md)

## <a name="choose-audio-conferencing-bridge-settings"></a>Elegir la configuración del puente de audioconferencia

### <a name="set-the-meeting-experience-when-callers-join-a-meeting-using-the-microsoft-teams-admin-center"></a>Establecer la experiencia de la reunión cuando las personas que llaman se unen a una reunión con el centro Microsoft Teams de administración

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.

2. En la parte superior de la **página Puentes de** conferencia, haga clic en **Configuración de puente.**

3. En el panel **Configuración de puente**, habilite o deshabilite **Notificaciones de entrada y salida de la reunión**.

    Esta opción está habilitada de forma predeterminada. Si deshabilita esta opción, los usuarios que ya se han unido a la reunión de forma predeterminada no se les notificará cuando alguien entre o abandone la reunión.

4. En **Tipo de anuncio de entrada o salida,** elija **Tonos** o Nombres o números **de teléfono.**

    Si elige **Nombres o números de teléfono,** también puede habilitar o deshabilitar Pedir a los autores de llamadas que graben su nombre antes de **unirse a la reunión.**
    > [!NOTE]
    > De forma predeterminada, los participantes externos no pueden ver los números de teléfono de los participantes marcados. Si desea mantener la privacidad de estos números de teléfono, seleccione **Tonos** de **entrada/salida tipo de anuncio** (esto evita que los Teams lean los números).
5. Haga clic en **Guardar**.

See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).
  
### <a name="set-the-pin-length-for-meetings"></a>Vea Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft.

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.

2. En la parte superior de la **página Puentes de** conferencia, haga clic en **Configuración de puente.**

3. En el **panel Configuración de puente,** escriba el número de dígitos que desea para el PIN en la lista Longitud del **PIN** y, a continuación, haga clic en **Guardar.**

    The PIN must be between 4 and 12 digits. The default is 5.

See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).

### <a name="enable-or-disable-email-from-being-sent-to-audio-users"></a>Vea Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft.

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.

2. En la parte superior de la **página Puentes de** conferencia, haga clic en **Configuración de puente.**

3. En el **panel Configuración de puente,** habilite o deshabilite Enviar mensajes de correo electrónico automáticamente a los usuarios si cambian sus opciones de **audioconferencia.**

4. Haga clic en **Guardar**.

    También puede enviar correo electrónico al usuario con la configuración de audioconferencia, yendo a las propiedades de audioconferencia del usuario y haciendo clic en Enviar información de conferencia **por correo electrónico.**

    If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.

See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md).

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Ver y establecer los idiomas principal (predeterminado) y secundario (alternativo) en un puente de audioconferencia

### <a name="see-primary-and-secondary-languages-using-the-microsoft-teams-admin-center"></a>Ver idiomas primarios y secundarios con el centro Microsoft Teams administración

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.

2. Seleccione un número de teléfono de la lista y haga clic en **Editar.**

3. Elija los idiomas que desee en **Idioma predeterminado** e **Idiomas alternativos (opcional).**

4. Haga clic en **Guardar**.

See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing-in-teams.md).
  
## <a name="see-audio-conferencing-dial-in-numbers-using-the-microsoft-teams-admin-center"></a>Ver números de acceso telefónico local de audioconferencia con el centro Microsoft Teams administración

1. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.

2. Seleccione un número de teléfono de la lista y haga clic en **Editar.** Here you can:

   - Vea los números de teléfono que se van a usar para las audioconferencias.

   - Vea la ubicación y el idioma principal que usará el operador automático de audioconferencias.

Vea [Ver una lista de números de audioconferencia.](see-a-list-of-audio-conferencing-numbers-in-teams.md)

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer. Para empezar con Windows PowerShell, vea estos temas:

- [¿Por qué necesita usar Microsoft 365 o Office 365 PowerShell?](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](/powershell/module/teams/?view=teams-ps).

## <a name="related-topics"></a>Temas relacionados

[Administrar la configuración de Audioconferencia para un usuario](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)
