---
title: Actualizar de Skype Empresarial Online a Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Aprenda a actualizar su organización a Microsoft Teams desde una implementación de Skype Empresarial Online.
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
ms.openlocfilehash: ca99c193a17547943018eba75004f0ec0a1a92f3
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578263"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Actualización de Skype Empresarial Online a Microsoft Teams

![Diagrama de viaje de actualización, que enfatiza la implementación y la implementación](media/upgrade-banner-deployment.png "Fases del viaje de actualización, con énfasis en la fase Implementación e Implementación")

Este artículo forma parte de la fase de implementación e implementación del viaje de actualización. Antes de continuar, confirma que has completado las siguientes actividades:

- [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
- [Ha definido el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)
- [Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Ha elegido el viaje de actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparado tu entorno](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Ha preparado tu organización](https://aka.ms/SkypeToTeams-UserReadiness)
- [Se realizó un piloto](https://aka.ms/SkypeToTeams-Pilot)

Siga las instrucciones de este artículo si ha implementado Skype Empresarial Online y desea actualizar sus usuarios de Skype Empresarial a Teams. Puede actualizar usuarios selectivo o todo el contenido, según el camino de actualización que haya elegido su organización, asignando el modo de coexistencia y actualización adecuados a los usuarios.

> [!IMPORTANT]
> Skype Empresarial Online se retirará el 31 de julio de 2021, momento a partir del cual ya no será posible obtener acceso a este soporte. Para aprovechar al máximo las ventajas y asegurarse de que su organización dispone del tiempo adecuado para implementar la actualización, le recomendamos que comience ahora su viaje hacia Microsoft Teams. Recuerde que una actualización correcta alinea la preparación técnica y de usuario, así que asegúrese de aprovechar las directrices en este documento mientras se desplaza a Microsoft Teams.

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Asignar el modo de coexistencia y actualización

Puede actualizar sus usuarios al modo TeamsOnly asignando la instancia UpgradeToTeams de TeamsUpgradePolicy, que se puede realizar mediante el Centro de administración de Microsoft Teams o una sesión remota de Windows PowerShell Skype Empresarial. Puede hacerlo por usuario o por inquilino si desea actualizar todo el espacio empresarial en un solo paso. 

Para obtener más información, vea [Configurar la coexistencia](https://aka.ms/SkypeToTeams-SetCoexistence) y la configuración de actualización y [TeamsUpgradePolicy: administrar la migración y coexistencia.](upgrade-to-teams-on-prem-tools.md)

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Actualizar todos los usuarios a Teams a la vez

Siga estos pasos para actualizar todos los usuarios a Teams a la vez.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>Paso 1: Notificar a los usuarios del cambio (opcional)

1. En el Centro de administración de Microsoft Teams, seleccione **la actualización de** Teams de configuración para toda la  >  **organización.**
2. En **el modo de coexistencia,** cambie el botón a Activar para notificar a los usuarios de Skype Empresarial que hay disponible una actualización a **Teams.** 

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>Paso 2: Establecer el modo de coexistencia en TeamsOnly para la organización

1. En el Centro de administración de Microsoft Teams, seleccione **configuración para toda la organización.**
2. Seleccione **solo el modo de** teams en la lista desplegable Modo de coexistencia. 

## <a name="upgrade-users-in-stages"></a>Actualizar usuarios por fases

Siga estos pasos si quiere actualizar gradualmente los usuarios a TeamsOnly.

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>Paso 1: Identificar grupos de usuarios para la actualización

Con frecuencia, las organizaciones pueden optar por actualizar sus organizaciones en una ola de usuarios con éxito.  Querrá identificar primero estos usuarios para poder buscarlos fácilmente en el Centro de administración de Microsoft Teams. Como alternativa, puede usar PowerShell para hacer esto de forma más eficaz. Una vez que haya identificado el conjunto de usuarios para una determinada ola de actualización, continúe con los pasos restantes.

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>Paso 2: Establecer una notificación para los usuarios en la ola de actualización actual (opcional)

Si utiliza el Centro de administración de Microsoft Teams, puede configurar TeamsUpgradePolicy para un máximo de 20 usuarios a la vez:
1. En el Centro de administración de Microsoft Teams, seleccione Usuarios y busque y seleccione varias casillas para un máximo de 20 usuarios que deberán actualizarse. 
2. Seleccione **Editar configuración** en la esquina superior izquierda de la vista de lista. 
3. En el **panel Editar** configuración de la derecha, en la actualización **de Teams,** cambie El cambio a Notificar al usuario de **Skype Empresarial** a **Activar.** Nota: Si el valor del modo de coexistencia es "Usar configuración para toda la organización", no verá este modificador, por lo que primero tendrá que establecer explícitamente el modo de coexistencia para estos usuarios en cualquier valor predeterminado para la organización.

Como alternativa, es posible que le resulte más fácil habilitar las notificaciones para grupos de usuarios a la vez con PowerShell. 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>Paso 3: Establecer el modo de coexistencia de los usuarios en Solo equipos

Cuando esté listo para actualizar los usuarios de la ola actual para que usen Teams como su única aplicación, establezca el modo de coexistencia para los usuarios en Solo equipos.

Si utiliza el Centro de administración de Microsoft Teams, puede configurar TeamsUpgradePolicy para un máximo de 20 usuarios a la vez:
1. En el Centro de administración de Microsoft Teams, seleccione **Usuarios** y, a continuación, seleccione la casilla de un máximo de 20 usuarios.
2. Seleccione **Editar configuración** en la esquina superior izquierda de la vista de lista.
3. En el **panel Editar** configuración a la derecha, en la sección actualización de **Teams,** establezca el modo de coexistencia en **Teams solo** en la lista desplegable.

Como alternativa, es posible que le resulte más fácil actualizar grupos de usuarios a la vez con PowerShell. 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>Paso 4: Repita los pasos 1 a 3 para sucesivas solicitudes de usuarios

Cuando valide la actualización al modo Solo equipos y esté listo para expandirse, repita los pasos anteriores para aplicar TeamsOnly a más usuarios.  


## <a name="phone-system-and-pstn-connectivity-options"></a>Opciones de conectividad de Sistema telefónico y RTC

Se admite Sistema telefónico con Teams después de que el usuario esté en modo TeamsOnly. (Si el usuario está en modo Islas, Sistema telefónico solo es compatible con Skype Empresarial).  

### <a name="pstn-connectivity-options"></a>Opciones de conectividad con RTC

Cuando se planteen opciones de conectividad de red telefónica conmutada (RTC), hay dos escenarios posibles al pasar de Skype Empresarial Online al modo TeamsOnly:

- Un usuario de Skype Empresarial Online con un plan de llamadas de Microsoft. Tras la actualización, este usuario seguirá teniendo un plan de Llamadas de Microsoft. Este es el escenario más sencillo que requiere solo un par de pasos. Para obtener más información, [consulte Desde Skype Empresarial Online con planes de llamadas de Microsoft.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)

- Un usuario de Skype Empresarial Online, con funcionalidad de voz local a través de Skype Empresarial local o Cloud Connector Edition. La actualización del usuario a Teams debe coordinarse con la migración del usuario a Enrutamiento directo para asegurarse de que el usuario de TeamsOnly tiene funcionalidad RTC.  Para obtener más información, [consulte Desde Skype Empresarial Online con voz local.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)


