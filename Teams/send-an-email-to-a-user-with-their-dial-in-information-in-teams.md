---
title: Enviar un correo electrónico a un usuario con su información de audioconferencia en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: None
ms.custom:
- Audio Conferencing
description: Envíe a sus usuarios un correo electrónico con la información de sus audioconferencias en Microsoft Teams.
ms.openlocfilehash: 85e219481884bb08a2574809b6170c232abccf83
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892095"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a>Enviar un correo electrónico a un usuario con su información de audioconferencia en Microsoft Teams

A veces, puede que los usuarios de Microsoft Teams necesiten que les envíe su información sobre la audioconferencia. Para ello, haga clic en **Enviar información de conferencia por correo electrónico** en las propiedades de un usuario. Cuando se envíe este correo electrónico, este contendrá toda la información de la audioconferencia, incluido lo siguiente:
  
- El número de teléfono de la conferencia o el número de teléfono de acceso telefónico local del usuario
    
- El Id. de conferencia del usuario
    
   
A continuación se muestra un ejemplo del correo electrónico que se envía:
  
![Correo electrónico de conferencia de acceso telefónico local](media/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Enviar un correo electrónico con la información de audioconferencia a un usuario

1. En el panel de navegación izquierdo, haga clic en **Usuarios** y seleccione el usuario en la lista de usuarios disponibles.

2. En la parte superior de la página, haga clic en **Editar**.

3. En **Audioconferencia**, haga clic en **Enviar información de conferencia por correo electrónico**.


## <a name="what-else-should-you-know-about-this-email"></a>¿Qué más tiene que saber sobre este correo electrónico?

- Existen diversos correos electrónicos que se envían a los usuarios de su organización una vez que se han habilitado para la audioconferencia:
    
  - Cuando se les asigna una licencia de **Audioconferencia**.
    
  - Al restablecer de forma manual el PIN de audioconferencia del usuario.
    
  - Al restablecer de forma manual el Id. de conferencia del usuario.
    
  - Cuando se elimina una licencia de **Audioconferencia** para el usuario.
    
  - Cuando el proveedor de servicios de audioconferencia de un usuario se cambia de Microsoft a otro usuario o a **Ninguno**.
    
  - Cuando el proveedor de servicios de audioconferencia de un usuario se cambia a Microsoft.
    
- De manera predeterminada, el remitente de los mensajes de correo electrónico será de Office 365, pero puede cambiar la dirección de correo electrónico y el nombre para mostrar con Windows PowerShell. Vea la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.
  
## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
