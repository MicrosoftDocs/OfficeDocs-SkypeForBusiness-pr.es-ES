---
title: Ver, modificar y restablecer un identificador de conferencia asignado a un usuario
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
description: "Learn how to assign a conference ID to a user in Skype for Business and what the conference ID's parameters should be. "
ms.openlocfilehash: 4922f896daa2bec976d7fb72dd519e9dd91d74f4
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2018
---
# <a name="see-change-and-reset-a-conference-id-assigned-to-a-user"></a>Ver, modificar y restablecer un identificador de conferencia asignado a un usuario

Un identificador de conferencia se asigna automáticamente a un Skype para usuario empresarial o Teams de Microsoft cuando se configuran para conferencias de Audio en Office 365 y usar Microsoft como el proveedor de conferencia de audio. El identificador de conferencia asignado se envía en la invitación a la reunión cuando la reunión está programada. Cada reunión que un usuario programa obtener asignará un identificador de conferencia único. 
  
Si bien crea automáticamente un identificador de conferencia y se asigna a un usuario, puede haber ocasiones cuando un usuario no desea usar este uno y que desea establecer para un cierto número, o cuando los usuarios no pueden recordar o que han perdido su identificador de conferencia. Puede usar el **Skype para el centro de administración de negocio** y Windows PowerShell para ver, cambiar y restablecer su identificador de conferencia.
  
Se enviará un correo electrónico al usuario con el identificador de conferencia y los números de teléfono de conferencia de audio predeterminada o, si restablece el identificador de conferencia se van a enviar un correo electrónico de diferente que incluirá el identificador de conferencia, pero no un PIN. Para obtener más información acerca de cómo restablecer el PIN del organizador de la conferencia, [haga clic aquí](reset-a-conference-id-for-a-user.md). 
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-view-and-change-conference-ids"></a>![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) Ver y cambiar los identificadores de conferencia

### <a name="to-view-the-conference-id"></a>Para ver el identificador de conferencia

Puede ver su identificador de conferencia y enviar a los usuarios.
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En el **Skype para el centro de administración de negocio**> **conferencias de Audio** > **a los usuarios**, seleccione el usuario que necesita identificador de la conferencia.
    
4. En la página acción, mire en el **Identificador de conferencia**.
    
    > [!TIP]
    > Puede enviar toda la información de conferencia para el usuario en un correo electrónico que incluye el identificador de conferencia y los números de teléfono de audio, haga clic en el vínculo **Enviar información de conferencia a través de correo electrónico** después de seleccionar el usuario en la página **usuarios** .
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

Puede usar Windows PowerShell para ver el identificador de conferencia para un usuario. Para ello, ejecute:
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    See [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) to learn more about the cmdlet.
    
### <a name="to-assign-or-change-the-conference-id"></a>Para asignar o cambiar el identificador de conferencia

Puede asignar o cambiar un identificador de conferencia para un usuario si, por ejemplo, alguien desea un identificador de conferencia que sea fácil de recordar.

  > [!NOTE]
  > El Skype para el centro de administración de negocio no se puede usar para editar un identificador de conferencia que se ha creado automáticamente, pero se puede usar Windows PowerShell para editar o cambiar un identificador de conferencia que se ha establecido. 
     
Para editar o cambiar el identificador de conferencia para un usuario, ejecute:
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964
  ```

  > [!TIP]
  > Para establecer el id. de conferencia de un usuario, ejecute: 
  
### <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-to-reset-the-conference-id"></a>![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) Para restablecer el identificador de conferencia

Puede restablecer un identificador de conferencia para un usuario si, por ejemplo, si olvida.
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En el **Skype para el centro de administración de negocio**> **conferencias de Audio** > **a los usuarios**, en el panel de acciones en **Identificador de conferencia**, haga clic en **Restablecer**.
    
4. En la **Restablecer el identificador de conferencia?** ventana, haga clic en **Sí**. Una conferencia que se creará automáticamente el identificador y un correo electrónico enviado al usuario con el nuevo identificador de conferencia.
    
    Puede restablecer el identificador de conferencia para un usuario mediante el uso de Windows PowerShell. Para ello, ejecute:
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetConferenceID 8271964
  ```

## <a name="what-else-should-you-know"></a>¿Qué más tengo que saber?

   > [!IMPORTANT]
   >  Una vez que se crea un nuevo identificador de conferencia o uno se restablece, no se puede usar el identificador de conferencia antigua por los autores de llamadas. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. Para ver cómo descargar, instalar y ejecutar la herramienta, vea: [Herramienta de actualización de la reunión de Skype para empresas y Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype para Online de negocio, herramienta de migración de reunión (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)y [Skype para Online de negocio, herramienta de migración de reunión (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).
  
- Para más información sobre el cmdlet, vea [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
- El identificador de conferencia debe cumplir la longitud en dígitos establecer en el puente de conferencia de audio. No se puede usar caracteres especiales o alfabéticos en conferencia identificadores; se pueden usar solo números.
    
- El identificador de conferencia para todos los usuarios de conferencia de audio será 7 dígitos de forma predeterminada y no se puede cambiar el número de dígitos.
    
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also

[Probar o comprar Audioconferencia en Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)

