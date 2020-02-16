---
title: Administrar la configuración de Audioconferencia de mi organización en Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
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
description: 'Consulte los pasos de Skype empresarial online para asignar una licencia de conferencia de acceso telefónico local y un identificador de conferencia a un usuario y muchas otras opciones de la Conferencia de acceso telefónico local. '
ms.openlocfilehash: 46f55ba256759d86e93e9436e949ee49ff337f7c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "41986525"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a>Administrar la configuración de Audioconferencia de mi organización en Skype for Business Online

> [!NOTE]
> Si desea administrar esta configuración en Teams, vea [Administrar la configuración de Audioconferencia de mi organización en Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).

Puede que le resulte más fácil ver toda la configuración de la audioconferencia para Skype empresarial en un solo lugar.


## <a name="assign-an-audio-conferencing-license"></a>Asignar una licencia de conferencia de acceso telefónico local

> [!NOTE]
> You can't assign licenses using the **Skype for Business admin center**. Debe usar el centro de administración de Microsoft 365. Consulte [Asignar licencias de Skype Empresarial](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

 **To assign a license for a user**

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. En el centro de navegación izquierdo del centro de administración, **vaya a** > usuarios**activos**y, a continuación, seleccione el usuario o los usuarios de la lista de usuarios disponibles.

    > [!NOTE]
    > Si va a asignar licencias a un máximo de 20 usuarios al mismo tiempo, puede usar el menú desplegable **Seleccionar una vista** y, luego, elegir una de las opciones o crear su propia vista. Luego, haga clic en **Editar**, haga clic dos veces en **Siguiente**, seleccione la licencia y haga clic en **Enviar**. También puede asignar licencias a varios usuarios con Windows PowerShell. Para obtener instrucciones y ejemplos de scripts de PowerShell, consulte [asignar licencias de Skype empresarial](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

3. En el panel de acciones, en **Licencia asignada**, haga clic en **Editar**.

4. En la página **Asignar licencia**, active **Conferencias RTC de Skype Empresarial** y haga clic en **Guardar**. Para obtener más información sobre las licencias, vea [licencias complementarias de Skype empresarial](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

> [!NOTE]
> Después de asignar la licencia, puede que Microsoft no aparezca en el menú desplegable como un proveedor de servicios de conferencia de acceso telefónico local. Si esto sucede, cierre sesión en el centro de administración o presione CTRL + F5 para actualizar la ventana del explorador.

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Enable or disable emails sent to audio conferencing users

![Un icono que muestra el logotipo](../images/sfb-logo-30x30.png) de Skype empresarial **con el centro de administración de Skype empresarial**

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Vaya al centro de administración > **Skype empresarial** y, en la barra de navegación izquierda, haga clic en **audioconferencia**.

3. On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.

4. Haga clic en **Guardar**.

    Haga clic en **Guardar**.

    Vea [Enviar un correo electrónico a un usuario con su información de Audioconferencia](send-an-email-to-a-user-with-their-dial-in-information.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.

- Usar Windows PowerShell

  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    También puede usar Windows PowerShell y ejecutar:[](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Change the sender's contact information in email messages sent to users

Puede realizar cambios en el correo electrónico que se envía automáticamente a los usuarios, incluida la dirección de correo electrónico real y el nombre para mostrar de la información de contacto del remitente. De forma predeterminada, el remitente de los mensajes de correo electrónico es Office 365, pero se puede cambiar la dirección de correo electrónico y nombre para mostrar con Windows PowerShell y el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps). Para realizar cambios en la dirección de correo electrónico que envía el correo electrónico a los usuarios, debe:

- Escriba la dirección de correo electrónico en el parámetro _SendEmailFromAddress_ .

- Escriba el nombre para mostrar del correo electrónico en el parámetro  _SendEmailFromDisplayName_.

- Establezca el parámetro _SendEmailOverride_ en _True_.

Puede realizar cambios en el correo electrónico enviado a los usuarios, como por ejemplo la dirección de correo electrónico desde la que se envía el correo electrónico o el nombre para mostrar para el correo electrónico haciendo lo siguiente:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Puede realizar cambios en el correo electrónico enviado a los usuarios, como la dirección de correo electrónico desde la que se envía el correo o el nombre para mostrar del correo electrónico al ejecutar:

You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to manage other settings for your organization, including email.

Ver [los correos electrónicos que se envían de forma automática a los usuarios cuando cambia la configuración de audioconferencia](emails-sent-to-users-when-their-settings-change.md).

## <a name="reset-the-meeting-conference-id"></a>Reset the meeting conference ID

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Vaya al centro de administración > **Skype empresarial**.

3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.

4. En la ventana **¿Restablecer Id. de conferencia?**, haga clic en **Sí**. Se creará automáticamente un Id. de conferencia y se enviará un correo electrónico al usuario con el nuevo Id. de conferencia si está habilitado el envío de correo electrónico a los usuarios. De manera predeterminada está habilitado.

    > [!IMPORTANT]
    >  After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. Para obtener información sobre cómo descargar, instalar y ejecutar la herramienta de actualización de reuniones de Skype empresarial, consulte la herramienta [de actualización de reuniones para Skype empresarial y Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype empresarial online, herramienta de migración de reuniones (64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)y [Skype empresarial online, herramienta de migración de reuniones (32 bits)](https://www.microsoft.com/download/details.aspx?id=54079).

See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).

## <a name="reset-a-conference-organizers-pin"></a>Reset a conference organizer's PIN

Se asignará un id. de conferencia único a cada reunión que programe un usuario. Aunque se creará automáticamente un identificador de conferencia y se le asignará a un usuario, puede haber ocasiones en las que un usuario no desee usarlo y usted quiera establecerlo en un número determinado, o los usuarios no podrán recordar o perder su identificador de conferencia. You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.


1. Aunque se creará y se asignará un identificador de conferencia automáticamente a un usuario, puede que a veces el usuario no desee usarlo y que usted desee establecerlo en un número concreto, o que los usuarios no recuerden o hayan perdido su identificador de conferencia. En esos casos, puede usar el centro de administración de Skype Empresarial y Windows PowerShell para ver, cambiar y restablecer su identificador de conferencia.

2. Vaya al centro de administración > **Skype empresarial** y, en la barra de navegación izquierda, haga clic en **audioconferencia**.

3. Click **Users**, and then select the user that you want to reset the PIN for.

4. In the Action pane, under **PIN**, click **Reset**.

Los usuarios recibirán un correo electrónico con su PIN cuando se habiliten para la audioconferencia o cuando se restablezca el PIN. Pero si ha deshabilitado automáticamente el envío de correos electrónicos, no se enviará un correo electrónico de restablecimiento de PIN y deberá enviar manualmente el PIN al usuario. El PIN solo se mostrará una vez tras su restablecimiento. Una vez que se muestre inmediatamente después de su restablecimiento, el PIN dejará de mostrarse en las propiedades del usuario; en su lugar, se mostrará *****.

Consulte [restablecer el PIN de audioconferencia](reset-the-audio-conferencing-pin.md).

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Send an email with Audio Conferencing information to a user

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Vaya al centro de administración > **Skype empresarial** y, en la barra de navegación izquierda, haga clic en **audioconferencia**.

3. Click **Users**, and then select the user that you want to reset the PIN for.

4. Haga clic en **Usuarios de acceso telefónico local** y seleccione el usuario para el que quiera restablecer el PIN.

    > [!NOTE]
    > When you do this, the audio conferencing PIN isn't sent to the user.

See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).

## <a name="setting-the-phone-numbers-included-on-invites"></a>Configurar los números de teléfono incluidos en los invitados

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Vaya al centro de administración > **Skype empresarial**.

3. En el navegación de la izquierda, vaya a**usuarios**de la **Conferencia** > de audio. Seleccione el usuario que desea habilitar para las conferencias de audio.

4. En el panel Acción, puede establecer el **Número de teléfono de pago** y, si se permite, el **Número de teléfono gratuito**.

5. Haga clic en **Guardar **.

Consulte [establecer los números de teléfono incluidos en los invitados](set-the-phone-numbers-included-on-invites.md).


## <a name="choosing-audio-conferencing-bridge-settings"></a>Elegir la configuración del puente de audioconferencia

**Set the meeting experience when callers join a meeting**


1. Establecer la experiencia de reunión cuando las personas que llaman se unen a una reunión

2. Vaya al centro de administración > **Skype empresarial**.

3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.

4. Under **Meeting join experience**, select the following actions:

   - En **Experiencia de entrada a la reunión**, seleccione las acciones siguientes:

     Esto se puede establecer en cada reunión cuando un usuario se une a una reunión con una aplicación de Skype empresarial y modifica la opción **anunciar cuando entra o sale usuarios** en el menú **Opciones** de reunión de Skype de la reunión.

   - Esta opción se puede configurar de manera específica en cada reunión cuando un usuario se une a una reunión con el cliente de Skype for Business y modifica la opción **Anunciar cuando entra o sale gente** en el menú Opciones de reunión de Skype de la reunión.

5. **Solicitar a los autores de la llamada que registren su nombre antes de unirse a la reunión**. Esta opción está seleccionada de forma predeterminada. Si la desactiva, no se solicitará a las personas que llamen que registren su nombre antes de unirse a una reunión.
    
Después de realizar los cambios, haga clic en [Guardar](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).
  
 Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.

1. Configurar la longitud del PIN de las reuniones

2. Vaya al centro de administración > **Skype empresarial**.

3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.

4. Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.

    The PIN must be between 4 and 12 digits. The default is 5.
    
See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).
  
 Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Vaya al centro de administración > **Skype empresarial** y, en la barra de navegación izquierda, haga clic en **audioconferencia**.

3. On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.

4. Haga clic en **Guardar**.

    Haga clic en **Guardar**.

    If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.

    See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Ver y establecer los idiomas principales (alternativos) y secundarios (alternativos) en un puente de audioconferencia


1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Vaya al centro de administración > **Skype empresarial**.

3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.

4. En el **Centro de administración de Skype Empresarial**, en el panel de navegación de la izquierda, vaya a **Conferencias de acceso telefónico local** y, luego, haga clic en **Puente de Microsoft**.

    You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.

También puede establecer el idioma principal y los idiomas secundarios compatibles al seleccionar Microsoft como proveedor de conferencias de acceso telefónico local. El orden que seleccione en las listas desplegables será el orden de los idiomas que se presentará a los autores de las llamadas.[](set-auto-attendant-languages-for-audio-conferencing.md)

## <a name="see-audio-conferencing-dial-in-numbers"></a>See audio conferencing dial-in numbers

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Vaya al centro de administración > **Skype empresarial**.

3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:

   - View the phone numbers that are set by Office 365 to be used for Audio Conferencing.

   - Puede ver los números de teléfono que Office 365 establece para usarse con las conferencias de acceso telefónico local.

   - También puede ver la ubicación y el idioma principal y los idiomas secundarios que usará el operador automático de las conferencias de acceso telefónico local.

Puede seleccionar el número de teléfono predeterminado de conferencia de acceso telefónico local que se asignará a los usuarios cuando estos se habiliten para la conferencia de acceso telefónico local. No obstante, si cambia el número de teléfono predeterminado del puente de conferencia de acceso telefónico local, el número de teléfono predeterminado de los usuarios existentes no cambiará.**** > ****

Consulte [ver una lista de números de audioconferencia](see-a-list-of-audio-conferencing-numbers.md).

## <a name="see-a-list-of-users-that-are-enabled"></a>See a list of users that are enabled

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Vaya al centro de administración > **Skype empresarial**.

3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.

See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

Hay varias opciones de configuración que puede administrar en el nivel de la organización mediante Windows PowerShell. Esto facilita la aplicación de la configuración a todos los usuarios.

To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).

A continuación se muestra la configuración de nivel de organización:

- **Configuración de notificaciones de entrada o salida** El valor predeterminado es _$true_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- **Configuración de grabación de nombre** El valor predeterminado es _$true_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **Establecer la longitud de PIN** El valor predeterminado es 5.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **Establecer sólo marcado en reuniones desde un teléfono** El valor predeterminado es _$false_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **Establecer si se enviará un correo electrónico a los usuarios** El valor predeterminado es _$true_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **Establecer si se enviará un correo electrónico desde una cuenta diferente** El valor predeterminado es _$false_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **Establecer la dirección de correo electrónico de remitente que se envía a los usuarios** El valor predeterminado es _$null_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **Establecer el nombre para mostrar para el correo electrónico que se envía a los usuarios** El valor predeterminado es _$null_.
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?
- Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:

  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

- Windows PowerShell tiene muchas ventajas en cuanto a velocidad, simplicidad y productividad a través del centro de administración, como cuando se están realizando cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes:

  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)

    El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)

## <a name="related-topics"></a>Temas relacionados

[Administrar la configuración de Audioconferencia para un usuario](manage-the-audio-conferencing-settings-for-a-user.md)


