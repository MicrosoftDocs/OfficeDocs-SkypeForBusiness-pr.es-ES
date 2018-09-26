---
title: Restablecer un Id. de conferencia para un usuario en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Conozca cuáles son los pasos que hay que seguir para restablecer el Id. de conferencia de reunión de un usuario en Microsoft Teams, y obtenga los vínculos para las herramientas de migración y actualización de reuniones. '
ms.openlocfilehash: bed015c92e197c1ee2dc1b48e495eee98445e3f0
ms.sourcegitcommit: 090ff859083ace43c08d483f4023009e8b6e79e4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/26/2018
ms.locfileid: "25019047"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Restablecer un Id. de conferencia para un usuario en Microsoft Teams

Un identificador de conferencia dinámico se incluye en la parte inferior de las invitaciones junto con los números de teléfono de acceso telefónico que pueden usarse por los autores de llamadas a llama a una reunión de la reunión. Cuando el usuario marca el número de teléfono, el operador automático de la reunión le preguntará el autor de la llamada para escribir este identificador de conferencia, por lo que pueden asistir a la reunión.
  
> [!NOTE]
> Si su proveedor de conferencia es Microsoft, los identificadores de conferencia de los usuarios se establecen en dinámico sólo de forma predeterminada. Lamentablemente, no hay ninguna capacidad para cambiarlo de manera que se convierten en estáticos, ya que esta es ahora no compatible. ID de conferencia se establece automáticamente solo para los usuarios de Microsoft Teams habilitados para conferencias de Audio. 


## <a name="resetting-the-conference-id-for-a-user"></a>Restablecer el Id. de conferencia para un usuario

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) Uso del equipos de Microsoft y Skype para centro de administración de negocio

1. En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. Haga clic en **Editar**.

3. En las **Conferencias de Audio** , haga clic en **Restablecer el identificador de conferencia**.

2. En la ventana **Restablecer Id. de conferencia** , haga clic en **Restablecer**. Una conferencia que se creará automáticamente el identificador y un correo electrónico enviado al usuario con el nuevo identificador de conferencia. De forma predeterminada, se envían mensajes de correo electrónico a los usuarios, pero esto se puede desactivar.   

    
> [!NOTE]
> Después de restablecer el identificador de conferencia, se enviará un correo electrónico con el nuevo identificador de conferencia al usuario. Este correo electrónico se enviarán a la dirección de correo electrónico principal, en muchos casos, su buzón de Office 365. El correo electrónico contiene el nuevo identificador de conferencia, números de teléfono de acceso telefónico predeterminada e instrucciones para la actualización de reuniones existentes. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>¿Qué más debo saber?

- Puede enviar toda la información de conferencia para el usuario en un correo electrónico que incluye el identificador de conferencia y los números de teléfono de acceso telefónico, haga clic en **Enviar información de conferencia en el correo electrónico** para el usuario en la sección de **Conferencias de Audio** . No envía el PIN.
    
- Un identificador de conferencia va a contener 7 dígitos, y no se puede cambiar su longitud.
    
- Una vez que se ha restablecido el nuevo id. de conferencia, podrá verlo en **Id. de conferencia**.
    
- After a new conference ID is created, the old conference ID can't be used by callers. Debe notificar a los usuarios para que reprogramen sus invitaciones de reunión existentes para asegurarse de que se agrega a las invitaciones el nuevo Id. de conferencia. 

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
## <a name="related-topics"></a>Temas relacionados

[Restablecer el PIN de conferencia de Audio](reset-the-audio-conferencing-pin-in-teams.md)
