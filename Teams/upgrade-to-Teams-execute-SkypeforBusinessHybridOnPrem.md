---
title: 'Actualizar a Teams desde una implementación local o híbrida de Skype Empresarial: Microsoft Teams'
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Consideraciones para actualizar a teams desde una implementación híbrida o local de Skype empresarial.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 731a6b30fe2476d180198e88f83e80f24c8e8227
ms.sourcegitcommit: 195a4e1bbab46034408a22d636874c10f797945a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "35934521"
---
![Actualizar diagrama de viaje, enfatizar implementación e implementación] (media/upgrade-banner-deployment.png "Etapas del viaje de actualización, con énfasis en la fase de implementación e") implementación

Este artículo forma parte de la fase de implementación e implementación de su viaje de actualización. Antes de continuar, confirme que ha completado las siguientes actividades:

-   [Inventar a los participantes del proyecto](upgrade-enlist-stakeholders.md)
-   [Definió el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)
-   [La coexistencia y la interoperabilidad de Skype para empresas y equipos](https://aka.ms/SkypeToTeams-Coexist)
-   [Eligió la actualización del viaje](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Preparado su entorno](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [Preparado para su organización](https://aka.ms/SkypeToTeams-UserReadiness)
-   [Ha realizado una prueba piloto](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-to-teams-from-a-skype-for-business-hybrid-or-on-premises-deployment"></a>Actualizar a teams desde una implementación híbrida o local de Skype empresarial

Siga las instrucciones de este artículo si ha implementado Skype empresarial o Microsoft Lync local y su organización desea actualizarse a teams de forma selectiva, mediante el uso de varios modos de coexistencia. El primer paso es configurar la conectividad híbrida con el inquilino de Office 365 y, a continuación, trasladar a los usuarios a Skype empresarial online y asignarles el modo de coexistencia y actualización apropiado. 

> [!IMPORTANT]
> Skype empresarial online se retirará el 31 de julio de 2021, después del cual ya no será accesible ni compatible. Para maximizar los beneficios y asegurarse de que su organización tenga el tiempo adecuado para implementar su actualización, le recomendamos que comience su viaje a Microsoft Teams hoy. Recuerde que una actualización correcta alinea la disposición de los usuarios y técnicos, así que asegúrese de aprovechar las instrucciones de este documento a medida que navega por Microsoft Teams.

## <a name="step-1-deploy-hybrid-connectivity"></a>Paso 1: implementar conectividad híbrida 

El requisito previo de actualización de los usuarios a teams es implementar la conectividad híbrida. Esto puede implicar la implementación de una nueva conectividad externa para su implementación actual de Skype empresarial o de Lync, o simplemente configurar una relación híbrida con su inquilino de Office 365. 

Para obtener más información, consulte [implementar conectividad híbrida entre Skype empresarial Server y Skype empresarial online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).

## <a name="step-2-move-users-to-skype-for-business-online"></a>Paso 2: mover usuarios a Skype empresarial online 

Una vez completada la configuración híbrida, mueva usuarios a Skype empresarial online. 

Para obtener más información, vea [mover usuarios de local a Skype empresarial online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online). 

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a>Paso 3: asignar un modo de coexistencia y actualización

Después de mover los usuarios a Skype empresarial online, puede asignarles el modo de coexistencia adecuado en función del recorrido de actualización que haya elegido su organización. Para obtener más información, vea [configurar la coexistencia y la configuración de actualización](https://aka.ms/SkypeToTeams-SetCoexistence) y [TeamsUpgradePolicy: administración de la migración y](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)la coexistencia.

> [!NOTE]
> Con Skype empresarial Server 2019 y una actualización acumulativa futura de Skype empresarial Server 2015, podrá realizar el paso 2 (mover usuarios a Skype empresarial online) y el paso 3 (actualizar usuarios a teams) en un solo paso. Se proporcionará más información después de que se publique el servidor 2019 de Skype empresarial.

## <a name="phone-system-and-teams-upgrade"></a>Actualización de equipos y sistemas telefónicos

Si va a realizar la transición de su implementación híbrida de Skype empresarial a un sistema telefónico con planes de llamadas y Microsoft será su proveedor de red telefónica pública conmutada (RTC) y se ha completado la portabilidad de los números de teléfono, actualice los usuarios a Teams migrará automáticamente las llamadas RTC entrantes a teams.

Si los planes de llamadas no están disponibles, debe realizar la transición de la implementación de telefonía IP empresarial en el enrutamiento directo de Microsoft Phone System. Para actualizar los usuarios a Teams, consulte las [consideraciones adicionales para el enrutamiento directo de sistema telefónico](2-envision-make-my-service-decisions-direct-routing.md).
