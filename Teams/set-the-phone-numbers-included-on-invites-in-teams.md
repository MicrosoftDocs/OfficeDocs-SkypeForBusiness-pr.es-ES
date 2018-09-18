---
title: Establecer los números de teléfono incluidos en las invitaciones en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
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
description: 'Vea los pasos que hay que seguir para crear un número de teléfono predeterminado con el que los autores de llamada puedan unirse a una reunión de Microsoft Teams. '
ms.openlocfilehash: eddab0762b679dba08dd9981d6ae61a1403ebf47
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23882963"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Establecer los números de teléfono incluidos en las invitaciones en Microsoft Teams

Con Audioconferencia de Office 365, los usuarios de su organización pueden crear reuniones de Microsoft Teams y permitir que los usuarios accedan por teléfono a la reunión con un teléfono. En Office 365, tiene la opción de usar un puente de audioconferencia de Microsoft o usar un puente de audioconferencia de terceros que esté hospedado por un proveedor de servicios de audioconferencia (ACP) aprobado.
  
Un puente de conferencia ofrece un conjunto de números de teléfono de acceso telefónico local para su organización. Todos ellos se pueden usar para unirse a las reuniones que cree un organizador de reuniones, pero puede seleccionar cuáles se incluirán en las invitaciones.
  
> [!NOTE]
> En la invitación para un organizador de reuniones, puede haber un máximo de un número de teléfono de pago y uno gratuito, aunque también habrá un vínculo situado en la parte inferior de cada invitación con el que se abre una lista de números de teléfono de acceso telefónico local que se pueden usar para unirse a una reunión. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>Establecer o cambiar el número de teléfono de audioconferencia predeterminado para un usuario o un organizar de reunión

1. En el panel de navegación izquierdo, haga clic en **Usuarios** y seleccione el usuario en la lista de usuarios disponibles.

    ![Muestra la selección de Usuarios en el Centro de administración de Skype Empresarial y Microsoft Teams](media/teamsselectusers.png)

2. En la parte superior de la página, haga clic en **Editar**.

    ![Haga clic en Editar en el Centro de administración de Skype Empresarial y Microsoft Teams](media/teamsedituser.png)

3. Junto a **Audioconferencia**, haga clic en **Editar**. 
    
    ![Haga clic en Editar junto a Audioconferencia](media/teamseditaudioconf.png)

4. Use los campos **Número de pago** o **Número gratuito** para introducir los números para el usuario.


> [!IMPORTANT]
> Cuando se cambia la configuración de audioconferencias de un usuario, también se tienen que actualizar las reuniones periódicas y futuras de Microsoft Teams y enviarlas a los asistentes. 

## <a name="want-to-use-windows-powershell"></a>¿Quiere usar Windows PowerShell?

Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps). 
  
    
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
