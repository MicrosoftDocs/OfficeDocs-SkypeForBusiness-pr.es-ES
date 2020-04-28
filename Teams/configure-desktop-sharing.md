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
description: Aprenda a configurar una directiva de reunión para permitir que los usuarios compartan sus escritorios en chats o reuniones de Teams.
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 955a642d2a2309ccbaf9f9d6280170a93a9179ae
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905902"
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

    - **Permitir que un participante pueda ceder o solicitar el control** : permite a los miembros del equipo ceder o solicitar el control del escritorio o de la aplicación del moderador.
    - **Permitir que un participante externo pueda ceder o solicitar el control** : permite a los invitados y a los usuarios externos (federados) ceder o solicitar el control del escritorio o de la aplicación del moderador.
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

