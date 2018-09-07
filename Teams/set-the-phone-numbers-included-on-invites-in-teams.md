---
title: Establecer el teléfono los números incluidos en invitaciones en los equipos de Microsoft
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtener los pasos para crear un número de teléfono predeterminado para los autores de llamadas para unirse a una reunión de los equipos de Microsoft. '
ms.openlocfilehash: 54778aac19d090b4c609da1c5a63da3ba146ae44
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "23857450"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Establecer el teléfono los números incluidos en invitaciones en Microsoft Teams

Conferencias de audio en Office 365 permiten a los usuarios de la organización crear reuniones de Microsoft Teams y, a continuación, permitir a los usuarios para conectarse a las reuniones utilizando un teléfono. En Office 365, tendrá la opción de utilizar un puente de conferencia de audio de Microsoft o un puente de conferencia de audio de terceros que está hospedado en un proveedor de conferencias de audio aprobadas (ACP).
  
Un puente de conferencia le proporciona un conjunto de números de teléfono de acceso telefónico para su organización. Todos ellos se pueden usar para unirse a las reuniones que ha creado un organizador de la reunión, pero puede seleccionar cuáles se incluirá en sus invitaciones de reunión.
  
> [!NOTE]
> Puede haber un máximo de un teléfono de pago y un número de teléfono gratuito en la invitación a la reunión para un organizador de la reunión, pero también hay un vínculo que se encuentra en la parte inferior de cada invitación a la reunión que se abre la lista completa de todos los números de teléfono de acceso telefónico que se pueden usar para unirse a una reunión. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>Establecer o cambiar el número de teléfono de conferencia de audio predeterminada para un usuario o el organizador de la reunión

1. En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

    ![Selección de los usuarios en el Microsoft Teams y Skype para el centro de administración de negocio de muestra](media/teamsselectusers.png)

2. En la parte superior de la página, haga clic en **Editar**.

    ![Haga clic en Editar en los equipos de Microsoft y Skype para el centro de administración de negocio](media/teamsedituser.png)

3. Junto a **Conferencias de Audio**, haga clic en **Editar**. 
    
    ![Haga clic en Editar junto a la conferencia de Audio](media/teamseditaudioconf.png)

4. Use los campos de **número de teléfono de pago** o **número de teléfono gratuito** para escribir los números para el usuario.


> [!IMPORTANT]
> Cuando se cambia la configuración de conferencia de audio de un usuario, las reuniones de Microsoft Teams periódicas y futuras deben actualiza y se envía a los asistentes. 

## <a name="want-to-use-windows-powershell"></a>¿Desea usar Windows PowerShell?

Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obtener más información acerca de Windows PowerShell, vea la [referencia de PowerShell de los equipos de Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obtener más información. 
  
    
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
