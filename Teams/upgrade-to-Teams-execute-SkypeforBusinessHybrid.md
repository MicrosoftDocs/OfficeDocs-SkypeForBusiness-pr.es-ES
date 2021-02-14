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
ms.openlocfilehash: 67bb6c10bb8cc5f37d332459d8e147f4f626497d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802350"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Actualizar desde una implementación híbrida de Skype Empresarial a Teams

![Fases del viaje de actualización, con énfasis en la fase Implementación e Implementación](media/upgrade-banner-deployment.png "Fases del viaje de actualización, con énfasis en la fase Implementación e Implementación")

Este artículo forma parte de la fase de implementación e implementación del viaje de actualización. Antes de continuar, confirma que has completado las siguientes actividades:

- [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
- [Ha definido el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)
- [Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Ha elegido el viaje de actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparado tu entorno](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Ha preparado tu organización](https://aka.ms/SkypeToTeams-UserReadiness)
- [Se realizó un piloto](https://aka.ms/SkypeToTeams-Pilot)

Siga las instrucciones de este artículo si ha implementado Skype Empresarial o Microsoft Lync local y lo ha configurado en una implementación híbrida con su organización de Microsoft 365 u Office 365 y su organización desea actualizar a Teams de forma selectiva (usando varios modos de coexistencia) o todo en él. Para ambos viajes de actualización, debe mover los usuarios a Skype Empresarial Online (si aún no están en línea) y asignarles el modo de coexistencia y actualización adecuados.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Paso 1: Mover usuarios a Skype Empresarial Online

Este paso se aplica a los usuarios que están actualmente homed on-premises. Para obtener más información sobre cómo mover estos usuarios a Skype Empresarial Online, vea Mover usuarios de una implementación local a [Skype Empresarial Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Paso 2: Asignar un modo de coexistencia y actualización

Después de mover los usuarios a Skype Empresarial Online, puede asignarles el modo de coexistencia adecuado en función del camino de actualización que haya elegido su organización. Para obtener más información, vea [Configurar la coexistencia](https://aka.ms/SkypeToTeams-SetCoexistence) y la configuración de actualización y [TeamsUpgradePolicy: administrar la migración y coexistencia.](upgrade-to-teams-on-prem-tools.md)

> [!NOTE]
> Con Skype Empresarial Server 2019 y una actualización acumulativa futura de Skype Empresarial Server 2015, podrá realizar los pasos 1 (mover usuarios a Skype Empresarial Online) y el paso 2 (actualizar usuarios a Teams) en un mismo paso. Después de la lanzamiento de Skype Empresarial Server 2019, se le dará más información.

## <a name="phone-system-and-teams-upgrade"></a>Actualización de Sistema telefónico y Teams

Si está cambiando su implementación híbrida de Skype Empresarial a Sistema telefónico con planes de llamadas y Microsoft será su proveedor de red telefónica conmutada (RTC) pública, y suponiendo que ha completado la porización de números de teléfono, al actualizar los usuarios a Teams se realizarán automáticamente las llamadas RTC de entrada a Teams.

Si los planes de llamadas no están disponibles o su intención es usar su proveedor de conectividad CON RTC, deberá pasar la implementación de voz empresarial (o una implementación de voz híbrida que usa su implementación local existente o Cloud Connector Edition) a Microsoft Phone System Direct Routing. Para actualizar los usuarios a Teams, consulte las [consideraciones adicionales para el enrutamiento directo de sistema telefónico.](2-envision-make-my-service-decisions-direct-routing.md)
