---
title: Actualizar la implementación híbrida de Skype empresarial a teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Obtenga información sobre cómo actualizar su organización a Microsoft Teams desde una implementación híbrida de Skype empresarial.
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
ms.openlocfilehash: a83840029eb1fb433c7a073b49ddaa2232b6485e
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905232"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Actualizar a teams desde una implementación híbrida de Skype empresarial

![Etapas del viaje de actualización, con énfasis en la fase de implementación e implementación](media/upgrade-banner-deployment.png "Etapas del viaje de actualización, con énfasis en la fase de implementación e implementación")

Este artículo forma parte de la fase de implementación e implementación de su viaje de actualización. Antes de continuar, confirme que ha completado las siguientes actividades:

- [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
- [Ha definido el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)
- [Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Eligió la actualización del viaje](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparado su entorno](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Preparado para su organización](https://aka.ms/SkypeToTeams-UserReadiness)
- [Ha realizado una prueba piloto](https://aka.ms/SkypeToTeams-Pilot)

Siga las instrucciones de este artículo si ha implementado Skype empresarial o Microsoft Lync local y lo ha configurado en una implementación híbrida con su organización de Office 365, y su organización quiere actualizar a teams de forma selectiva, mediante el uso de varios modos de coexistencia. Para realizar cualquiera de las actualizaciones, necesita mover los usuarios a Skype empresarial online (si no están conectados) y, a continuación, asignarles el modo de coexistencia y actualización apropiado.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Paso 1: mover usuarios a Skype empresarial online

Este paso se aplica a los usuarios que actualmente están alojados en local. Para obtener más información sobre cómo mover estos usuarios a Skype empresarial online, consulte [mover usuarios de local a Skype empresarial online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Paso 2: asignar un modo de coexistencia y actualización

Después de mover los usuarios a Skype empresarial online, puede asignarles el modo de coexistencia adecuado en función del recorrido de actualización que haya elegido su organización. Para obtener más información, vea [configurar la coexistencia y la configuración de actualización](https://aka.ms/SkypeToTeams-SetCoexistence) y [TeamsUpgradePolicy: administración de la migración y la coexistencia](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

> [!NOTE]
> Con Skype empresarial Server 2019 y una actualización acumulativa futura de Skype empresarial Server 2015, podrá realizar el paso 1 (mover usuarios a Skype empresarial online) y el paso 2 (actualizar usuarios a teams) en un solo paso. Se proporcionará más información después de que se publique el servidor 2019 de Skype empresarial.

## <a name="phone-system-and-teams-upgrade"></a>Actualización de equipos y sistemas telefónicos

Si va a realizar la transición de la implementación híbrida de Skype empresarial a un sistema telefónico con planes de llamadas y Microsoft será su proveedor de red de telefonía pública conmutada (RTC) y suponiendo que haya completado la portabilidad de los números de teléfono, la actualización de los usuarios a teams migrará automáticamente las llamadas RTC entrantes a teams.

Si los planes de llamadas no están disponibles o pretende usar su proveedor de conectividad RTC existente, debe realizar la transición de la implementación de telefonía IP empresarial, o de la implementación de voz híbrida que use su implementación local existente o la edición de conector de nube, al enrutamiento directo de Microsoft Phone System. Para actualizar los usuarios a Teams, consulte las [consideraciones adicionales para el enrutamiento directo de sistema telefónico](2-envision-make-my-service-decisions-direct-routing.md).
