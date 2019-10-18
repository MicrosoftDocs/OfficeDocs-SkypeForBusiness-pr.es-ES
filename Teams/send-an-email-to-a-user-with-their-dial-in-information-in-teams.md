---
title: Enviar un correo electrónico a un usuario con su información de audioconferencia en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: None
ms.custom:
- Audio Conferencing
description: Envíe a sus usuarios un correo electrónico con la información de sus audioconferencias en Microsoft Teams.
ms.openlocfilehash: 9e4508f3907de35ee2752077ac22b5cd8a5e5735
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571320"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a>Enviar un correo electrónico a un usuario con su información de audioconferencia en Microsoft Teams

A veces, puede que los usuarios de Microsoft Teams necesiten que les envíe su información sobre la audioconferencia. Para ello, haga clic en **Enviar información de conferencia por correo electrónico** en las propiedades de un usuario. Cuando se envíe este correo electrónico, este contendrá toda la información de la audioconferencia, incluido lo siguiente:
  
- El número de teléfono de la conferencia o el número de teléfono de acceso telefónico local del usuario
    
- El Id. de conferencia del usuario
    
   
A continuación se muestra un ejemplo del correo electrónico que se envía:
  
![Ejemplo de un mensaje de correo de conferencia de acceso telefónico local](media/teams-send-email-to-user-with-audio-conferencing-image1.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a>Enviar un correo electrónico con la información de audioconferencia a un usuario

### <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) Usar el centro de administración de Microsoft Teams

1. En el navegación de la izquierda, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En la parte superior de la página, haga clic en **Editar**.

3. En **Conferencia de audio**, haga clic en **enviar información de conferencia por correo electrónico**.


## <a name="what-else-should-you-know-about-this-email"></a>¿Qué más debe saber sobre este correo electrónico?

- Se envían varios correos electrónicos a los usuarios de su organización después de que estén habilitados para las conferencias de audio:
    
  - Cuando se les asigna una licencia de **conferencias de audio** .
    
  - Cuando restablece manualmente el PIN de conferencia de audio del usuario.
    
  - Al restablecer de forma manual el id. de conferencia del usuario.
    
  - Cuando se quita una licencia de **conferencias de audio** de ellos.
    
  - Cuando el proveedor de servicios de audioconferencia de un usuario cambia de Microsoft a otro proveedor o a **ninguno**.
    
  - Cuando se cambia el proveedor de servicios de audioconferencia de un usuario a Microsoft.
  
## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
  
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
