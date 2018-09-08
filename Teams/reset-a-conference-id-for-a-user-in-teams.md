---
title: Restablecer un identificador de conferencia para un usuario en Microsoft Teams
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
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtenga información sobre los pasos para restablecer un usuario reunión de identificador de conferencia en Microsoft Teams y get contiene vínculos a las herramientas de actualización y migración de la reunión. '
ms.openlocfilehash: 4e338e5ad00792a48e0a6c9e0791c0c5e4b759ac
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887855"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a>Restablecer un identificador de conferencia para un usuario en Microsoft Teams

Un identificador de conferencia dinámico se incluye en la parte inferior de las invitaciones junto con los números de teléfono de acceso telefónico que pueden usarse por los autores de llamadas a llama a una reunión de la reunión. Cuando el usuario marca el número de teléfono, el operador automático de la reunión le preguntará el autor de la llamada para escribir este identificador de conferencia, por lo que pueden asistir a la reunión.
  
> [!NOTE]
> Si su proveedor de conferencia es Microsoft, los identificadores de conferencia de los usuarios se establecen en dinámico sólo de forma predeterminada. Lamentablemente, no hay ninguna capacidad para cambiarlo de manera que se convierten en estáticos, ya que esta es ahora no compatible. ID de conferencia se establece automáticamente solo para los usuarios de Microsoft Teams habilitados para conferencias de Audio. 


## <a name="resetting-the-conference-id-for-a-user"></a>Restablecer el identificador de conferencia para un usuario

1. En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En la parte superior de la página, haga clic en **Editar**.

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
    
Para obtener más información acerca de Windows PowerShell, vea la [referencia de PowerShell de los equipos de Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.
    
## <a name="related-topics"></a>Temas relacionados

[Restablecer el PIN de conferencia de Audio](reset-the-audio-conferencing-pin-in-teams.md)
