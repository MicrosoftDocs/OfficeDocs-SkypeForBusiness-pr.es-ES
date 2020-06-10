---
title: Actualizar Skype Empresarial local a Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Aprenda a realizar una transición de su organización a Microsoft Teams desde una implementación local de Skype empresarial.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 34502fe9883c98179a6b2e23cd8360ae823c1853
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "44666022"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Actualizar desde una implementación local de Skype empresarial a teams

![Etapas del viaje de actualización, con énfasis en la fase de implementación e implementación](media/upgrade-banner-deployment.png "Etapas del viaje de actualización, con énfasis en la fase de implementación e implementación")

Este artículo forma parte de la fase de implementación e implementación de su viaje de actualización. Antes de continuar, confirme que ha completado las siguientes actividades:

- [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
- [Ha definido el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)
- [Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Eligió la actualización del viaje](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparado su entorno](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Preparado para su organización](https://aka.ms/SkypeToTeams-UserReadiness)
- [Ha realizado una prueba piloto](https://aka.ms/SkypeToTeams-Pilot)

Siga las instrucciones de este artículo si ha implementado Skype empresarial o Microsoft Lync local y su organización quiere actualizar a Microsoft Teams de forma selectiva, mediante el uso de varios modos de coexistencia. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Paso 1: implementar conectividad híbrida

El requisito previo de actualización de los usuarios a teams es implementar la conectividad híbrida.

Para obtener más información, consulte [implementar conectividad híbrida entre Skype empresarial Server y Skype empresarial online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity) .

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>Paso 2: implementar el viaje de actualización elegido para su organización

Una vez completada la configuración híbrida, puede planificar mover los usuarios a Microsoft 365 u Office 365.

Para obtener más información, vea:

- [TeamsUpgradePolicy: administración de la migración y la coexistencia](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

- [Mover usuarios de local a Skype empresarial online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="phone-system-and-teams-upgrade"></a>Actualización de equipos y sistemas telefónicos

La transición de sistemas telefónicos locales a equipos le permitirá aprovechar las ventajas del enrutamiento directo del sistema telefónico ("enrutamiento directo") o los planes de llamadas proporcionados por Microsoft para Microsoft 365 u Office 365.

Si no usa planes de llamadas, debe realizar la transición de la implementación de telefonía IP empresarial al enrutamiento del sistema telefónico directo como parte de la actualización a teams.

Para obtener más información, consulte [consideraciones adicionales para el enrutamiento directo de un sistema telefónico](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing). Si tiene pensado usar planes de llamadas, consulte nuestras instrucciones para [transferir los números de teléfono a teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).