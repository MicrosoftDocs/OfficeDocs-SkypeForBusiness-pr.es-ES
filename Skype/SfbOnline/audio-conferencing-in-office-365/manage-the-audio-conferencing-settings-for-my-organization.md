---
title: Administrar la configuración de la conferencia de acceso telefónico local en mi organización
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Vea los pasos para asignar un identificador de conferencia y licencia de conferencia de acceso telefónico a un usuario y muchas otras opciones de conferencia de acceso telefónico. '
ms.openlocfilehash: 26d80b71344227aeaec7089e2bb9f9a9dfe32ad2
ms.sourcegitcommit: 527c7dd4c5edc70503ba31e7c689a71d7356b17e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2018
ms.locfileid: "19703672"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a>Administrar la configuración de la conferencia de acceso telefónico local en mi organización

[] Puede que le resulte más sencillo ver todas las opciones de configuración de conferencia de acceso telefónico local en un mismo lugar. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
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
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Habilitar o deshabilitar los correos electrónicos enviados a los usuarios de conferencia de audio

![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

1. En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página de **Puentes de conferencia** , haga clic en **configuración de puente**. 

3. En el panel **configuración de puente** , habilitar o deshabilitar **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de acceso telefónico**.

4. Haga clic en **Guardar**.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**
  
1. Habilitar o deshabilitar el correo electrónico que se envían a los usuarios de acceso telefónico local
    
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
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a>Cambiar la información de contacto de la dirección del remitente en los mensajes de correo electrónico enviados a los usuarios

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
  
Vea los [mensajes de correo electrónico que se envían automáticamente a los usuarios al cambia su configuración de conferencias de Audio](emails-sent-to-users-when-their-settings-change.md).
  
## <a name="reset-the-meeting-conference-id"></a>Restablecer el id. de conferencia de reunión

![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

1. En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En la parte superior de la página, haga clic en **Editar**.

3. En **Conferencias de Audio**, haga clic en **Restablecer el identificador de conferencia**.  

4. En la **Restablecer el identificador de conferencia?** ventana, haga clic en **Restablecer**. Se creará automáticamente un identificador de conferencia y un correo electrónico enviado al usuario con el nuevo identificador de conferencia si está habilitado el envío de correo electrónico a los usuarios. Está habilitada de forma predeterminada.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**  

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.
    
4. In the **Reset conference ID?** window, click **Yes**. A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled. It's enabled by default.
    
    > [!IMPORTANT]
    >  After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. Para ver cómo descargar, instalar y ejecutar la Skype para la herramienta de actualización de reunión empresarial, consulte: [Herramienta de actualización de la reunión de Skype para empresas y Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype para Online de negocio, herramienta de migración de reunión (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)y [Skype para en línea de negocio, reunión Herramienta de migración (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).
  
Vea [Restablecer un id. de conferencia para un usuario](reset-a-conference-id-for-a-user.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Restablecer el PIN del organizador de una conferencia

Cada reunión que un usuario programa obtener asignará un identificador de conferencia único. Si bien crea automáticamente un identificador de conferencia y se asigna a un usuario, puede haber ocasiones cuando un usuario no desea utilizar este y que desea establecer para un cierto número, o los usuarios no pueden recordar o han perdido su identificador de conferencia. You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.

![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

1. En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En la parte superior de la página, haga clic en **Editar**.

3. En **Conferencias de Audio**, haga clic en **Restablecer PIN**y, a continuación, haga clic en **Restablecer**. 
  
![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio** 

1. Habilitar o deshabilitar el correo electrónico que se envían a los usuarios de acceso telefónico local
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. Click **Users**, and then select the user that you want to reset the PIN for.
    
4. In the Action pane, under **PIN**, click **Reset**.
    
Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset. But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user. The PIN will only be shown once after it has been reset. After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, ***** will be shown. 
  
Vea [Restablecer el PIN de conferencia de Audio](reset-the-audio-conferencing-pin.md).
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Enviar un correo electrónico con información de conferencia de Audio a un usuario

![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

1. En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En la parte superior de la página, haga clic en **Editar**.

3. En **Conferencias de Audio**, haga clic en **Enviar información de conferencia en el correo electrónico**. 

    > [!NOTE]
    > When you do this, the audio conferencing PIN isn't sent to the user. 

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**  

1. Habilitar o deshabilitar el correo electrónico que se envían a los usuarios de acceso telefónico local
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. Click **Users**, and then select the user that you want to reset the PIN for.
    
4. Haga clic en **Usuarios de acceso telefónico local** y seleccione el usuario para el que quiera restablecer el PIN.
    
    > [!NOTE]
    > When you do this, the audio conferencing PIN isn't sent to the user. 
  
Después de completar esta acción, el PIN de conferencia de acceso telefónico local no se enviará al usuario.
  
## <a name="setting-the-phone-numbers-included-on-invites"></a>Configuración del teléfono los números incluidos en invitaciones

![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

1. En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. Junto a **Conferencias de Audio**, haga clic en **Editar**.
 
3. En el panel de **Conferencia de Audio** , puede establecer el **número de teléfono de pago** y, si se permite, el **número de teléfono gratuito**.

4. Haga clic en **Guardar**.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**  
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
4. En el panel de acciones, puede establecer el **número de teléfono de pago** y, si se permite, el **número de teléfono gratuito**.

5. Haga clic en **Guardar**.
    
Vea [el teléfono los números incluidos en invitaciones](set-the-phone-numbers-included-on-invites.md).
  
  
## <a name="choosing-audio-conferencing-bridge-settings"></a>Elegir la configuración de puente de conferencia de audio

Configuración del puente de audioconferencia o de conferencia de acceso telefónico local

 ![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

1. En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página de **Puentes de conferencia** , haga clic en **configuración de puente**. 

3. En el panel **configuración de puente** , habilitar o deshabilitar la **entrada de la reunión y salir de las notificaciones**.

    Esto está habilitado de forma predeterminada. Si deshabilita esta opción, no se le notificará a los usuarios que ya se han unido a la reunión de forma predeterminada cuando alguien entra o sale de la reunión.

4. En **tipo de anuncio de entrada o salida**, elija **tonos** o **nombres o números de teléfono**. 

    Si elige **los nombres o números de teléfono**, también puede elegir habilitar o deshabilitar **los autores de llamadas Ask para registrar su nombre antes de unirse a la reunión**. 

1. Haga clic en **Guardar**.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio** 
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.
    
4. Under **Meeting join experience**, select the following actions:
    
  - En **Experiencia de entrada a la reunión**, seleccione las acciones siguientes:
    
    This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business or Microsoft Teams app and they modify the **Announce when people enter or leave** setting in the Skype Meeting or Microsoft Teams **Options** menu of the meeting.
    
  - Esta opción se puede configurar de manera específica en cada reunión cuando un usuario se une a una reunión con el cliente de Skype Empresarial y modifica la opción **Anunciar cuando entra o sale gente** en el menú Opciones de reunión de Skype de la reunión.
    
5. **Solicitar a los autores de la llamada que registren su nombre antes de unirse a la reunión**. Esta opción está seleccionada de forma predeterminada. Si la desactiva, no se solicitará a las personas que llamen que registren su nombre antes de unirse a una reunión.
    
Después de realizar los cambios, haga clic en [Guardar](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.

 ![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

1. En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página de **Puentes de conferencia** , haga clic en **configuración de puente**. 

3. En el panel **configuración de puente** , escriba el número de dígitos que desee para el PIN en la lista de **longitud PIN** y, a continuación, haga clic en **Guardar**.

    The PIN must be between 4 and 12 digits. The default is 5.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio** 
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.
    
4. Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.
    
    The PIN must be between 4 and 12 digits. The default is 5.
    
El PIN solo puede tener de 4 a 12 dígitos. El valor predeterminado es 5.
  
 Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.

 ![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

1. En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página de **Puentes de conferencia** , haga clic en **configuración de puente**. 

3. En el panel **configuración de puente** , habilitar o deshabilitar **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de conferencias de audio**.

4. Haga clic en **Guardar**. 
 
    También puede enviar correo electrónico al usuario con la configuración de conferencias de audio, vaya a las propiedades del usuario conferencias de audio y haciendo clic en **Enviar información de conferencia en el correo electrónico**.
    
    If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio** 
  
1. Habilitar o deshabilitar el correo electrónico que se envían a los usuarios de acceso telefónico local
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.
    
4. Click **Save**.
    
    Haga clic en **Guardar**.
    
    If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.
    
    Si hace esto, se enviará un correo electrónico que solo contenga el id. de la conferencia y el número de teléfono de la conferencia, pero no se incluirá el PIN.
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a>Vea y establezca la primaria (valor predeterminado) y los idiomas (alternativos) secundarios en un puente de conferencia de audio

 ![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

1. En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**. 

2. Seleccione un número de teléfono de la lista y haga clic en **Editar**.

3. Elija los idiomas que desee en **idioma predeterminado** e **idiomas alternativos (opcionales)**.

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio** 

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.
    
4. En el **Centro de administración de Skype Empresarial**, en el panel de navegación de la izquierda, vaya a **Conferencias de acceso telefónico local** y, luego, haga clic en **Puente de Microsoft**.
    
    You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider. The order that you select in the lists is the same order in which languages will be presented to callers.
    
También puede establecer el idioma principal y los idiomas secundarios compatibles al seleccionar Microsoft como proveedor de conferencias de acceso telefónico local. El orden que seleccione en las listas desplegables será el orden de los idiomas que se presentará a los autores de las llamadas.
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>Vea los números de acceso telefónico de conferencias de audio

![los equipos-logotipo-30x30.png](../images/teams-logo-30x30.png) **utilizando los equipos de Microsoft y Skype para el centro de administración de negocio**

1. En el panel de navegación izquierdo, vaya a **las reuniones** > **Puentes de conferencia**. 

2. Seleccione un número de teléfono de la lista y haga clic en **Editar**. Here you can:
    
  - View the phone numbers that are set by Office 365 to be used for Audio Conferencing. 
    
  - Ver la ubicación y el idioma principal, que se utilizará en el operador automático de conferencia de Audio.


![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **utilizando el Skype para el centro de administración de negocio**  

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**. Here you can:
    
  - View the phone numbers that are set by Office 365 to be used for Audio Conferencing. 
    
  - Puede ver los números de teléfono que Office 365 establece para usarse con las conferencias de acceso telefónico local.
    
  - También puede ver la ubicación y el idioma principal y los idiomas secundarios que usará el operador automático de las conferencias de acceso telefónico local.
    
Puede seleccionar el número de teléfono predeterminado de conferencia de acceso telefónico local que se asignará a los usuarios cuando estos se habiliten para la conferencia de acceso telefónico local. No obstante, si cambia el número de teléfono predeterminado del puente de conferencia de acceso telefónico local, el número de teléfono predeterminado de los usuarios existentes no cambiará.
  
Vea [una lista de números de conferencias de Audio](see-a-list-of-audio-conferencing-numbers.md).
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-see-a-list-of-users-that-are-enabled"></a>![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) Ver una lista de usuarios habilitados

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.
    
See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

Hay varias opciones de configuración que puede administrar en el nivel de organización mediante Windows PowerShell. Esto facilita la configuración se aplican a todos los usuarios. 
    
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

- **Establecer la longitud PIN** El valor predeterminado es 5.
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- **Establecer sólo marcado en reuniones desde un teléfono** El valor predeterminado _$false_.
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

- **Configuración de la dirección de correo electrónico que se envía a los usuarios** El valor predeterminado es _$null_. 
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
    
- Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics: 
    
  - [Introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
    
## <a name="related-topics"></a>See also

[Administrar la configuración de Audioconferencia para un usuario](manage-the-audio-conferencing-settings-for-a-user.md)


