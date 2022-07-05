---
title: Actualizar Skype Empresarial local a Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Obtenga información sobre cómo hacer la transición de su organización a Microsoft Teams desde una implementación Skype Empresarial local.
ms.localizationpriority: medium
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
ms.openlocfilehash: 7b06134a0fe0f72e8dc9c01b4faa85c67a6063f3
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615446"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a>Actualizar de una implementación local de Skype Empresarial a Teams

![Fases del recorrido de la actualización, con énfasis en la fase de implementación e implementación.](media/upgrade-banner-deployment.png "Fases del recorrido de la actualización, con énfasis en la fase de implementación e implementación")

Este artículo forma parte de la fase de implementación e implementación del recorrido de la actualización. Antes de continuar, confirma que has completado las siguientes actividades:

- [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
- [Ha definido el ámbito del proyecto](./upgrade-define-project-scope.md)
- [Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Elige tu viaje de actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparado para su entorno](./upgrade-prepare-environment.md)
- [Preparado para su organización](./upgrade-prepare-organization.md)
- [Se realizó un piloto](./pilot-essentials.md)

Siga las instrucciones de este artículo si ha implementado Skype Empresarial o Microsoft Lync local y su organización quiere actualizar a Microsoft Teams de forma selectiva,usando varios modos de coexistencia o todo en. 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a>Paso 1: Implementar la conectividad híbrida

El requisito previo clave para actualizar los usuarios a Teams es implementar la conectividad híbrida.

Para obtener más información, vea [Implementar la conectividad híbrida entre Skype Empresarial Server y Skype Empresarial Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a>Paso 2: Implementar el recorrido de actualización elegido para su organización

Después de completar la configuración híbrida, puede planear mover los usuarios a Microsoft 365 o Office 365.

Para obtener más información, vea:

- [TeamsUpgradePolicy: gestión de la migración y coexistencia](upgrade-to-teams-on-prem-tools.md).

- [Mover usuarios de local a Skype Empresarial En línea](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="phone-system-and-teams-upgrade"></a>Actualización de Sistema telefónico y Teams

La transición de sistemas telefónicos locales a Teams le permitirá aprovechar las ventajas del enrutamiento directo del sistema telefónico ("enrutamiento directo") o los planes de llamadas proporcionados por Microsoft para Microsoft 365 o Office 365.

Si no usa planes de llamadas, debe realizar la transición de la implementación de voz empresarial a Enrutamiento directo del sistema telefónico como parte de la actualización a Teams.

Para obtener más información, consulta [consideraciones adicionales sobre el enrutamiento directo del sistema telefónico](./direct-routing-landing-page.md). Si tiene previsto usar planes de llamadas, consulte nuestra guía para [transferir sus números de teléfono a Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).