---
title: Ver, modificar y restablecer un identificador de conferencia asignado a un usuario
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Learn how to assign a conference ID to a user in Skype for Business and what the conference ID's parameters should be. "
ms.openlocfilehash: 12fe2b0f425f58dca8272f5f0536ba5393b2f76c
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/03/2018
---
# <a name="see-change-and-reset-a-conference-id-assigned-to-a-user"></a>Ver, modificar y restablecer un identificador de conferencia asignado a un usuario

Un ID de conferencia se asigna automáticamente a un Skype para usuarios de negocios o Teams de Microsoft cuando se configuran para conferencias de Audio en Office 365 y usar Microsoft como proveedor de conferencia de audio. de conferencia a un usuario
  
Identificadores estáticos se utilizan cuando las personas de la organización no desean recordar un número aleatorio; Puede seleccionar un determinado número o utilizar uno que sea fácil de recordar. Cuando se utilizan identificadores de conferencia dinámico, cada reunión programaciones de un usuario obtener asignará un identificador único conferencia. Si desea asignar el dinámico en lugar de conferencia estática IDs, [vaya aquí](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
Aunque crea automáticamente un ID de conferencia estática y se asigna a un usuario, puede haber ocasiones cuando un usuario no desea utilizar esta y desea establecerla en un número determinado, o cuando los usuarios no recuerdan o han perdido su ID de conferencia. Puede utilizar el **Skype para el centro de administración de negocios** y de Windows PowerShell para ver, cambiar y restablecer su ID de conferencia.
  
Se enviará un correo electrónico al usuario con el identificador de la conferencia y los números de teléfono de conferencia de audio predeterminada o si restablece el ID de la conferencia se enviará otro correo electrónico que incluirá el identificador de la conferencia, pero no un PIN.
  
## <a name="view-and-change-conference-ids"></a>Ver y cambiar los identificadores de la conferencia

### <a name="to-view-the-conference-id"></a>Para ver el identificador de la conferencia

Puede ver su ID de conferencia y enviarla a los usuarios.
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En el **Skype para el centro de administración de negocios**> **conferencias de Audio** > **usuarios**, seleccione el usuario que necesita la conferencia Id.
    
4. En la página acción, busque bajo **Id. de conferencia**.
    
    > [!TIP]
    > Toda la información de la conferencia puede enviar al usuario en un correo electrónico que incluye el Id. de conferencia y números de teléfono de audio haciendo clic en el vínculo **Enviar información de conferencia a través de correo electrónico** después de seleccionar el usuario en la página **usuarios** .
  
    Puede utilizar Windows PowerShell para ver el Id. de conferencia para un usuario. Para ello, ejecute:
    
  ```
  Get-CsOnlineDialInConferencingUser -Identity "Amos Marble"  
  ```

    Consulte [Get-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617693 ) para obtener más información acerca del cmdlet.
    
### <a name="to-assign-or-change-the-conference-id"></a>Para asignar o cambiar el ID de la conferencia

Puede asignar o cambiar un ID de conferencia para un usuario si, por ejemplo, alguien quiere un ID de conferencia que sea fácil de recordar.

  > [!NOTE]
  > No se puede utilizar el Skype para el centro de administración de negocios para modificar un ID de conferencia que se ha creado automáticamente, pero puede utilizar Windows PowerShell para modificar o cambiar el ID de conferencia que ha establecido. 
     
Para modificar o cambiar el ID de conferencia para un usuario, ejecute:
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964
  ```

  > [!TIP]
  > Para establecer el id. de conferencia de un usuario, ejecute: 
  
### <a name="to-reset-the-conference-id"></a>Para restablecer el identificador de la conferencia

Puede restablecer un Id. de conferencia para un usuario si, por ejemplo, si olvida.
  
1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En el **Skype para el centro de administración de negocios**> **conferencias de Audio** > **los usuarios**, en el panel de acción en el **Id. de conferencia**, haga clic en **Restablecer**.
    
4. En el **Restablecer Id. de conferencia?** ventana, haga clic en **Sí**. Una conferencia que se creará automáticamente el ID y el correo electrónico enviado al usuario con el nuevo ID de conferencia.
    
    Puede restablecer el Id. de conferencia para un usuario mediante el de Windows PowerShell. Para ello, ejecute:
    
  ```
  Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ResetLeaderPIN 8271964
  ```

## <a name="what-else-should-you-know"></a>¿Qué más tengo que saber?

   > [!IMPORTANT]
   >  Después se crea un nuevo ID de conferencia o uno se restablece, no se puede utilizar el ID de conferencia antigua los llamadores. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. The users can use the Skype for Business Meeting Migration Tool to update their existing meetings. Para ver cómo descargar, instalar y ejecutar la herramienta, vea: [Herramienta de actualización de la reunión para Skype para empresas y Lync](http://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype para los negocios en línea, herramienta de migración de reunión (64 bits)](http://go.microsoft.com/fwlink/?LinkID=626047)y [Skype para los negocios en línea, herramienta de migración de reunión (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).
  
- Para más información sobre el cmdlet, vea [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).
    
- El identificador de la conferencia debe cumplir la longitud en dígitos establecido en el puente de conferencia de audio. No puede utilizar caracteres especiales o alfabéticos en conferencia identificadores; pueden utilizarse sólo números.
    
- El ID de conferencia para todos los usuarios de conferencia de audio será 7 dígitos de forma predeterminada y no se puede cambiar el número de dígitos.
    
    
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

