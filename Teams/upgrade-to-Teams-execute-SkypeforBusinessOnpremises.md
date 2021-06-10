---
title: Actualizar Skype Empresarial local a Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Obtenga información sobre cómo cambiar su organización a Microsoft Teams desde una Skype Empresarial implementación local.
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
ms.openlocfilehash: 0585f0ad829f19334d5a970461f1f3248a107e9d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115558"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Actualizar de una Skype Empresarial local a Teams

![Fases del viaje de actualización, con énfasis en la fase implementación e implementación](media/upgrade-banner-deployment.png "Fases del viaje de actualización, con énfasis en la fase implementación e implementación")

Este artículo forma parte de la fase implementación e implementación del viaje de actualización. Antes de continuar, confirme que ha completado las siguientes actividades:

- [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
- [Ha definido el ámbito del proyecto](./upgrade-define-project-scope.md)
- [Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Elegido el viaje de actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparado el entorno](./upgrade-prepare-environment.md)
- [Preparar la organización](./upgrade-prepare-organization.md)
- [Llevó a cabo un piloto](./pilot-essentials.md)

Siga las instrucciones de este artículo si ha implementado Skype Empresarial o Microsoft Lync local y su organización quiere actualizar a Microsoft Teams de forma selectiva, mediante varios modos de coexistencia, o todo en. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Paso 1: Implementar conectividad híbrida

El requisito previo clave para actualizar los usuarios a Teams es implementar la conectividad híbrida.

Para obtener más información, vea Implementar conectividad [híbrida entre Skype Empresarial Server y Skype Empresarial Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>Paso 2: Implementar el viaje de actualización elegido para su organización

Después de completar la configuración híbrida, puede planear mover los usuarios a Microsoft 365 o Office 365.

Para obtener más información, vea:

- [TeamsUpgradePolicy: administrar la migración y la coexistencia.](upgrade-to-teams-on-prem-tools.md)

- [Mover usuarios locales a Skype Empresarial Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="phone-system-and-teams-upgrade"></a>Sistema telefónico y Teams actualización

La transición de sistemas telefónicos locales a Teams le permitirá aprovechar Sistema telefónico enrutamiento directo ("enrutamiento directo") o los planes de llamadas proporcionados por Microsoft para Microsoft 365 o Office 365.

Si no usa planes de llamadas, debe cambiar la implementación de voz empresarial a Sistema telefónico enrutamiento directo como parte de la actualización a Teams.

Para obtener más información, [vea consideraciones adicionales para Sistema telefónico enrutamiento directo.](./direct-routing-landing-page.md) Si está pensando en usar planes de llamadas, consulte nuestras instrucciones para transferir sus números de teléfono a [Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).