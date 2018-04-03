---
title: Correos electrónicos enviados a los usuarios cuando cambia su configuración
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
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
description: 'Learn about what information is sent automatically to users by email when their dial-in conferencing settings change. '
ms.openlocfilehash: f504e9b807afb4a587a9d6f13baf69a3c5b9db68
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2018
---
# <a name="emails-sent-to-users-when-their-settings-change"></a>Correos electrónicos enviados a los usuarios cuando cambia su configuración

Los correos electrónicos se enviarán automáticamente a los usuarios que están [habilitados para conferencias de Audio](set-up-audio-conferencing.md) mediante Microsoft como proveedor de conferencia de audio.
  
De forma predeterminada, hay cuatro tipos de correo electrónico que se enviará a los usuarios que están habilitados para conferencias de Audio. Pero, si quiere limitar el número de correos electrónicos que se envían a los usuarios, puede desactivarlo. Conferencias de audio en Office 365 enviará correo electrónico a los usuarios de correo electrónico cuando:
  
- **Una licencia de conferencia de Audio se asigna a ellos o cuando se cambia el proveedor de conferencia de audio a Microsoft.**
    
     Este correo electrónico incluye el identificador de la conferencia, el número de teléfono de conferencia predeterminado para las reuniones, la conferencias de audio PIN para el usuario y las instrucciones y vínculos utilizar el Skype para negocios reunión actualizar herramienta Online que se utiliza para actualizar las reuniones existentes para el usuario. Consulte [Asignar Skype para licencias de negocio y equipos de Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) o [Microsoft asignar como el proveedor de conferencia de audio](assign-microsoft-as-the-audio-conferencing-provider.md).
    
    > [!NOTE]
    > Si en su organización se han habilitado los identificadores de conferencia dinámicos, todas las reuniones que se programen de un usuario tendrán identificadores de conferencia únicos. Puede configurar [identificadores dinámicos de conferencia de Audio en su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Este es un ejemplo de este correo electrónico:
    
     ![Skype Empresarial: comprobar licencia](../images/audio-conferencing-user-enabled.png)
  
    Puede encontrar más información acerca de Skype para Business licensing mirando [Skype para negocios y equipos de Microsoft licencias adicionales](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
- **Cambia el id. de conferencia o número de teléfono de conferencia predeterminado de un usuario.**
    
    Este mensaje contiene el identificador de la conferencia, número de teléfono de conferencia predeterminado y las instrucciones y vínculos que para utilizar el Skype para negocios reunión actualizar herramienta Online que se utiliza para actualizar las reuniones existentes para el usuario. Pero este mensaje no incluye conferencias de audio PIN del usuario. See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).
    
    > [!NOTE]
    > Si en su organización se han habilitado los identificadores de conferencia dinámicos, todas las reuniones que se programen de un usuario tendrán identificadores de conferencia únicos. Puede configurar [identificadores dinámicos de conferencia de Audio en su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Este es un ejemplo de este correo electrónico:
    
     ![La información de conferencias de acceso telefónico local ha cambiado.](../images/audio-conferencing-info-change.png)
  
- **Se restablecen el NIP de un usuario de audioconferencias.**
    
    Este mensaje contiene audioconferencia del organizador de la PIN, ID de conferencia existente y número de teléfono de conferencia predeterminado para el usuario. Los usuarios recibirán un correo electrónico con su PIN cuando estén habilitados para la conferencia de acceso telefónico local o cuando se restablezca el PIN. Pero, si deshabilitó el envío automático de correos electrónicos, no se enviará un correo electrónico de restablecimiento de PIN al usuario y tendrá que enviar el PIN al usuario de forma manual. El PIN solo se mostrará una vez después de que se haya restablecido. Una vez que se muestra inmediatamente después de haberse restablecido, el PIN no se mostrará más en las propiedades del usuario y en su lugar se mostrará *****.
    
    > [!NOTE]
    > Si en su organización se han habilitado los identificadores de conferencia dinámicos, todas las reuniones que se programen de un usuario tendrán identificadores de conferencia únicos. Puede configurar [identificadores dinámicos de conferencia de Audio en su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Este es un ejemplo de este correo electrónico:
    
     ![El PIN para las conferencias de acceso telefónico local ha cambiado.](../images/audio-conferencing-pin-has-changed.png)
  
- **Se quita una licencia de usuario o cuando se cambia el proveedor de conferencia de audio de Microsoft otro proveedor o ninguno.**
    
    Esto ocurre cuando se quita la licencia de **Conferencia de Audio** de un usuario o al cambiar el proveedor de conferencia de audio de un usuario de Microsoft a un proveedor de conferencia de audio de terceros o cuando se configura el proveedor como **Ninguno**. Este correo electrónico contiene las instrucciones y la información del usuario utilizar el Skype para la herramienta de actualización de reunión en línea de negocio para quitar la información específica de conferencias de audio, como el ID predeterminado conferencia telefónica número o conferencia.
    
    Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc).
    
    Este es un ejemplo de este correo electrónico:
    
     ![Las conferencias de acceso telefónico local están desactivadas.](../images/audio-conferencing-turned-off.png)
  
## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Realizar cambios en los mensajes de correo electrónico que se les envían

Puede realizar cambios en el correo electrónico que se envía automáticamente a los usuarios incluidos en la dirección de correo electrónico y el nombre para mostrar que se incluye en la información *de* contacto. De forma predeterminada, el remitente de los correos electrónicos será de Office 365, pero puede cambiar la dirección de correo electrónico y nombre para mostrar con Windows PowerShell y el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) . Para realizar cambios en la dirección de correo electrónico que está enviando el correo electrónico a los usuarios, debe:
  
- Puede realizar cambios en el correo electrónico que se envía de forma automática a los usuarios, como la dirección de correo electrónico real y el nombre para mostrar de la información de contacto del remitente. De manera predeterminada, el remitente de los mensajes será de Office 365, pero puede cambiar la dirección de correo electrónico y el nombre para mostrar con Windows PowerShell y el cmdlet _Set-CsOnlineDialInConferencingTenantSettings_. Para realizar cambios en la dirección de correo electrónico que envía el correo electrónico a los usuarios:
    
- Escriba el nombre para mostrar del correo electrónico en el parámetro  _SendEmailFromDisplayName_.
    
- Establezca el parámetro _SendEmailOverride_ en _True_.
    
Puede realizar cambios en el correo electrónico enviado a los usuarios, como el correo electrónico se envía desde la dirección de correo electrónico y el nombre para mostrar para el correo electrónico, mediante la ejecución de:
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  Si desea cambiar la información de la dirección de correo electrónico, debe asegurarse de que las directivas de correo electrónico entrante de su entorno permiten correos electrónicos procedentes de personalizado especificado en la dirección. Si decide reemplazar la información *de* contacto, debe comprobar que los mensajes se envían correctamente a los usuarios. Para ello, puede probar esto con un usuario de la organización.
  
Si quiere cambiar la información de la dirección de correo electrónico, tendrá que asegurarse de que las directivas de correo electrónico de entrada de su organización permitan la recepción de mensajes enviados por la dirección de correo electrónico personalizada.
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>¿Qué pasa si no desea que se les envíen correos electrónicos?

Cuando se deshabilita el envío de correos electrónicos a los usuarios, no se enviará el correo electrónico incluso cuando un usuario obtiene asignado una licencia. En este caso, el identificador de la conferencia, predeterminado el número de teléfono de conferencia y, más importante aún, sus conferencias de audio PIN no se enviará al usuario. Cuando esto sucede, se debe indicar el usuario mediante el envío de un correo electrónico o mediante una llamada a ellos.
  
De forma predeterminada, se enviará un correo electrónico a los usuarios, pero si desea impedir que la recepción de correo electrónico para conferencias de audio, puede utilizar el Skype para el centro de administración de negocios o de Windows PowerShell. 
  
 Puede usar el Centro de administración de Skype Empresarial o Windows PowerShell para habilitar o deshabilitar el envío de correos electrónicos a los usuarios.
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.
    
4. En la página **configuración de puente de Microsoft** , active o desactive **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de conferencia de audio**. 
    
5. Haga clic en **Guardar**. 
    
 Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.
  
1. Ejecute las acciones siguientes para deshabilitar el envío de todos los correos electrónicos a sus usuarios:
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

Si quiere cambiar la información de la dirección de correo electrónico, tendrá que asegurarse de que las directivas de correo electrónico de entrada de su organización permitan la recepción de mensajes enviados por la dirección de correo electrónico personalizada.
  
## <a name="what-else-should-you-know-about-this-email"></a>¿Qué más debe saber sobre este correo electrónico?

- Para más información sobre habilitar y deshabilitar el envío de correos electrónicos de forma automática a sus usuarios, vea [Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de conferencias de Audio](enable-or-disable-sending-emails-when-their-settings-change.md).
    
- A veces los usuarios pierden su información de audio y necesita poder enviarlos a toda su información de audio a ellos. Puede hacerlo mediante el Skype para centro de administración de negocios y hacer clic en **Enviar información de conferencia a través de correo electrónico** en las propiedades de conferencia de audio de un usuario. See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md). Sin embargo, esta información no incluye el PIN de la conferencia de audio.
    
    Este es un ejemplo del correo electrónico que se les enviará:
    
     ![Correo electrónico de conferencia de acceso telefónico](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- De forma predeterminada, el remitente de los correos electrónicos será de Office 365, pero puede cambiar la dirección de correo electrónico y nombre para mostrar con Windows PowerShell y el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) .
    
- Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell cuenta con muchas ventajas en velocidad, simplicidad y productividad en comparación con solo usar el centro de administración de Office 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes: 
    
  - [Introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>See also

[Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de conferencias de Audio](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[Enviar un correo electrónico a un usuario con su información de conferencias de Audio](send-an-email-to-a-user-with-their-dial-in-information.md)
