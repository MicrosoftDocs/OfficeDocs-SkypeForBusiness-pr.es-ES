---
title: Actualizar Skype empresarial local a Microsoft Teams | Implementar | Lync
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Consideraciones para actualizar a teams desde una implementación local de Skype empresarial.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1b41de8f54eb0e2a09e7e3700b25cba1e5564f0a
ms.sourcegitcommit: a47f0841b9a14ede65171a817ecb7ebc72f209e5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2019
ms.locfileid: "34288191"
---
![Etapas del viaje de actualización, con énfasis en la fase de implementación e] implementación (media/upgrade-banner-deployment.png "Etapas del viaje de actualización, con énfasis en la fase de implementación e") implementación

Este artículo forma parte de la fase de implementación e implementación de su viaje de actualización. Antes de continuar, confirme que ha completado las siguientes actividades:

- [Inventar a los participantes del proyecto](upgrade-enlist-stakeholders.md)
- [Definió el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)
- [La coexistencia y la interoperabilidad de Skype para empresas y equipos](https://aka.ms/SkypeToTeams-Coexist)
- [Eligió la actualización del viaje](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparado su entorno](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Preparado para su organización](https://aka.ms/SkypeToTeams-UserReadiness)
- [Ha realizado una prueba piloto](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Actualizar desde una implementación local de Skype empresarial a teams

Siga las instrucciones de este artículo si ha implementado Skype empresarial o Microsoft Lync local y su organización quiere actualizar a Microsoft Teams de forma selectiva, mediante el uso de varios modos de coexistencia. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Paso 1: implementar conectividad híbrida

El requisito previo de actualización de los usuarios a teams es implementar la conectividad híbrida.

Para obtener más información, consulte [implementar conectividad híbrida entre Skype empresarial Server y Skype empresarial online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity) .

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>Paso 2: implementar el viaje de actualización elegido para su organización

Una vez completada la configuración híbrida, puede planear mover los usuarios a Office 365.

Para obtener más información, vea:

- [TeamsUpgradePolicy: administración de la migración y](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)la coexistencia.

- [Mover usuarios de local a Skype empresarial online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="phone-system-and-teams-upgrade"></a>Actualización de equipos y sistemas telefónicos

La transición de sistemas telefónicos locales a equipos le permitirá aprovechar las ventajas del enrutamiento directo de sistema telefónico ("enrutamiento directo") o los planes de llamadas proporcionadas por Microsoft para Office 365.

Si no usa planes de llamadas en Office 365, necesitará realizar la transición de la implementación de telefonía IP empresarial al enrutamiento de sistema telefónico directo como parte de la actualización a teams.

Para obtener más información, consulte [consideraciones adicionales para el enrutamiento directo de un sistema telefónico](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing). Si tiene pensado usar planes de llamadas en Office 365, consulte nuestras instrucciones para [transferir sus números de teléfono a office 365](https://docs.microsoft.com/microsoftteams/transfer-phone-numbers-to-office-365).