---
title: Ver, cambiar y restablecer el identificador de conferencia de un usuario
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
description: Aprenda a asignar un identificador de conferencia a un usuario en Microsoft Teams y a los parámetros de IDs de conferencia.
ms.openlocfilehash: 4f24fb85479e6a52c8b2658b7a8a41beb0e1c6ad
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691156"
---
# <a name="view-and-reset-a-conference-id-assigned-to-a-user-in-microsoft-teams"></a>Ver y restablecer un Id. de conferencia asignado a un usuario en Microsoft Teams

Se asigna automáticamente un identificador de conferencia a un usuario de Microsoft Teams cuando se configura para audioconferencia en Microsoft 365 u Office 365 y se usa Microsoft como proveedor de servicios de audioconferencia. El Id. de conferencia asignado se envía en la invitación de la reunión cuando esta se programa. Se asignará un Id. de conferencia único a cada reunión que programe un usuario. 
  
Aunque el Id. de conferencia se crea y se asigna automáticamente a un usuario, puede suceder que un usuario no quiera usar este Id. y quiera configurar un número concreto, o que los usuarios no lo recuerden o lo hayan perdido. En esos casos, puede usar el Centro de administración de Microsoft Teams o Windows PowerShell para ver, modificar y restablecer el Id. de conferencia.
  
Se enviará un correo electrónico al usuario con el Id. de conferencia y los números de teléfono de audioconferencia predeterminados, o si restablece el Id. de conferencia, se enviará un correo electrónico diferente que incluirá el Id. de conferencia, pero no un PIN. Para obtener más información sobre cómo restablecer el PIN de un organizador de una conferencia, consulte [restablecer un identificador de conferencia para un usuario en Microsoft Teams](reset-a-conference-id-for-a-user-in-teams.md) . 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="view-and-reset-conference-ids"></a>Ver y restablecer los identificadores de conferencia

### <a name="to-view-the-conference-id"></a>Para ver el Id. de conferencia

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, haga clic en **Usuarios** y seleccione el usuario en la lista de usuarios disponibles.

2. En la parte superior de la página, haga clic en **Editar**.

3. En **Audioconferencia**, mire en **Id. de conferencia**.

    > [!TIP]
    > Puede enviar toda la información de la conferencia al usuario en un correo electrónico que incluya el Id. de conferencia y los números de teléfono de audioconferencia haciendo clic en el vínculo **Enviar información de conferencia por correo electrónico**.
  
**Uso de Windows PowerShell**

Vea la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.
    
  
### <a name="to-reset-the-conference-id"></a>Para restablecer el Id. de conferencia

El Id. de conferencia se puede restablecer para un usuario si, por ejemplo, se le olvida.
  
![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

1. En el panel de navegación izquierdo, haga clic en **Usuarios** y seleccione el usuario en la lista de usuarios disponibles.

2. En la parte superior de la página, haga clic en **Editar**.

3. En **Audioconferencia**, haga clic en **Restablecer Id. de conferencia**.

4. En la ventana **Restablecer Id. de conferencia**, haga clic en **Restablecer**. El Id. de conferencia se creará automáticamente y se enviará un correo electrónico al usuario con el Id. de conferencia nuevo.
  
**Uso de Windows PowerShell**

Vea la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información.


## <a name="what-else-should-you-know"></a>¿Qué más debe saber?

   > [!IMPORTANT]
   >  Una vez que se haya creado el Id. de conferencia nuevo o se haya restablecido el anterior, los autores de llamada no podrán usar el Id. anterior. Tendrá que notificar a los usuarios que deben volver a programar las invitaciones de reunión que ya tienen y comprobar que se haya añadido el nuevo Id. de conferencia a las invitaciones. 
  
    
- El Id. de conferencia tiene que cumplir con el requisito de longitud en dígitos que se haya configurado en el puente de audioconferencia. No se pueden usar caracteres alfabéticos o especiales en los id. de conferencia, solo se pueden usar números.
   
    
## <a name="want-to-know-more-about-windows-powershell"></a>¿Quiere saber más sobre Windows PowerShell?

Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas para hacer. To get started with Windows PowerShell, see these topics:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
    
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar audioconferencia en Microsoft 365 u Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
