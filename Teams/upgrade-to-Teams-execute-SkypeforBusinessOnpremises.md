---
title: Actualizar Skype Empresarial local a Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Obtenga información sobre cómo realizar la transición de su organización a Microsoft Teams desde una implementación local de Skype Empresarial.
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
ms.openlocfilehash: 90542f680c1d3992f5f318bfedad8a12470d282b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820950"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Actualizar desde una implementación local de Skype Empresarial a Teams

![Fases del viaje de actualización, con énfasis en la fase Implementación e Implementación](media/upgrade-banner-deployment.png "Fases del viaje de actualización, con énfasis en la fase Implementación e Implementación")

Este artículo forma parte de la fase de implementación e implementación del viaje de actualización. Antes de continuar, confirma que has completado las siguientes actividades:

- [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
- [Ha definido el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)
- [Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Ha elegido el viaje de actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparado tu entorno](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Ha preparado tu organización](https://aka.ms/SkypeToTeams-UserReadiness)
- [Se realizó un piloto](https://aka.ms/SkypeToTeams-Pilot)

Siga las instrucciones de este artículo si ha implementado Skype Empresarial o Microsoft Lync local y su organización desea actualizar a Microsoft Teams ya sea de forma selectiva (usando varios modos de coexistencia) o todo en todo el contenido. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Paso 1: Implementar conectividad híbrida

El requisito previo clave para actualizar los usuarios a Teams es implementar la conectividad híbrida.

Para obtener más información, vea [Implementar conectividad híbrida entre Skype Empresarial Server y Skype Empresarial Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>Paso 2: Implementar el camino de actualización elegido para su organización

Después de completar la configuración híbrida, puede planear mover los usuarios a Microsoft 365 u Office 365.

Para obtener más información, vea:

- [TeamsUpgradePolicy: administrar la migración y coexistencia.](upgrade-to-teams-on-prem-tools.md)

- [Mueva usuarios locales a Skype Empresarial Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="phone-system-and-teams-upgrade"></a>Actualización de Sistema telefónico y Teams

La transición de sistemas telefónicos locales a Teams le permitirá aprovechar las ventajas del enrutamiento directo de sistema telefónico ("enrutamiento directo") o de los planes de llamadas proporcionados por Microsoft para Microsoft 365 u Office 365.

Si no usa planes de llamadas, deberá realizar la transición de la implementación de voz empresarial al enrutamiento directo de Sistema telefónico como parte de la actualización a Teams.

Para obtener más información, vea [consideraciones adicionales para el enrutamiento directo de sistema telefónico.](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing) Si está pensando en usar planes de llamadas, consulte nuestras instrucciones para [transferir sus números de teléfono a Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)