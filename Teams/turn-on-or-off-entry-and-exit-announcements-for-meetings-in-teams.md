---
title: Activar o desactivar los anuncios de entrada y salida para reuniones en Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
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
description: El administrador puede obtener información sobre cómo activar o desactivar los anuncios de entrada y salida en una Microsoft Teams reunión.
ms.openlocfilehash: 6be1c6dc86d8088b5ddb54b2141a10172ba13cc5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121338"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a>Activar o desactivar los anuncios de entrada y salida para las reuniones en Microsoft Teams

Al configurar conferencias de audio en Microsoft 365 o Office 365, recibirá un puente de audioconferencia. Un puente de conferencia puede contener uno o varios números de teléfono que los contactos usarán para llamar a una reunión de Microsoft Teams.
  
El puente de conferencia responderá a las llamadas de los usuarios que llamen a una reunión con un teléfono. El puente de conferencia responde a la persona que llama con avisos de voz de un operador automático de conferencia y, luego, según cuál sea su configuración, puede reproducir notificaciones, solicitar a los autores de las llamadas que registren sus nombres y configurar la seguridad del PIN. El PIN se ofrece al organizador de la reunión de Microsoft Teams para que pueda iniciar una reunión si no puede hacerlo con la aplicación de Microsoft Teams. Sin embargo, puede configurarlo para que no se solicite al iniciar una reunión.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>Configurar las opciones para unirse a una reunión

![Un icono que muestra el logotipo de Microsoft Teams](media/teams-logo-30x30.png) **Usando el centro de administración de Microsoft Teams**

Debe ser administrador de servicio de Teams para poder realizar estos cambios. Consulte [Usar los roles de administrador de Teams para administrar Teams](./using-admin-roles.md) para obtener información sobre cómo obtener roles de administrador y permisos.

1. Inicie sesión en el centro de administración.

2. En el panel de navegación izquierdo, vaya a **Reuniones** > **Puentes de conferencia**.

3. En la parte superior de la página **Puentes de conferencia**, haga clic en **Configuración de puente**.

4. En el panel **Configuración de puente**, habilite o deshabilite **Notificaciones de entrada y salida de la reunión**. Esta es la opción seleccionada de forma predeterminada, pero, si la desactiva, los usuarios que ya se hayan unido a la reunión no recibirán ninguna notificación cuando alguien entre en la reunión o la abandone.

5. En **Tipo de anuncio de entrada o salida**, seleccione **Nombres o números de teléfono** o **Tonos**.

   > [!NOTE]
   > De forma predeterminada, los participantes externos no pueden ver los números de teléfono de los participantes marcados. Si desea mantener la privacidad de estos números de teléfono, seleccione **Tonos** de **entrada/salida tipo de anuncio** (esto evita que los Teams lean los números).

6. Si ha elegido **Nombres o números de teléfono**, habilite o deshabilite **Pida a los autores de llamadas que registren su nombre antes de unirse a la reunión**.

7. Haga clic en **Guardar**.

## <a name="want-to-know-more-about-windows-powershell"></a>¿Desea obtener más información sobre Windows PowerShell

Windows PowerShell se centra en la administración de usuarios y en las acciones que se les está permitido o no realizar. Con Windows PowerShell, puede administrar Microsoft 365 o Office 365 un único punto de administración que puede simplificar su trabajo diario cuando tiene varias tareas que hacer. Para empezar con Windows PowerShell, vea estos temas:

- [¿Por qué necesita usar Microsoft 365 o Office 365 PowerShell?](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Las mejores formas de administrar Microsoft 365 o Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Para obtener más información sobre Windows PowerShell, consulte la [referencia de PowerShell para Microsoft Teams](/powershell/module/teams/?view=teams-ps).
  
## <a name="related-topics"></a>Temas relacionados

[Preguntas comunes sobre Audioconferencia](audio-conferencing-common-questions.md)