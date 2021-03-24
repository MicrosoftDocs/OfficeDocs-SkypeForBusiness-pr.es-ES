---
title: Actualizar la implementación híbrida de Skype Empresarial a Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Obtenga información sobre cómo actualizar su organización a Microsoft Teams desde una implementación híbrida de Skype Empresarial.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 97725e7a9790f47f9789366567981f0167fdd806
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104026"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Actualizar de una implementación híbrida de Skype Empresarial a Teams

![Fases del viaje de actualización, con énfasis en la fase implementación e implementación](media/upgrade-banner-deployment.png "Fases del viaje de actualización, con énfasis en la fase implementación e implementación")

Este artículo forma parte de la fase de implementación e implementación del viaje de actualización. Antes de continuar, confirme que ha completado las siguientes actividades:

- [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
- [Ha definido el ámbito del proyecto](./upgrade-define-project-scope.md)
- [Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Elegido el viaje de actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparado el entorno](./upgrade-prepare-environment.md)
- [Preparar la organización](./upgrade-prepare-organization.md)
- [Llevó a cabo un piloto](./pilot-essentials.md)

Siga las instrucciones de este artículo si ha implementado Skype Empresarial o Microsoft Lync local y lo ha configurado en una implementación híbrida con su organización de Microsoft 365 u Office 365, y su organización quiere actualizar a Teams de forma selectiva (mediante varios modos de coexistencia) o todo en. Para cualquier viaje de actualización, debe mover a los usuarios a Skype Empresarial Online (si aún no están en línea) y, a continuación, asignarles el modo de coexistencia y actualización adecuados.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Paso 1: Mover usuarios a Skype Empresarial Online

Este paso se aplica a los usuarios que se encuentran actualmente en el entorno local. Para obtener más información sobre cómo mover estos usuarios a Skype Empresarial Online, vea Mover usuarios de local [a Skype Empresarial Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Paso 2: Asignar un modo de coexistencia y actualización

Después de mover a los usuarios a Skype Empresarial Online, puede asignarles el modo de coexistencia adecuado en función del viaje de actualización que haya elegido su organización. Para obtener más información, vea [Establecer la configuración de](./setting-your-coexistence-and-upgrade-settings.md) coexistencia y actualización y [TeamsUpgradePolicy: administrar la migración y la coexistencia.](upgrade-to-teams-on-prem-tools.md)

> [!NOTE]
> Con Skype Empresarial Server 2019 y una actualización acumulativa futura de Skype Empresarial Server 2015, podrá realizar el paso 1 (mover usuarios a Skype Empresarial Online) y el paso 2 (actualizar usuarios a Teams) en un solo paso. Después de publicar Skype Empresarial Server 2019, se proporciona más información.

## <a name="phone-system-and-teams-upgrade"></a>Actualización de Sistema telefónico y Teams

Si está cambiando su implementación híbrida de Skype Empresarial a Sistema telefónico con planes de llamadas y Microsoft será su proveedor de red telefónica conmutada (RTC) público y, suponiendo que haya completado la porción de número de teléfono, actualizar los usuarios a Teams pasará automáticamente las llamadas RTC entrantes a Teams.

Si los planes de llamadas no están disponibles o tiene la intención de usar su proveedor de conectividad RTC existente, debe cambiar la implementación de voz empresarial (o la implementación de voz híbrida que usa su implementación local existente o Cloud Connector Edition) a Enrutamiento directo de Microsoft Phone System. Para actualizar los usuarios a Teams, vea las [consideraciones adicionales](./direct-routing-landing-page.md)para enrutamiento directo del sistema telefónico.