---
title: Actualizar Skype Empresarial local a Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Obtenga información sobre cómo actualizar su organización a Microsoft Teams desde una implementación local de Skype empresarial.
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
ms.openlocfilehash: 491f4132d5f5c4c4e5d8215d0d48277a864cf064
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905222"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Actualizar de Skype empresarial local a teams

![Actualizar diagrama de viaje, enfatizar implementación e implementación](media/upgrade-banner-deployment.png "Etapas del viaje de actualización, con énfasis en la fase de implementación e implementación")

Este artículo forma parte de la fase de implementación e implementación de su viaje de actualización. Antes de continuar, confirme que ha completado las siguientes actividades:

-   [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
-   [Ha definido el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)
-   [Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams](https://aka.ms/SkypeToTeams-Coexist)
-   [Eligió la actualización del viaje](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Preparado su entorno](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [Preparado para su organización](https://aka.ms/SkypeToTeams-UserReadiness)
-   [Ha realizado una prueba piloto](https://aka.ms/SkypeToTeams-Pilot)

Si ha implementado Skype empresarial Server o Microsoft Lync local y su organización quiere actualizar a Teams, siga las instrucciones de este artículo. Debe configurar la conectividad híbrida con su organización de Office 365 y determinar los requisitos de coexistencia si va a mover a los usuarios a Teams por fases. 

> [!IMPORTANT]
> Skype Empresarial Online se retirará el 31 de julio de 2021, momento a partir del cual ya no será posible obtener acceso a este soporte. Para aprovechar al máximo las ventajas y asegurarse de que su organización dispone del tiempo adecuado para implementar la actualización, le recomendamos que comience ahora su viaje hacia Microsoft Teams. Recuerde que una actualización correcta alinea la disposición de los usuarios y técnicos, así que asegúrese de aprovechar las instrucciones de este documento a medida que navega por Microsoft Teams.

## <a name="step-1-configure-hybrid-connectivity"></a>Paso 1: configurar la conectividad híbrida 

La clave previa para actualizar los usuarios locales a teams es configurar la conectividad híbrida para la implementación local de Skype empresarial Server. 

Empiece por leer [planear la conectividad híbrida](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) y, a continuación, siga las tareas indicadas en [configurar conectividad híbrida](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>Paso 2: establecer el modo de coexistencia de transición (opcional)

La coexistencia y la interoperabilidad entre los clientes de Skype empresarial y de equipos se definen en los modos de actualización de Teams.  De forma predeterminada, las organizaciones están en el modo islas, lo que permite a los usuarios usar tanto equipos como clientes de Skype empresarial en paralelo.

En el caso de una organización que se desplaza a Teams, el modo TeamsOnly es el destino final de cada usuario, aunque no es necesario que todos los usuarios tengan asignado TeamsOnly (o cualquier otro modo) al mismo tiempo.

Antes de que los usuarios alcanzaran el modo TeamsOnly, las organizaciones pueden usar de forma opcional cualquiera de los modos de coexistencia de Skype empresarial para asegurar una comunicación predecible entre los usuarios que están en el modo TeamsOnly y los usuarios que aún no tienen.  El propósito de los modos de coexistencia de Skype empresarial (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) es proporcionar una experiencia sencilla y predecible a los usuarios finales a medida que las organizaciones pasan de Skype empresarial a teams. 

Cuando un usuario se encuentra en cualquiera de los modos de Skype empresarial, todas las conversaciones y llamadas entrantes se enrutan al cliente de Skype empresarial del usuario. Para evitar la confusión entre usuarios finales y garantizar el enrutamiento adecuado, la funcionalidad de llamadas y chats en el cliente de equipos está deshabilitada cuando un usuario se encuentra en cualquiera de los modos de Skype empresarial. De forma similar, la programación de reuniones de Teams se deshabilita de forma explícita cuando los usuarios se encuentran en los modos SfBOnly o SfBWithTeamsCollab, y se habilita de forma explícita cuando un usuario está en el modo de SfBWithTeamsCollabAndMeetings.

Según sus necesidades, puede asignar el modo de coexistencia adecuado en función de la ruta de actualización que haya elegido su organización. Para obtener más información, consulte [Guía de migración e interoperabilidad para las organizaciones que usan Teams conjuntamente con Skype empresarial](migration-interop-guidance-for-teams-with-skype.md) y [establecer la coexistencia y la configuración de actualización](https://aka.ms/SkypeToTeams-SetCoexistence).


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>Paso 3: mover usuarios de Skype empresarial local solo a teams

En última instancia, querrás mover a los usuarios al modo TeamsOnly. Esto puede implicar uno o dos pasos en función de su entorno local actual.  

Para obtener más información, vea [mover usuarios de local y de nube](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) y [mover usuarios de local a teams](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams). 



## <a name="phone-system-and-teams-upgrade"></a>Actualización de equipos y sistemas telefónicos

Si va a realizar una transición de la implementación de Skype empresarial al sistema telefónico con planes de llamadas, Microsoft será su proveedor de red de telefonía pública conmutada (RTC). Suponiendo que haya completado la portabilidad de los números de teléfono, la actualización de los usuarios a teams migrará automáticamente las llamadas RTC entrantes a teams.

Si va a realizar la transición de la implementación de Skype empresarial al sistema telefónico pero no usa planes de llamadas, tendrá que realizar la transición de la implementación de voz empresarial a enrutamiento directo de Microsoft Phone System. Para obtener más información, consulte [enrutamiento directo de sistema telefónico](direct-routing-landing-page.md).
