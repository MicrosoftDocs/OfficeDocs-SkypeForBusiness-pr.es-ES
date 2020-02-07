---
title: Establecer los números de teléfono incluidos en las invitaciones en Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
description: 'Siga los pasos para crear un número de teléfono predeterminado para que las personas que llaman participen en una reunión de Microsoft Teams. '
ms.openlocfilehash: b5a43b0987160b87ac4a6e25b10ae6d850612ac1
ms.sourcegitcommit: 8e2fa7b744d0a174b699ae7298d4688b971eeff3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2020
ms.locfileid: "41845241"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Establecer los números de teléfono incluidos en las invitaciones en Microsoft Teams

Las conferencias de audio en Office 365 permiten a los usuarios de su organización crear reuniones de Microsoft Teams y, a continuación, permitir a los usuarios que llamen a esas reuniones con un teléfono.
  
Un puente de conferencia le ofrece un conjunto de números de teléfono de acceso telefónico local para su organización. Todas ellas se pueden usar para unirse a las reuniones que ha creado el organizador de la reunión, pero puede seleccionar cuáles se incluirán en sus invitaciones a reuniones.
  
> [!NOTE]
> Puede haber un máximo de un número de teléfono de pago y un número de teléfono gratuito en la invitación a la reunión para un organizador de la reunión, pero también hay un vínculo en la parte inferior de cada invitación a la reunión que abre la lista completa de todos los números de teléfono de acceso telefónico local que se pueden usar para unirse a una reunión. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a>Asignación inicial de números de teléfono que se incluyen en las invitaciones a reuniones para nuevos usuarios

Los números de teléfono que se incluyen en las invitaciones de reunión de los usuarios habilitados para las conferencias de audio se definen mediante el número de teléfono de conferencia predeterminado y la configuración de usuario gratuito de las conferencias de conferencia predeterminada. Cada opción especifica qué número de pago y gratuito se incluirá en la invitación a la reunión de un usuario dado. Como se mencionó anteriormente, cada invitación a una reunión contiene un número de teléfono, un número opcional gratuito y un vínculo que abre la lista completa de todos los números de teléfono de acceso telefónico local que se pueden usar para unirse a una reunión determinada.

Para un nuevo usuario, los números de teléfono de conferencia predeterminados se asignan en función del país establecido en el perfil de Office 365 del usuario cuando el usuario está habilitado para el servicio audioconferencia. Si hay un número de pago en el puente de conferencia que coincide con el país del usuario, ese número se asignará automáticamente como el número de pago predeterminado del usuario. Si no hay ninguno, el número que se define como número de teléfono predeterminado del puente de conferencia se asignará como número de teléfono de pago predeterminado del usuario.  

Una vez que el usuario está habilitado para el servicio de audioconferencia, los números de teléfono de pago y gratuitos, que el administrador del inquilino puede cambiar de forma predeterminada en cualquier momento.

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>Establecer o cambiar el número de teléfono de conferencia de audio predeterminado para un organizador de la reunión o un usuario

![Un icono que muestra el logotipo](media/teams-logo-30x30.png) de Microsoft Teams **con el centro de administración de Microsoft Teams**

1. En el navegación de la izquierda, haga clic en **usuarios**.

    ![Se muestra la selección de usuarios en el centro de administración de Microsoft Teams](media/teams-set-phone-numbers-on-invites-image1.png)

2. Haga clic en el nombre de usuario de la lista de usuarios disponibles.

3. Junto a **audioconferencia**, haga clic en **Editar**. 
    
    ![Haga clic en Editar junto a audioconferencia](media/teams-set-phone-numbers-on-invites-image3.png)

4. Use los campos **número de pago** o **número gratuito** para introducir los números del usuario.


> [!IMPORTANT]
> Al cambiar la configuración de la Conferencia de audio de un usuario, las reuniones periódicas y futuras de Microsoft Teams deben actualizarse y enviarse a los asistentes. 

## <a name="want-to-use-windows-powershell"></a>¿Desea usar Windows PowerShell?

Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps). 
  
    
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[Cambiar los números de teléfono de su puente de Audioconferencia](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
