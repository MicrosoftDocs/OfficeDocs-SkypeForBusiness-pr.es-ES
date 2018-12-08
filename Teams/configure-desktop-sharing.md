---
title: Configuración de uso compartido de escritorio en Microsoft Teams
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 12/07/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Configurar una directiva de reunión para permitir a los usuarios compartir sus escritorios en chats de los equipos o las reuniones
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 422d5fb3a19dad2e14e0cdf54a532b0afc6eed67
ms.sourcegitcommit: ea6ee8ce28e82fcd7c07554c3428ae242d6f04da
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/07/2018
ms.locfileid: "27202516"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a>Configuración de uso compartido de escritorio en Microsoft Teams
============================================

Uso compartido de escritorio permite a los usuarios presentar una pantalla o una aplicación durante una reunión o conversación. Los administradores pueden configurar el uso compartido en Microsoft Teams para permitir a los usuarios compartir una pantalla completa, una aplicación o un archivo de pantalla. Puede permitir a los usuarios conceder o solicitar el control, permitir el uso compartido de PowerPoint, agregar una pizarra y permitir notas compartidas. También puede configurar si los usuarios anónimos o externos pueden solicitar el control de la pantalla compartida.

Para configurar el uso compartido de la pantalla, crear una nueva directiva de reuniones y, a continuación, se asigna a los usuarios que desea administrar.

En los equipos de Microsoft & Skype para el centro de administración de negocio:

1. Seleccione **las reuniones** > **las directivas de reunión**.

    ![Seleccione las directivas de reunión](media/configure-desktop-sharing-image1.png)

2. En la página de **directivas de reunión** , seleccione **nueva directiva**.

    ![Seleccione nueva directiva](media/configure-desktop-sharing-image2.png)

3. Asigne un título único a la directiva y escriba una descripción breve.

4. En el **uso compartido de contenido**, elija un **modo de uso compartido de pantalla** de la lista desplegable:

   - **Pantalla completa** – permite a los usuarios compartir su escritorio completo.
   - **Única aplicación** – permite a los usuarios límite pantalla de uso compartido en una única aplicación activa.
   - **Deshabilitado** : desactiva el uso compartido de la pantalla.

    ![Elija una modo de uso compartido de pantalla](media/configure-desktop-sharing-image3.png)

5. Activar o desactivar la los valores siguientes:

    - A **Permitir que un participante dar o solicitar el control** – permite a los miembros del equipo de dar o solicitar el control del escritorio del moderador o la aplicación.
    - **Permitir que un participante externo a proporcionar o solicitar el control** – permite a los invitados y usuarios (federados) externos concesión o solicitar el control del escritorio del moderador o la aplicación.
    - El **uso compartido de PowerPoint permitir** - permite a los usuarios crear reuniones que permiten presentaciones de PowerPoint cargar y compartir.
    - **Permitir Pizarra** – permite a los usuarios compartir una pizarra.
    - **Permitir notas compartidas** – permite a los usuarios tomar notas compartidas.

6. Haga clic en **Guardar**.

## <a name="use-powershell-to-configure-shared-desktop"></a>Uso de PowerShell para configurar el escritorio compartido

También puede usar el cmdlet [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) para controlar el uso compartido de escritorio. Establezca los siguientes parámetros:

- Descripción
- ScreenSharingMode
- AllowParticipantGiveRequestControl
- AllowExternalParticipantGiveRequestControl
- AllowPowerPointSharing
- AllowWhiteboard
- AllowSharedNotes

[Más información sobre cómo usar el cmdlet csTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).

