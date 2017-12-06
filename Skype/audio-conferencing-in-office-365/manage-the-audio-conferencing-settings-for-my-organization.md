---
title: "¿Administrar la configuración de conferencias de Audio de mi organización?"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/14/2017
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- Strat_SB_PSTN
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
description: "See steps to assign a dial-in conferencing license and conference ID to a user, set up a third party conferencing provider, and many other dial-in conferencing settings. "
---

# ¿Administrar la configuración de conferencias de Audio de mi organización?

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la [declinación de responsabilidades](bc9bd328-c5b2-44e5-af15-e02bf00e1c81.md#MT_Footer). Para su referencia, puede encontrar la versión en inglés de este artículo [aquí](https://support.office.com/en-us/article/bc9bd328-c5b2-44e5-af15-e02bf00e1c81). 
  
Es posible que resulte más fácil ver toda la configuración de conferencias de audio de Skype para la empresa y Teams de Microsoft en un único lugar.
  
## Asignar una licencia de conferencias de Audio

> [!NOTE]
> No puede asignar licencias con la **Centro de administración de Skype Empresarial**. Deberá usar el centro de administración de Office 365. Vea [Asignar Skype para Business y Microsoft Teams licencias](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). 
  
 **Para asignar una licencia para un usuario**
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. En el panel de navegación izquierdo del **Centro de administración de Office 365**, vaya a **usuarios** > **usuarios activos** y, a continuación, seleccione el usuario o los usuarios de la lista de usuarios disponibles.
    
    > [!NOTE]
    > Si va a asignar licencias a hasta 20 usuarios al mismo tiempo, puede usar la lista desplegable **Seleccionar una vista**, a continuación, elija una de las opciones o crear su propia vista. A continuación, haga clic en **Editar**, **siguiente** dos veces, a continuación, seleccione la licencia y haga clic en **Enviar**. También puede asignar licencias a varios usuarios con Windows Powershell. Para obtener instrucciones y secuencias de comandos de PowerShell de ejemplo, vea [Asignar Skype para Business y Microsoft Teams licencias](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). 
  
3. En el panel de acciones, en **Licencias de productos**, haga clic en **Editar**. 
    
4. En la página **Licencias de producto**, activar **Conferencias de Audio** y, a continuación, haga clic en **Guardar**. Para obtener más información sobre las licencias, vea [Skype para Business y Microsoft Teams licencias de complemento](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
> [!NOTE]
> Después de asignar la licencia, Microsoft puede no aparecer inicialmente en la lista como un proveedor de servicios de audioconferencia. Si esto sucede, inicie sesión en el centro de administración de Office 365 o presione CTRL + F5 para actualizar la ventana del explorador. 
  
## Asignar un id. de conferencia a un usuario

Un identificador de conferencia se asigna automáticamente a un usuario cuando están configurados para conferencias de audio con Microsoft como proveedor de conferencias de audio. El identificador de conferencia asignado puede ser estática o dinámica y se envía la invitación a la reunión si la reunión está programada.
  
Identificadores estáticos se usan cuando los usuarios de su organización no necesita recordar un número aleatorio; Puede seleccionar un número determinado o elegir uno que sea fácil de recordar. Cuando se usan los identificadores de conferencia dinámicos, cada reunión las programaciones de un usuario obtener asignará un identificador único. Si desea asignar dinámico en lugar de la conferencia estático identificadores, [Uso de los identificadores dinámicos de conferencias de Audio de su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
El Centro de administración de Skype Empresarial no se puede usar para asignar un id. de conferencia a un usuario, pero se puede usar el cmdlet de Windows PowerShell para esta finalidad.
  
Para establecer el id. de conferencia de un usuario, ejecute:
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> Un identificador de conferencia debe contener 7 dígitos y no puede cambiar en la Skype centro de administración de la empresa o con Windows PowerShell. 
  
Consulte [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) para obtener más información sobre el cmdlet.
  
> [!IMPORTANT]
>  Después de crea un nuevo identificador de conferencia, el identificador de conferencia antiguo no puede ser usado por las personas que llaman. Debe notificar a los usuarios a programar sus existentes invitaciones para asegurarse de que la conferencia nueva que identificador se agrega a las invitaciones de la reunión. Los usuarios pueden usar la herramienta de migración de reuniones Skype Empresarial para actualizar sus reuniones existentes. Para ver cómo descargar, instalar y ejecutar la Skype para la herramienta de actualización de reuniones de empresa, consulte:> [Herramienta de actualización de reuniones para Skype y Lync](http://technet.microsoft.com/library/2b525fe6-ed0f-4331-b533-c31546fcf4d4%28Office.14%29.aspx)> [Skype Empresarial Online, herramienta de migración de reuniones (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)> [Skype empresarial Online, la herramienta de migración de reuniones (32 bits)](https://go.microsoft.com/fwlink/?LinkID=626046)
  
Consulte [Ver, modificar y restablecer un identificador de conferencia asignado a un usuario](see-change-and-reset-a-conference-id-assigned-to-a-user.md).
  
## Cambiar el proveedor de conferencias de audio de Microsoft a un proveedor de terceros

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En la **Centro de administración de Skype Empresarial**, en el panel de navegación izquierdo, vaya a las **conferencias de Audio** > **usuarios** y luego seleccione el usuario que desea cambiar el proveedor de conferencias de audio para.
    
4. En el panel de acciones, haga clic en **Editar**.
    
5. En la página de **Propiedades**, en **nombre del proveedor**, seleccione el proveedor de servicios de audioconferencia para el usuario.
    
    > [!NOTE]
    > Solo puede seleccionar Microsoft como proveedor de conferencias de audio o **Ninguno** si ha seleccionado varios usuarios.
  
6. Haga clic en **Guardar**.
    
Consulte [Cambiar el proveedor de servicios de conferencia de acceso telefónico local para los usuarios](http://technet.microsoft.com/library/9b74f053-4d23-485f-9232-3d30370a8c6e%28Office.14%29.aspx).
  
## Habilitar o deshabilitar los correos electrónicos enviados a los usuarios de conferencias de audio

Puede usar la Skype centro de administración de la empresa o Windows PowerShell para habilitar o deshabilitar el correo electrónico enviado a los usuarios.
  
 **Usar la Skype centro de administración de la empresa**
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya al **Centro de administración de Office 365** > **Skype Empresarial** y en el panel de navegación izquierdo, haga clic en **conferencias de Audio**.
    
3. En la página **Configuración del puente de Microsoft**, active o desactive **Enviar automáticamente los mensajes de correo electrónico a los usuarios si cambia su configuración de conferencias de audio**.
    
4. Haga clic en **Guardar**.
    
    También puede enviar mensajes de correo electrónico al usuario con la configuración de conferencias de audio va a las propiedades del usuario audioconferencia y haciendo clic en **Enviar información de conferencia por correo electrónico**. El número de teléfono conferencia predeterminada y el identificador de conferencia de audio se incluye en la invitación a la reunión pero no el PIN.
    
    Vea [Enviar un correo electrónico a un usuario con su información de conferencias de Audio](send-an-email-to-a-user-with-their-audio-conferencing-information.md).
    
 **Uso de Windows PowerShell**
  
- También puede usar Windows PowerShell y ejecutar:
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    Puede usar el [Conjunto CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) administrar otras opciones de configuración de la organización, como correo electrónico.
    
## Cambiar la información de contacto del remitente en los mensajes de correo electrónico enviado a los usuarios

Puede realizar cambios en el correo electrónico que se envía automáticamente a los usuarios, incluida la dirección de correo electrónico real y el nombre para mostrar de la información de contacto del remitente. De forma predeterminada, el remitente de los mensajes de correo electrónico es Office 365, pero puede cambiar la dirección de correo electrónico y nombre para mostrar con Windows PowerShell y el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) . Para realizar cambios en la dirección de correo electrónico que envía el correo electrónico a los usuarios, debe:
  
- Escriba la dirección de correo electrónico en el parámetro  _SendEmailFromAddress_.
    
- Escriba el nombre para mostrar del correo electrónico en el parámetro  _SendEmailFromDisplayName_.
    
- Establecer el parámetro  _SendEmailOverride_ en _True_.
    
Puede realizar cambios en el correo electrónico enviado a los usuarios, como la dirección de correo electrónico desde la que se envía el correo o el nombre para mostrar del correo electrónico al ejecutar:
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

Si quiere cambiar la información de la dirección de correo electrónico, tendrá que asegurarse de que las directivas de correo electrónico de entrada de su organización permitan la recepción de mensajes enviados por la dirección de correo electrónico personalizada.
  
Puede usar el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) administrar otras opciones de configuración de la organización, como correo electrónico.
  
Ver [Mensajes de correo electrónico que se envían automáticamente a los usuarios cuando cambie su configuración de conferencias de Audio](emails-that-are-automatically-sent-to-users-when-their-audio-conferencing-settin.md).
  
## Restablecer el id. de conferencia de reunión

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En la **Centro de administración de Skype Empresarial**, en el panel de navegación izquierdo, vaya a las **conferencias de Audio** y, en el panel Acción, en **El identificador de conferencia**, haga clic en **Restablecer**.
    
4. En la **Restablecer Id. de conferencia?** ventana, haga clic en **Sí**. Se crea automáticamente un identificador de conferencia y envía un correo electrónico al usuario con el nuevo identificador de conferencia si se habilita el envío de correo electrónico a los usuarios. Se habilita de forma predeterminada.
    
    > [!IMPORTANT]
    >  Después de crea un nuevo identificador de conferencia, el identificador de conferencia antiguo no puede ser usado por las personas que llaman. Debe notificar a los usuarios a programar sus existentes invitaciones para asegurarse de que la conferencia nueva que identificador se agrega a las invitaciones de la reunión. Los usuarios pueden usar la herramienta de migración de reuniones Skype Empresarial para actualizar sus reuniones existentes. Para ver cómo descargar, instalar y ejecutar la Skype para la herramienta de actualización de reuniones de empresa, consulte:> [Herramienta de actualización de reuniones para Skype y Lync](http://technet.microsoft.com/library/2b525fe6-ed0f-4331-b533-c31546fcf4d4%28Office.14%29.aspx)> [Skype Empresarial Online, herramienta de migración de reuniones (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)> [Skype empresarial Online, la herramienta de migración de reuniones (32 bits)](https://go.microsoft.com/fwlink/?LinkID=626046)
  
Vea [Restablecer un id. de conferencia para un usuario](reset-a-conference-id-for-a-user.md).
  
## Restablecer el PIN del organizador de una conferencia

Identificadores estáticos se usan cuando los usuarios de su organización no necesita recordar un número aleatorio; Puede seleccionar un número determinado o utilice uno que sea fácil de recordar. Cuando se usan los identificadores de conferencia dinámicos, cada reunión las programaciones de un usuario obtener asignará un identificador único. Si desea asignar dinámico en lugar de la conferencia estático identificadores, [Uso de los identificadores dinámicos de conferencias de Audio de su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
Aunque se crea automáticamente un identificador de conferencia estático y se asigna a un usuario, puede haber ocasiones cuando un usuario no desea usar esta y desea configurar a un número determinado, o los usuarios no recuerda o que han perdido su identificador de conferencia. Puede usar la Skype centro de administración de la empresa y Windows PowerShell para ver, modificar y restablecer su identificador de conferencia.
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya al **Centro de administración de Office 365** > **Skype Empresarial** y en el panel de navegación izquierdo, haga clic en **conferencias de Audio**.
    
3. Haga clic en **usuarios** y, a continuación, seleccione el usuario que desea restablecer el PIN para.
    
4. En el panel Acción, **PIN**, haga clic en **Restablecer**.
    
Los usuarios recibirán un correo electrónico con su PIN cuando se encuentran habilitadas para conferencias de audio o cuando se restablece el PIN. Pero, si ha deshabilitado automáticamente enviar correos electrónicos, no se enviará un correo electrónico de restablecimiento PIN y tendrá que enviar manualmente el PIN para el usuario. El PIN sólo se mostrará una vez después de que se ha restablecido. Después de que se muestra inmediatamente después de restablecer, el PIN no se muestra ya en las propiedades de usuario en su lugar, *** se mostrarán.
  
Vea [Restablecer el PIN de conferencia de Audio para un usuario](reset-the-audio-conferencing-pin-for-a-user.md).
  
## Enviar un correo electrónico con la información de conferencias de Audio a un usuario

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya al **Centro de administración de Office 365** > **Skype Empresarial** y en el panel de navegación izquierdo, haga clic en **conferencias de Audio**.
    
3. Haga clic en **usuarios** y, a continuación, seleccione el usuario que desea restablecer el PIN para.
    
4. En el panel de acciones, haga clic en **Enviar información de conferencia por correo electrónico**.
    
    > [!NOTE]
    > Cuando hace esto, la audioconferencia PIN no se envía al usuario. 
  
Vea [Enviar un correo electrónico a un usuario con su información de conferencias de Audio](send-an-email-to-a-user-with-their-audio-conferencing-information.md).
  
## Establecer el número de teléfono de conferencias de audio predeterminado para los organizadores de la reunión

 **Para establecer el número de teléfono de conferencias de audio predeterminado para los organizadores de la reunión cuando se habilita un usuario para conferencias de Audio**
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En el panel de navegación izquierdo, vaya a las **conferencias de Audio** > **usuarios**. Seleccione el usuario que desea habilitar para conferencias de Audio.
    
4. En el panel Acción, en las propiedades del usuario, haga clic en **Editar**.
    
5. En la página de **Propiedades**, en **nombre del proveedor**, use la lista desplegable para seleccionar el proveedor de servicios de audioconferencia.
    
  - Si selecciona Microsoft como proveedor de conferencias de audio, puede elegir el número de teléfono de conferencias de audio predeterminado de la lista.
    
  - Si selecciona un ACP de terceros como proveedor de conferencias de audio, debe introducir manualmente el número de pago y si es necesario, el número de teléfono gratuito. Los números de teléfono será el número de teléfono predeterminado.
    
    El número de teléfono de conferencias de audio predeterminado de un usuario es el número que se muestra en la invitación a la reunión al programar una reunión.
    
6. Haga clic en **Guardar**.
    
Consulte [Establecer los números de teléfono de conferencias de Audio para organizadores que se incluyen en invitaciones](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
 **Para establecer el número de teléfono de conferencias de audio predeterminado para los organizadores de la reunión después de habilitar a un usuario para conferencias de audio**
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En la **Centro de administración de Skype Empresarial**, en el panel de navegación izquierdo, vaya a las **conferencias de Audio** > **usuarios**, seleccione el usuario que desee y, en la página acción, haga clic en **Editar**.
    
4. En la página de **Propiedades**, en **nombre del proveedor**, use la lista desplegable para seleccionar el proveedor de servicios de audioconferencia.
    
  - Si el usuario usa Microsoft como proveedor de conferencias de audio, puede elegir el número de teléfono de conferencias de audio predeterminado de la lista.
    
  - Si el usuario usa un ACP de terceros como proveedor de conferencias de audio, debe introducir manualmente el número de pago y si es necesario, el número de teléfono gratuito.
    
    El número de teléfono de conferencias de audio predeterminado de un usuario es el número que se muestra en la invitación a la reunión al programar una reunión.
    
5. Haga clic en **Guardar**.
    
Consulte [Establecer los números de teléfono de conferencias de Audio para organizadores que se incluyen en invitaciones](set-the-audio-conferencing-phone-numbers-for-meeting-organizers-that-are-include.md).
  
## Establecer la configuración del puente de conferencia de audio

 **Establecer la experiencia de reunión cuando las personas que llaman unirse a una reunión**
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En la **Centro de administración de Skype Empresarial**, en el panel de navegación izquierdo, vaya a las **conferencias de Audio** > **Configuración del puente de Microsoft**.
    
4. En **experiencia de unirse a la reunión**, seleccione las acciones siguientes:
    
  - **Habilitar la entrada de la reunión y salir de notificaciones para ser activado** Esta opción está seleccionada de forma predeterminada. Si desactiva esta casilla, los usuarios que ya se han unido a la reunión de forma predeterminada no recibir una notificación cuando alguien entra o sale de la reunión.
    
    Se puede establecer en una base de la reunión por reunión cuando un usuario une a una reunión mediante un Skype para empresas o Microsoft Teams la aplicación y modifican la configuración de **anunciar cuando entra o sale gente** en el menú **Opciones** de Microsoft Teams o reunión de Skype de la la reunión.
    
  - **Personas que llaman de ASK grabar su nombre antes de unirse a la reunión** Esta opción está seleccionada de forma predeterminada. Si desactiva esta casilla, las personas que llaman no pedirá que graben sus nombres antes de unirse a una reunión.
    
5. Después de realizar los cambios, haga clic en **Guardar**.
    
Consulte [Cambiar la configuración de un puente de conferencia de Audio](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Establecer la longitud del PIN para las reuniones**
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En la **Centro de administración de Skype Empresarial**, en el panel de navegación izquierdo, vaya a las **conferencias de Audio** > **Configuración del puente de Microsoft**.
    
4. En **seguridad**, escriba el número de dígitos que desee para el PIN en la lista de **longitud del PIN** y, a continuación, haga clic en **Guardar**.
    
    El PIN debe estar entre 4 y 12 dígitos. El valor predeterminado es 5.
    
Consulte [Cambiar la configuración de un puente de conferencia de Audio](change-the-settings-for-an-audio-conferencing-bridge.md).
  
 **Habilitar o deshabilitar el correo electrónico se envíe a los usuarios de audio**
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya al **Centro de administración de Office 365** > **Skype Empresarial** y en el panel de navegación izquierdo, haga clic en **conferencias de Audio**.
    
3. En la página **Configuración del puente de Microsoft**, active o desactive **Enviar automáticamente los mensajes de correo electrónico a los usuarios si cambia su configuración de conferencias de audio**.
    
4. Haga clic en **Guardar**.
    
    También puede enviar correo electrónico al usuario con la configuración de conferencias de audio, las propiedades del usuario conferencias de audio y haga clic en **Enviar información de conferencia por correo electrónico**.
    
    Si hace esto, se enviará un correo electrónico que solo contenga el id. de la conferencia y el número de teléfono de la conferencia, pero no se incluirá el PIN.
    
    Vea [Enviar un correo electrónico a un usuario con su información de conferencias de Audio](send-an-email-to-a-user-with-their-audio-conferencing-information.md).
    
## Ver y configurar los idiomas primarios y secundarios en un puente de conferencia de audio

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En la **Centro de administración de Skype Empresarial**, en el panel de navegación izquierdo, vaya a las **conferencias de Audio** y, a continuación, haga clic en **puente de Microsoft**.
    
4. Seleccione un número de teléfono de la lista, haga clic en **establecer idiomas** en el panel acción y, a continuación, en la página **establecer idiomas**, haga clic en usar la lista **idioma principal** para ver la lista completa de los idiomas admitidos.
    
    También puede configurar los idiomas primario y secundarios que son compatibles cuando se selecciona Microsoft como el proveedor de servicios de audioconferencia. El orden en que se selecciona en las listas es el mismo orden en que se presentará los idiomas a las personas que llaman.
    
Consulte [Establecer idiomas del operador automático para conferencias de Audio](set-auto-attendant-languages-for-audio-conferencing.md).
  
## Ver los números de acceso telefónico de conferencias de audio

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En la **Centro de administración de Skype Empresarial**, en el panel de navegación izquierdo, vaya a las **conferencias de Audio** > **puente de Microsoft**. Aquí puede:
    
  - Ver los números de teléfono que Office 365 establece para usarse para conferencias de Audio.
    
  - Ver la ubicación y los idiomas principales y secundarios, que se usará el operador automático de conferencias de Audio.
    
  - Seleccione el número de teléfono predeterminado que se asignará a los usuarios cuando están habilitadas para conferencias de Audio. Sin embargo, si cambia el número de teléfono predeterminado del puente de conferencia de audio, no cambiará el número de teléfono predeterminado para los usuarios existentes.
    
Puede ir a las **conferencias de Audio** > **usuarios** y seleccione las propiedades del usuario para cambiar el valor predeterminado de número para un usuario seleccionando un nuevo número de la lista de números que están disponibles en su organización.
  
Vea [Ver una lista de números de conferencias de Audio](see-a-list-of-audio-conferencing-numbers.md).
  
## Ver una lista de usuarios habilitados

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En la **Centro de administración de Skype Empresarial**, en el panel de navegación izquierdo, vaya a las **conferencias de Audio** > y, a continuación, **los usuarios**.
    
Vea [Ver una lista de usuarios que están habilitados para conferencias de Audio](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).
  
## ¿Desea saber cómo administrar con Windows PowerShell?

- Existen varias opciones que puede administrar en el nivel de organización con Windows PowerShell. Esto facilita la configuración se aplican a todos los usuarios. Estas son la configuración de nivel de la organización:
    
    Para obtener más ayuda sobre cada cmdlet, vea [Skype para empresarial Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

    El valor predeterminado es  _$true_.
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

    El valor predeterminado es  _$true_.
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

    El valor predeterminado es 5.
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

    El valor predeterminado es  _$false_.
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    El valor predeterminado es  _$true_.
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

    El valor predeterminado es  _$false_.
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

    El valor predeterminado es  _$null_.
    
> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

    El valor predeterminado es  _$null_.
    
- Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [¿Por qué necesita usar PowerShell de Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tiene muchas ventajas velocidad, simplificar y productividad sobre usando solo el centro de administración de Office 365, como cuando realice cambios en la configuración de muchos usuarios a la vez. Obtenga más información sobre estas ventajas en los siguientes temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
    
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  
## Vea también
<a name="MT_Footer"> </a>

#### 

[Configurar conferencias de Audio de Skype para la empresa y Teams de Microsoft](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)

