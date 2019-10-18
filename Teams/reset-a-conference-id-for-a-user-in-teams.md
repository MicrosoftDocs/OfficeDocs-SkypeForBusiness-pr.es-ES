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
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Conozca cuáles son los pasos que hay que seguir para restablecer el Id. de conferencia de reunión de un usuario en Microsoft Teams, y obtenga los vínculos para las herramientas de migración y actualización de reuniones. '
ms.openlocfilehash: 894761811bfc9c353c7a145c83c7a201a587f1e2
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37568372"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Restablecer un Id. de conferencia para un usuario en Microsoft Teams

Al final de las invitaciones de reunión se incluye un Id. de conferencia dinámico junto con los números de teléfono de acceso telefónico local que pueden usar los autores de llamada para llamar a una reunión. Cuando el usuario marque el número de teléfono, el operador automático de la reunión le pedirá al autor de la llamada que introduzca este Id. de conferencia para que pueda asistir a la reunión.
  
> [!NOTE]
> Si el proveedor de servicios de conferencia es Microsoft, los Id. de conferencia de los usuarios se establecen en Dynamic Only (Solo dinámico) de forma predeterminada. Lamentablemente, no existe ninguna forma de cambiarlo de nuevo a estático, no es compatible todavía. Los Id. de conferencia solo se establecen automáticamente para los usuarios de Microsoft Teams que tengan habilitada la Audioconferencia. 


## <a name="resetting-the-conference-id-for-a-user"></a>Restablecer el Id. de conferencia para un usuario

![Un icono que muestra el logotipo](media/teams-logo-30x30.png) de Microsoft Teams **con el centro de administración de Microsoft Teams**

1. En el navegación de la izquierda, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. Haga clic en **Editar**.

3. En **Conferencia de audio** , haga clic en **restablecer ID de conferencia**.

2. En la ventana **restablecer ID de conferencia** , haga clic en **restablecer**. Se creará automáticamente un ID de conferencia y un mensaje de correo electrónico con el nuevo identificador de conferencia. De forma predeterminada, los correos electrónicos se envían a los usuarios, pero esto se puede desactivar.   

    
> [!NOTE]
> Después de restablecer el identificador de conferencia, se enviará al usuario un mensaje de correo electrónico con la nueva identificación de conferencia. Este mensaje de correo electrónico se enviará a la dirección de correo electrónico principal, en muchos casos, el buzón de Office 365. El correo electrónico contiene el nuevo identificador de conferencia, los números de teléfono de acceso telefónico (s) predeterminados y las instrucciones para actualizar las reuniones existentes. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>¿Qué más debo saber?

- Puede enviar toda la información de la Conferencia al usuario en un correo electrónico que incluya el identificador de la Conferencia y los números de teléfono de acceso telefónico local haciendo clic en **enviar información de conferencia por correo electrónico** para el usuario en la sección **audioconferencia** . No envía el PIN.
    
- Un identificador de conferencia contendrá 7 dígitos y no se puede cambiar su longitud.
    
- Una vez que se ha restablecido el nuevo id. de conferencia, podrá verlo en **Id. de conferencia**.
    
- After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. 

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
## <a name="related-topics"></a>Temas relacionados

[Restablecer el PIN de Audioconferencia](reset-the-audio-conferencing-pin-in-teams.md)
