---
title: Ver, cambiar y restablecer el id. de conferencia de un usuario
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 77d36233-2aab-4802-ba9c-e9a8885ea643
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
- seo-marvel-apr2020
description: Obtenga información sobre cómo asignar un id. de conferencia a un usuario en Microsoft Teams y cuáles deben ser los parámetros de id. de conferencia.
ms.openlocfilehash: b57a419266ceca09a73fc4bf75bb12153e41ea91
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117213"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>Ver y restablecer un id. de conferencia asignado a un usuario en Microsoft Teams

Un id. de conferencia se asigna automáticamente a un usuario de Microsoft Teams cuando se configura para conferencias de audio en Microsoft 365 o Office 365 y usa Microsoft como proveedor de audioconferencias. El id. de conferencia asignado se envía en la invitación a la reunión cuando se programa la reunión. Se asignará un Id. de conferencia único a cada reunión que programe un usuario. 
  
Aunque un id. de conferencia se creará automáticamente y se asignará a un usuario, es posible que haya ocasiones en las que un usuario no quiera usar este y quiera establecerlo en un número determinado, o cuando los usuarios no puedan recordar o haber perdido su id. de conferencia. Puede usar Microsoft Teams centro de administración o Windows PowerShell para ver, cambiar y restablecer su id. de conferencia.
  
Se enviará un correo electrónico al usuario con el Id. de conferencia y los números de teléfono de audioconferencia predeterminados, o si restablece el Id. de conferencia, se enviará un correo electrónico diferente que incluirá el Id. de conferencia, pero no un PIN. Vea [Restablecer un id. de](reset-a-conference-id-for-a-user-in-teams.md) conferencia para un usuario en Microsoft Teams para obtener más información sobre cómo restablecer el PIN de un organizador de conferencias. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>Ver y restablecer los identificadores de conferencia

### <a name="to-view-the-conference-id"></a>Para ver el id. de conferencia

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**

1. En el panel de navegación izquierdo, haga clic **en Usuarios** y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En la parte superior de la página, haga clic en **Editar.**

3. En **Audioconferencia,** busque en **Id. de conferencia**.

    > [!TIP]
    > Puede enviar toda la información de conferencia al usuario en un correo electrónico que incluya el id. de conferencia y los números de teléfono de audio haciendo clic en el vínculo Enviar información de conferencia por **correo** electrónico.
  
Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.

Vea la [Microsoft Teams referencia de PowerShell](/powershell/module/teams/?view=teams-ps) para obtener más información.
    
  
### <a name="to-reset-the-conference-id"></a>Para restablecer el id. de conferencia

Puede restablecer un Id. de conferencia para un usuario si, por ejemplo, este lo olvida.
  
![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Centro de administración de Microsoft Teams en uso**

1. En el panel de navegación izquierdo, haga clic **en Usuarios** y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

2. En la parte superior de la página, haga clic en **Editar.**

3. En **Audioconferencia, haga** clic **en Restablecer id. de conferencia.**

4. En la ventana **Restablecer id. de** conferencia, haga clic en **Restablecer.** Se creará automáticamente un id. de conferencia y se enviará un correo electrónico al usuario con el nuevo id. de conferencia.
  
Vea **Enviar un correo electrónico a un usuario con su información de conferencias de Audio**.

Vea la [Microsoft Teams referencia de PowerShell](/powershell/module/teams/?view=teams-ps) para obtener más información.


## <a name="what-else-should-you-know"></a>¿Qué más debe saber?

   > [!IMPORTANT]
   >  Después de crear un id. de conferencia nuevo o restablecer uno, los autores de la llamada no pueden usar el id. de conferencia antiguo. You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations. 
  
    
- El id. de conferencia debe cumplir la longitud de los dígitos establecidos en el puente de audioconferencia. No se pueden usar caracteres alfabéticos o especiales en los id. de conferencia, solo se pueden usar números.
   
    
## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 mediante un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer. To get started with Windows PowerShell, see these topics:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](/powershell/module/teams/?view=teams-ps).
    
## <a name="related-topics"></a>Temas relacionados

[Pruebe o compre Audioconferencia en Microsoft 365 o Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)