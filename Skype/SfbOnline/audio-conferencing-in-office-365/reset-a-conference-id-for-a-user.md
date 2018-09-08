---
title: Restablecer un identificador de conferencia para un usuario en Skype para profesionales en línea
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
description: 'Obtenga información sobre los pasos para restablecer un usuario reunión de identificador de conferencia en Skype para profesionales en línea y get contiene vínculos a las herramientas de actualización y migración de la reunión. '
ms.openlocfilehash: d569dfb015db5cea79c57233ba455adfd90a3182
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887549"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a>Restablecer un identificador de conferencia para un usuario en Skype para profesionales en línea

> [!NOTE]
> Para obtener información acerca del restablecimiento de identificador de conferencia en Microsoft Teams, consulte [Restablecer un identificador de conferencia para un usuario en los equipos de Microsoft](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).

Un identificador de conferencia dinámico se incluye en la parte inferior de las invitaciones junto con los números de teléfono de acceso telefónico que pueden usarse por los autores de llamadas a llama a una reunión de la reunión. Cuando el usuario marca el número de teléfono, el operador automático de la reunión le preguntará el autor de la llamada para escribir este identificador de conferencia, por lo que pueden asistir a la reunión.
  
> [!NOTE]
> Si su proveedor de conferencia es Microsoft, los identificadores de conferencia de los usuarios se establecen en dinámico sólo de forma predeterminada. Lamentablemente, no hay ninguna capacidad para cambiar en la Skype para el centro de administración de negocio o el uso de Windows Powershell para convertirse en estáticos, ya que esta es ahora no compatible. ID de conferencia se establece automáticamente solo para Skype para usuarios profesionales habilitado para conferencias de Audio. 

## <a name="resetting-the-conference-id-for-a-user"></a>Restablecer el identificador de conferencia para un usuario
   
1. En el **Skype para el centro de administración de negocio**, haga clic en **conferencias de Audio** > **a los usuarios**, seleccione un usuario y, a continuación, en el panel de acciones en el **Identificador de conferencia** , haga clic en **Restablecer**.
    
2. En la ventana **Restablecer Id. de conferencia?**, haga clic en **Sí**. Una conferencia que se creará automáticamente el identificador y un correo electrónico enviado al usuario con el nuevo identificador de conferencia. De forma predeterminada, se envían mensajes de correo electrónico a los usuarios, pero esto se puede desactivar.
    
> [!NOTE]
> Después de restablecer el Id. de conferencia, se enviará al usuario un correo electrónico con el nuevo Id. de conferencia. Este mensaje de correo electrónico se enviará a la dirección de correo electrónico principal, en muchos casos, su buzón de correo de Office 365. El correo electrónico contiene el nuevo Id. de conferencia, los números de teléfono de acceso telefónico local predeterminados y las instrucciones para usar la herramienta de actualización de reuniones de Skype Empresarial para actualizar las reuniones existentes. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>¿Qué más debo saber?

- Puede enviar toda la información de conferencia para el usuario en un correo electrónico que incluye el identificador de conferencia y los números de teléfono de acceso telefónico, haga clic en **Enviar información de conferencia a través de correo electrónico** para el usuario en el panel de acciones. No envía el PIN.
    
- Un identificador de conferencia va a contener 7 dígitos, y no se puede cambiar su longitud en el Skype para el centro de administración de negocio o mediante el uso de Windows PowerShell.
    
- Una vez que se ha restablecido el nuevo id. de conferencia, podrá verlo en **Id. de conferencia**.
    
- El identificador de conferencia para un usuario para conferencias de audio se puede ver en la parte inferior del panel de acciones en **conferencias de Audio** cuando se selecciona el usuario en la página **usuarios** .
    
- After a new conference ID is created, the old conference ID can't be used by callers. Debe notificar a los usuarios para que reprogramen sus invitaciones de reunión existentes para asegurarse de que se agrega a las invitaciones el nuevo Id. de conferencia. Los usuarios pueden utilizar Skype para la herramienta de reunión empresarial para actualizar sus reuniones existentes. Para ver cómo descargar, instalar y ejecutar la Skype para la herramienta de actualización de reunión empresarial, consulte:
    
  - [Herramienta de actualización de reuniones para Skype y Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [Skype Empresarial Online, herramienta de migración de reuniones (64 bits)](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [Skype Empresarial Online, herramienta de migración de reuniones (32 bits)](https://www.microsoft.com/en-us/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>¿Desea saber cómo administrar con Windows PowerShell?

- En relación con Windows PowerShell, todo se reduce a la administración de usuarios y de lo que pueden o no hacer los usuarios. Con Windows PowerShell, puede administrar Office 365 y Skype Empresarial Online con un único punto de administración que puede simplificar su trabajo diario si tiene que realizar varias tareas. Para empezar con Windows PowerShell, vea estos temas:
    
  - [Una introducción a Windows PowerShell y Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell ofrece numerosas ventajas de velocidad, sencillez y productividad con respecto al uso exclusivo del Centro de administración de Office 365, como por ejemplo a la hora de realizar cambios de configuración para varios usuarios a la vez. Más información sobre estas ventajas en los siguientes temas:
    
  - [Mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar Windows PowerShell para administrar Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usar Windows PowerShell para realizar tareas de administración comunes de Skype Empresarial Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also

[Restablecer el PIN de conferencia de Audio](reset-the-audio-conferencing-pin.md)
