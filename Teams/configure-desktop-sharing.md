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
description: Aprenda a configurar una directiva de reuniones que permita a los usuarios compartir sus escritorios en los chats o reuniones de Teams.
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 56ee2c83827c25da5b16cc3f7c2725a3daf815c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121518"
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

    ![Directivas de reuniones seleccionadas](media/configure-desktop-sharing-image1.png)

2. En la página **Directivas de reunión**, seleccione **Agregar**.

    ![El mensaje de directivas de reunión](media/addMeeting.png)

3. Asigne un título único a la directiva y escriba una breve descripción.

4. En **de uso compartido de contenido**, elija **un modo de uso compartido de** Pantalla de la lista desplegable:

   - **Toda la pantalla**: le permite a los usuarios compartir todo el escritorio.
   - **Una sola aplicación**: esto permite a los usuarios limitar el uso compartido de la pantalla a una única aplicación activa.
   - **Deshabilitada**: desactiva el uso compartido de la pantalla.

    ![Las opciones del modo de uso compartido](media/configure-desktop-sharing-image3.png)

  > [!Note]
  > No tiene que habilitar la directiva de llamada para que los usuarios puedan usar el recurso compartido de pantalla desde el chat. Sin embargo, su audio se desactivará hasta lo activen ellos mismos. Además, el usuario que comparte la pantalla puede hacer clic en **Agregar audio** para habilitar el audio. Si la directiva de llamada está deshabilitada, los usuarios no podrán agregar audio a la pantalla compartida desde una sesión de chat.

5. Activar o desactivar la siguiente configuración:

    - **Permitir que un participante ceda o solicite control**: permite a los miembros del equipo ceder o dar el control de la aplicación o el escritorio del presentador.
    - **Permitir a un participante externo ceder o solicitar el control**: esta es una directiva por usuario. Que una organización haya definido esto para un usuario no controla lo que puedan hacer los participantes externos, independientemente de lo que haya configurado el organizador de la reunión. Lo que controla este parámetro es si los participantes externos pueden recibir o solicitar el control de la pantalla que comparten, en función de lo que la persona que comparte haya establecido en las directivas de reuniones de su organización.
    - **Permitir el uso compartido de PowerPoint**: permite a los usuarios crear reuniones que permiten cargar y compartir presentaciones de PowerPoint.
    - **Permitir pizarra**: permite a los usuarios compartir una pizarra.
    - **Permitir notas compartidas**: permite a los usuarios tomar notas compartidas.

6. Haga clic en **Guardar**.

## <a name="use-powershell-to-configure-shared-desktop"></a>Use PowerShell para configurar el escritorio compartido

También puede usar [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) para controlar el uso compartido del escritorio. Ajuste los siguientes parámetros:

- Descripción
- ScreenSharingMode
- AllowPrivateCalling
- AllowParticipantGiveRequestControl
- AllowExternalParticipantGiveRequestControl
- AllowPowerPointSharing
- AllowWhiteboard
- AllowSharedNotes

[Obtenga más información sobre el uso del cmdlet csTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).