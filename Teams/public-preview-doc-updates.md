---
title: Versión preliminar pública para Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: dansteve
search.appverid: MET150
f1.keywords:
- NOCSH
description: Obtenga más información sobre la versión preliminar pública en Microsoft Teams. Pruebe nuevas características y envíe sus comentarios.
appliesto:
- Microsoft Teams
localization_priority: Priority
ms.openlocfilehash: 6a8d677b4acd56e6de5681d40a1e1aa69008a1ad
ms.sourcegitcommit: 6262deaede6f25b17624d7468eff7a2863eeacf7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2021
ms.locfileid: "50043964"
---
# <a name="microsoft-teams-public-preview"></a>Versión preliminar pública en Microsoft Teams

> [!NOTE]
> Es posible que las características incluidas en la versión preliminar no estén completas y experimenten cambios antes de que estén disponibles en la versión pública. Se ofrecen solo para fines de evaluación y exploración.

La versión preliminar pública para Microsoft Teams ofrece acceso anticipado a características no publicadas en Teams. Las versiones preliminares le permiten explorar y probar las características futuras. También agradecemos sus comentarios sobre cualquier característica de la versión preliminar pública. La versión preliminar pública está habilitada por usuario de Teams, por lo que no tiene que preocuparse por si afecta a toda la organización.

Para consultar una lista de elementos disponibles en la versión preliminar pública de Teams, visite [Notas de la versión para el canal actual (versión preliminar) de Office](https://docs.microsoft.com/officeupdates/current-channel-preview).

## <a name="set-the-update-policy"></a>Configure la directiva de actualización

La versión preliminar pública está habilitada de manera individual por cada usuario y la opción para activarla se controla en una directiva de administración. Las directivas de actualización se utilizan para administrar a usuarios de Office y Teams que verán las funciones de prelanzamiento o de versión preliminar en la aplicación de Teams. Puede usar la directiva global (predeterminada para toda la organización) y personalizarla, o bien crear una o varias directivas personalizadas para sus usuarios. La directiva debe asignarse a usuarios específicos porque no sobrescribe la directiva global.

1. Inicie sesión en el Centro de administración.
2. Seleccione **Teams**>**Actualizar directivas**.

   ![Seleccione la opción Actualizar directivas](media/updatePolicies.png)

3. Seleccione **Agregar**.
4. Asigne un nombre a la directiva de actualización, agregue una descripción y active **Mostrar características de versión preliminar**.

También puede establecer la directiva con PowerShell usando el cmdlet de `CsTeamsUpdateManagementPolicy`.

## <a name="enable-public-preview"></a>Habilite la versión preliminar pública

Para habilitar la versión preliminar pública en un escritorio o cliente web, tiene que realizar las siguientes tareas:

1. Seleccione su perfil para mostrar el menú de Teams.
2. Seleccione **Acerca de** → **Versión preliminar pública**.
3. Seleccione **Cambiar a la Versión preliminar pública**.

## <a name="related-topics"></a>Temas relacionados

[Versión preliminar pública para desarrolladores](https://docs.microsoft.com/microsoftteams/platform/resources/dev-preview/developer-preview-intro)

