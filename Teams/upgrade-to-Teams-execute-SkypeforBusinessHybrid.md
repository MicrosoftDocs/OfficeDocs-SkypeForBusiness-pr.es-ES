---
title: Actualizar la implementación híbrida de Skype empresarial a Microsoft Teams | RTC
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Consideraciones para actualizar a teams desde una implementación híbrida de Skype empresarial.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7729cd65ff5d58d348229c4ec5ec6182f06aa5de
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235913"
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

# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a>Actualizar a teams desde una implementación híbrida de Skype empresarial

Siga las instrucciones de este artículo si ha implementado Skype empresarial o Microsoft Lync local y lo ha configurado en una implementación híbrida con su inquilino de Office 365, y su organización quiere actualizar a teams de forma selectiva; para ello, use varias modos de coexistencia. Para realizar cualquiera de las actualizaciones, necesita mover los usuarios a Skype empresarial online (si no están conectados) y, a continuación, asignarles el modo de coexistencia y actualización apropiado.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a>Paso 1: mover usuarios a Skype empresarial online

Este paso se aplica a los usuarios que actualmente están alojados en local. Para obtener más información sobre cómo mover estos usuarios a Skype empresarial online, consulte [mover usuarios de local a Skype empresarial online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a>Paso 2: asignar un modo de coexistencia y actualización

Después de mover los usuarios a Skype empresarial online, puede asignarles el modo de coexistencia adecuado en función del recorrido de actualización que haya elegido su organización. Para obtener más información, vea [configurar la coexistencia y la configuración de actualización](https://aka.ms/SkypeToTeams-SetCoexistence) y [TeamsUpgradePolicy: administración de la migración y](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)la coexistencia.

> [!NOTE]
> Con Skype empresarial Server 2019 y una actualización acumulativa futura de Skype empresarial Server 2015, podrá realizar el paso 1 (mover usuarios a Skype empresarial online) y el paso 2 (actualizar usuarios a teams) en un solo paso. Se proporcionará más información después de que se publique el servidor 2019 de Skype empresarial.

## <a name="phone-system-and-teams-upgrade"></a>Actualización de equipos y sistemas telefónicos

Si va a realizar la transición de su implementación híbrida de Skype empresarial a un sistema telefónico con planes de llamadas y Microsoft será su proveedor de red telefónica pública conmutada (RTC) y se ha completado la portabilidad de los números de teléfono, actualice los usuarios a Teams migrará automáticamente las llamadas RTC entrantes a teams.

Si los planes de llamadas no están disponibles o pretende usar su proveedor de conectividad con RTC existente, debe realizar una transición de la implementación de telefonía IP empresarial, o de la implementación de voz híbrida que usa su implementación local existente o de la versión de conector de nube, para Enrutamiento directo de Microsoft Phone System. Para actualizar los usuarios a Teams, consulte las [consideraciones adicionales para el enrutamiento directo de sistema telefónico](2-envision-make-my-service-decisions-direct-routing.md).
