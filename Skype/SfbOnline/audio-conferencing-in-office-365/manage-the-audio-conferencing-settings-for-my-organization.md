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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Vea Skype para ver los pasos en línea de negocio para asignar un identificador de conferencia y licencia de conferencia de acceso telefónico a un usuario y muchas otras opciones de conferencia de acceso telefónico. '
ms.openlocfilehash: 55e0e09e9b1b0875fd2ebd19aea5c3ae99392299
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23890334"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a>Administrar la configuración de Audioconferencia de mi organización en Skype for Business Online

> [!NOTE]
> Si desea administrar esta configuración en Teams, vea [Administrar la configuración de Audioconferencia de mi organización en Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).

Sería más fácil para que pueda ver toda la configuración de conferencias de audio de Skype para la empresa en un solo lugar.


## <a name="assign-an-audio-conferencing-license"></a>Asignar una licencia de conferencia de acceso telefónico local

> [!NOTE]
> You can't assign licenses using the **Skype for Business admin center**. You must use the Office 365 admin center. Consulte [Asignar licencias de Skype Empresarial](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

 Para asignar una licencia a un usuario

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. En la navegación izquierda del **Centro de administración de Office 365**, vaya a **Usuarios** > **Usuarios activos** y a continuación seleccione el usuario o los usuarios en la lista de usuarios disponibles.

    > [!NOTE]
    > Si va a asignar licencias a un máximo de 20 usuarios al mismo tiempo, puede usar el menú desplegable **Seleccionar una vista** y, luego, elegir una de las opciones o crear su propia vista. Luego, haga clic en **Editar**, haga clic dos veces en **Siguiente**, seleccione la licencia y haga clic en **Enviar**. También puede asignar licencias a varios usuarios con Windows PowerShell. Para obtener instrucciones y secuencias de comandos de PowerShell de ejemplo, vea [Asignar Skype para licencias de negocio](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).

3. En el panel de acciones, en **Licencia asignada**, haga clic en **Editar**.

4. En la página **Asignar licencia**, active **Conferencias RTC de Skype Empresarial** y haga clic en **Guardar**. Para obtener más información acerca de las licencias, vea [Skype para Business licensing del complemento](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

> [!NOTE]
> Después de asignar la licencia, puede que Microsoft no aparezca en el menú desplegable como un proveedor de servicios de conferencia de acceso telefónico local. Si esto ocurre, cierre la sesión del centro de administración de Office 365 o presione CTRL + F5 para actualizar la ventana del explorador.

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Enable or disable emails sent to audio conferencing users

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Inicie sesión en Office 365 con su cuenta profesional o educativa.**** > ********

3. En la página **Configuración de puente de Microsoft**, seleccione o deseleccione **Enviar automáticamente correos electrónicos a los usuarios si la configuración de audioconferencia cambia**.

4. Haga clic en **Guardar**.

    Haga clic en **Guardar**.

    Vea [Enviar un correo electrónico a un usuario con su información de Audioconferencia](send-an-email-to-a-user-with-their-dial-in-information.md).

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

**Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.**

- Usar Windows PowerShell

  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    También puede usar Windows PowerShell y ejecutar:[](https://go.microsoft.com/fwlink/?LinkId=627285)

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Change the sender's contact information in email messages sent to users

Puede realizar cambios en el correo electrónico que se envía automáticamente a los usuarios, incluida la dirección de correo electrónico real y el nombre para mostrar de la información de contacto del remitente. De forma predeterminada, el remitente de los mensajes de correo electrónico es Office 365, pero se puede cambiar la dirección de correo electrónico y nombre para mostrar con Windows PowerShell y el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285). Para realizar cambios en la dirección de correo electrónico que envía el correo electrónico a los usuarios, debe:

- Escriba la dirección de correo electrónico en el parámetro _SendEmailFromAddress_ .

- Escriba el nombre para mostrar del correo electrónico en el parámetro  _SendEmailFromDisplayName_.

- Establezca el parámetro _SendEmailOverride_ en _True_.

Puede realizar cambios en el correo electrónico enviado a los usuarios, como por ejemplo la dirección de correo electrónico desde la que se envía el correo electrónico o el nombre para mostrar para el correo electrónico haciendo lo siguiente:

```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Puede realizar cambios en el correo electrónico enviado a los usuarios, como la dirección de correo electrónico desde la que se envía el correo o el nombre para mostrar del correo electrónico al ejecutar:

Si quiere cambiar la información de la dirección de correo electrónico, tendrá que asegurarse de que las directivas de correo electrónico de entrada de su organización permitan la recepción de mensajes enviados por la dirección de correo electrónico personalizada.

Vea los [mensajes de correo electrónico que se envían automáticamente a los usuarios al cambia su configuración de conferencias de Audio](emails-sent-to-users-when-their-settings-change.md).

## <a name="reset-the-meeting-conference-id"></a>Restablecer el id. de conferencia de reunión

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Inicie sesión en Office 365 con su cuenta profesional o educativa.**** > ****

3. En el **Centro de administración de Skype for Business**, en la navegación izquierda, vaya a **Audioconferencia** y, en el panel Acción en **Id. de conferencia**, haga clic en **Restablecer**.

4. En la ventana **¿Restablecer Id. de conferencia?**, haga clic en **Sí**. Se creará automáticamente un Id. de conferencia y se enviará un correo electrónico al usuario con el nuevo Id. de conferencia si está habilitado el envío de correo electrónico a los usuarios. De manera predeterminada está habilitado.

    > [!IMPORTANT]
    >  After a new conference ID is created, the old conference ID can't be used by callers. Debe notificar a los usuarios para que reprogramen sus invitaciones de reunión existentes para asegurarse de que se agrega a las invitaciones el nuevo Id. de conferencia. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. Para ver cómo descargar, instalar y ejecutar la Skype para la herramienta de actualización de reunión empresarial, consulte: [Herramienta de actualización de la reunión de Skype para empresas y Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype para Online de negocio, herramienta de migración de reunión (64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)y [Skype para en línea de negocio, reunión Herramienta de migración (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).

Vea [Restablecer un id. de conferencia para un usuario](reset-a-conference-id-for-a-user.md).

## <a name="reset-a-conference-organizers-pin"></a>Restablecer el PIN del organizador de una conferencia

Se asignará un id. de conferencia único a cada reunión que programe un usuario. Si bien crea automáticamente un identificador de conferencia y se asigna a un usuario, puede haber ocasiones cuando un usuario no desea utilizar este y que desea establecer para un cierto número, o los usuarios no pueden recordar o han perdido su identificador de conferencia. You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.


1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Inicie sesión en Office 365 con su cuenta profesional o educativa.**** > ********

3. Haga clic en **Usuarios** y a continuación seleccione el usuario para el que desea restablecer el PIN.

4. En el panel Acción, en **PIN**, haga clic en **Restablecer**.

Los usuarios recibirán un correo electrónico con su PIN cuando se habiliten para la audioconferencia o cuando se restablezca el PIN. Pero si ha deshabilitado automáticamente el envío de correos electrónicos, no se enviará un correo electrónico de restablecimiento de PIN y deberá enviar manualmente el PIN al usuario. El PIN solo se mostrará una vez tras su restablecimiento. Una vez que se muestre inmediatamente después de su restablecimiento, el PIN dejará de mostrarse en las propiedades del usuario; en su lugar, se mostrará *****.

Vea [Restablecer el PIN de conferencia de Audio](reset-the-audio-conferencing-pin.md).

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Send an email with Audio Conferencing information to a user

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Inicie sesión en Office 365 con su cuenta profesional o educativa.**** > ********

3. Haga clic en **Usuarios** y a continuación seleccione el usuario para el que desea restablecer el PIN.

4. Haga clic en **Usuarios de acceso telefónico local** y seleccione el usuario para el que quiera restablecer el PIN.

    > [!NOTE]
    > Cuando hace esto, el PIN de audioconferencia no se envía al usuario.

Después de completar esta acción, el PIN de conferencia de acceso telefónico local no se enviará al usuario.

## <a name="setting-the-phone-numbers-included-on-invites"></a>Configuración del teléfono los números incluidos en invitaciones

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Inicie sesión en Office 365 con su cuenta profesional o educativa.**** > ****

3. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.

4. En el panel Acción, puede establecer el **Número de teléfono de pago** y, si se permite, el **Número de teléfono gratuito**.

5. Haga clic en **Guardar**.

Vea [el teléfono los números incluidos en invitaciones](set-the-phone-numbers-included-on-invites.md).


## <a name="choosing-audio-conferencing-bridge-settings"></a>Elegir la configuración de puente de conferencia de audio

Configuración del puente de audioconferencia o de conferencia de acceso telefónico local


1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Vaya a **Centro de administración de Office 365** > **Skype for Business**.

3. En el **centro de administración de Skype for Business**, en la navegación izquierda, vaya a **Audioconferencia** > **Configuración de puente de Microsof**.

4. En **Experiencia de participación en reuniones**, seleccione las acciones siguientes:

  - En **Experiencia de entrada a la reunión**, seleccione las acciones siguientes:

    Esto se puede establecer según la reunión por reunión cuando un usuario se une a una reunión mediante un Skype para la aplicación empresarial y modifican la configuración de **anunciar cuando las personas o la abandonan** en el menú de **Opciones** de reunión de Skype de la reunión.

  - Esta opción se puede configurar de manera específica en cada reunión cuando un usuario se une a una reunión con el cliente de Skype for Business y modifica la opción **Anunciar cuando entra o sale gente** en el menú Opciones de reunión de Skype de la reunión.

5. **Solicitar a los autores de la llamada que registren su nombre antes de unirse a la reunión**. Esta opción está seleccionada de forma predeterminada. Si la desactiva, no se solicitará a las personas que llamen que registren su nombre antes de unirse a una reunión.
    
Después de realizar los cambios, haga clic en [Guardar](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).
  
 **Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.**

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Vaya a **Centro de administración de Office 365** > **Skype for Business**.

3. En el **centro de administración de Skype for Business**, en la navegación izquierda, vaya a **Audioconferencia** > **Configuración de puente de Microsof**.

4. En **Seguridad**, especifique el número de dígitos que desea para el PIN en la lista **Longitud de PIN** y a continuación haga clic en **Guardar**.

    El PIN debe tener entre 4 y 12 dígitos. El valor predeterminado es 5.
    
El PIN solo puede tener de 4 a 12 dígitos. El valor predeterminado es 5.[](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)
  
 **Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.**

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Inicie sesión en Office 365 con su cuenta profesional o educativa.**** > ********

3. En la página **Configuración de puente de Microsoft**, seleccione o deseleccione **Enviar automáticamente correos electrónicos a los usuarios si la configuración de audioconferencia cambia**.

4. Haga clic en **Guardar**.

    Haga clic en **Guardar**.

    Si hace esto, se enviará un correo electrónico que incluye solo el Id. de conferencia y el número de teléfono de conferencia, pero no se incluirá el PIN.

    Si hace esto, se enviará un correo electrónico que solo contenga el id. de la conferencia y el número de teléfono de la conferencia, pero no se incluirá el PIN.

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Vea y establezca la primaria (valor predeterminado) y los idiomas (alternativos) secundarios en un puente de conferencia de audio


1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Inicie sesión en Office 365 con su cuenta profesional o educativa.**** > ****

3. En el **centro de administración de Skype for Business**, en la navegación izquierda, vaya a **Audioconferencia** y a continuación haga clic en **Puente de Microsoft**.

4. En el **Centro de administración de Skype for Business**, en el panel de navegación de la izquierda, vaya a **Conferencias de acceso telefónico local** y, luego, haga clic en **Puente de Microsoft**.

    También puede establecer los idiomas principal y secundarios admitidos al seleccionar Microsoft como proveedor de audioconferencia. El orden de selección en la lista equivale al orden en que se presentarán los idiomas a las personas que llamen.

También puede establecer el idioma principal y los idiomas secundarios compatibles al seleccionar Microsoft como proveedor de conferencias de acceso telefónico local. El orden que seleccione en las listas desplegables será el orden de los idiomas que se presentará a los autores de las llamadas.[](set-auto-attendant-languages-for-audio-conferencing.md)

## <a name="see-audio-conferencing-dial-in-numbers"></a>See audio conferencing dial-in numbers

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Inicie sesión en Office 365 con su cuenta profesional o educativa.**** > ****

3. En el **centro de administración de Skype for Business**, en la navegación izquierda, vaya a **Audioconferencia** > **Puente de Microsoft**. Aquí puede:

  - Vea los números de teléfono que ha establecido Office 365 para utilizar para Audioconferencia.

  - Puede ver los números de teléfono que Office 365 establece para usarse con las conferencias de acceso telefónico local.

  - También puede ver la ubicación y el idioma principal y los idiomas secundarios que usará el operador automático de las conferencias de acceso telefónico local.

Puede seleccionar el número de teléfono predeterminado de conferencia de acceso telefónico local que se asignará a los usuarios cuando estos se habiliten para la conferencia de acceso telefónico local. No obstante, si cambia el número de teléfono predeterminado del puente de conferencia de acceso telefónico local, el número de teléfono predeterminado de los usuarios existentes no cambiará.**** > ****

Vea [una lista de números de conferencias de Audio](see-a-list-of-audio-conferencing-numbers.md).

## <a name="see-a-list-of-users-that-are-enabled"></a>Ver una lista de usuarios habilitados

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.

2. Inicie sesión en Office 365 con su cuenta profesional o educativa.**** > ****

3. En el **centro de administración de Skype for Business**, en la navegación izquierda, vaya a **Audioconferencia** y a continuación **Usuarios**.

See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

Hay varias opciones de configuración que puede administrar en el nivel de organización mediante Windows PowerShell. Esto facilita la aplicación de la configuración a todos los usuarios.

Existen varias opciones que puede configurar en el nivel de la organización con Windows PowerShell. Esto facilita la configuración de estas opciones y las aplica a todos los usuarios. Estas son las opciones de configuración de nivel de organización:

A continuación presentamos la configuración de nivel de la organización:

- **Configuración de notificaciones de entrada o salida** El valor predeterminado es _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- **Configuración de grabación de nombre** El valor predeterminado es _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **Establecer la longitud de PIN** El valor predeterminado es 5.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **Establecer sólo marcado en reuniones desde un teléfono** El valor predeterminado es _$false_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **Establecer si se enviará un correo electrónico a los usuarios** El valor predeterminado es _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **Establecer si se enviará un correo electrónico desde una cuenta diferente** El valor predeterminado es _$false_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **Establecer la dirección de correo electrónico de remitente que se envía a los usuarios** El valor predeterminado es _$null_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **Establecer el nombre para mostrar para el correo electrónico que se envía a los usuarios** El valor predeterminado es _$null_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a>Desea saber más acerca de Windows PowerShell
- Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:

  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

- Windows PowerShell tiene muchas ventajas en velocidad, simplificidad y productividad respecto a utilizar únicamente el centro de administración de Office 365 como, por ejemplo, al realizar cambios de configuración para muchos usuarios en una única ubicación. Obtenga más información sobre estas ventajas en los temas siguientes:

  - [Introducción a Windows PowerShell y Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [Usar Windows PowerShell para administrar Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)

    El módulo Windows PowerShell para Skype for Business Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype for Business Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)

## <a name="related-topics"></a>See also

[Administrar la configuración de Audioconferencia para un usuario](manage-the-audio-conferencing-settings-for-a-user.md)


