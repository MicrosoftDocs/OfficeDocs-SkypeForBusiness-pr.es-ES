---
title: Configure el uso compartido del escritorio en Microsoft Teams
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
description: Configurar una directiva de reuniones para permitir que los usuarios compartan los escritorios en Teams de chats o reuniones
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 366aaeb4f48670ae04d4b53d21196ef2d9e81fb4
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825548"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a>Configure el uso compartido del escritorio en Microsoft Teams
============================================

Al compartir el escritorio, los usuarios pueden presentar una pantalla o aplicación durante una reunión o un chat. Los administradores pueden configurar la pantalla compartiendo en Microsoft Teams para que los usuarios puedan compartir una pantalla completa, una aplicación o un archivo. Puede permitir que los usuarios puedan dar control, permitir el uso compartido de PowerPoint, agregar una pizarra y permitir notas compartidas. Asimismo, puede configurar si los usuarios anónimos o externos pueden solicitar el control de la pantalla compartida.

Para configurar el uso compartido de la pantalla, debe crear una nueva Directiva de reuniones y, a continuación, asignarla a los usuarios que quiera administrar.

**En el [centro de administración de Microsoft Teams](https://admin.teams.microsoft.com/)**

1. Seleccione **Reuniones** > **Directivas de reunión**.

    ![Captura de pantalla que muestra las directivas de reuniones seleccionadas](media/configure-desktop-sharing-image1.png)

2. En la página **Directivas de reunión**, seleccione **Nueva Directiva**.

    ![Captura de pantalla que muestra el mensaje directivas de reunión](media/configure-desktop-sharing-image2.png)

3. Asigne un título único a la directiva y escriba una breve descripción.

4. En **de uso compartido de contenido**, elija **un modo de uso compartido de **Pantalla de la lista desplegable:

   - **Toda la pantalla**: le permite a los usuarios compartir todo el escritorio.
   - **Una sola aplicación**: esto permite a los usuarios limitar el uso compartido de la pantalla a una única aplicación activa.
   - **Deshabilitada**: desactiva el uso compartido de la pantalla.

    ![Captura de pantalla que muestra las opciones del modo de uso compartido](media/configure-desktop-sharing-image3.png)

5. Activar o desactivar la siguiente configuración:

    - **Permitir un participante que de o** solicite un control: permite a los miembros del equipo dar control de la aplicación o el escritorio del presentador.
    - **Permitir a un participante dar o** solicitar un control: permite a los miembros del equipo dar control de la aplicación o el escritorio del moderador.
    - **Permitir el uso compartido de PowerPoint**: permite a los usuarios crear reuniones que permiten cargar y compartir presentaciones de PowerPoint.
    - **Permitir pizarra**: permite a los usuarios compartir una pizarra.
    - **Permitir notas compartidas**: permite a los usuarios tomar notas compartidas.

6. Haga clic en **Guardar **.

## <a name="use-powershell-to-configure-shared-desktop"></a>Use PowerShell para configurar el escritorio compartido

También puede usar [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) para controlar el uso compartido del escritorio. Ajuste los siguientes parámetros:

- Descripción
- ScreenSharingMode
- AllowParticipantGiveRequestControl
- AllowExternalParticipantGiveRequestControl
- AllowPowerPointSharing
- AllowWhiteboard
- AllowSharedNotes

[Obtenga más información sobre el uso del cmdlet csTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).

