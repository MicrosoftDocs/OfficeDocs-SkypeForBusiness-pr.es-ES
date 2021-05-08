---
title: Correos electrónicos enviados a los usuarios cuando su configuración cambia en Skype Empresarial Online
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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Obtenga información sobre qué información se envía automáticamente a los usuarios por correo electrónico cuando la configuración de las conferencias de acceso telefónico local cambia en Skype Empresarial Online. '
ms.openlocfilehash: 75ed80ef7d686ecb649bc1d21f30a43fd115f1a3
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237346"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a>Correos electrónicos enviados a los usuarios cuando su configuración cambia en Skype Empresarial Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Si busca información de correo electrónico automática en Microsoft Teams, vea Correos electrónicos enviados a los usuarios cuando la configuración cambia [en Microsoft Teams](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).

Los correos electrónicos se enviarán automáticamente a los usuarios habilitados para [conferencias](set-up-audio-conferencing.md) de audio con Microsoft como proveedor de audioconferencias.
  
De forma predeterminada, hay cuatro tipos de correo electrónico que se enviarán a los usuarios habilitados para audioconferencias. Pero, si quiere limitar el número de correos electrónicos que se envían a los usuarios, puede desactivarlo. Las conferencias de audio Microsoft 365 o Office 365 enviarán correo electrónico a los usuarios cuando:
  
- **Se les asigna una licencia de audioconferencia o cuando cambia el proveedor de audioconferencias a Microsoft.**
    
     Este correo electrónico incluye el id. de conferencia, el número de teléfono de conferencia predeterminado para las reuniones, el PIN de audioconferencia para el usuario, las instrucciones y el vínculo para usar la Herramienta de actualización de reuniones en línea de Skype Empresarial que se usa para actualizar las reuniones existentes para el usuario. Vea [Asignar Skype Empresarial licencias](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) o Asignar Microsoft como el proveedor de [audioconferencias.](assign-microsoft-as-the-audio-conferencing-provider.md)
    
    > [!NOTE]
    > Si en su organización se han habilitado los identificadores de conferencia dinámicos, todas las reuniones que se programen de un usuario tendrán identificadores de conferencia únicos. Puede configurar los [ID dinámicos de audioconferencia en su organización.](./reset-a-conference-id-for-a-user.md) 
  
    Este es un ejemplo de este correo electrónico:
    
     ![Skype Empresarial: comprobar licencia](../images/audio-conferencing-user-enabled.png)
  
    Para más información sobre las licencias de Skype Empresarial, vea [Licencias complementarias de Skype Empresarial](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).
    
- **Cambia el id. de conferencia o número de teléfono de conferencia predeterminado de un usuario.**
    
    Este correo electrónico contiene el id. de conferencia, el número de teléfono de conferencia predeterminado, las instrucciones y el vínculo para usar la Herramienta de actualización de reuniones en línea de Skype Empresarial que se usa para actualizar las reuniones existentes para el usuario. Pero este correo electrónico no incluye el PIN de audioconferencia del usuario. See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).
    
    > [!NOTE]
    > Si en su organización se han habilitado los identificadores de conferencia dinámicos, todas las reuniones que se programen de un usuario tendrán identificadores de conferencia únicos. Puede configurar los [ID dinámicos de audioconferencia en su organización.](./reset-a-conference-id-for-a-user.md) 
  
    Este es un ejemplo de este correo electrónico:
    
     ![La información de conferencias de acceso telefónico local ha cambiado.](../images/audio-conferencing-info-change.png)
  
- **Se restablece el PIN de audioconferencia de un usuario.**
    
    Este correo electrónico contiene el PIN de audioconferencia del organizador, el id. de conferencia existente y el número de teléfono de conferencia predeterminado para el usuario. Vea [Restablecer el PIN de audioconferencia.](reset-the-audio-conferencing-pin.md)
    
    > [!NOTE]
    > Si en su organización se han habilitado los identificadores de conferencia dinámicos, todas las reuniones que se programen de un usuario tendrán identificadores de conferencia únicos. Puede configurar los [ID dinámicos de audioconferencia en su organización.](./reset-a-conference-id-for-a-user.md) 
  
    Este es un ejemplo de este correo electrónico:
    
     ![El PIN para las conferencias de acceso telefónico local ha cambiado.](../images/audio-conferencing-pin-has-changed.png)
  
- **Se quita la licencia de un usuario o cuando el proveedor de servicios de audioconferencia cambia de Microsoft a otro proveedor o ninguno.**
    
    Esto ocurre  cuando la licencia de audioconferencia se quita de un usuario o al cambiar el proveedor de audioconferencia de un usuario de Microsoft a un proveedor de audioconferencia de terceros o al establecer el proveedor en **Ninguno.** Este correo electrónico contiene las instrucciones e información para que el usuario use la Herramienta de actualización de reuniones en línea de Skype Empresarial para quitar información específica de las audioconferencias, como el número de teléfono de conferencia predeterminado o el id. de conferencia.
    
    Vea [Asignar o quitar licencias para Aplicaciones Microsoft 365 para negocios](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
    
    Este es un ejemplo de este correo electrónico:
    
     ![Las conferencias de acceso telefónico local están desactivadas.](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Realizar cambios en los mensajes de correo electrónico que se les envían

Puede realizar cambios en el correo electrónico que se envía automáticamente a los usuarios, incluida la dirección de correo electrónico y el nombre para mostrar que se incluye en *la* información de contacto De. De forma predeterminada, el remitente de los correos electrónicos será de Microsoft 365 o Office 365, pero puede cambiar la dirección de correo electrónico y el nombre para mostrar con Windows PowerShell y el cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](/previous-versions//mt228132(v=technet.10)) To make changes to the email address that is sending the email to the users, you must:
  
- Puede realizar cambios en el correo electrónico que se envía de forma automática a los usuarios, como la dirección de correo electrónico real y el nombre para mostrar de la información de contacto del remitente. De manera predeterminada, el remitente de los mensajes será de Office 365, pero puede cambiar la dirección de correo electrónico y el nombre para mostrar con Windows PowerShell y el cmdlet _Set-CsOnlineDialInConferencingTenantSettings_. Para realizar cambios en la dirección de correo electrónico que envía el correo electrónico a los usuarios:
    
- Escriba el nombre para mostrar del correo electrónico en el parámetro  _SendEmailFromDisplayName_.
    
- Establezca el  _parámetro SendEmailOverride_ en  _True_.
    
Puede realizar cambios en el correo electrónico enviado a los usuarios, como la dirección de correo electrónico desde la que se envía el correo electrónico y el nombre para mostrar del correo electrónico, ejecutando:
  
```PowerShell
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  Si desea cambiar la información de la dirección de correo electrónico, debe asegurarse de que las directivas de correo electrónico entrante de su entorno permiten los correos electrónicos que proceden de la dirección personalizada especificada. Si decide invalidar la *información* de contacto De, debe comprobar que los correos electrónicos se envían correctamente a los usuarios. Para ello, puede probar esto con un usuario de su organización.
  
You can use the [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet to manage other settings for your organization, including email.
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>¿Qué pasa si no desea que se les envíen correos electrónicos?

Al deshabilitar el envío de correos electrónicos a los usuarios, el correo electrónico no se enviará incluso cuando se asigne una licencia a un usuario. En este caso, el ID de conferencia, el número de teléfono de conferencia predeterminado y, lo que es más importante, su PIN de audioconferencia no se enviarán al usuario. Cuando esto sucede, debe avisarle al usuario enviándole un correo electrónico independiente o llamándolo.
  
De forma predeterminada, los correos electrónicos se enviarán a los usuarios, pero si quiere evitar que reciban correo electrónico para audioconferencias, puede usar el centro de administración de Skype Empresarial o Windows PowerShell. 
 
![Un icono que muestra el Skype Empresarial ](../images/sfb-logo-30x30.png) **con el centro Skype Empresarial administración**  
    
1. In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.
    
2. En la **página Configuración del puente de Microsoft,** seleccione o desactive Enviar mensajes de correo electrónico automáticamente a los usuarios si la configuración de las **audioconferencias cambia.** 
    
3. Haga clic en **Guardar**. 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.
  
1. Ejecute las acciones siguientes para deshabilitar el envío de todos los correos electrónicos a sus usuarios:
    
   ```PowerShell
   Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $false
   ```

You can use the [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet to manage other settings for your organization, including email.
  
## <a name="what-else-should-you-know-about-this-email"></a>¿Qué más debe saber sobre este correo electrónico?

- Para más información sobre habilitar y deshabilitar el envío de correos electrónicos de forma automática a sus usuarios, vea [Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de conferencias de Audio](enable-or-disable-sending-emails-when-their-settings-change.md).
    
- A veces, los usuarios pierden su información de audio y necesita poder enviarles toda su información de audio. Para ello, use el centro de administración  de Skype Empresarial y haga clic en Enviar información de conferencia por correo electrónico en las propiedades de audioconferencia de un usuario. See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md). Sin embargo, esta información no incluye el PIN de audioconferencia.
    
    Este es un ejemplo del correo electrónico que se les enviará:
    
     ![Correo electrónico de conferencia de acceso telefónico](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- De forma predeterminada, el remitente de los correos electrónicos será de Microsoft 365 o Office 365, pero puede cambiar la dirección de correo electrónico y el nombre para mostrar con Windows PowerShell y el cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](/previous-versions//mt228132(v=technet.10))
    
- Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer. Para empezar con Windows PowerShell, vea estos temas:
    
  - [¿Por qué necesita usar Microsoft 365 o Office 365 PowerShell?](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell tiene muchas ventajas en la velocidad, la sencillez y la productividad sobre el uso del centro de administración de Microsoft 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes: 
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>Temas relacionados

[Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de conferencias de Audio](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[Enviar un correo electrónico a un usuario con su información de conferencias de Audio](send-an-email-to-a-user-with-their-dial-in-information.md)
