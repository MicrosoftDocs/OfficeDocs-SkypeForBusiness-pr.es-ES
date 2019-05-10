---
title: Correos electrónicos enviados a los usuarios al cambia su configuración en Skype para profesionales en línea
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
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
description: 'Obtenga información acerca de qué información se envía automáticamente a los usuarios por correo electrónico al cambia su configuración de conferencia de acceso telefónico en Skype para profesionales en línea. '
ms.openlocfilehash: 814414139c985de6571a7e48aeb0bff208aa9ce3
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/09/2019
ms.locfileid: "33865084"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a>Correos electrónicos enviados a los usuarios al cambia su configuración en Skype para profesionales en línea

> [!Note]
> Si está buscando información automática de correo electrónico en Microsoft Teams, vea [los correos electrónicos envían a los usuarios al cambia su configuración en los equipos de Microsoft](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).

Los correos electrónicos se enviarán automáticamente a los usuarios que están [habilitados para conferencias de Audio](set-up-audio-conferencing.md) con Microsoft como proveedor de conferencias de audio.
  
De forma predeterminada, hay cuatro tipos de correo electrónico que se van a enviar a los usuarios que están habilitados para conferencias de Audio. Pero, si quiere limitar el número de correos electrónicos que se envían a los usuarios, puede desactivarlo. Conferencias de audio en Office 365 va a enviar correo electrónico a los usuarios de correo electrónico cuando:
  
- **Una licencia de conferencias de Audio se asigna a ellos o cuando se cambia el proveedor de conferencia de audio a Microsoft.**
    
     Este correo electrónico incluye el identificador de conferencia, el número de teléfono de conferencia de forma predeterminada para las reuniones, la conferencia de audio PIN para el usuario y las instrucciones y el vínculo que se usará el Skype para Online Meeting actualizar herramienta empresarial que se utiliza para actualizar las reuniones existentes para la usuario. Vea [Asignar Skype para licencias de negocio](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) o [Asignar Microsoft como proveedor de conferencias de audio](assign-microsoft-as-the-audio-conferencing-provider.md).
    
    > [!NOTE]
    > Si en su organización se han habilitado los identificadores de conferencia dinámicos, todas las reuniones que se programen de un usuario tendrán identificadores de conferencia únicos. Puede configurar [los identificadores dinámicos de conferencias de Audio en su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Este es un ejemplo de este correo electrónico:
    
     ![Skype Empresarial: comprobar licencia](../images/audio-conferencing-user-enabled.png)
  
    Para más información sobre las licencias de Skype Empresarial, vea [Licencias complementarias de Skype Empresarial](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
- **Cambia el id. de conferencia o número de teléfono de conferencia predeterminado de un usuario.**
    
    Este correo electrónico contiene el identificador de conferencia, número de teléfono de conferencia de forma predeterminada y las instrucciones y vínculos para usar el Skype para Online Meeting actualizar herramienta empresarial que se utiliza para actualizar las reuniones existentes para el usuario. Pero este correo electrónico no incluye los PIN de conferencia de audio del usuario. See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).
    
    > [!NOTE]
    > Si en su organización se han habilitado los identificadores de conferencia dinámicos, todas las reuniones que se programen de un usuario tendrán identificadores de conferencia únicos. Puede configurar [los identificadores dinámicos de conferencias de Audio en su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Este es un ejemplo de este correo electrónico:
    
     ![La información de conferencias de acceso telefónico local ha cambiado.](../images/audio-conferencing-info-change.png)
  
- **Se restablece el NIP de un usuario de conferencias de audio.**
    
    Este mensaje contiene el PIN de conferencia de audio del organizador, el identificador de conferencia existente y número de teléfono de conferencia predeterminado para el usuario. Vea [Restablecer el PIN de conferencia de Audio](reset-the-audio-conferencing-pin.md).
    
    > [!NOTE]
    > Si en su organización se han habilitado los identificadores de conferencia dinámicos, todas las reuniones que se programen de un usuario tendrán identificadores de conferencia únicos. Puede configurar [los identificadores dinámicos de conferencias de Audio en su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Este es un ejemplo de este correo electrónico:
    
     ![El PIN para las conferencias de acceso telefónico local ha cambiado.](../images/audio-conferencing-pin-has-changed.png)
  
- **Se ha quitado la licencia de un usuario o cuando se cambia el proveedor de conferencia de audio de Microsoft a otro proveedor o ninguno.**
    
    Esto sucede cuando se quita la licencia de **Conferencias de Audio** de un usuario o cuando se cambia el proveedor de conferencia de audio de un usuario de Microsoft a un proveedor de conferencia de audio de terceros o al establecer el proveedor en **Ninguno**. Este correo electrónico contiene las instrucciones y la información del usuario usar el Skype para la herramienta de actualización de reunión en línea de negocio para quitar la información específica de conferencias de audio, como el ID predeterminado conferencia teléfono número o conferencia.
    
    Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc).
    
    Este es un ejemplo de este correo electrónico:
    
     ![Las conferencias de acceso telefónico local están desactivadas.](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Realizar cambios en los mensajes de correo electrónico que se les envían

Puede realizar cambios en el correo electrónico que se envía automáticamente a los usuarios incluidos en la dirección de correo electrónico y el nombre para mostrar que se incluye en la información *de* contacto. De forma predeterminada, será el remitente de los mensajes de correo electrónico de Office 365, pero se puede cambiar la dirección de correo electrónico y nombre para mostrar con Windows PowerShell y el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) . To make changes to the email address that is sending the email to the users, you must:
  
- Puede realizar cambios en el correo electrónico que se envía de forma automática a los usuarios, como la dirección de correo electrónico real y el nombre para mostrar de la información de contacto del remitente. De manera predeterminada, el remitente de los mensajes será de Office 365, pero puede cambiar la dirección de correo electrónico y el nombre para mostrar con Windows PowerShell y el cmdlet _Set-CsOnlineDialInConferencingTenantSettings_. Para realizar cambios en la dirección de correo electrónico que envía el correo electrónico a los usuarios:
    
- Escriba el nombre para mostrar del correo electrónico en el parámetro  _SendEmailFromDisplayName_.
    
- Establezca el parámetro _SendEmailOverride_ en _True_.
    
Puede realizar cambios en el correo electrónico enviado a los usuarios, como la dirección de correo electrónico que se envía el correo electrónico desde y el nombre para mostrar para el correo electrónico, mediante la ejecución de:
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  Si desea cambiar la información de dirección de correo electrónico, debe asegurarse de que las directivas de correo electrónico entrante de su entorno de permitir que los mensajes de correo electrónico que provienen de personalizados especificado a partir de la dirección. Si decide reemplazar la información *de* contacto, debe comprobar que los correos electrónicos se envían correctamente a los usuarios. Para ello, puede probar esto con un usuario de la organización.
  
You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>¿Qué pasa si no desea que se les envíen correos electrónicos?

Cuando se deshabilitación el envío de correos electrónicos a los usuarios, no se enviará el correo electrónico incluso cuando un usuario obtiene asigna una licencia. En este caso, el identificador de conferencia, predeterminado el número de teléfono de conferencia y, lo que es más importante, su PIN de conferencia de audio no se enviará al usuario. Cuando esto sucede, debe indicar al usuario mediante el envío de un correo electrónico independiente o mediante una llamada a ellos.
  
De forma predeterminada, los correos electrónicos se enviarán a los usuarios, pero si desea impedir que recibir el correo electrónico para conferencias de audio, puede usar el Skype para el centro de administración de negocio o Windows PowerShell. 
 
![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png)  **utilizando el Skype para el centro de administración de negocio**
    
1. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.
    
2. En la página **configuración de puente de Microsoft** , active o desactive **Enviar automáticamente mensajes de correo electrónico a los usuarios si cambia su configuración de conferencias de audio**. 
    
3. Haga clic en **Guardar **. 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.
  
1. Ejecute las acciones siguientes para deshabilitar el envío de todos los correos electrónicos a sus usuarios:
    
   ```
   Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $false
   ```

You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.
  
## <a name="what-else-should-you-know-about-this-email"></a>¿Qué más debe saber sobre este correo electrónico?

- Para más información sobre habilitar y deshabilitar el envío de correos electrónicos de forma automática a sus usuarios, vea [Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de conferencias de Audio](enable-or-disable-sending-emails-when-their-settings-change.md).
    
- En ocasiones, los usuarios pierden su información de audio y necesita poder enviarles toda su información de audio a ellos. Puede hacerlo mediante el Skype para centro de administración de negocio y hacer clic en **Enviar información de conferencia a través de correo electrónico** en las propiedades de conferencia de audio para un usuario. See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md). Sin embargo, esta información no incluye el PIN de conferencia de audio.
    
    Este es un ejemplo del correo electrónico que se les enviará:
    
     ![Correo electrónico de conferencia de acceso telefónico](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- De forma predeterminada, será el remitente de los mensajes de correo electrónico de Office 365, pero se puede cambiar la dirección de correo electrónico y nombre para mostrar con Windows PowerShell y el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) .
    
- Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell cuenta con muchas ventajas en velocidad, simplicidad y productividad en comparación con solo usar el centro de administración de Office 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes: 
    
  - [Introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Temas relacionados

[Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de conferencias de Audio](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[Enviar un correo electrónico a un usuario con su información de conferencias de Audio](send-an-email-to-a-user-with-their-dial-in-information.md)
