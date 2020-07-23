---
title: Establecer los números de teléfono incluidos en las invitaciones
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
- seo-marvel-mar2020
description: Siga estos pasos para crear un número de teléfono predeterminado para que las personas que llamen se unan a una reunión de Microsoft Teams.
ms.openlocfilehash: 7dd59950403543074d8428d35270ab963ca824e3
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372189"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Establecer los números de teléfono incluidos en las invitaciones en Microsoft Teams

La Conferencia de audio en Microsoft 365 y Office 365 permite a los usuarios de su organización crear reuniones de Microsoft Teams y, a continuación, permitir a los usuarios que llamen a esas reuniones con un teléfono.
  
Un puente de conferencia le ofrece un conjunto de números de teléfono de acceso telefónico local para su organización. Todas ellas se pueden usar para unirse a las reuniones que ha creado el organizador de la reunión, pero puede seleccionar cuáles se incluirán en sus invitaciones a reuniones.
  
> [!NOTE]
> Puede haber un máximo de un número de teléfono de pago y un número de teléfono gratuito en la invitación a la reunión para un organizador de la reunión, pero también hay un vínculo en la parte inferior de cada invitación a la reunión que abre la lista completa de todos los números de teléfono de acceso telefónico local que se pueden usar para unirse a una reunión.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a>Asignación inicial de números de teléfono que se incluyen en las invitaciones a reuniones para nuevos usuarios

Los números de teléfono que se incluyen en las invitaciones de reunión de los usuarios habilitados para las conferencias de audio se definen mediante el número de teléfono de conferencia predeterminado y la configuración de usuario gratuito de las conferencias de conferencia predeterminada. Cada opción especifica qué número de pago y gratuito se incluirá en la invitación a la reunión de un usuario dado. Como se mencionó anteriormente, cada invitación a una reunión contiene un número de teléfono, un número opcional gratuito y un vínculo que abre la lista completa de todos los números de teléfono de acceso telefónico local que se pueden usar para unirse a una reunión determinada.

Para un nuevo usuario, los números de teléfono de conferencia predeterminados se asignan en función de la ubicación de uso establecida en el centro de administración de Microsoft 365 del usuario cuando el usuario está habilitado para el servicio audioconferencia. Si hay un número de pago en el puente de conferencia que coincide con el país del usuario, ese número se asignará automáticamente como el número de pago predeterminado del usuario. Si no hay ninguno, el número que se define como número de teléfono predeterminado del puente de conferencia se asignará como número de teléfono de pago predeterminado del usuario.  

Una vez que el usuario está habilitado para el servicio de audioconferencia, los números de teléfono de pago y gratuitos, que el administrador del inquilino puede cambiar de forma predeterminada en cualquier momento.

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>Establecer o cambiar el número de teléfono de conferencia de audio predeterminado para un organizador de la reunión o un usuario

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

Para realizar estos cambios, debe ser administrador del servicio de Teams. Consulte [usar los roles de administrador de Teams para administrar los equipos](https://docs.microsoft.com/microsoftteams/using-admin-roles) para obtener información sobre cómo obtener roles y permisos de administrador.

1. Inicie sesión en el centro de administración de Microsoft Teams.

2. En el navegación de la izquierda, haga clic en **usuarios**.

    ![Se muestra la selección de usuarios en el centro de administración de Microsoft Teams](media/Admin-users.png)

3. Haga clic en el nombre de usuario de la lista de usuarios disponibles.

4. Junto a **audioconferencia**, haga clic en **Editar**.

    ![Haga clic en Editar junto a audioconferencia](media/teams-set-phone-numbers-on-invites-image3.png)

5. Use los campos **número de pago** o **número gratuito** para introducir los números del usuario.

> [!IMPORTANT]
> Al cambiar la configuración de la Conferencia de audio de un usuario, las reuniones periódicas y futuras de Microsoft Teams deben actualizarse y enviarse a los asistentes.

## <a name="want-to-use-windows-powershell"></a>¿Quiere usar Windows PowerShell?

Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas para hacer. To get started with Windows PowerShell, see these topics:

- [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar audioconferencia en Microsoft 365 u Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[Cambiar los números de teléfono de su puente de Audioconferencia](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
