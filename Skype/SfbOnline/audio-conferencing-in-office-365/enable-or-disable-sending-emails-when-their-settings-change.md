---
title: Habilitar o deshabilitar el envío de correos electrónicos cuando cambia su configuración
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
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
description: 'Learn how to enable or disable Skype from sending emails to users when settings such as pin changes or the default conferencing number changes. '
ms.openlocfilehash: c7582030765db6951c972dc3fa59610aca73417e
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/05/2018
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change"></a>Habilitar o deshabilitar el envío de correos electrónicos cuando cambie la configuración de conferencias de Audio

Los usuarios se notifican automáticamente por correo electrónico cuando están habilitados para conferencias de Audio. Puede haber ocasiones, sin embargo, cuando desea reducir el número de mensajes de correo electrónico que se envían a Skype para usuarios empresariales y Teams de Microsoft. En tales casos, puede deshabilitar el envío de correo electrónico.
  
Si deshabilita el envío de correos electrónicos, mensajes de correo electrónico de conferencia de Audio no se enviará a los usuarios, incluidos los mensajes de correo electrónico para cuando los usuarios están habilitados o deshabilitados para conferencias de audio, cuando se restablezca su NIP y el identificador de la conferencia y la conferencia predeterminado cambios del número de teléfono .
  
Aquí es un ejemplo del correo electrónico que se envía a los usuarios cuando están habilitados para conferencias de Audio:
  
![Correo de conferencia de audio](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a>¿Cuándo se envían correos electrónicos a los usuarios?

- Hay varios correos electrónicos que se envían a los usuarios de la organización después de que se hayan habilitado para conferencias de audio:
    
  - Cuando se asigna una licencia de **Conferencia de Audio** a ellos.
    
  - Cuando restablece manualmente conferencias de audio PIN del usuario.
    
  - Al restablecer de forma manual el id. de conferencia del usuario.
    
  - Cuando se quita la licencia de **Conferencia de Audio** de ellos.
    
  - Cuando se cambia el proveedor de conferencia de audio de un usuario de Microsoft a otro proveedor, o **Ninguno**.
    
  - Cuando se cambia el proveedor de conferencia de audio de un usuario a Microsoft.
    
## <a name="enable-or-disable-email-from-being-sent-to-users"></a>Habilitar o deshabilitar el correo electrónico se envíe a los usuarios

Puede utilizar Microsoft Teams, el Skype para el centro de administración de negocios o de Windows PowerShell para habilitar o deshabilitar el correo electrónico enviado a los usuarios.

**Utilizando los equipos de Microsoft y Skype para el centro de administración de negocios**
1. En la exploración de la izquierda, vaya a **reuniones** > **Puentes de conferencia**. 

2. En la parte superior de la página **Puentes de conferencia** , haga clic en **Configuración de puente**. 

3. En el panel **configuración de puente** , habilitar o deshabilitar **automáticamente enviar correos electrónicos a los usuarios si cambia su configuración de acceso telefónico**.

4. Haga clic en **Aplicar**.
  
Puede usar el Centro de administración de Skype Empresarial o Windows PowerShell para habilitar o deshabilitar el envío de correos electrónicos a los usuarios.
    
1. En el **Skype para el centro de administración de negocios**, en la exploración de la izquierda, haga clic en **conferencias de Audio**.
    
2. On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.
    
3. Click **Save**.
    
    > [!TIP]
    > También puede enviar correo electrónico a un usuario con la configuración de conferencia de audio yendo a las **conferencias de Audio** > **usuarios**, seleccionar el usuario y hacer clic en **Enviar información de conferencia a través de correo electrónico**.  Si lo hace, se enviará un correo electrónico que sólo incluye los Id. de conferencia y número de teléfono de conferencia, pero no el PIN.  Para obtener más información, vea [Enviar un correo electrónico a un usuario con su información de conferencia de Audio](send-an-email-to-a-user-with-their-dial-in-information.md) .
  
Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.
  
- Ejecute el siguiente procedimiento para deshabilitar el envío de correos electrónicos: 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    Para obtener ayuda con este cmdlet, vea [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).
    
## <a name="what-else-should-you-know"></a>¿Qué más tengo que saber?

- Cuando están deshabilitados los correos electrónicos, puede desencadenar manualmente sigue enviando un correo electrónico con el número de ID y teléfono de conferencia usando el Skype para el centro de administración de negocios. Sin embargo, si lo hace, no se incluirán el NIP. Si desea restablecer el PIN de conferencias de audio y enviar mensajes de correo electrónico está deshabilitado, debe enviar al usuario en otra forma.
    
- De forma predeterminada, será el remitente de los mensajes de correo electrónico de Office 365, pero puede cambiar la dirección de correo electrónico y Mostrar nombre mediante Windows PowerShell y también usar el cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) .
    
    > [!NOTE]
    >  Si desea cambiar la información de la dirección de correo electrónico, debe asegurarse de que las directivas de correo electrónico entrante de su entorno permiten correos electrónicos procedentes de personalizado especificado en la dirección.
  
  - Escriba la dirección de correo electrónico en el parámetro  _SendEmailFromAddress_.
    
  - Escriba el nombre para mostrar del correo electrónico en el parámetro  _SendEmailFromDisplayName_.
    
  - Establezca el parámetro _SendEmailOverride_ en _True_.
    
  -  `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
- El envío de correos electrónicos a los usuarios se puede deshabilitar con el Centro de administración de Skype Empresarial o con Windows PowerShell.
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- Puede usar estos cmdlets para ahorrar tiempo o automatizar esta tarea.
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [Quitar CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [Get-CsOnlineDialinConferencingTenantConfiguration](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [Get-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell cuenta con muchas ventajas en velocidad, simplicidad y productividad en comparación con solo usar el centro de administración de Office 365, como cuando realiza cambios de configuración para muchos usuarios a la vez. Más información sobre estas ventajas en los temas siguientes: 
    
  - [Introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > El módulo Windows PowerShell para Skype Empresarial Online le permite crear una sesión de Windows PowerShell remota que se conecta con Skype Empresarial Online. Este módulo, que solo es compatible con equipos de 64 bits, se puede descargar desde el Centro de descarga de Microsoft en [Módulo de Windows PowerShell para Skype Empresarial Online.](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>See also

[Correos electrónicos enviados a los usuarios cuando cambia su configuración de conferencia de Audio](emails-sent-to-users-when-their-settings-change.md)

[Enviar un correo electrónico a un usuario con su información de conferencias de Audio](send-an-email-to-a-user-with-their-dial-in-information.md)


