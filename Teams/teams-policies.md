---
title: Administrar directivas de canal en Microsoft Teams
author: MikePlumleyMSFT
ms.author: mikeplum
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
ms.localizationpriority: medium
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
description: Obtenga información sobre cómo usar y administrar directivas de canal de equipos en su organización para controlar lo que los usuarios pueden hacer en equipos y canales.
ms.openlocfilehash: 5acac362485b1004e1db61229c437810fdbcbc6d
ms.sourcegitcommit: fcac607fb4ad342a0936527f848e04c85f153ba5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2022
ms.locfileid: "63711784"
---
# <a name="manage-channel-policies-in-microsoft-teams"></a>Administrar directivas de canal en Microsoft Teams

Como administrador, puede usar directivas en Microsoft Teams controlar lo que los usuarios de su organización pueden hacer en equipos y canales. Por ejemplo, puede establecer si los usuarios pueden crear canales privados o compartidos.

Para administrar directivas de equipos, **vaya a Teams** >  **Teams directivas en** el centro Microsoft Teams administración. Puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas. Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada.

Puede editar la directiva global o crear y asignar una directiva personalizada. Después de editar la directiva global o asignar una directiva, los cambios pueden tardar 24 horas en tener efecto.

## <a name="channel-policies"></a>Directivas de canal

Las siguientes directivas están disponibles para los canales de teams:

|Directiva|Descripción|
|:-----|:----------|
|**Crear canales privados**|Cuando **está en**, los propietarios y miembros del equipo pueden crear canales privados. (Los propietarios del equipo pueden controlar si los miembros pueden crear canales privados en cada equipo).|
|**Crear canales compartidos**|Cuando **está en**, los propietarios de equipos pueden crear canales compartidos. Teams aplicaciones disponibles para su organización también están disponibles en canales compartidos.|
|**Invitar a usuarios externos a canales compartidos**|Cuando **está activo**, los propietarios y los miembros de los canales compartidos pueden invitar a participantes externos de organizaciones en las que se haya configurado una confianza entre organizaciones. Teams directivas de su organización se aplican a estos canales.|
|**Unirse a canales compartidos externos**|Cuando **está en**, los usuarios pueden participar en canales compartidos creados por otras organizaciones donde se ha configurado una confianza entre organizaciones. Teams directivas de la otra organización se aplican a estos canales.|

## <a name="create-a-custom-teams-policy"></a>Crear una directiva de equipos personalizada

1. En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a **Teams** >  **Teams directivas**.
2. Haga clic en **Agregar**.
3. Escriba un nombre y una descripción para la directiva.

    ![Captura de pantalla de la configuración de directiva de teams.](media/teams-policies.png)
4. Active o desactive la configuración que desee y, a continuación, haga clic en **Guardar**.

5. Haga clic en **Guardar**.

## <a name="edit-a-teams-policy"></a>Editar una directiva de equipos

Puede editar la directiva global o las directivas personalizadas que cree.

1. En el panel de navegación izquierdo del Microsoft Teams de administración, vaya a **Teams** >  **Teams directivas**.
2. Haga clic a la izquierda del nombre de la directiva para seleccionarla y, luego, en **Editar**.
3. Active o desactive la configuración que desee y, a continuación, haga clic en **Guardar**.

## <a name="assign-a-custom-teams-policy-to-users"></a>Asignar una directiva de equipos personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Temas relacionados

[Administrar Teams sitios conectados y sitios de canal](/SharePoint/teams-connected-sites)

[Canales privados en Teams](private-channels.md)

[Asignar directivas a los usuarios en Teams](policy-assignment-overview.md)

[New-CsTeamsChannelsPolicy](/powershell/module/skype/new-csteamschannelspolicy)
