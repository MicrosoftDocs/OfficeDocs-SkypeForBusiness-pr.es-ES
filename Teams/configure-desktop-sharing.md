---
title: Configure el uso compartido del escritorio en Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
description: Aprenda a configurar una directiva de reunión para permitir que los usuarios compartan sus escritorios en reuniones o chats de Teams.
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: d75e540de7e40206f0b1dd15e26adc62d6f6baa7
ms.sourcegitcommit: d27b97f012d0cb3f1690d3673d50bbaa0caae16f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2020
ms.locfileid: "47652482"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a>Configure el uso compartido del escritorio en Microsoft Teams
============================================

Al compartir el escritorio, los usuarios pueden presentar una pantalla o aplicación durante una reunión o un chat. Los administradores pueden configurar la pantalla compartiendo en Microsoft Teams para que los usuarios puedan compartir una pantalla completa, una aplicación o un archivo. Puede permitir que los usuarios puedan dar control, permitir el uso compartido de PowerPoint, agregar una pizarra y permitir notas compartidas. Asimismo, puede configurar si los usuarios anónimos o externos pueden solicitar el control de la pantalla compartida. Los participantes externos en reuniones de Teams se pueden categorizar de la siguiente forma:

- Usuario anónimo
- Usuarios invitados
- Usuario B2B
- Usuario federado

Para configurar el uso compartido de la pantalla, debe crear una nueva Directiva de reuniones y, a continuación, asignarla a los usuarios que quiera administrar.

**En el [centro de administración de Microsoft Teams](https://admin.teams.microsoft.com/)**

1. Seleccione **Reuniones** > **Directivas de reunión**.

    ![Directivas de reunión seleccionadas](media/configure-desktop-sharing-image1.png)

2. En la **página Directivas de** reunión, seleccione **Agregar.**

    ![Mensaje directivas de reunión](media/addMeeting.png)

3. Asigne un título único a la directiva y escriba una breve descripción.

4. En **de uso compartido de contenido**, elija **un modo de uso compartido de** Pantalla de la lista desplegable:

   - **Toda la pantalla**: le permite a los usuarios compartir todo el escritorio.
   - **Una sola aplicación**: esto permite a los usuarios limitar el uso compartido de la pantalla a una única aplicación activa.
   - **Deshabilitada**: desactiva el uso compartido de la pantalla.

    ![Las opciones del modo de uso compartido](media/configure-desktop-sharing-image3.png)

  > [!Note]
  > No es momento de habilitar la directiva de llamadas para que los usuarios puedan usar el uso compartido de la pantalla del chat. Sin embargo, el audio se desactivará hasta que se reanmuten. Además, el usuario que comparte la pantalla puede hacer clic **en Agregar audio** para habilitar el audio. Si la directiva de llamadas está deshabilitada, los usuarios no podrán agregar audio al recurso compartido de pantalla desde una sesión de chat.

5. Activar o desactivar la siguiente configuración:

    - **Permitir que un participante dé o solicite el control:** permite a los miembros del equipo ceder o solicitar el control del escritorio o la aplicación del moderador.
    - **Permitir que un participante externo dé o solicite el control:** esta es una directiva por usuario. Que una organización haya definido esto para un usuario no controla lo que puedan hacer los participantes externos, independientemente de lo que haya configurado el organizador de la reunión. Lo que controla este parámetro es si los participantes externos pueden recibir o solicitar el control de la pantalla que comparten, en función de lo que la persona que comparte haya establecido en las directivas de reuniones de su organización.
    - **Permitir el uso compartido de PowerPoint**: permite a los usuarios crear reuniones que permiten cargar y compartir presentaciones de PowerPoint.
    - **Permitir pizarra**: permite a los usuarios compartir una pizarra.
    - **Permitir notas compartidas**: permite a los usuarios tomar notas compartidas.

6. Haga clic en **Guardar**.

## <a name="use-powershell-to-configure-shared-desktop"></a>Use PowerShell para configurar el escritorio compartido

También puede usar [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) para controlar el uso compartido del escritorio. Ajuste los siguientes parámetros:

- Descripción
- ScreenSharingMode
- AllowPrivateCalling
- AllowParticipantGiveRequestControl
- AllowExternalParticipantGiveRequestControl
- AllowPowerPointSharing
- AllowWhiteboard
- AllowSharedNotes

[Obtenga más información sobre el uso del cmdlet csTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).
