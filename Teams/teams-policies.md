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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
description: Obtenga información sobre cómo usar y administrar directivas de Teams en su organización para controlar qué pueden hacer los usuarios en Teams y en los canales.
ms.openlocfilehash: 0b4664c36f24a057a7c8237823b7eafaad8ea6ba
ms.sourcegitcommit: 44bd56f67b1ad85ef8c21bb30d5b0d47e5a80339
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/06/2021
ms.locfileid: "49772030"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>Administrar directivas de Teams en Microsoft Teams

Como administrador, puede usar las directivas de Teams en Microsoft Teams para controlar lo que los usuarios de su organización pueden hacer en Teams y en los canales. Por ejemplo, puede establecer si los usuarios pueden crear canales privados.

Para administrar las directivas de Teams, vaya a **Teams**  >  **Policies** en el centro de administración de Microsoft Teams. Puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas. Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada.

Puede editar la directiva global o crear y asignar una directiva personalizada. Después de modificar la directiva global o asignar una directiva, los cambios pueden demorar algunas horas en surtir efecto.

## <a name="create-a-custom-teams-policy"></a>Crear una directiva de Teams personalizada

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, **vaya a**  >  **directivas de Teams** Teams.
2. Haga clic en **Agregar**.
3. Escriba un nombre y una descripción para la directiva.

    ![Captura de pantalla de la configuración de directiva de Teams](media/teams-policies.png)
4. Active o desactive la opción **crear canales privados**, <a name="createchannels"></a> en función de si desea permitir que los usuarios creen canales privados.

5. Haga clic en **Guardar**.

## <a name="edit-a-teams-policy"></a>Editar una directiva de Teams

Puede editar la directiva global o cualquier directiva personalizada que cree.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, **vaya a**  >  **directivas de Teams** Teams.
2. Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva y, a continuación, haga clic en **Editar**.
3. Active o desactive la configuración que desee y, a continuación, haga clic en **Guardar**.

## <a name="assign-a-custom-teams-policy-to-users"></a>Asignar una directiva de Teams personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Temas relacionados

[Canales privados en Teams](private-channels.md)

[Asignar directivas a los usuarios en Teams](assign-policies.md)

[Nuevo: CsTeamsChannelsPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)
