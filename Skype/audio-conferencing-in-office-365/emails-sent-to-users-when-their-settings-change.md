---
title: "Correos electrónicos enviados a los usuarios cuando cambia su configuración"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
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
description: "Obtenga información acerca de qué información se envía automáticamente a los usuarios por correo electrónico cuando cambie su configuración de acceso telefónico de la conferencia. "
ms.openlocfilehash: a7746018a03a69e429eb8a5df4c68c17f29a97df
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="emails-sent-to-users-when-their-settings-change"></a>Correos electrónicos enviados a los usuarios cuando cambia su configuración

Los correos electrónicos se enviarán automáticamente a los usuarios que están [habilitados para conferencias de Audio](set-up-audio-conferencing.md) mediante Microsoft como proveedor de conferencia de audio.
  
De forma predeterminada, hay cuatro tipos de correo electrónico que se enviará a los usuarios que están habilitados para conferencias de Audio. Sin embargo, si desea limitar el número de correos electrónicos enviados a los usuarios, usted puede desactivarlo. Conferencias de audio en Office 365 enviará correo electrónico a los usuarios de correo electrónico cuando:
  
- **Una licencia de conferencia de Audio se asigna a ellos o cuando se cambia el proveedor de conferencia de audio a Microsoft.**
    
     Este correo electrónico incluye el identificador de la conferencia, el número de teléfono de conferencia predeterminado para las reuniones, la conferencias de audio PIN para el usuario y las instrucciones y vínculos utilizar el Skype para negocios reunión actualizar herramienta Online que se utiliza para actualizar las reuniones existentes para el usuario. Consulte [Asignar Skype para licencias de negocio y equipos de Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) o [Microsoft asignar como el proveedor de conferencia de audio](assign-microsoft-as-the-audio-conferencing-provider.md).
    
    > [!NOTE]
    > Si su organización se ha habilitado para identificadores de conferencia dinámico, todas las reuniones de un usuario que programan tendrá conferencia único Id. Puede configurar [identificadores dinámicos de conferencia de Audio en su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Aquí es un ejemplo de este correo electrónico:
    
     ![Skype para empresas comprobar la licencia](../images/audio-conferencing-user-enabled.png)
  
    Puede encontrar más información acerca de Skype para Business licensing mirando [Skype para negocios y equipos de Microsoft licencias adicionales](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
- **Conferencia ID o default conferencia número de teléfono de un usuario cambios.**
    
    Este mensaje contiene el identificador de la conferencia, número de teléfono de conferencia predeterminado y las instrucciones y vínculos que para utilizar el Skype para negocios reunión actualizar herramienta Online que se utiliza para actualizar las reuniones existentes para el usuario. Pero este mensaje no incluye conferencias de audio PIN del usuario. Vea [Restablecer un Id. de conferencia para un usuario](reset-a-conference-id-for-a-user.md).
    
    > [!NOTE]
    > Si su organización se ha habilitado para identificadores de conferencia dinámico, todas las reuniones de un usuario que programan tendrá conferencia único Id. Puede configurar [identificadores dinámicos de conferencia de Audio en su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Aquí es un ejemplo de este correo electrónico:
    
     ![Se cambió la información de acceso telefónico de la conferencia.](../images/audio-conferencing-info-change.png)
  
- **Se restablecen el NIP de un usuario de audioconferencias.**
    
    Este mensaje contiene audioconferencia del organizador de la PIN, ID de conferencia existente y número de teléfono de conferencia predeterminado para el usuario. Los usuarios recibirán un correo electrónico con su PIN cuando estén habilitados para la conferencia de acceso telefónico local o cuando se restablezca el PIN. Pero, si deshabilitó el envío automático de correos electrónicos, no se enviará un correo electrónico de restablecimiento de PIN al usuario y tendrá que enviar el PIN al usuario de forma manual. El PIN solo se mostrará una vez después de que se haya restablecido. Una vez que se muestra inmediatamente después de haberse restablecido, el PIN no se mostrará más en las propiedades del usuario y en su lugar se mostrará *****.
    
    > [!NOTE]
    > Si su organización se ha habilitado para identificadores de conferencia dinámico, todas las reuniones de un usuario que programan tendrá conferencia único Id. Puede configurar [identificadores dinámicos de conferencia de Audio en su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Aquí es un ejemplo de este correo electrónico:
    
     ![Conferencia telefónica de NIP cambiado.](../images/audio-conferencing-pin-has-changed.png)
  
- **Se quita una licencia de usuario o cuando se cambia el proveedor de conferencia de audio de Microsoft otro proveedor o ninguno.**
    
    Esto ocurre cuando se quita la licencia de **Conferencia de Audio** de un usuario o al cambiar el proveedor de conferencia de audio de un usuario de Microsoft a un proveedor de conferencia de audio de terceros o cuando se configura el proveedor como **Ninguno**. Este correo electrónico contiene las instrucciones y la información del usuario utilizar el Skype para la herramienta de actualización de reunión en línea de negocio para quitar la información específica de conferencias de audio, como el ID predeterminado conferencia telefónica número o conferencia.
    
    Consulte [asignar o quitar licencias para Office 365 para el negocio](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc) o [asignar un tercero como el proveedor de conferencia de audio](assign-a-third-party-as-the-audio-conferencing-provider.md).
    
    Aquí es un ejemplo de este correo electrónico:
    
     ![Conferencia de marcado está desactivada.](../images/audio-conferencing-turned-off.png)
  
## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Realizar cambios en los que se les envían mensajes de correo electrónico

Puede realizar cambios en el correo electrónico que se envía automáticamente a los usuarios incluidos en la dirección de correo electrónico y el nombre para mostrar que se incluye en la información *de* contacto. De forma predeterminada, el remitente de los correos electrónicos será de Office 365, pero puede cambiar la dirección de correo electrónico y nombre para mostrar con Windows PowerShell y el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) . Para realizar cambios en la dirección de correo electrónico que está enviando el correo electrónico a los usuarios, debe:
  
- Escriba la dirección de correo electrónico en el parámetro  _SendEmailFromAddress_.
    
- Escriba el nombre para mostrar del correo electrónico en el parámetro  _SendEmailFromDisplayName_.
    
- Establezca el parámetro _SendEmailOverride_ en _True_.
    
Puede realizar cambios en el correo electrónico enviado a los usuarios, como el correo electrónico se envía desde la dirección de correo electrónico y el nombre para mostrar para el correo electrónico, mediante la ejecución de:
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  Si desea cambiar la información de la dirección de correo electrónico, debe asegurarse de que las directivas de correo electrónico entrante de su entorno permiten correos electrónicos procedentes de personalizado especificado en la dirección. Si decide reemplazar la información *de* contacto, debe comprobar que los mensajes se envían correctamente a los usuarios. Para ello, puede probar esto con un usuario de la organización.
  
Si quiere cambiar la información de la dirección de correo electrónico, tendrá que asegurarse de que las directivas de correo electrónico de entrada de su organización permitan la recepción de mensajes enviados por la dirección de correo electrónico personalizada.
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>¿Qué ocurre si no desea correo electrónico se envíe a ellos?

Cuando se deshabilita el envío de correos electrónicos a los usuarios, no se enviará el correo electrónico incluso cuando un usuario obtiene asignado una licencia. En este caso, el identificador de la conferencia, predeterminado el número de teléfono de conferencia y, más importante aún, sus conferencias de audio PIN no se enviará al usuario. Cuando esto sucede, se debe indicar el usuario mediante el envío de un correo electrónico o mediante una llamada a ellos.
  
De forma predeterminada, se enviará un correo electrónico a los usuarios, pero si desea impedir que la recepción de correo electrónico para conferencias de audio, puede utilizar el Skype para el centro de administración de negocios o de Windows PowerShell. 
  
 Puede usar el Centro de administración de Skype Empresarial o Windows PowerShell para habilitar o deshabilitar el envío de correos electrónicos a los usuarios.
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
3. En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, vaya a las **conferencias de Audio** > **configuración de puente de Microsoft**.
    
4. En la página **configuración de puente de Microsoft** , active o desactive **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de conferencia de audio**. 
    
5. Haga clic en **Guardar**. 
    
 Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.
  
1. Ejecute el siguiente procedimiento para deshabilitar el envío de todos los usuarios de correo electrónico:
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

Si quiere cambiar la información de la dirección de correo electrónico, tendrá que asegurarse de que las directivas de correo electrónico de entrada de su organización permitan la recepción de mensajes enviados por la dirección de correo electrónico personalizada.
  
## <a name="what-else-should-you-know-about-this-email"></a>¿Qué más debe saber sobre este correo electrónico?

- Para habilitar en más y deshabilitar automáticamente enviar correo electrónico a los usuarios, vea [Habilitar o deshabilitar el envío correos electrónicos cuando cambie la configuración de conferencia de Audio](enable-or-disable-sending-emails-when-their-settings-change.md).
    
- A veces los usuarios pierden su información de audio y necesita poder enviarlos a toda su información de audio a ellos. Puede hacerlo mediante el Skype para centro de administración de negocios y hacer clic en **Enviar información de conferencia a través de correo electrónico** en las propiedades de conferencia de audio de un usuario. Si hace esto, se enviará un correo electrónico que solo contenga el id. de la conferencia y el número de teléfono de la conferencia, pero no se incluirá el PIN. Sin embargo, esta información no incluye el PIN de la conferencia de audio.
    
    Aquí es un ejemplo de este correo electrónico que se enviará a ellos:
    
     ![Correo electrónico de conferencia de acceso telefónico](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- De forma predeterminada, el remitente de los correos electrónicos será de Office 365, pero puede cambiar la dirección de correo electrónico y nombre para mostrar con Windows PowerShell y el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) .
    
- Windows PowerShell es todo sobre la administración de usuarios y lo que los usuarios se permiten o no realizar. Con Windows PowerShell, puede administrar Office 365 mediante un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer. Para empezar a utilizar Windows PowerShell, consulte estos temas:
    
  - Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tiene muchas ventajas en velocidad, simplicidad y productividad sobre utilizando sólo el centro de administración de Office 365, como cuando realice cambios en la configuración de muchos usuarios al mismo tiempo. Obtenga información acerca de estas ventajas en los siguientes temas: 
    
  - [Introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Temas relacionados

[Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de conferencia de Audio](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[Enviar un correo electrónico a un usuario con su información de conferencia de Audio](send-an-email-to-a-user-with-their-dial-in-information.md)

