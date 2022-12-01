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
- chat-teams-channels-revamp
description: Aprenda a usar y administrar las directivas de canal de los equipos de su organización para controlar lo que los usuarios pueden hacer en los equipos y canales.
ms.openlocfilehash: 1223f191550675d5edd7b99a1cf9820fa14c9992
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198562"
---
# <a name="manage-channel-policies-in-microsoft-teams"></a>Administrar directivas de canal en Microsoft Teams

Como administrador, puede usar directivas en Microsoft Teams para controlar lo que los usuarios de su organización pueden hacer en equipos y canales. Por ejemplo, puede establecer si los usuarios pueden crear canales privados o compartidos.

Para administrar las directivas de los equipos, vaya a Directivas de **Teams** > **en el** centro de administración de Microsoft Teams. Puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas. Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada.

Puede editar la directiva global o crear y asignar una directiva personalizada. Después de editar la directiva global o asignar una directiva, es posible que los cambios tarden 24 horas en surtir efecto.

## <a name="channel-policies"></a>Directivas de canal

Las siguientes directivas están disponibles para los canales de equipos:

|Directiva|Descripción|
|:-----|:----------|
|**Crear canales privados**|Cuando **está activado**, los propietarios y miembros del equipo pueden crear canales privados. (Los propietarios de equipos pueden controlar si los miembros pueden crear canales privados en cada equipo).|
|**Crear canales compartidos**|Cuando **está activado**, los propietarios de equipos pueden crear canales compartidos. Las aplicaciones de Teams que están disponibles para su organización también están disponibles en canales compartidos.|
|**Invitar a usuarios externos a canales compartidos**|Cuando **está activada**, los propietarios y los miembros de canales compartidos pueden invitar a participantes externos de organizaciones donde se haya configurado una confianza entre organizaciones. Las directivas de Teams para su organización se aplican a estos canales.|
|**Unirse a canales compartidos externos**|Si **está activada**, los usuarios pueden participar en canales compartidos creados por otras organizaciones donde se haya configurado una confianza entre organizaciones. Las directivas de Teams para la otra organización se aplican a estos canales.|

## <a name="create-a-custom-teams-policy"></a>Crear una directiva de equipos personalizada

1. En el panel de navegación izquierdo del Microsoft centro de administración de Teams, vaya a **Directivas** de **Teams** > .
2. Haga clic en **Agregar**.
3. Escriba un nombre y una descripción para la directiva.

    ![Captura de pantalla de la configuración de directivas de teams.](media/teams-policies.png)
4. Active o desactive la configuración que desee y, a continuación, haga clic en **Guardar**.

5. Haga clic en **Guardar**.

## <a name="edit-a-teams-policy"></a>Editar una directiva de equipos

Puede editar la directiva global o cualquier directiva personalizada que cree.

1. En el panel de navegación izquierdo del Microsoft centro de administración de Teams, vaya a **Directivas** de **Teams** > .
2. Haga clic a la izquierda del nombre de la directiva para seleccionarla y, luego, en **Editar**.
3. Active o desactive la configuración que desee y, a continuación, haga clic en **Guardar**.

## <a name="assign-a-custom-teams-policy-to-users"></a>Asignar una directiva de equipos personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="related-topics"></a>Temas relacionados

[Administrar sitios conectados y sitios de canal de Teams](/SharePoint/teams-connected-sites)

[Canales privados en Teams](private-channels.md)

[Asignar directivas a los usuarios en Teams](policy-assignment-overview.md)

[New-CsTeamsChannelsPolicy](/powershell/module/skype/new-csteamschannelspolicy)
