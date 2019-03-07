---
title: 'Actualizar a Teams desde una implementación local o híbrida de Skype Empresarial: Microsoft Teams'
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Consideraciones para la actualización a los equipos de un Skype para la implementación híbrida o local de empresa.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 38a9c3bd2e9649ea657a559f1c6d41aab86edd56
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464767"
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

# <a name="upgrade-to-teams-from-a-skype-for-business-hybrid-or-on-premises-deployment"></a>Actualizar a los equipos desde una Skype para la implementación híbrida o local de empresa

Siga las instrucciones de este artículo si ha implementado Skype para la empresa o Microsoft Lync local y su organización desea actualizar a los equipos de forma selectiva: mediante el uso de varios modos de coexistencia, o todo. El primer paso es configurar conectividad híbrida con el inquilino de Office 365 y, a continuación, mover los usuarios a Skype para profesionales en línea y asígneles la coexistencia adecuada y modo de actualización. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Paso 1: Implementar conectividad híbrida 

El requisito previo clave para actualizar a los usuarios a los equipos consiste en implementar conectividad híbrida. Esto podría implicar la implementación nueva conectividad externa para su Skype existente para la implementación empresarial o Lync, o simplemente configurar una relación de híbrida con el inquilino de Office 365. 

Para obtener más información, consulte [Deploy la conectividad híbrida entre Skype para Business Server y Skype para profesionales en línea](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).

## <a name="step-2-move-users-to-skype-for-business-online"></a>Paso 2: Mover usuarios a Skype para profesionales en línea 

Una vez completada la configuración híbrida, mover usuarios a Skype para profesionales en línea. 

Para obtener más información, vea [mover usuarios de local a Skype para profesionales en línea](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online). 

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a>Paso 3: Asignar una coexistencia y modo de actualización

Una vez que haya movido a los usuarios a Skype para profesionales en línea, se puede asignar el modo de coexistencia apropiado según el viaje de actualización que ha elegido la organización. Para obtener más información, vea [establecer la coexistencia y la configuración de actualizaciones](https://aka.ms/SkypeToTeams-SetCoexistence) y [TeamsUpgradePolicy: administración de migración y coexistencia](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

> [!NOTE]
> Skype para Business Server 2019 y una futura actualización acumulativa de Skype para Business Server 2015, podrá realizar el paso 2 (migración de usuarios a Skype para profesionales en línea) y el paso 3 (actualización a los equipos de los usuarios) en un solo paso. Obtener más información, se proporcionará después del lanzamiento de Skype para Business Server 2019.

## <a name="phone-system-and-teams-upgrade"></a>Sistema telefónico y los equipos de actualización

Si está migrando su Skype para implementación híbrida de negocio al sistema de teléfono con planes de llamada y Microsoft será su proveedor de telefónica conmutada (RTC) de la red, y suponiendo que haya completado el número de teléfono trasladar — actualizar a los usuarios a Los equipos automáticamente va a realizar la transición de RTC entrante a los equipos de llamada.

Si al llamar a los planes de no está disponible, debe realizar la transición de su implementación de enterprise voice para enrutamiento directo de Microsoft teléfono del sistema. Para actualizar a los usuarios a los equipos, consulte las [Consideraciones adicionales para el enrutamiento directo de teléfono del sistema](2-envision-make-my-service-decisions-direct-routing.md).
