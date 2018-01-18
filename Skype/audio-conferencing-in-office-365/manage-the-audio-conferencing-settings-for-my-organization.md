---
title: "Administrar la configuración de la conferencia de acceso telefónico local en mi organización"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'See steps to assign a dial-in conferencing license and conference ID to a user, set up a third party conferencing provider, and many other dial-in conferencing settings. '
ms.openlocfilehash: 6bca89f60c5ee4e9b840d2094500077cfa972902
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a>Administrar la configuración de la conferencia de acceso telefónico local en mi organización

[] Puede que le resulte más sencillo ver todas las opciones de configuración de conferencia de acceso telefónico local en un mismo lugar. 
  
## <a name="assign-an-audio-conferencing-license"></a>Asignar una licencia de conferencia de acceso telefónico local

> [!NOTE]
> No se puede asignar licencias usando el **Skype para el centro de administración de negocios**. Debe utilizar el centro de administración de Office 365. Consulte [Asignar Skype para licencias de negocio y equipos de Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). 
  
 Para asignar una licencia a un usuario
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. En la exploración de la izquierda del **Centro de administración de Office 365**, vaya a **usuarios** > **usuarios activos**y a continuación, seleccione el usuario o usuarios de la lista de usuarios disponibles.
    
    > [!NOTE]
    > Si va a asignar licencias a un máximo de 20 usuarios al mismo tiempo, puede usar el menú desplegable **Seleccionar una vista** y, luego, elegir una de las opciones o crear su propia vista. Luego, haga clic en **Editar**, haga clic dos veces en **Siguiente**, seleccione la licencia y haga clic en **Enviar**. También puede asignar licencias a varios usuarios con Windows PowerShell. Para obtener instrucciones y scripts de PowerShell de ejemplo, vea [Asignar licencias de Skype Empresarial](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). 
  
3. En el panel de acciones, en **Licencia asignada**, haga clic en **Editar**. 
    
4. En la página **Asignar licencia**, active **Conferencias RTC de Skype Empresarial** y haga clic en **Guardar**. Para obtener más información sobre licencias, consulte [Licencias complementarias de Skype Empresarial](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
> [!NOTE]
> Después de asignar la licencia, puede que Microsoft no aparezca en el menú desplegable como un proveedor de servicios de conferencia de acceso telefónico local. Si esto ocurre, cierre la sesión del centro de administración de Office 365 o presione CTRL + F5 para actualizar la ventana del explorador. 
  
## <a name="assign-a-conference-id-for-a-user"></a>Asignar un ID de conferencia para un usuario

Asignar un id. de conferencia a un usuario 
  
Identificadores estáticos se utilizan cuando las personas de la organización no desean recordar un número aleatorio; Puede seleccionar un determinado número o elija uno que sea fácil de recordar. Cuando se utilizan identificadores de conferencia dinámico, cada reunión programaciones de un usuario obtener asignará un identificador único conferencia. Si desea asignar el dinámico en lugar de conferencia estática identificadores, vea [conferencias de Audio utilizando identificadores dinámicos en su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
El Skype para el centro de administración de negocios no puede utilizarse para asignar un ID de conferencia a un usuario, pero puede utilizar el cmdlet de Windows PowerShell para ello.
  
El Centro de administración de Skype Empresarial no se puede usar para asignar un id. de conferencia a un usuario, pero se puede usar el cmdlet de Windows PowerShell para esta finalidad.
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> Para establecer el id. de conferencia de un usuario, ejecute: 
  
El id. de conferencia tiene que contener siete dígitos y no se puede cambiar en el Centro de administración de Skype Empresarial ni con Windows PowerShell.
  
> [!IMPORTANT]
>  Después de crea un nuevo ID de conferencia, no se puede utilizar el ID de conferencia antigua por los llamadores. Debe notificar a los usuarios a programar sus invitaciones para asegurarse de que la nueva conferencia que ID se agrega a las invitaciones para reuniones existentes. Los usuarios pueden utilizar el Skype para la herramienta de migración de reuniones de negocios para actualizar sus reuniones existentes. Para ver cómo descargar, instalar y ejecutar el Skype para la herramienta de actualización de reunión empresarial, consulte: [Herramienta de actualización de la reunión para Skype para empresas y Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype para los negocios en línea, herramienta de migración de reunión (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)y [Skype para los negocios en línea, reunión Herramienta de migración (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).
  
Consulte [Ver, cambiar y restablecer un ID de conferencia asignado a un usuario](see-change-and-reset-a-conference-id-assigned-to-a-user.md).
  
## <a name="change-the-audio-conferencing-provider-from-microsoft-to-a-third-party-provider"></a>Cambiar el proveedor de conferencia de audio de Microsoft a un proveedor de terceros

1. Cambiar el proveedor de servicios de conferencia de acceso telefónico local de Microsoft a un proveedor de terceros
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio** > **los usuarios**y a continuación seleccione el usuario que desea cambiar el proveedor de conferencia de audio para.
    
4. En el panel de acciones, haga clic en **Editar**. 
    
5. En la página de **Propiedades** , en **nombre del proveedor**, elija el proveedor de conferencia de audio para el usuario.
    
    > [!NOTE]
    > Sólo puede seleccionar Microsoft como proveedor de conferencia de audio o **Ninguno** , si ha seleccionado varios usuarios.
  
6. Solo puede seleccionar Microsoft como el proveedor de servicios de conferencia de acceso telefónico local o **Ninguno** si ha seleccionado varios usuarios. 
    
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a>Habilitar o deshabilitar los mensajes de correo electrónico enviados a los usuarios de conferencia de audio

Habilitar o deshabilitar el envío de correos electrónicos a los usuarios de acceso telefónico local
  
 Puede usar el Centro de administración de Skype Empresarial o Windows PowerShell para habilitar o deshabilitar el envío de correos electrónicos a los usuarios.
  
1. Usar el Centro de administración de Skype Empresarial
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En la página **configuración de puente de Microsoft** , active o desactive la **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de conferencia de audio**.
    
4. Haga clic en **Guardar**.
    
    Haga clic en **Guardar**.
    
    Si hace esto, se enviará un correo electrónico que solo contenga el id. de la conferencia y el número de teléfono de la conferencia, pero no se incluirá el PIN.
    
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
    
Puede realizar cambios en el correo electrónico enviado a los usuarios, como el correo electrónico se envía desde la dirección de correo electrónico o el nombre para mostrar para el correo electrónico mediante la ejecución de:
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Puede realizar cambios en el correo electrónico enviado a los usuarios, como la dirección de correo electrónico desde la que se envía el correo o el nombre para mostrar del correo electrónico al ejecutar:
  
Si quiere cambiar la información de la dirección de correo electrónico, tendrá que asegurarse de que las directivas de correo electrónico de entrada de su organización permitan la recepción de mensajes enviados por la dirección de correo electrónico personalizada.
  
Ver [mensajes de correo electrónico que se envían automáticamente a los usuarios al cambia su configuración de conferencia de Audio](emails-sent-to-users-when-their-settings-change.md).
  
## <a name="reset-the-meeting-conference-id"></a>Restablecer la reunión Id. de conferencia

1. Restablecer el id. de conferencia de reunión
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio**y, en el panel de acción en el **Id. de conferencia**, haga clic en **Restablecer**.
    
4. En el **Restablecer Id. de conferencia?** ventana, haga clic en **Sí**. Se creará automáticamente un Id. de conferencia y un correo electrónico al usuario con el nuevo ID de conferencia si está habilitado el envío de correo electrónico a los usuarios. Está habilitado de forma predeterminada.
    
    > [!IMPORTANT]
    >  Después de crea un nuevo ID de conferencia, no se puede utilizar el ID de conferencia antigua por los llamadores. Debe notificar a los usuarios a programar sus invitaciones para asegurarse de que la nueva conferencia que ID se agrega a las invitaciones para reuniones existentes. Los usuarios pueden utilizar el Skype para la herramienta de migración de reuniones de negocios para actualizar sus reuniones existentes. Para ver cómo descargar, instalar y ejecutar el Skype para la herramienta de actualización de reunión empresarial, consulte: [herramienta de actualización de la reunión para Skype para empresas y Lync] ((https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype para negocios en línea Reunión de la herramienta de migración (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)y [Skype para negocios en línea, herramienta de migración de reunión (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).
  
Vea [Restablecer un Id. de conferencia para un usuario](reset-a-conference-id-for-a-user.md).
  
## <a name="reset-a-conference-organizers-pin"></a>Restablecer el PIN del organizador de una conferencia

Identificadores estáticos se utilizan cuando las personas de la organización no desean recordar un número aleatorio; Puede seleccionar un determinado número o utilizar uno que sea fácil de recordar. Cuando se utilizan identificadores de conferencia dinámico, cada reunión programaciones de un usuario obtener asignará un identificador único conferencia. Si desea asignar el dinámico en lugar de conferencia estática IDs, [conferencias de Audio utilizando identificadores dinámicos en su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
Aunque crea automáticamente un ID de conferencia estática y se asigna a un usuario, puede haber ocasiones cuando un usuario no desea utilizar esta y desea establecerla en un número determinado, o los usuarios no recuerdan o han perdido su ID de conferencia. Puede utilizar el Skype para el centro de administración de negocios y de Windows PowerShell para ver, cambiar y restablecer su ID de conferencia.
  
1. Habilitar o deshabilitar el correo electrónico que se envían a los usuarios de acceso telefónico local
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. Haga clic en **usuarios**y, a continuación, seleccione el usuario que desea restablecer el PIN para.
    
4. En el panel de acción, **PIN**, haga clic en **Restablecer**.
    
Los usuarios recibirán un correo electrónico con su NIP cuando están habilitados para conferencias de audio o cuando se restablece el NIP. Pero si ha deshabilitado automáticamente enviar mensajes de correo electrónico, no se enviará un correo electrónico de restablecimiento PIN y tendrá que enviar manualmente el PIN al usuario. El PIN sólo aparecerá una vez después de que se ha restablecido. Después se muestra inmediatamente después de que se restablezca, el PIN no se muestra ya en las propiedades del usuario; en su lugar, *** aparecerá. 
  
Los usuarios recibirán un correo electrónico con su PIN cuando estén habilitados para la conferencia de acceso telefónico local o cuando se restablezca el PIN. Pero, si deshabilitó el envío automático de correos electrónicos, no se enviará un correo electrónico de restablecimiento de PIN al usuario y tendrá que enviar el PIN al usuario de forma manual. El PIN solo se mostrará una vez después de que se haya restablecido. Una vez que se muestra inmediatamente después de haberse restablecido, el PIN no se mostrará más en las propiedades del usuario y en su lugar se mostrará *****.
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Enviar un correo electrónico con información de conferencia de Audio a un usuario

1. Enviar un correo electrónico con información sobre la conferencia de acceso telefónico local a un usuario
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. Haga clic en **usuarios**y, a continuación, seleccione el usuario que desea restablecer el PIN para.
    
4. Haga clic en **Usuarios de acceso telefónico local** y seleccione el usuario para el que quiera restablecer el PIN.
    
    > [!NOTE]
    > Al hacerlo, la conferencia de audio PIN no se envía al usuario. 
  
Después de completar esta acción, el PIN de conferencia de acceso telefónico local no se enviará al usuario.
  
## <a name="setting-the-default-audio-conferencing-phone-number-for-meeting-organizers"></a>Establecer el número de teléfono de conferencia de audio predeterminado para los organizadores de la reunión

 Configurar el número de teléfono de conferencias de acceso telefónico local predeterminado para los organizadores de reuniones
  
1. Para establecer el número de teléfono de conferencias de acceso telefónico local predeterminado para los organizadores de reuniones cuando está habilitando un usuario para las conferencias de acceso telefónico local
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
4. En el panel de acciones, en las propiedades del usuario, haga clic en **Editar**.
    
5. En la página de **Propiedades** , en **nombre del proveedor**, utilice la lista desplegable para seleccionar el proveedor de conferencia de audio.
    
  - Si selecciona Microsoft como proveedor de conferencia de audio, puede elegir el número de teléfono de conferencia de audio predeterminado en la lista.  
    
  - Si selecciona Microsoft como el proveedor de servicios de conferencia de acceso telefónico local, puede elegir de la lista el número de teléfono predeterminado de las conferencias de acceso telefónico local.
    
    Si selecciona un ACP de terceros como proveedor de servicios de conferencia de acceso telefónico local, tendrá que introducir manualmente el número de pago y, si es necesario, el número de teléfono gratuito. Estos números de teléfono serán el número de teléfono predeterminado.
    
6. El número de teléfono de conferencias de acceso telefónico local predeterminado de un usuario es el número que se muestra en la invitación a la reunión cuando se programa una. 
    
Consulte [el teléfono invita números incluidos en](set-the-phone-numbers-included-on-invites.md).
  
 Vea **Establecer los números de teléfono de conferencias de Audio para organizadores que se incluyen en invitaciones**.
  
1. Para establecer el número de teléfono de conferencias de acceso telefónico local predeterminado después de haber habilitado un usuario para las conferencias de acceso telefónico local
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio** > **usuarios**, seleccione el usuario que desee y, en la página acción, haga clic en **Editar**.
    
4. En la página de **Propiedades** , en **nombre del proveedor**, utilice la lista desplegable para seleccionar el proveedor de conferencia de audio.
    
  - Si el usuario utiliza Microsoft como proveedor de conferencia de audio, puede elegir el número de teléfono de conferencia de audio predeterminado en la lista.  
    
  - Si el usuario usa Microsoft como el proveedor de servicios de conferencia de acceso telefónico local, puede elegir de la lista el número de teléfono predeterminado de las conferencias de acceso telefónico local.
    
    Si el usuario usa un ACP de terceros como proveedor de servicios de conferencia de acceso telefónico local, tendrá que introducir manualmente el número de pago y, si es necesario, el número de teléfono gratuito.
    
5. El número de teléfono de conferencias de acceso telefónico local predeterminado de un usuario es el número que se muestra en la invitación a la reunión cuando se programa una. 
    
Consulte [el teléfono invita números incluidos en](set-the-phone-numbers-included-on-invites.md).
  
## <a name="setting-audio-conferencing-bridge-settings"></a>Configuración de puente de conferencia de audio

 Configuración del puente de audioconferencia o de conferencia de acceso telefónico local
  
1. Establecer la experiencia de reunión cuando las personas que llaman se unen a una reunión
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio** > **configuración de puente de Microsoft**.
    
4. En **experimentar la combinación de reunión**, seleccione las siguientes acciones:
    
  - En **Experiencia de entrada a la reunión**, seleccione las acciones siguientes:
    
    Se puede establecer de forma reunión cuando un usuario une a una reunión mediante un Skype para la aplicación de negocios o Teams de Microsoft y modifican la configuración de **anunciar cuando entran o salen** del menú reunión de Skype o Microsoft Teams **Opciones** de la reunión.
    
  - Esta opción se puede configurar de manera específica en cada reunión cuando un usuario se une a una reunión con el cliente de Skype Empresarial y modifica la opción **Anunciar cuando entra o sale gente** en el menú Opciones de reunión de Skype de la reunión.
    
5. **Solicitar a los autores de la llamada que registren su nombre antes de unirse a la reunión**. Esta opción está seleccionada de forma predeterminada. Si la desactiva, no se solicitará a las personas que llamen que registren su nombre antes de unirse a una reunión.
    
Después de realizar los cambios, haga clic en [Guardar](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.
  
1. Configurar la longitud del PIN de las reuniones
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio** > **configuración de puente de Microsoft**.
    
4. En **seguridad**, especifique el número de dígitos que desee para el PIN en la lista de **longitud PIN** y, a continuación, haga clic en **Guardar**.
    
    El NIP debe tener entre 4 y 12 dígitos. El valor predeterminado es 5.
    
El PIN solo puede tener de 4 a 12 dígitos. El valor predeterminado es 5.
  
 Vea **Cambiar la configuración de un puente de conferencias de acceso telefónico local de Microsoft**.
  
1. Habilitar o deshabilitar el correo electrónico que se envían a los usuarios de acceso telefónico local
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En la página **configuración de puente de Microsoft** , active o desactive la **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de conferencia de audio**.
    
4. Haga clic en **Guardar**.
    
    Haga clic en **Guardar**.
    
    Si lo hace, se enviará un correo electrónico que sólo incluye los Id. de conferencia y número de teléfono de conferencia, pero el PIN no se incluirán.
    
    Si hace esto, se enviará un correo electrónico que solo contenga el id. de la conferencia y el número de teléfono de la conferencia, pero no se incluirá el PIN.
    
## <a name="see-and-set-the-primary-and-secondary-languages-on-an-audio-conferencing-bridge"></a>Ver y configurar los idiomas primarios y secundarios en un puente de conferencia de audio

1. Ver y configurar el idioma principal y los secundarios en un puente de conferencias de acceso telefónico local
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio**y, a continuación, haga clic en **puente de Microsoft**.
    
4. En el **Centro de administración de Skype Empresarial**, en el panel de navegación de la izquierda, vaya a **Conferencias de acceso telefónico local** y, luego, haga clic en **Puente de Microsoft**.
    
    También puede establecer los idiomas primarios y secundarios que son compatibles cuando se selecciona Microsoft como proveedor de conferencia de audio. El orden en que se selecciona en la lista es el mismo orden en el que se presentará idiomas a los llamadores.
    
También puede establecer el idioma principal y los idiomas secundarios compatibles al seleccionar Microsoft como proveedor de conferencias de acceso telefónico local. El orden que seleccione en las listas desplegables será el orden de los idiomas que se presentará a los autores de las llamadas.
  
## <a name="see-audio-conferencing-dial-in-numbers"></a>Ver números de acceso telefónico de conferencia de audio

1. Ver números de acceso telefónico para conferencias de acceso telefónico local
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio** > **puente de Microsoft**. Aquí puede:
    
  - Ver los números de teléfono que se configuran mediante Office 365 para utilizarse para conferencias de Audio. 
    
  - Puede ver los números de teléfono que Office 365 establece para usarse con las conferencias de acceso telefónico local.
    
  - También puede ver la ubicación y el idioma principal y los idiomas secundarios que usará el operador automático de las conferencias de acceso telefónico local.
    
Puede seleccionar el número de teléfono predeterminado de conferencia de acceso telefónico local que se asignará a los usuarios cuando estos se habiliten para la conferencia de acceso telefónico local. No obstante, si cambia el número de teléfono predeterminado del puente de conferencia de acceso telefónico local, el número de teléfono predeterminado de los usuarios existentes no cambiará.
  
Vea [una lista de números de conferencia de Audio](see-a-list-of-audio-conferencing-numbers.md).
  
## <a name="see-a-list-of-users-that-are-enabled"></a>Ver una lista de usuarios que están habilitados

1. Ver una lista de usuarios habilitados
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio**> y, a continuación, **los usuarios**.
    
Vea [una lista de usuarios que están habilitados para conferencias de Audio](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).
  
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
- Windows PowerShell es todo sobre la administración de usuarios y lo que los usuarios se permiten o no realizar. Con Windows PowerShell, puede administrar Office 365 mediante un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer. Para empezar a utilizar Windows PowerShell, consulte estos temas:
    
  - Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad sobre utilizando sólo el centro de administración de Office 365, como cuando realice cambios en la configuración de muchos usuarios al mismo tiempo. Obtenga información acerca de estas ventajas en los siguientes temas: 
    
  - [Introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
    
## <a name="related-topics"></a>Temas relacionados

[Administrar la configuración de conferencia de Audio para un usuario](manage-the-audio-conferencing-settings-for-a-user.md)

[Configurar Audioconferencia para Skype Empresarial y Microsoft Teams](set-up-audio-conferencing.md)

