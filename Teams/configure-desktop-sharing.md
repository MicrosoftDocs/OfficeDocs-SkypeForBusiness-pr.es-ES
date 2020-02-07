---
title: Configurar Compartir escritorio en Microsoft Teams
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
description: Configurar una directiva de reunión para permitir que los usuarios compartan sus escritorios en chats o reuniones de Teams
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 366aaeb4f48670ae04d4b53d21196ef2d9e81fb4
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825548"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a>Configurar Compartir escritorio en Microsoft Teams
============================================

El uso compartido de escritorio permite a los usuarios presentar una pantalla o una aplicación durante una reunión o un chat. Los administradores pueden configurar la pantalla compartida en Microsoft Teams para permitir que los usuarios compartan una pantalla completa, una aplicación o un archivo. Puede permitir a los usuarios asignar o solicitar el control, permitir el uso compartido de PowerPoint, agregar una pizarra y permitir notas compartidas. También puede configurar si usuarios anónimos o externos pueden solicitar el control de la pantalla compartida.

Para configurar la pantalla compartida, debe crear una nueva Directiva de reuniones y, a continuación, asignarla a los usuarios que desee administrar.

**En el [centro de administración de Microsoft Teams](https://admin.teams.microsoft.com/)**

1. Seleccione **** > **políticas**de reuniones de reuniones.

    ![Captura de pantalla que muestra las directivas de reunión seleccionadas](media/configure-desktop-sharing-image1.png)

2. En la página directivas de la **reunión** , seleccione **nueva Directiva**.

    ![Captura de pantalla que muestra el mensaje directivas de la reunión](media/configure-desktop-sharing-image2.png)

3. Asigne un título único a la Directiva y escriba una descripción breve.

4. En **uso compartido de contenido**, seleccione un **modo de uso compartido de pantalla** de la lista desplegable:

   - **Pantalla completa** : permite que los usuarios compartan todo su escritorio.
   - Una **sola aplicación** : permite que los usuarios limiten la pantalla compartida a una sola aplicación activa.
   - **Deshabilitado** : desactiva la pantalla compartida.

    ![Captura de pantalla que muestra las opciones del modo de uso compartido](media/configure-desktop-sharing-image3.png)

5. Activar o desactivar la siguiente configuración:

    - **Permitir que un participante pueda ceder o solicitar el control** : permite a los miembros del equipo ceder o solicitar el control del escritorio o de la aplicación del moderador.
    - **Permitir que un participante externo pueda ceder o solicitar el control** : permite a los invitados y a los usuarios externos (federados) ceder o solicitar el control del escritorio o de la aplicación del moderador.
    - **Permitir el uso compartido de PowerPoint** : permite a los usuarios crear reuniones que permiten que las presentaciones de PowerPoint se carguen y compartan.
    - **Permitir pizarra** : permite a los usuarios compartir una pizarra.
    - **Permitir notas compartidas** : permite a los usuarios tomar notas compartidas.

6. Haga clic en **Guardar **.

## <a name="use-powershell-to-configure-shared-desktop"></a>Usar PowerShell para configurar el escritorio compartido

También puede usar el cmdlet [set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) para controlar el uso compartido del escritorio. Establezca los siguientes parámetros:

- Descripción
- ScreenSharingMode
- AllowParticipantGiveRequestControl
- AllowExternalParticipantGiveRequestControl
- AllowPowerPointSharing
- AllowWhiteboard
- AllowSharedNotes

[Más información sobre cómo usar el cmdlet csTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).

