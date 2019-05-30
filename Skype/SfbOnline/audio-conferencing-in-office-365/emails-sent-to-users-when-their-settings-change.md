---
title: Correos electrónicos enviados a los usuarios cuando cambia la configuración en Skype empresarial online
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtenga información acerca de qué información se envía automáticamente a los usuarios por correo electrónico cuando cambia la configuración de la Conferencia de acceso telefónico local en Skype empresarial online. '
ms.openlocfilehash: acdc16a1af2666dcb84599fae31a910be83ac08f
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494290"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a>Correos electrónicos enviados a los usuarios cuando cambia la configuración en Skype empresarial online

> [!Note]
> Si está buscando información de correo electrónico automática en Microsoft Teams, consulte [correos electrónicos enviados a los usuarios cuando cambie su configuración en Microsoft Teams](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).

Los mensajes de correo electrónico se enviarán automáticamente a los usuarios que están [habilitados para conferencias de audio](set-up-audio-conferencing.md) usando Microsoft como proveedor de servicios de audioconferencia.
  
De forma predeterminada, hay cuatro tipos de mensajes de correo electrónico que se enviarán a los usuarios que estén habilitados para las conferencias de audio. Pero, si quiere limitar el número de correos electrónicos que se envían a los usuarios, puede desactivarlo. Las conferencias de audio en Office 365 enviarán correos electrónicos al correo electrónico de los usuarios cuando:
  
- **Se les asigna una licencia de audioconferencia o cuando está cambiando el proveedor de servicios de audioconferencia a Microsoft.**
    
     Este correo electrónico incluye el identificador de conferencia, el número de teléfono de conferencia predeterminado para las reuniones, el PIN de audioconferencia para el usuario y las instrucciones y el vínculo para usar la herramienta de actualización de reuniones de Skype empresarial online que se usa para actualizar las reuniones existentes para el usuario. Consulte [asignar licencias de Skype empresarial](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) o [asignar Microsoft como el proveedor](assign-microsoft-as-the-audio-conferencing-provider.md)de servicios de audioconferencia.
    
    > [!NOTE]
    > Si en su organización se han habilitado los identificadores de conferencia dinámicos, todas las reuniones que se programen de un usuario tendrán identificadores de conferencia únicos. Puede configurar [los identificadores dinámicos de audioconferencias en su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Este es un ejemplo de este correo electrónico:
    
     ![Skype Empresarial: comprobar licencia](../images/audio-conferencing-user-enabled.png)
  
    Para más información sobre las licencias de Skype Empresarial, vea [Licencias complementarias de Skype Empresarial](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
- **Cambia el id. de conferencia o número de teléfono de conferencia predeterminado de un usuario.**
    
    Este correo electrónico contiene el identificador de la Conferencia, el número de teléfono de conferencia predeterminado y las instrucciones y el vínculo para usar la herramienta de actualización de reuniones de Skype empresarial online que se usa para actualizar las reuniones existentes para el usuario. Pero este mensaje de correo electrónico no incluye el PIN de audioconferencia del usuario. See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).
    
    > [!NOTE]
    > Si en su organización se han habilitado los identificadores de conferencia dinámicos, todas las reuniones que se programen de un usuario tendrán identificadores de conferencia únicos. Puede configurar [los identificadores dinámicos de audioconferencias en su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Este es un ejemplo de este correo electrónico:
    
     ![La información de conferencias de acceso telefónico local ha cambiado.](../images/audio-conferencing-info-change.png)
  
- **Se restablece el PIN de audioconferencia de un usuario.**
    
    Este correo electrónico contiene el PIN de conferencia de audio del organizador, el identificador de conferencia existente y el número de teléfono de conferencia predeterminado para el usuario. Consulte [restablecer el PIN de audioconferencia](reset-the-audio-conferencing-pin.md).
    
    > [!NOTE]
    > Si en su organización se han habilitado los identificadores de conferencia dinámicos, todas las reuniones que se programen de un usuario tendrán identificadores de conferencia únicos. Puede configurar [los identificadores dinámicos de audioconferencias en su organización](using-audio-conferencing-dynamic-ids-in-your-organization.md). 
  
    Este es un ejemplo de este correo electrónico:
    
     ![El PIN para las conferencias de acceso telefónico local ha cambiado.](../images/audio-conferencing-pin-has-changed.png)
  
- **Se quita la licencia de un usuario o cuando el proveedor de servicios de audioconferencia cambia de Microsoft a otro proveedor o a ninguno.**
    
    Esto sucede cuando se quita la licencia de **Conferencia de audio** de un usuario o cuando se cambia el proveedor de audioconferencias de un usuario de Microsoft a un proveedor de servicios de audioconferencia de terceros o cuando se establece el proveedor en **ninguno**. Este mensaje de correo electrónico contiene las instrucciones e información para que el usuario Use la herramienta de actualización de reuniones de Skype empresarial online para quitar la información específica de la Conferencia de audio, como el número de teléfono predeterminado de la Conferencia o el identificador de la Conferencia.
    
    Consulte [Asignar o cancelar licencia para Office 365 para empresas](https://support.office.com/en-us/article/997596b5-4173-4627-b915-36abac6786dc).
    
    Este es un ejemplo de este correo electrónico:
    
     ![Las conferencias de acceso telefónico local están desactivadas.](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Realizar cambios en los mensajes de correo electrónico que se les envían

Puede realizar cambios en el correo electrónico que se envía automáticamente a los usuarios, incluida la dirección de correo electrónico y el nombre para mostrar que se incluye en la información *de* contacto. De forma predeterminada, el remitente de los mensajes de correo electrónico será de Office 365, pero puede cambiar la dirección de correo electrónico y el nombre para mostrar con Windows PowerShell y el cmdlet [set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) . To make changes to the email address that is sending the email to the users, you must:
  
- Puede realizar cambios en el correo electrónico que se envía de forma automática a los usuarios, como la dirección de correo electrónico real y el nombre para mostrar de la información de contacto del remitente. De manera predeterminada, el remitente de los mensajes será de Office 365, pero puede cambiar la dirección de correo electrónico y el nombre para mostrar con Windows PowerShell y el cmdlet _Set-CsOnlineDialInConferencingTenantSettings_. Para realizar cambios en la dirección de correo electrónico que envía el correo electrónico a los usuarios:
    
- Escriba el nombre para mostrar del correo electrónico en el parámetro  _SendEmailFromDisplayName_.
    
- Establezca el parámetro _SendEmailOverride_ en _true_.
    
Puede realizar cambios en el correo electrónico que se envía a los usuarios, como la dirección de correo electrónico desde la que se envía el correo electrónico y el nombre para mostrar del correo electrónico, ejecutando:
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  Si desea cambiar la información de la dirección de correo electrónico, debe asegurarse de que las directivas de correo electrónico de entrada de su entorno permitan la entrada de mensajes provenientes de la dirección especificada personalizada. Si decide anular la información *de* contacto, debe comprobar que los mensajes de correo electrónico se envían correctamente a los usuarios. Para ello, puede probarlo con un usuario de su organización.
  
You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>¿Qué pasa si no desea que se les envíen correos electrónicos?

Cuando deshabilite el envío de correos electrónicos a los usuarios, el correo electrónico no se enviará aunque se asigne una licencia a un usuario. En este caso, el identificador de la Conferencia, el número de teléfono de conferencia predeterminado y, lo que es más importante, su PIN de audioconferencia no se enviará al usuario. Cuando esto sucede, debe decir al usuario enviándoles un mensaje de correo electrónico o llamándolos.
  
De forma predeterminada, los correos electrónicos se enviarán a los usuarios, pero si desea evitar que reciban correo electrónico para las conferencias de audio, puede usar el centro de administración de Skype empresarial o Windows PowerShell. 
 
![Un icono que muestra el logotipo](../images/sfb-logo-30x30.png)de Skype empresarial**con el centro de administración de Skype empresarial**  
    
1. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.
    
2. En la página **configuración del puente de Microsoft** , Active o desactive **enviar automáticamente correos electrónicos a los usuarios si cambian las opciones de configuración de audioconferencia**. 
    
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
    
- A veces, los usuarios pierden su información de audio y usted necesita poder enviarles toda su información de audio. Para ello, puede usar el centro de administración de Skype empresarial y hacer clic en **enviar información de conferencia por correo electrónico** en las propiedades de audioconferencia de un usuario. See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md). Sin embargo, esta información no incluye el PIN de audioconferencia.
    
    Este es un ejemplo del correo electrónico que se les enviará:
    
     ![Correo electrónico de conferencia de acceso telefónico](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- De forma predeterminada, el remitente de los mensajes de correo electrónico será de Office 365, pero puede cambiar la dirección de correo electrónico y el nombre para mostrar con Windows PowerShell y el cmdlet [set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) .
    
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
