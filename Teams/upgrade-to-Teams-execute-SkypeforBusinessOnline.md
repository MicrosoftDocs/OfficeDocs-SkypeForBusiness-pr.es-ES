---
title: Actualización de Skype para la empresa en línea a equipos - equipos de Microsoft
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Consideraciones para actualizar a los equipos de Skype para profesionales en línea
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: fabcd88a0444a01f950064ade0c49dfef50400e1
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2018
ms.locfileid: "25013574"
---
![Fases de la actualización viaje, con especial hincapié en la implementación y la fase de implementación] (media/upgrade-banner-deployment.png "Fases de la actualización viaje, con especial hincapié en la implementación y la fase de implementación")

En este artículo forma parte de la fase de implementación y la implementación de su viaje por la actualización. Antes de continuar, confirme que ha realizado las siguientes actividades:

-   [Los participantes en el proyecto de alta](upgrade-enlist-stakeholders.md)
-   [Define el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)
-   [Entiende coexistencia e interoperabilidad de Skype para profesionales y los equipos](https://aka.ms/SkypeToTeams-Coexist)
-   [Elegido su viaje por la actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Preparar el entorno](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [Preparar la organización](https://aka.ms/SkypeToTeams-UserReadiness)
-   [Realiza una prueba piloto](https://aka.ms/SkypeToTeams-Pilot)


# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Actualización de Skype para la empresa en línea a los equipos

Siga las instrucciones de este artículo si totalmente implementado Skype para profesionales en línea y desea actualizar los usuarios de Skype para la empresa a los equipos. Puede actualizar a los usuarios de forma selectiva o en función de la actualización, todo viaje que su organización ha decidido, mediante la asignación de la coexistencia adecuada y el modo de actualización a los usuarios.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Asignar el modo de actualización y coexistencia

Actualización a los equipos puede realizarse mediante la asignación el modo de TeamsOnly de TeamsUpgradePolicy, que se puede realizar mediante el uso de Microsoft Teams & Skype para el centro de administración de negocio o un Skype para la sesión remota de Windows Powershell de negocio.

Para obtener más información, vea [establecer la coexistencia y la configuración de actualizaciones](https://aka.ms/SkypeToTeams-SetCoexistence) y [TeamsUpgradePolicy: administración de migración y coexistencia](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

## <a name="phone-system-and-teams-upgrade"></a>Sistema telefónico y los equipos de actualización

Si su Skype para la implementación empresarial Online incluye sistema telefónico con planes de llamada y Microsoft es su proveedor de telefónica conmutada (RTC), actualizar a los usuarios a los equipos automáticamente transición RTC entrante a los equipos de llamada.

Si su Skype para la implementación empresarial Online incluye sistema telefónico con la edición de conector en la nube, consulte las [Consideraciones adicionales para el enrutamiento directo de teléfono del sistema](2-envision-make-my-service-decisions-direct-routing.md).