---
title: Actualizar Skype Empresarial implementación híbrida a Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Obtenga información sobre cómo actualizar su organización a Microsoft Teams desde una implementación Skype Empresarial híbrida.
ms.localizationpriority: medium
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
ms.openlocfilehash: 4ea8db9f53b891002cf7fbe1f5282051e7aca7ea
ms.sourcegitcommit: a6f4c459b9c8154814a8a5b098bde1e374348c99
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/05/2022
ms.locfileid: "66615606"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Actualizar de una implementación híbrida Skype Empresarial a Teams

![Fases del recorrido de la actualización, con énfasis en la fase de implementación e implementación.](media/upgrade-banner-deployment.png "Fases del recorrido de la actualización, con énfasis en la fase de implementación e implementación")

Este artículo forma parte de la fase de implementación e implementación del recorrido de la actualización. Antes de continuar, confirma que has completado las siguientes actividades:

- [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
- [Ha definido el ámbito del proyecto](./upgrade-define-project-scope.md)
- [Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Elige tu viaje de actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparado para su entorno](./upgrade-prepare-environment.md)
- [Preparado para su organización](./upgrade-prepare-organization.md)
- [Se realizó un piloto](./pilot-essentials.md)

Siga las instrucciones de este artículo si ha implementado Skype Empresarial o Microsoft Lync local y la ha configurado en una implementación híbrida con Su organización de Microsoft 365 o Office 365, y su organización quiere actualizar a Teams de forma selectiva(usando varios modos de coexistencia) o todo en. Para cualquier viaje de actualización, debe mover los usuarios a Skype Empresarial Online (si aún no están alojados en línea) y, a continuación, asignarles el modo de coexistencia y actualización adecuado.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Paso 1: Mover usuarios a Skype Empresarial En línea

Este paso se aplica a los usuarios que actualmente están alojados en local. Para obtener más información sobre cómo mover estos usuarios a Skype Empresarial Online, vea [Mover usuarios de local a Skype Empresarial en línea](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Paso 2: Asignar un modo de coexistencia y actualización

Después de mover los usuarios a Skype Empresarial Online, puede asignarles el modo de coexistencia adecuado en función del recorrido de actualización que haya elegido su organización. Para obtener más información, consulte [Configuración de la coexistencia y la actualización](./setting-your-coexistence-and-upgrade-settings.md) y [TeamsUpgradePolicy: administración de la migración y coexistencia](upgrade-to-teams-on-prem-tools.md).

> [!NOTE]
> Con Skype Empresarial Server 2019 y una futura actualización acumulativa de Skype Empresarial Server 2015, podrá realizar el paso 1 (mover usuarios a Skype Empresarial Online) y el paso 2 (actualizar usuarios a Teams) en un solo paso. Se proporcionará más información después de Skype Empresarial Server 2019.

## <a name="phone-system-and-teams-upgrade"></a>Actualización de Sistema telefónico y Teams

Si está cambiando su Skype Empresarial implementación híbrida a Sistema telefónico con planes de llamadas y Microsoft será su proveedor de red telefónica conmutada (RTC) pública y suponiendo que haya completado la portabilidad de números de teléfono, la actualización de los usuarios a Teams cambiará automáticamente las llamadas RTC entrantes a Teams.

Si los planes de llamadas no están disponibles o su intención es usar el proveedor de conectividad RTC existente, debe realizar la transición de la implementación de voz empresarial (o la implementación de voz híbrida que usa la implementación local existente o Cloud Connector Edition) al enrutamiento directo del sistema de Microsoft Phone. Para actualizar los usuarios a Teams, consulte las [consideraciones adicionales sobre el enrutamiento directo del sistema telefónico](./direct-routing-landing-page.md).