---
title: Consultar, cambiar y restablecer un Id. de conferencia asignado a un usuario en Microsoft Teams
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
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Aprenda a asignar un Id. de conferencia a un usuario en Microsoft Teams y cuáles deben ser los parámetros del Id. de conferencia. '
ms.openlocfilehash: 317216f84044eb404541a98d24c69b2f7fb61bc4
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25017088"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>Ver y restablecer un Id. de conferencia asignado a un usuario en Microsoft Teams

Un identificador de conferencia se asigna automáticamente a un usuario de Microsoft Teams cuando se configuran para conferencias de Audio en Office 365 y usar Microsoft como el proveedor de conferencia de audio. El identificador de conferencia asignado se envía en la invitación a la reunión cuando la reunión está programada. Se asignará un Id. de conferencia único a cada reunión que programe un usuario. 
  
Si bien crea automáticamente un identificador de conferencia y se asigna a un usuario, puede haber ocasiones cuando un usuario no desea usar este uno y que desea establecer para un cierto número, o cuando los usuarios no pueden recordar o que han perdido su identificador de conferencia. Puede usar el centro de administración de Microsoft Teams o Windows PowerShell para ver, cambiar y restablecer su identificador de conferencia.
  
Se enviará un correo electrónico al usuario con el Id. de conferencia y los números de teléfono de audioconferencia predeterminados, o si restablece el Id. de conferencia, se enviará un correo electrónico diferente que incluirá el Id. de conferencia, pero no un PIN. Para obtener más información sobre cómo restablecer el PIN de un organizador de conferencias, [haga clic aquí](reset-a-conference-id-for-a-user-in-teams.md). 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>Ver y restablecer los identificadores de conferencia

### <a name="to-view-the-conference-id"></a>Para ver el Id. de conferencia

![teams-logo-30x30.png](media/teams-logo-30x30.png) **Mediante el Centro de administración de Skype for Business y Microsoft Teams:**

1. En el panel de navegación izquierdo, haga clic en **Usuarios** y seleccione el usuario en la lista de usuarios disponibles.

2. En la parte superior de la página, haga clic en **Editar**.

3. En **Audioconferencia**, mire en **Id. de conferencia**.

    > [!TIP]
    > Puede enviar toda la información de la conferencia al usuario en un correo electrónico que incluya el Id. de conferencia y los números de teléfono de audioconferencia haciendo clic en el vínculo **Enviar información de conferencia por correo electrónico**.
  
**Uso de Windows PowerShell**

Vea la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.
    
  
### <a name="to-reset-the-conference-id"></a>Para restablecer el Id. de conferencia

El Id. de conferencia se puede restablecer para un usuario si, por ejemplo, se le olvida.
  
![teams-logo-30x30.png](media/teams-logo-30x30.png) **Mediante el Centro de administración de Skype for Business y Microsoft Teams:**

1. En el panel de navegación izquierdo, haga clic en **Usuarios** y seleccione el usuario en la lista de usuarios disponibles.

2. En la parte superior de la página, haga clic en **Editar**.

3. En **Audioconferencia**, haga clic en **Restablecer Id. de conferencia**.

4. En la ventana **Restablecer Id. de conferencia** , haga clic en **Restablecer**. Una conferencia que se creará automáticamente el identificador y un correo electrónico enviado al usuario con el nuevo identificador de conferencia.
  
**Uso de Windows PowerShell**

Vea la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.


## <a name="what-else-should-you-know"></a>¿Qué más debe saber?

   > [!IMPORTANT]
   >  Una vez que se crea un nuevo identificador de conferencia o uno se restablece, no se puede usar el identificador de conferencia antigua por los autores de llamadas. Debe notificar a los usuarios para que reprogramen sus invitaciones de reunión existentes para asegurarse de que se agrega a las invitaciones el nuevo Id. de conferencia. 
  
    
- El identificador de conferencia debe cumplir la longitud en dígitos establecer en el puente de conferencia de audio. No se pueden usar caracteres alfabéticos o especiales en los id. de conferencia, solo se pueden usar números.
    
- El Id. de conferencia de todos los usuarios de audioconferencias será de siete dígitos de manera predeterminada. Además, el número de dígitos no se puede cambiar.
    
    
## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

