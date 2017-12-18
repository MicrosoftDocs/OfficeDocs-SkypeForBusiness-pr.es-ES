---
title: "Ver, modificar y restablecer un identificador de conferencia asignado a un usuario"
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
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
description: "Learn how to assign a conference ID to a user in Skype for Business and what the conference ID's parameters should be. "
---

# Ver, modificar y restablecer un identificador de conferencia asignado a un usuario

> [!IMPORTANT]
> Este artículo se ha traducido con traducción automática; vea la declinación de responsabilidades.  
  
Un identificador de conferencia se asigna automáticamente a un Skype para empresas o Microsoft Teams usuario cuando están configuradas para conferencias de Audio en Office 365 y usar Microsoft como proveedor de conferencias de audio. El identificador de conferencia asignado puede ser estática o dinámica y se envía la invitación a la reunión si la reunión está programada.
  
Identificadores estáticos se usan cuando los usuarios de su organización no necesita recordar un número aleatorio; Puede seleccionar un número determinado o utilice uno que sea fácil de recordar. Cuando se usan los identificadores de conferencia dinámicos, cada reunión las programaciones de un usuario obtener asignará un identificador único. Si desea asignar dinámico en lugar de la conferencia estático identificadores, [Uso de los identificadores dinámicos de conferencias de Audio de su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
Aunque se crea automáticamente un identificador de conferencia estático y se asigna a un usuario, puede haber ocasiones cuando un usuario no desea usar esta y desea configurar a un número determinado, o cuando los usuarios no recuerda o han perdido su identificador de conferencia. Puede usar la **Skype centro de administración de la empresa** y Windows PowerShell para ver, modificar y restablecer su identificador de conferencia.
  
Se enviará un correo electrónico al usuario con el identificador de conferencia y los números de teléfono de conferencias de audio predeterminado o si restablece el identificador de conferencia se enviarán otro correo electrónico que incluye el identificador de conferencia, pero no un PIN.
  
## Ver y cambiar los identificadores de conferencia

### Para ver el id. de conferencia

Puede ver su identificador de conferencia y enviar a los usuarios.
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En la **Centro de administración de Skype Empresarial**> **de audioconferencia** > **usuarios**, seleccione el usuario que necesita la conferencia Id.
    
4. En la página acción, busque **Identificador de conferencia**.
    
    > [!TIP]
    > Puede enviar toda la información de conferencia para el usuario en un correo electrónico que incluye el identificador de conferencia y números de teléfono de audio haciendo clic en el vínculo **Enviar información de conferencia por correo electrónico** después de seleccionar el usuario en la página **usuarios**. 
  
    Puede usar Windows PowerShell para ver el identificador de conferencia para un usuario. Para ello, ejecute:
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    Vea [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) para obtener más información sobre el cmdlet.
    
### Para asignar o cambiar el id. de conferencia

Puede asignar o cambiar un identificador de conferencia para un usuario si, por ejemplo, alguien desea un identificador de conferencia que sea fácil de recordar.
  
> [!NOTE]
> La Skype centro de administración de la empresa no se pueden usar para modificar un identificador de conferencia que se ha creado automáticamente, pero puede usar Windows PowerShell para editar o cambiar un identificador de conferencia que ha establecido. 
  
> Para editar o cambiar el id. de conferencia de un usuario, ejecute:
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964
  ```

    > [!TIP]
    > Un identificador de conferencia debe contener 7 dígitos y no puede cambiar en la Skype centro de administración de la empresa o con Windows PowerShell. 
  
### Para restablecer el id. de conferencia

Puede restablecer el id. de conferencia de un usuario, por ejemplo, si lo ha olvidado.
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En la **Centro de administración de Skype Empresarial**> **de audioconferencia** > **usuarios**, en el panel Acción, en el **Identificador de conferencia**, haga clic en **Restablecer**.
    
4. En la **Restablecer Id. de conferencia?** ventana, haga clic en **Sí**. Una conferencia que se crearán automáticamente ID y un correo electrónico enviado al usuario con el nuevo identificador de conferencia.
    
    Puede restablecer el id. de conferencias de un usuario si usa Windows PowerShell. Para ello, ejecute:
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetLeaderPIN 8271964
  ```

## ¿Qué más tengo que saber?

-     > [!IMPORTANT]
    >  Cuando se crea un nuevo identificador de conferencia o uno se restablece, no se puede utilizar el identificador de conferencia antiguo por las personas que llaman. Debe notificar a los usuarios a programar sus existentes invitaciones para asegurarse de que la conferencia nueva que identificador se agrega a las invitaciones de la reunión. Los usuarios pueden usar la herramienta de migración de reuniones Skype Empresarial para actualizar sus reuniones existentes. Para ver cómo descargar, instalar y ejecutar la herramienta, consulte:> [Herramienta de actualización de reuniones para Skype y Lync](http://technet.microsoft.com/library/2b525fe6-ed0f-4331-b533-c31546fcf4d4%28Office.14%29.aspx)> [Skype Empresarial Online, herramienta de migración de reuniones (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)> [Skype empresarial Online, la herramienta de migración de reuniones (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
  
- Consulte [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) para obtener más información sobre el cmdlet.
    
- El identificador de conferencia debe cumplir la longitud en dígitos establecido en el puente de conferencia de audio. No puede usar caracteres especiales o alfabéticos de conferencia identificadores; pueden utilizarse solo números.
    
- El identificador de conferencia para todos los usuarios de conferencias de audio será 7 dígitos de forma predeterminada, y no se puede cambiar el número de dígitos.
    
- Si el usuario se mueve de Microsoft como el proveedor de servicios de audioconferencia a un proveedor de servicios de audioconferencia de terceros o el proveedor de conferencias de audio está establecido en **Ninguno**, el identificador de conferencia ya no funcionarán. Vea [Asignar a un tercero como el proveedor de conferencias de audio](assign-a-third-party-as-the-audio-conferencing-provider.md) o[Mover el proveedor de servicios de audioconferencia de un usuario a Microsoft](moving-a-user-s-audio-conferencing-provider-to-microsoft.md).
    
## ¿Desea saber cómo administrar con Windows PowerShell?

- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis razones por las podría desear usar Windows PowerShell para administrar Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## Temas relacionados

[Configurar conferencias de Audio de Skype para la empresa y Teams de Microsoft](set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Declinación de responsabilidades de traducción automática**: Este artículo se ha traducido con un sistema informático sin intervención humana. Microsoft ofrece estas traducciones automáticas para que los hablantes de otros idiomas distintos del inglés puedan disfrutar del contenido sobre los productos, los servicios y las tecnologías de Microsoft. Puesto que este artículo se ha traducido con traducción automática, es posible que contenga errores de vocabulario, sintaxis o gramática. 
  

