---
title: Restablecer un id. de conferencia para un usuario
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: 'Learn the steps to reset a user''s meeting conference ID, and get links to meeting update and migration tools. '
ms.openlocfilehash: 2f2cbd6efa61e05defb17ef05f86fd9a228987ac
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/15/2017
---
# <a name="reset-a-conference-id-for-a-user"></a>Restablecer un id. de conferencia para un usuario

Cuando las organizaciones todavía no ha habilitado para identificadores de conferencia dinámico, un ID de conferencia estática se crea automáticamente cuando se habilita un Skype para usuarios de negocios o Teams de Microsoft para conferencias de Audio mediante Microsoft como proveedor. Este ID de conferencia se incluye en la parte inferior de las invitaciones junto con los números de teléfono de acceso telefónico que pueden utilizarse por los llamadores que llaman a una reunión a reuniones. Cuando el usuario marca el número de teléfono, el operador automático de la reunión le preguntará el llamador para introducir este ID de conferencia para poder asistir a la reunión.
  
> [!NOTE]
> Si su proveedor de conferencias es Microsoft, identificadores de conferencia de los usuarios se establecen en sólo dinámica predeterminada. Por desgracia, no podrá cambiarla en el Skype para el centro de administración de negocio o el uso de Windows Powershell. Tendrá que ponerse en contacto con el soporte técnico de Microsoft. 
  
Identificadores estáticos se utilizan cuando las personas de la organización no desean recordar un número aleatorio; Puede seleccionar un determinado número o utilizar uno que sea fácil de recordar. Cuando se utilizan identificadores de conferencia dinámico, cada reunión programaciones de un usuario obtener asignará un identificador único conferencia. Si desea asignar el dinámico en lugar de conferencia estática IDs, [vaya aquí](using-audio-conferencing-dynamic-ids-in-your-organization.md).
  
Identificadores de conferencia sólo se establecen automáticamente sólo para Skype para usuarios de negocios y Teams de Microsoft habilitado para conferencias de Audio mediante Microsoft como su proveedor de conferencia de audio. Si necesita restablecer un Id. de conferencia para un usuario que está usando un proveedor de conferencia de audio de terceros (ACP), deberá especificar manualmente un Id. de conferencia en la página de propiedades para el usuario.
  
## <a name="resetting-the-conference-id-for-a-user"></a>Restablecer el Id. de conferencia para un usuario

1. Inicie sesión en Office 365 con su cuenta profesional o educativa.
    
2. Vaya a **Centro de administración de Office 365** > **Skype Empresarial**.
    
3. En el **Skype para el centro de administración de negocios**, haga clic en **conferencias de Audio** > **usuarios**, seleccione un usuario y, a continuación, en el panel de acción en el **Id. de conferencia** , haga clic en **Restablecer**.
    
4. En el **Restablecer Id. de conferencia?** ventana, haga clic en **Sí**. Una conferencia que se creará automáticamente el ID y el correo electrónico enviado al usuario con el nuevo ID de conferencia. De forma predeterminada, se envían mensajes de correo electrónico a los usuarios, pero esto se puede desactivar.
    
    > [!NOTE]
    > Después de restablecer el Id. de conferencia, se enviará al usuario un correo electrónico con el nuevo Id. de conferencia. Este mensaje de correo electrónico se enviará a la dirección de correo electrónico principal, en muchos casos, su buzón de correo de Office 365. El correo electrónico contiene el nuevo Id. de conferencia, los números de teléfono de acceso telefónico local predeterminados y las instrucciones para usar la herramienta de actualización de reuniones de Skype Empresarial para actualizar las reuniones existentes. 
  
## <a name="what-else-should-i-know"></a>¿Qué más debo saber?

- Toda la información de la conferencia puede enviar al usuario en un correo electrónico que incluye el Id. de conferencia y números de teléfono de acceso telefónico, haga clic en **Enviar información de conferencia a través de correo electrónico** para el usuario en el panel de acciones. No envía el PIN.
    
- Un ID de conferencia contiene 7 dígitos y no puede cambiar su longitud en el Skype para el centro de administración de negocios o mediante Windows PowerShell.
    
- Una vez que se ha restablecido el nuevo id. de conferencia, podrá verlo en **Id. de conferencia**.
    
- El identificador de la conferencia de un usuario para conferencias de audio puede verse en la parte inferior del panel de acciones en **conferencias de Audio** cuando se selecciona el usuario en la página **usuarios** .
    
- Después de crea un nuevo ID de conferencia, no se puede utilizar el ID de conferencia antigua por los llamadores. Debe notificar a los usuarios a programar sus invitaciones para asegurarse de que la nueva conferencia que ID se agrega a las invitaciones para reuniones existentes. Los usuarios pueden utilizar Skype para la herramienta de reuniones de negocios para actualizar sus reuniones existentes. Para ver cómo descargar, instalar y ejecutar el Skype para la herramienta de actualización de reunión empresarial, consulte:
    
  - [Herramienta de actualización de reuniones para Skype y Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype Empresarial Online, herramienta de migración de reuniones (64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype Empresarial Online, herramienta de migración de reuniones (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Temas relacionados

[Restablecer el PIN de conferencia de Audio para un usuario](reset-the-audio-conferencing-pin-for-a-user.md)
