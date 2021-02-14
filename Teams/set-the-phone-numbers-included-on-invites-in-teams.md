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
description: Siga estos pasos para crear un número de teléfono predeterminado para que los autores de llamadas se unan a una reunión de Microsoft Teams.
ms.openlocfilehash: 7dd59950403543074d8428d35270ab963ca824e3
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372189"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a>Establecer los números de teléfono incluidos en las invitaciones en Microsoft Teams

Las audioconferencias en Microsoft 365 y Office 365 permiten a los usuarios de su organización crear reuniones de Microsoft Teams y, a continuación, permiten que los usuarios llamen a esas reuniones con un teléfono.
  
Un puente de conferencias le proporciona un conjunto de números de teléfono de acceso telefónico local para su organización. Todos ellos se pueden usar para unirse a las reuniones que haya creado un organizador de reuniones, pero puede seleccionar los que se incluirán en las invitaciones a la reunión.
  
> [!NOTE]
> Puede haber un máximo de un número de pago y un número gratuito en la invitación a la reunión para el organizador de la reunión, pero también hay un vínculo en la parte inferior de cada invitación de reunión que abre la lista completa de los números de acceso telefónico local que se pueden usar para unirse a una reunión.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a>Asignación inicial de números de teléfono que se incluyen en las invitaciones de reunión para nuevos usuarios

Los números de teléfono que se incluyen en las invitaciones de reunión de los usuarios habilitados para Audioconferencia se definen por el número de teléfono de pago de las conferencias y por la configuración predeterminada del usuario de número de teléfono gratuito para conferencias. Cada opción especifica qué número gratuito y de pago se incluirá en la invitación a la reunión de un usuario determinado. Como se indicó anteriormente, cada invitación a una reunión contiene un número de pago, un número gratuito opcional y un vínculo que abre la lista completa de todos los números de acceso telefónico que se pueden usar para unirse a una reunión determinada.

Para un nuevo usuario, los números de pago de conferencia predeterminados se asignan según la ubicación de uso establecida en el centro de administración de Microsoft 365 del usuario cuando el usuario está habilitado para el servicio de Audioconferencia. Si hay un número de pago en el puente de conferencia que coincida con el país del usuario, ese número se asignará automáticamente como el número de pago predeterminado del usuario. Si no lo hay, el número que se define como el número de pago predeterminado del puente de conferencia se asignará como el número de pago predeterminado del usuario.  

Una vez que el usuario está habilitado para el servicio de Audioconferencia, el administrador de inquilinos puede cambiar los números de teléfono gratuitos y de pago predeterminados del usuario de sus valores iniciales en cualquier momento.

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a>Establecer o cambiar el número de teléfono de audioconferencia predeterminado para un organizador o usuario de la reunión

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

Debe ser administrador del servicio de Teams para realizar estos cambios. Consulte [Usar los roles de administrador de Teams para administrar Teams y](https://docs.microsoft.com/microsoftteams/using-admin-roles) obtener información sobre cómo obtener permisos y roles de administrador.

1. Inicie sesión en el Centro de administración de Microsoft Teams.

2. En el panel de navegación izquierdo, haga clic en **Usuarios.**

    ![Muestra la selección de usuarios en el Centro de administración de Microsoft Teams](media/Admin-users.png)

3. Haga clic en el nombre de usuario de la lista de usuarios disponibles.

4. Junto a **Audioconferencia,** haga clic en **Editar.**

    ![Haga clic en Editar junto a Audioconferencia](media/teams-set-phone-numbers-on-invites-image3.png)

5. Use los **campos Número de pago** o Número **gratuito** para introducir los números del usuario.

> [!IMPORTANT]
> Cuando cambia la configuración de audioconferencia de un usuario, las reuniones periódicas y futuras de Microsoft Teams deben actualizarse y enviarse a los asistentes.

## <a name="want-to-use-windows-powershell"></a>¿Desea usar Windows PowerShell

Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 u Office 365 con un único punto de administración que puede simplificar su trabajo diario cuando tenga que realizar varias tareas. To get started with Windows PowerShell, see these topics:

- [Seis motivos por los que posiblemente quiera usar Windows PowerShell para administrar Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

- [Las mejores formas de administrar Microsoft 365 u Office 365 con Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Temas relacionados

[Probar o comprar Audioconferencia en Microsoft 365 u Office 365](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[Cambiar los números de teléfono de su puente de Audioconferencia](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
