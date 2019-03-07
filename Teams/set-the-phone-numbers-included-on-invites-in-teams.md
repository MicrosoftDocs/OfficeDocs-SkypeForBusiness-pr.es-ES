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
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Obtener los pasos para crear un número de teléfono predeterminado para los autores de llamadas para unirse a una reunión de Microsoft Teams. '
ms.openlocfilehash: 3e6aae2c01962a4cd3c704cded1e284dc2975d28
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464247"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Establecer los números de teléfono incluidos en las invitaciones en Microsoft Teams

Conferencias de audio en Office 365 permiten a los usuarios de la organización crear reuniones de Microsoft Teams y, a continuación, permitir a los usuarios para conectarse a las reuniones utilizando un teléfono.
  
Un puente de conferencia le proporciona un conjunto de números de teléfono de acceso telefónico para su organización. Todos ellos se pueden usar para unirse a las reuniones que ha creado un organizador de la reunión, pero puede seleccionar cuáles se incluirá en sus invitaciones de reunión.
  
> [!NOTE]
> Puede haber un máximo de un teléfono de pago y un número de teléfono gratuito en la invitación a la reunión para un organizador de la reunión, pero también hay un vínculo que se encuentra en la parte inferior de cada invitación a la reunión que se abre la lista completa de todos los números de teléfono de acceso telefónico que se pueden usar para unirse a una reunión. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a>Asignación inicial de números de teléfono que se incluyen en la reunión invitaciones para nuevos usuarios

Se invita los números de teléfono que se incluyan en la reunión de los usuarios habilitados para conferencias de Audio se definen mediante el número de teléfono de pago de conferencia de forma predeterminada y la configuración de la conferencia teléfono gratuito número del usuario predeterminado. Cada opción de configuración especifica qué números de pago y el número de teléfono gratuito se incluirá en la invitación a la reunión de un usuario determinado. Como se mencionó anteriormente, cada invitación a la reunión contiene el número de teléfono de uno pago, un número de teléfono gratuito opcional y un vínculo que se abre la lista completa de todos los números de teléfono de acceso telefónico que se pueden usar para unirse a una reunión determinada.

Para un nuevo usuario, se asignan los números de teléfono de pago de conferencia predeterminados según el país en el que se establece en el perfil de Office 365 del usuario cuando el usuario está habilitado para el servicio de conferencia de Audio. Si no hay un número de teléfono de pago en el puente de conferencia que coincide con el país del usuario, ese número se asignará automáticamente como el número de teléfono de pago predeterminado del usuario. Si no hay, se asignará el número al que se ha definido como el número de teléfono de pago predeterminado del puente de conferencia como el número de teléfono de pago predeterminado del usuario.  

Una vez que el usuario está habilitado para el servicio de conferencia de Audio, el pago de forma predeterminada y los números de teléfono gratuito del usuario pueden cambiarse por el Administrador de inquilinos de sus valores iniciales en cualquier momento.

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>Establecer o cambiar el número de teléfono de conferencia de audio predeterminada para un usuario o el organizador de la reunión

![los equipos-logotipo-30x30.png](media/teams-logo-30x30.png) **desde el centro de administración de equipos de Microsoft**

1. En el panel de navegación izquierdo, haga clic en **usuarios**y, a continuación, seleccione el usuario de la lista de usuarios disponibles.

    ![Muestra la selección de los usuarios en el centro de administración de Microsoft Teams](media/teams-set-phone-numbers-on-invites-image1.png)

2. En la parte superior de la página, haga clic en **Editar**.

    ![Haga clic en Editar en el centro de administración de Microsoft Teams](media/teams-set-phone-numbers-on-invites-image2.png)

3. Junto a **Conferencias de Audio**, haga clic en **Editar**. 
    
    ![Haga clic en Editar junto a la conferencia de Audio](media/teams-set-phone-numbers-on-invites-image3.png)

4. Use los campos de **número de teléfono de pago** o **número de teléfono gratuito** para escribir los números para el usuario.


> [!IMPORTANT]
> Cuando se cambia la configuración de conferencia de audio de un usuario, las reuniones de Microsoft Teams periódicas y futuras deben actualiza y se envía a los asistentes. 

## <a name="want-to-use-windows-powershell"></a>¿Desea usar Windows PowerShell?

Windows PowerShell se usa para administrar los usuarios y las acciones que pueden o no realizar. Con Windows PowerShell, puede administrar Office 365 con un único punto de administración que puede simplificar el trabajo diario cuando tenga que realizar varias tareas. Para empezar a usar Windows PowerShell, vea estos temas:
    
  - [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Las mejores formas de administrar Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps). 
  
    
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
