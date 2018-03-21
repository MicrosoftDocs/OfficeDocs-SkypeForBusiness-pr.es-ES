---
title: "Administrar la configuración de la conferencia de acceso telefónico local en mi organización"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'See steps to assign a dial-in conferencing license and conference ID to a user, set up a third party conferencing provider, and many other dial-in conferencing settings. '
ms.openlocfilehash: b890358cebfe6b5d701758c4b6086d6e1f388ca1
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/16/2018
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a>Administrar la configuración de la conferencia de acceso telefónico local en mi organización

[] Puede que le resulte más sencillo ver todas las opciones de configuración de conferencia de acceso telefónico local en un mismo lugar. 
  
## <a name="assign-an-audio-conferencing-license"></a>Asignar una licencia de conferencia de acceso telefónico local

> [!NOTE]
> You can't assign licenses using the **Skype for Business admin center**. You must use the Office 365 admin center. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). 
  
 Para asignar una licencia a un usuario
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.
    
    > [!NOTE]
    > Si va a asignar licencias a un máximo de 20 usuarios al mismo tiempo, puede usar el menú desplegable **Seleccionar una vista** y, luego, elegir una de las opciones o crear su propia vista. Luego, haga clic en **Editar**, haga clic dos veces en **Siguiente**, seleccione la licencia y haga clic en **Enviar**. También puede asignar licencias a varios usuarios con Windows PowerShell. Para obtener instrucciones y scripts de PowerShell de ejemplo, vea [Asignar licencias de Skype Empresarial](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). 
  
3. En el panel de acciones, en **Licencia asignada**, haga clic en **Editar**. 
    
4. En la página **Asignar licencia**, active **Conferencias RTC de Skype Empresarial** y haga clic en **Guardar**. Para obtener más información sobre licencias, consulte [Licencias complementarias de Skype Empresarial](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
> [!NOTE]
> Después de asignar la licencia, puede que Microsoft no aparezca en el menú desplegable como un proveedor de servicios de conferencia de acceso telefónico local. Si esto ocurre, cierre la sesión del centro de administración de Office 365 o presione CTRL + F5 para actualizar la ventana del explorador. 
  
## <a name="assign-a-conference-id-for-a-user"></a>Asignar un id. de conferencia a un usuario

Asignar un id. de conferencia a un usuario 
  
Identificadores estáticos se utilizan cuando las personas de la organización no desean recordar un número aleatorio; Puede seleccionar un determinado número o elija uno que sea fácil de recordar. Cuando se utilizan identificadores de conferencia dinámico, cada reunión programaciones de un usuario obtener asignará un identificador único conferencia. Si desea asignar el dinámico en lugar de conferencia estática identificadores, vea [conferencias de Audio utilizando identificadores dinámicos en su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
The Skype for Business admin center can't be used to assign a conference ID to a user, but you can use the Windows PowerShell cmdlet to do this.
  
El Centro de administración de Skype Empresarial no se puede usar para asignar un id. de conferencia a un usuario, pero se puede usar el cmdlet de Windows PowerShell para esta finalidad.
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> Para establecer el id. de conferencia de un usuario, ejecute: 
  
Para más información sobre el cmdlet, vea [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
  
> [!IMPORTANT]
>  After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. Para ver cómo descargar, instalar y ejecutar el Skype para la herramienta de actualización de reunión empresarial, consulte: [Herramienta de actualización de la reunión para Skype para empresas y Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype para los negocios en línea, herramienta de migración de reunión (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)y [Skype para los negocios en línea, reunión Herramienta de migración (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).
  
See [See, change, and reset a conference ID assigned to a user](see-change-and-reset-a-conference-id-assigned-to-a-user.md).
  
## <a name="change-the-audio-conferencing-provider-from-microsoft-to-a-third-party-provider"></a>Cambiar el proveedor de conferencia de audio de Microsoft a un proveedor de terceros

1. Cambiar el proveedor de servicios de conferencia de acceso telefónico local de Microsoft a un proveedor de terceros
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then and select the user you want to change the audio conferencing provider for.
    
4. In the Action pane, click **Edit**. 
    
5. On the **Properties** page, under **Provider name**, choose the audio conferencing provider for the user.
    
    > [!NOTE]
    > You can only select Microsoft as the audio conferencing provider or **None** if you have selected multiple users.
  
6. Solo puede seleccionar Microsoft como el proveedor de servicios de conferencia de acceso telefónico local o **Ninguno** si ha seleccionado varios usuarios. 
    
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Habilitar o deshabilitar los mensajes de correo electrónico enviados a los usuarios de conferencia de audio

Habilitar o deshabilitar el envío de correos electrónicos a los usuarios de acceso telefónico local
  
 Puede usar el Centro de administración de Skype Empresarial o Windows PowerShell para habilitar o deshabilitar el envío de correos electrónicos a los usuarios.
  
1. Usar el Centro de administración de Skype Empresarial
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.
    
4. Click **Save**.
    
    Haga clic en **Guardar**.
    
    See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).
    
 Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.
  
- Usar Windows PowerShell 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    También puede usar Windows PowerShell y ejecutar:
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Cambiar información de contacto del remitente en los mensajes de correo electrónico enviados a los usuarios

Cambiar la información de contacto de los remitentes de mensajes de correo electrónico enviados a los usuarios
  
- Escriba la dirección de correo electrónico en el parámetro _SendEmailFromAddress_ .
    
- Escriba el nombre para mostrar del correo electrónico en el parámetro  _SendEmailFromDisplayName_.
    
- Establezca el parámetro _SendEmailOverride_ en _True_.
    
You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Puede realizar cambios en el correo electrónico enviado a los usuarios, como la dirección de correo electrónico desde la que se envía el correo o el nombre para mostrar del correo electrónico al ejecutar:
  
Si quiere cambiar la información de la dirección de correo electrónico, tendrá que asegurarse de que las directivas de correo electrónico de entrada de su organización permitan la recepción de mensajes enviados por la dirección de correo electrónico personalizada.
  
Ver [mensajes de correo electrónico que se envían automáticamente a los usuarios al cambia su configuración de conferencia de Audio](emails-sent-to-users-when-their-settings-change.md).
  
## <a name="reset-the-meeting-conference-id"></a>Restablecer el id. de conferencia de reunión

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.
    
4. In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.
    
    > [!IMPORTANT]
    >  After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. Para ver cómo descargar, instalar y ejecutar el Skype para la herramienta de actualización de reunión empresarial, consulte: [herramienta de actualización de la reunión para Skype para empresas y Lync] ((https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype para los negocios en línea, herramienta de migración de reunión (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)y [Skype para negocios en línea Reunión (32-bit) de la herramienta de migración](https://www.microsoft.com/en-us/download/details.aspx?id=54079).
  
Vea [Restablecer un id. de conferencia para un usuario](reset-a-conference-id-for-a-user.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Restablecer el PIN del organizador de una conferencia

Identificadores estáticos se utilizan cuando las personas de la organización no desean recordar un número aleatorio; Puede seleccionar un determinado número o utilizar uno que sea fácil de recordar. Cuando se utilizan identificadores de conferencia dinámico, cada reunión programaciones de un usuario obtener asignará un identificador único conferencia. Si desea asignar el dinámico en lugar de conferencia estática IDs, [conferencias de Audio utilizando identificadores dinámicos en su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID. You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.
  
1. Aunque se creará y se asignará un identificador de conferencia automáticamente a un usuario, puede que a veces el usuario no desee usarlo y que usted desee establecerlo en un número concreto, o que los usuarios no recuerden o hayan perdido su identificador de conferencia. En esos casos, puede usar el centro de administración de Skype Empresarial y Windows PowerShell para ver, cambiar y restablecer su identificador de conferencia.
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. Click **Users**, and then select the user that you want to reset the PIN for.
    
4. In the Action pane, under **PIN**, click **Reset**.
    
Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, ***** will be shown. 
  
Los usuarios recibirán un correo electrónico con su PIN cuando estén habilitados para la conferencia de acceso telefónico local o cuando se restablezca el PIN. Pero, si deshabilitó el envío automático de correos electrónicos, no se enviará un correo electrónico de restablecimiento de PIN al usuario y tendrá que enviar el PIN al usuario de forma manual. El PIN solo se mostrará una vez después de que se haya restablecido. Una vez que se muestra inmediatamente después de haberse restablecido, el PIN no se mostrará más en las propiedades del usuario y en su lugar se mostrará *****.
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Enviar un correo electrónico con información de conferencia de Audio a un usuario

1. Enviar un correo electrónico con información sobre la conferencia de acceso telefónico local a un usuario
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. Click **Users**, and then select the user that you want to reset the PIN for.
    
4. Haga clic en **Usuarios de acceso telefónico local** y seleccione el usuario para el que quiera restablecer el PIN.
    
    > [!NOTE]
    > When you do this, the audio conferencing PIN isn't sent to the user. 
  
Después de completar esta acción, el PIN de conferencia de acceso telefónico local no se enviará al usuario.
  
## <a name="setting-the-default-audio-conferencing-phone-number-for-meeting-organizers"></a>Establecer el número de teléfono de conferencia de audio predeterminado para los organizadores de la reunión

 Configurar el número de teléfono de conferencias de acceso telefónico local predeterminado para los organizadores de reuniones
  
1. Para establecer el número de teléfono de conferencias de acceso telefónico local predeterminado para los organizadores de reuniones cuando está habilitando un usuario para las conferencias de acceso telefónico local
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
4. In the Action pane, in the user's properties, click **Edit**.
    
5. On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.
    
  - If you select Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.  
    
  - Si selecciona Microsoft como el proveedor de servicios de conferencia de acceso telefónico local, puede elegir de la lista el número de teléfono predeterminado de las conferencias de acceso telefónico local.
    
    Si selecciona un ACP de terceros como proveedor de servicios de conferencia de acceso telefónico local, tendrá que introducir manualmente el número de pago y, si es necesario, el número de teléfono gratuito. Estos números de teléfono serán el número de teléfono predeterminado.
    
6. El número de teléfono de conferencias de acceso telefónico local predeterminado de un usuario es el número que se muestra en la invitación a la reunión cuando se programa una. 
    
Consulte [el teléfono invita números incluidos en](set-the-phone-numbers-included-on-invites.md).
  
 Vea **Establecer los números de teléfono de conferencias de Audio para organizadores que se incluyen en invitaciones**.
  
1. Para establecer el número de teléfono de conferencias de acceso telefónico local predeterminado después de haber habilitado un usuario para las conferencias de acceso telefónico local
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, select the user you want, and in the Action page, click **Edit**.
    
4. On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.
    
  - If the user uses Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.  
    
  - Si el usuario usa Microsoft como el proveedor de servicios de conferencia de acceso telefónico local, puede elegir de la lista el número de teléfono predeterminado de las conferencias de acceso telefónico local.
    
    Si el usuario usa un ACP de terceros como proveedor de servicios de conferencia de acceso telefónico local, tendrá que introducir manualmente el número de pago y, si es necesario, el número de teléfono gratuito.
    
5. El número de teléfono de conferencias de acceso telefónico local predeterminado de un usuario es el número que se muestra en la invitación a la reunión cuando se programa una. 
    
Consulte [el teléfono invita números incluidos en](set-the-phone-numbers-included-on-invites.md).
  
## <a name="setting-audio-conferencing-bridge-settings"></a>Configuración de puente de conferencia de audio

 Configuración del puente de audioconferencia o de conferencia de acceso telefónico local
  
1. Establecer la experiencia de reunión cuando las personas que llaman se unen a una reunión
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.
    
4. Under **Meeting join experience**, select the following actions:
    
  - En **Experiencia de entrada a la reunión**, seleccione las acciones siguientes:
    
    This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business or Microsoft Teams app and they modify the **Announce when people enter or leave** setting in the Skype Meeting or Microsoft Teams **Options** menu of the meeting.
    
  - Esta opción se puede configurar de manera específica en cada reunión cuando un usuario se une a una reunión con el cliente de Skype Empresarial y modifica la opción **Anunciar cuando entra o sale gente** en el menú Opciones de reunión de Skype de la reunión.
    
5. **Solicitar a los autores de la llamada que registren su nombre antes de unirse a la reunión**. Esta opción está seleccionada de forma predeterminada. Si la desactiva, no se solicitará a las personas que llamen que registren su nombre antes de unirse a una reunión.
    
Después de realizar los cambios, haga clic en [Guardar](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.
  
1. Configurar la longitud del PIN de las reuniones
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.
    
4. Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.
    
    The PIN must be between 4 and 12 digits. The default is 5.
    
El PIN solo puede tener de 4 a 12 dígitos. El valor predeterminado es 5.
  
 Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.
  
1. Habilitar o deshabilitar el correo electrónico que se envían a los usuarios de acceso telefónico local
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.
    
4. Click **Save**.
    
    Haga clic en **Guardar**.
    
    If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.
    
    Si hace esto, se enviará un correo electrónico que solo contenga el id. de la conferencia y el número de teléfono de la conferencia, pero no se incluirá el PIN.
    
## <a name="see-and-set-the-primary-and-secondary-languages-on-an-audio-conferencing-bridge"></a>Ver y configurar los idiomas primarios y secundarios en un puente de conferencia de audio

1. Ver y configurar el idioma principal y los secundarios en un puente de conferencias de acceso telefónico local
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.
    
4. En el **Centro de administración de Skype Empresarial**, en el panel de navegación de la izquierda, vaya a **Conferencias de acceso telefónico local** y, luego, haga clic en **Puente de Microsoft**.
    
    You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.
    
También puede establecer el idioma principal y los idiomas secundarios compatibles al seleccionar Microsoft como proveedor de conferencias de acceso telefónico local. El orden que seleccione en las listas desplegables será el orden de los idiomas que se presentará a los autores de las llamadas.
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>Ver números de acceso telefónico de conferencia de audio

1. Ver números de acceso telefónico para conferencias de acceso telefónico local
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:
    
  - View the phone numbers that are set by Office 365 to be used for Audio Conferencing. 
    
  - Puede ver los números de teléfono que Office 365 establece para usarse con las conferencias de acceso telefónico local.
    
  - También puede ver la ubicación y el idioma principal y los idiomas secundarios que usará el operador automático de las conferencias de acceso telefónico local.
    
Puede seleccionar el número de teléfono predeterminado de conferencia de acceso telefónico local que se asignará a los usuarios cuando estos se habiliten para la conferencia de acceso telefónico local. No obstante, si cambia el número de teléfono predeterminado del puente de conferencia de acceso telefónico local, el número de teléfono predeterminado de los usuarios existentes no cambiará.
  
Vea [una lista de números de conferencia de Audio](see-a-list-of-audio-conferencing-numbers.md).
  
## <a name="see-a-list-of-users-that-are-enabled"></a>Ver una lista de usuarios habilitados

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.
    
See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

Hay varias configuraciones que se pueden administrar en el nivel de organización mediante Windows PowerShell. Esto facilita la configuración se aplican a todos los usuarios. 
    
Existen varias opciones que puede configurar en el nivel de la organización con Windows PowerShell. Esto facilita la configuración de estas opciones y las aplica a todos los usuarios. Estas son las opciones de configuración de nivel de organización:

Aquí está la configuración de nivel de organización: 
> 
- **Establecimiento de notificaciones de entrada y salida** El valor predeterminado es _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- **Configuración de grabación de nombre** El valor predeterminado es _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- **Establecer la longitud del perno** El valor predeterminado es 5.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **Configuración de sólo marcado en reuniones desde el teléfono** El valor predeterminado _$false_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- **Si desea enviar correo electrónico a los usuarios establecer** El valor predeterminado es _$true_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- **Establecer si se va a enviar correo electrónico desde una cuenta diferente** El valor predeterminado es _$false_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- **Establecer la dirección de correo electrónico que se envía a los usuarios** El valor predeterminado es _$null_. 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- **Establecer el nombre para mostrar para el correo electrónico que se envía a los usuarios** El valor predeterminado es _$null_.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a>Para obtener más información acerca de Windows PowerShell   
- Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics: 
    
  - [Introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
    
## <a name="related-topics"></a>See also

[Administrar la configuración de Audioconferencia para un usuario](manage-the-audio-conferencing-settings-for-a-user.md)

[Configurar conferencias de Audio de Skype para la empresa y Teams de Microsoft](set-up-audio-conferencing.md)
