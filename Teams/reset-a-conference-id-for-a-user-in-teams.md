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
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Conozca cuáles son los pasos que hay que seguir para restablecer el Id. de conferencia de reunión de un usuario en Microsoft Teams, y obtenga los vínculos para las herramientas de migración y actualización de reuniones.
ms.openlocfilehash: 52b547fee5bf027bcef21914e3ba3aa79b0e4e08
ms.sourcegitcommit: 7a9c63ee790108eaa61950ce28ae8027311039d9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662130"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Restablecer un Id. de conferencia para un usuario en Microsoft Teams

Al final de las invitaciones de reunión se incluye un Id. de conferencia dinámico junto con los números de teléfono de acceso telefónico local que pueden usar los autores de llamada para llamar a una reunión. Cuando el usuario marque el número de teléfono, el operador automático de la reunión le pedirá al autor de la llamada que introduzca este Id. de conferencia para que pueda asistir a la reunión.
  
> [!NOTE]
> Los id. de conferencia se generan automáticamente, tendrán entre 7 y 9 dígitos y se establecen cuando se habilita Audioconferencia para un usuario. **No se admiten los iD de conferencia estáticos.** 

## <a name="resetting-the-conference-id-for-a-user"></a>Restablecer el id. de conferencia de un usuario

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, haga clic en **Usuarios** y seleccione el usuario en la lista de usuarios disponibles.

2. Haga clic **en Editar.**

3. En **Audioconferencia**, haga clic en **Restablecer Id. de conferencia**.

2. En la ventana **Restablecer Id. de conferencia**, haga clic en **Restablecer**. El Id. de conferencia se creará automáticamente y se enviará un correo electrónico al usuario con el Id. de conferencia nuevo. Los correos electrónicos se envían a los usuarios de forma predeterminada, aunque esto también se puede desactivar.   

    
> [!NOTE]
> Después de restablecer el Id. de conferencia, se enviará un correo electrónico al usuario con el nuevo Id. de conferencia. Este correo electrónico se enviará a la dirección de correo electrónico principal, en muchos casos, su buzón de Microsoft 365 u Office 365. El correo electrónico contiene el nuevo Id. de conferencia, los números de teléfono de acceso telefónico local predeterminados y las instrucciones para actualizar las reuniones existentes. 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a>¿Qué más debo saber?

- Puede enviar toda la información de la conferencia al usuario en un correo electrónico que incluya el Id. de conferencia y los números de teléfono de acceso telefónico local haciendo clic en **Enviar información de conferencia a través del correo electrónico** para el usuario en la sección **Audioconferencia**. De esta forma no se envía el PIN.
    
- El servicio de Teams crea un id. de conferencia de 7 a 9 dígitos. No puede cambiar su longitud.
    
- Una vez que se ha restablecido el nuevo id. de conferencia, podrá verlo en **Id. de conferencia**.
    
- After a new conference ID is created, the old conference ID can't be used by callers. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. 

## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tenga que realizar varias tareas. To get started with Windows PowerShell, see these topics:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
## <a name="related-topics"></a>Temas relacionados

[Restablecer el PIN de Audioconferencia](reset-the-audio-conferencing-pin-in-teams.md)
