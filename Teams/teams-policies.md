---
title: Administrar directivas de equipos en Microsoft Teams
author: cichur
ms.author: v-cichur
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
description: Obtenga información sobre cómo usar y administrar directivas de equipos en su organización para controlar lo que los usuarios pueden hacer en equipos y canales.
ms.openlocfilehash: 81541c08ac963f0bcef18ba589b2341915c20d5d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094210"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a>Administrar directivas de equipos en Microsoft Teams

Como administrador, puede usar directivas de equipos en Microsoft Teams controlar lo que los usuarios de su organización pueden hacer en equipos y canales. Por ejemplo, puede establecer si los usuarios pueden crear canales privados.

Para administrar directivas de equipos, **vaya a Teams** Teams directivas  >  **en** el centro Microsoft Teams administración. Puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas. Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada.

Puede editar la directiva global o crear y asignar una directiva personalizada. Después de editar la directiva global o asignar una directiva, los cambios pueden tardar unas horas en tener efecto.

## <a name="create-a-custom-teams-policy"></a>Crear una directiva de equipos personalizada

1. En el panel de navegación izquierdo del Microsoft Teams de administración, vaya **a Teams**  >  **Teams directivas.**
2. Haga clic en **Agregar**.
3. Escriba un nombre y una descripción para la directiva.

    ![Captura de pantalla de la configuración de directiva de teams](media/teams-policies.png)
4. Activa o desactiva Crear canales **privados,** <a name="createchannels"></a> dependiendo de si quieres permitir que los usuarios creen canales privados.

5. Haga clic en **Guardar**.

## <a name="edit-a-teams-policy"></a>Editar una directiva de equipos

Puede editar la directiva global o las directivas personalizadas que cree.

1. En el panel de navegación izquierdo del Microsoft Teams de administración, vaya **a Teams**  >  **Teams directivas.**
2. Haga clic a la izquierda del nombre de la directiva para seleccionarla y, luego, en **Editar**.
3. Active o desactive la configuración que desee y, a continuación, haga clic en **Guardar.**

## <a name="assign-a-custom-teams-policy-to-users"></a>Asignar una directiva de equipos personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Temas relacionados

[Canales privados en Teams](private-channels.md)

[Asignar directivas a los usuarios en Teams](assign-policies.md)

[New-CsTeamsChannelsPolicy](/powershell/module/skype/new-csteamschannelspolicy?view=skype-ps)