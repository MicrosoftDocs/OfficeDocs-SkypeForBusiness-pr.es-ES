---
title: Actualización de Skype para su implementación híbrida empresarial en Microsoft Teams | RTC
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Consideraciones para la actualización a los equipos de un Skype para implementación híbrida de negocio.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: c78c5b519997c125dc1902021acabe664ea03047
ms.sourcegitcommit: 716d39077784417c3545a91e501ae26ff56ebdf4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2019
ms.locfileid: "29349578"
---
![Fases de la actualización viaje, con especial hincapié en la implementación y la fase de implementación] (media/upgrade-banner-deployment.png "Fases de la actualización viaje, con especial hincapié en la implementación y la fase de implementación")

En este artículo forma parte de la fase de implementación y la implementación de su viaje por la actualización. Antes de continuar, confirme que ha realizado las siguientes actividades:

- [Los participantes en el proyecto de alta](upgrade-enlist-stakeholders.md)
- [Define el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)
- [Entiende coexistencia e interoperabilidad de Skype para profesionales y los equipos](https://aka.ms/SkypeToTeams-Coexist)
- [Elegido su viaje por la actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparar el entorno](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Preparar la organización](https://aka.ms/SkypeToTeams-UserReadiness)
- [Realiza una prueba piloto](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Actualizar desde un Skype para implementación híbrida de negocio a los equipos

Siga las instrucciones de este artículo si ha implementado Skype para la empresa o Microsoft Lync local configurado en una implementación híbrida con el inquilino de Office 365 y su organización desea actualizar a los equipos de forma selectiva: mediante el uso de varios modos de coexistencia, o todo. Para cualquier viaje de actualización, debe mover los usuarios a Skype para profesionales en línea (si ya no están alojados en línea) y a continuación, asignar la coexistencia adecuada y el modo de actualización.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Paso 1: Mover usuarios a Skype para profesionales en línea

En este paso se aplica a los usuarios que están actualmente asignados local. Para obtener más información sobre cómo mover estos usuarios a Skype para profesionales en línea, consulte [mover usuarios de local - a Skype para profesionales en línea](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Paso 2: Asignar una coexistencia y modo de actualización

Una vez que haya movido a los usuarios a Skype para profesionales en línea, se puede asignar el modo de coexistencia apropiado según el viaje de actualización que ha elegido la organización. Para obtener más información, vea [establecer la coexistencia y la configuración de actualizaciones](https://aka.ms/SkypeToTeams-SetCoexistence) y [TeamsUpgradePolicy: administración de migración y coexistencia](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

> [!NOTE]
> Skype para Business Server 2019 y una futura actualización acumulativa de Skype para Business Server 2015, podrá realizar el paso 1 (mover los usuarios a Skype para profesionales en línea) y el paso 2 (actualización a los equipos de los usuarios) en un solo paso. Obtener más información, se proporcionará después del lanzamiento de Skype para Business Server 2019.

## <a name="phone-system-and-teams-upgrade"></a>Sistema telefónico y los equipos de actualización

Si está migrando su Skype para implementación híbrida de negocio al sistema de teléfono con planes de llamada y Microsoft será su proveedor de telefónica conmutada (RTC) de la red, y suponiendo que haya completado el número de teléfono trasladar — actualizar a los usuarios a Los equipos automáticamente va a realizar la transición de RTC entrante a los equipos de llamada.

Si al llamar a los planes de no está disponible o piensa usar el proveedor de conectividad RTC existente, es necesario realizar la transición de su implementación de enterprise voice: implementación de voz híbrida que usa la existente local o en la implementación o en la nube conector Edition — a Enrutamiento directo de sistema telefónico de Microsoft. Para actualizar a los usuarios a los equipos, consulte las [Consideraciones adicionales para el enrutamiento directo de teléfono del sistema](2-envision-make-my-service-decisions-direct-routing.md).
