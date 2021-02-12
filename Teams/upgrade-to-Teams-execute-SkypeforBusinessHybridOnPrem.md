---
title: Actualizar Skype Empresarial local a Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Aprenda a actualizar su organización a Microsoft Teams desde una implementación local de Skype Empresarial.
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
ms.openlocfilehash: 961ac4f9bcce3c24d62ec1c744d2c9cd15e2ee1b
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578173"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a>Actualizar de Skype Empresarial local a Teams

![Diagrama de viaje de actualización, que enfatiza la implementación y la implementación](media/upgrade-banner-deployment.png "Fases del viaje de actualización, con énfasis en la fase implementación e implementación")

Este artículo forma parte de la fase de implementación e implementación del viaje de actualización. Antes de continuar, confirma que has completado las siguientes actividades:

-   [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
-   [Ha definido el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)
-   [Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams](https://aka.ms/SkypeToTeams-Coexist)
-   [Ha elegido el viaje de actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [Preparado tu entorno](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [Ha preparado tu organización](https://aka.ms/SkypeToTeams-UserReadiness)
-   [Se realizó un piloto](https://aka.ms/SkypeToTeams-Pilot)

Si ha implementado Skype Empresarial Server o Microsoft Lync local y su organización quiere actualizar a Teams, siga las instrucciones de este artículo. Necesita configurar la conectividad híbrida con su organización de Microsoft 365 u Office 365 y determinar los requisitos de coexistencia si va a mover los usuarios a Teams por fases. 

> [!IMPORTANT]
> Skype Empresarial Online se retirará el 31 de julio de 2021, momento a partir del cual ya no será posible obtener acceso a este soporte. Para aprovechar al máximo las ventajas y asegurarse de que su organización dispone del tiempo adecuado para implementar la actualización, le recomendamos que comience ahora su viaje hacia Microsoft Teams. Recuerde que una actualización correcta alinea la preparación técnica y de usuario, así que asegúrese de aprovechar las directrices en este documento mientras se desplaza a Microsoft Teams.

## <a name="step-1-configure-hybrid-connectivity"></a>Paso 1: Configurar la conectividad híbrida 

El requisito previo clave para actualizar los usuarios locales a Teams es configurar la conectividad híbrida para su implementación local de Skype Empresarial Server. 

Empiece leyendo [Planear conectividad híbrida y,](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) después, siga las tareas descritas en Configurar conectividad [híbrida.](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)


## <a name="step-2-set-transitional-coexistence-mode-optional"></a>Paso 2: Establecer el modo de coexistencia transitional (opcional)

Los modos de actualización de Teams definen la coexistencia e interoperabilidad entre los clientes y los usuarios de Skype Empresarial y Teams.  De forma predeterminada, las organizaciones están en modo Islas, lo que permite a los usuarios usar los clientes teams y Skype Empresarial en paralelo.

En el caso de organizaciones que se muevan a Teams, el modo TeamsOnly es el destino final para cada usuario, aunque no es necesario asignar a todos los usuarios TeamsOnly (o a cualquier otro modo) al mismo tiempo.

Antes de que los usuarios alcancen el modo TeamsOnly, las organizaciones pueden usar cualquiera de los modos de coexistencia de Skype Empresarial para garantizar una comunicación predecible entre los usuarios que están en modo TeamsOnly y los que aún no lo están.  El propósito de los modos de coexistencia de Skype Empresarial (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) es proporcionar una experiencia sencilla y predecible para los usuarios finales a medida que las organizaciones pasen de Skype Empresarial a Teams. 

Cuando un usuario se encuentra en cualquiera de los modos de Skype Empresarial, todos los chats y llamadas entrantes se enruta al cliente de Skype Empresarial del usuario. Para evitar la confusión del usuario final y garantizar un enrutamiento adecuado, la funcionalidad de llamadas y chats en el cliente de Teams se deshabilita cuando un usuario se encuentra en cualquiera de los modos de Skype Empresarial. De forma similar, la programación de reuniones en Teams se deshabilita explícitamente cuando los usuarios están en los modos SfBOnly o SfBWithTeamsCollab y se habilitan explícitamente cuando un usuario está en el modo SfBWithTeamsCollabAndMeetings.

Según sus requisitos, puede asignar el modo de coexistencia adecuado en función de la ruta de actualización que haya elegido su organización. Para obtener más información, vea las instrucciones de migración e [interoperabilidad](migration-interop-guidance-for-teams-with-skype.md) para las organizaciones que usan Teams junto con Skype Empresarial y Cómo establecer la configuración de [coexistencia y actualización.](https://aka.ms/SkypeToTeams-SetCoexistence)


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a>Paso 3: Mover usuarios de Skype Empresarial local a Solo Teams

Finalmente, querrá mover los usuarios al modo TeamsOnly. Esto puede implicar uno o dos pasos dependiendo de su entorno local.  

Para obtener más información, vea Mover usuarios entre local [y la nube,](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) y Mover usuarios de local [a Teams.](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams) 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a>Paso 4: Deshabilitar la implementación híbrida para completar la migración a la nube

Después de mover todos los usuarios de la implementación local a la nube, puede retirar la implementación local de Skype Empresarial. Para obtener más información, vea [Deshabilitar la implementación híbrida para completar la migración a la nube.](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)


## <a name="phone-system-and-pstn-connectivity-options"></a>Opciones de conectividad de Sistema telefónico y RTC

Se admite Sistema telefónico con Teams después de que el usuario esté en modo TeamsOnly. (Si el usuario está en modo Islas, Sistema telefónico solo es compatible con Skype Empresarial). 

### <a name="pstn-connectivity-options"></a>Opciones de conectividad con RTC

Cuando se planteen opciones de conectividad de red telefónica conmutada (RTC), hay dos escenarios posibles al pasar de Skype Empresarial local al modo TeamsOnly:

- Un usuario de Skype Empresarial local con Telefonía IP empresarial que se trasladará a Internet y que utiliza un plan de Llamadas de Microsoft. Migrar este usuario a Teams requiere mover la cuenta local de Skype Empresarial a la nube y coordinar que mueva con A el puerto del número de teléfono de ese usuario a un plan de llamadas de Microsoft o B) asignando un nuevo número de suscriptor desde las regiones disponibles.  Para obtener más información, consulte Skype Empresarial Server local, con [Telefonía IP empresarial, hasta Plan de llamadas de Microsoft.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)

- Un usuario de Skype Empresarial local con Telefonía IP empresarial que pasará a estar conectado y mantendrá la conectividad con RTC local. Migrar este usuario a Teams requiere mover la cuenta de Skype Empresarial local a la nube y coordinar ese movimiento con la migración del usuario a Enrutamiento directo. Para obtener más información, vea De Skype Empresarial Server local, con [Telefonía IP empresarial, a Enrutamiento directo.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)
