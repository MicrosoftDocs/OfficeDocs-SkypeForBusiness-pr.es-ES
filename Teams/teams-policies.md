---
title: Administrar directivas de Teams en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo usar y administrar directivas de Teams en su organización para controlar qué pueden hacer los usuarios en Teams y en los canales.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: 9ed0bd3aadcde76835bb3d435429785ceaf562a2
ms.sourcegitcommit: 60b859dcb8ac727a38bf28cdb63ff762e7338af8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/30/2020
ms.locfileid: "44938149"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>Administrar directivas de Teams en Microsoft Teams

Como administrador, puede usar las directivas de Teams en Microsoft Teams para controlar lo que los usuarios de su organización pueden hacer en Teams y en los canales. Por ejemplo, puede establecer si los usuarios podrán detectar equipos privados en los resultados de búsqueda y en la galería de equipos y si los usuarios pueden crear canales privados.

Para administrar las directivas de Teams, vaya a **Teams**  >  **Policies** en el centro de administración de Microsoft Teams. Puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas. Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada.

Puede editar la directiva global o crear y asignar una directiva personalizada. Después de modificar la directiva global o asignar una directiva, los cambios pueden demorar algunas horas en surtir efecto.

## <a name="create-a-custom-teams-policy"></a>Crear una directiva de Teams personalizada

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, **vaya a**  >  **directivas de Teams**Teams.
2. Haga clic en **Agregar**.
3. Escriba un nombre y una descripción para la directiva.

    ![Captura de pantalla de la configuración de directiva de Teams](media/teams-policies.png)
4. Elija la configuración que desee:

- **Descubrir equipos privados** (en la versión preliminar privada<a name="discoverteams"> </a> ): Active esta configuración para permitir que los usuarios detecten equipos privados en los resultados de búsqueda y en la galería de equipos.
- **Crear canales privados**: <a name="createchannels"> </a>Active esta opción para permitir a los usuarios crear canales privados.

5. Haga clic en **Guardar **.

## <a name="edit-a-teams-policy"></a>Editar una directiva de Teams

Puede editar la directiva global o cualquier directiva personalizada que cree.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, **vaya a**  >  **directivas de Teams**Teams.
2. Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva y, a continuación, haga clic en **Editar**.
3. Active o desactive la configuración que desee y, a continuación, haga clic en **Guardar**.

## <a name="assign-a-custom-teams-policy-to-users"></a>Asignar una directiva de Teams personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Temas relacionados

[Administrar la detección de equipos privados en Teams](manage-discovery-of-private-teams.md)

[Canales privados en Teams](private-channels.md)

[Asignar directivas a los usuarios de Teams](assign-policies.md)
