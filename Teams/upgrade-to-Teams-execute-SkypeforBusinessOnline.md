---
title: Actualizar de Skype Empresarial Online a Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Obtenga información sobre cómo actualizar su organización a Microsoft Teams desde una implementación de Skype Empresarial Online.
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
ms.openlocfilehash: 65b00f8e56792164ed2aa0b8240d0d131a7bdbcd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104016"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Actualización de Skype Empresarial Online a Microsoft Teams

![Diagrama de viaje de actualización, haciendo hincapié en la implementación y la implementación](media/upgrade-banner-deployment.png "Fases del viaje de actualización, con énfasis en la fase implementación e implementación")

Este artículo forma parte de la fase de implementación e implementación del viaje de actualización. Antes de continuar, confirme que ha completado las siguientes actividades:

- [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
- [Ha definido el ámbito del proyecto](./upgrade-define-project-scope.md)
- [Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Elegido el viaje de actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparado el entorno](./upgrade-prepare-environment.md)
- [Preparar la organización](./upgrade-prepare-organization.md)
- [Llevó a cabo un piloto](./pilot-essentials.md)

Siga las instrucciones de este artículo si ha implementado totalmente Skype Empresarial Online y desea actualizar sus usuarios de Skype Empresarial a Teams. Puede actualizar usuarios de forma selectiva o todo en función del recorrido de actualización que haya elegido su organización, asignando el modo de coexistencia y actualización adecuados a los usuarios.

> [!IMPORTANT]
> Skype Empresarial Online se retirará el 31 de julio de 2021, momento a partir del cual ya no será posible obtener acceso a este soporte. Para aprovechar al máximo las ventajas y asegurarse de que su organización dispone del tiempo adecuado para implementar la actualización, le recomendamos que comience ahora su viaje hacia Microsoft Teams. Recuerde que una actualización correcta alinea la preparación técnica y del usuario, por lo que asegúrese de aprovechar las instrucciones aquí a medida que se desplaza a Microsoft Teams.

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Asignar el modo de coexistencia y actualización

Puede actualizar los usuarios al modo TeamsOnly asignando la instancia UpgradeToTeams de TeamsUpgradePolicy, que se puede realizar mediante el Centro de administración de Microsoft Teams o una sesión remota Windows PowerShell Skype Empresarial. Puede hacerlo por usuario o en todo el espacio empresarial si desea actualizar todo el espacio empresarial en un solo paso. 

Para obtener más información, vea [Establecer la configuración de](./setting-your-coexistence-and-upgrade-settings.md) coexistencia y actualización y [TeamsUpgradePolicy: administrar la migración y la coexistencia.](upgrade-to-teams-on-prem-tools.md)

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Actualizar todos los usuarios a Teams a la vez

Siga estos pasos para actualizar todos los usuarios a Teams a la vez.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>Paso 1: Notificar a los usuarios del cambio (opcional)

1. En el Centro de administración de Microsoft Teams, seleccione **Configuración de** toda la organización Actualización  >  **de Teams.**
2. En **Modo de coexistencia,** cambie el cambio a Activar para notificar a los usuarios de Skype Empresarial que hay disponible una actualización a **Teams.**

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>Paso 2: Establecer el modo de coexistencia en TeamsOnly para la organización

1. En el Centro de administración de Microsoft Teams, seleccione **Configuración de toda la organización.**
2. Seleccione **Modo solo de** Teams en la **lista** desplegable Modo de coexistencia.

## <a name="upgrade-users-in-stages"></a>Actualizar usuarios por fases

Siga estos pasos si desea actualizar gradualmente los usuarios a TeamsOnly.

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>Paso 1: Identificar grupos de usuarios para la actualización

A menudo, las organizaciones pueden optar por actualizar sus organizaciones en oleadas de usuarios correctas.  Primero querrá identificar a estos usuarios para que pueda buscarlos fácilmente en el Centro de administración de Microsoft Teams. Como alternativa, es posible que desee usar PowerShell para hacerlo de forma más eficiente. Una vez que haya identificado el conjunto de usuarios para una ola de actualización determinada, continúe con los pasos restantes.

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>Paso 2: Establecer una notificación para los usuarios de la ola de actualización actual (opcional)

Si usa el Centro de administración de Microsoft Teams, puede configurar TeamsUpgradePolicy para un máximo de 20 usuarios a la vez:
1. En el Centro de administración de Microsoft Teams, seleccione Usuarios **y** busque y seleccione varias casillas para un máximo de 20 usuarios que deberán actualizarse. 
2. Seleccione **Editar configuración** en la esquina superior izquierda de la vista de lista. 
3. En el **panel Editar configuración** de la derecha, en Actualización de **Teams,** cambie Notificar al usuario de **Skype Empresarial** que cambie a **Activar**. Nota: Si el valor del modo de coexistencia es "Usar la configuración de toda la organización", no verá este modificador, por lo que primero tendrá que establecer explícitamente el modo coexistencia para estos usuarios en cualquiera que sea el valor predeterminado para la organización.

Como alternativa, es posible que le resulte más fácil habilitar notificaciones para grupos de usuarios a la vez con PowerShell. 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>Paso 3: Establecer el modo de coexistencia para los usuarios en Solo Teams

Cuando esté listo para actualizar los usuarios de la ola actual para usar Teams como única aplicación, establezca el modo coexistencia para los usuarios en Solo teams.

Si usa el Centro de administración de Microsoft Teams, puede configurar TeamsUpgradePolicy para un máximo de 20 usuarios a la vez:
1. En el Centro de administración de Microsoft Teams, seleccione **Usuarios** y, a continuación, seleccione la casilla para un máximo de 20 usuarios.
2. Seleccione **Editar configuración** en la esquina superior izquierda de la vista de lista.
3. En el **panel Editar configuración** de la derecha, en la sección Actualización de **Teams,** establezca el modo de coexistencia en **Solo** teams en la lista desplegable.

Como alternativa, es posible que le resulte más fácil actualizar grupos de usuarios a la vez con PowerShell. 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>Paso 4: Repetir los pasos 1 a 3 para las sucesivas oleadas de usuarios

A medida que valide la actualización al modo solo de Teams y esté listo para expandirse, repita los pasos anteriores para aplicar TeamsOnly a más usuarios.  


## <a name="phone-system-and-pstn-connectivity-options"></a>Opciones de conectividad del sistema telefónico y RTC

Sistema telefónico con Teams es compatible después de que el usuario esté en modo TeamsOnly. (Si el usuario está en modo Islas, El sistema telefónico solo es compatible con Skype Empresarial).  

### <a name="pstn-connectivity-options"></a>Opciones de conectividad RTC

Al considerar las opciones de conectividad de red telefónica conmutada (RTC), hay dos escenarios posibles al pasar de Skype Empresarial Online al modo TeamsOnly:

- Un usuario de Skype Empresarial Online, con un plan de llamadas de Microsoft. Tras la actualización, este usuario seguirá teniendo un plan de Llamadas de Microsoft. Este es el escenario más sencillo que requiere solo un par de pasos. Para obtener más información, vea [Desde Skype Empresarial Online con planes de llamadas de Microsoft.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)

- Un usuario de Skype Empresarial Online, con funcionalidad de voz local a través de Skype Empresarial local o Cloud Connector Edition. La actualización del usuario a Teams debe coordinarse con la migración del usuario a Enrutamiento directo para asegurarse de que el usuario de TeamsOnly tiene funcionalidad RTC.  Para obtener más información, [vea Desde Skype Empresarial Online con voz local.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)