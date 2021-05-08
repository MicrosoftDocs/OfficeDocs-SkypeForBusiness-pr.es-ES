---
title: Actualizar de Skype Empresarial Online a Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Obtenga información sobre cómo actualizar su organización a Microsoft Teams desde una Skype Empresarial en línea.
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
ms.openlocfilehash: 7c35909bf7787242a07f89d1442a25365348c91a
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282107"
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

Siga las instrucciones de este artículo si ha implementado completamente Skype Empresarial Online y desea actualizar los usuarios de Skype Empresarial a Teams. Puede actualizar usuarios de forma selectiva o todo en función del recorrido de actualización que haya elegido su organización, asignando el modo de coexistencia y actualización adecuados a los usuarios.

> [!IMPORTANT]
> Skype Empresarial Online se retirará el 31 de julio de 2021, momento a partir del cual ya no será posible obtener acceso a este soporte. Para aprovechar al máximo las ventajas y asegurarse de que su organización dispone del tiempo adecuado para implementar la actualización, le recomendamos que comience ahora su viaje hacia Microsoft Teams. Recuerde que una actualización correcta alinea la preparación técnica y del usuario, por lo que asegúrese de aprovechar las instrucciones aquí a medida que vaya navegando hasta Microsoft Teams.

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Asignar el modo de coexistencia y actualización

Puede actualizar los usuarios al modo TeamsOnly asignando la instancia UpgradeToTeams de TeamsUpgradePolicy, que se puede realizar mediante el centro de administración de Microsoft Teams o una sesión de Skype Empresarial Windows PowerShell remoto. Puede hacerlo por usuario o en todo el espacio empresarial si desea actualizar todo el espacio empresarial en un solo paso. 

Para obtener más información, vea [Establecer la configuración de](./setting-your-coexistence-and-upgrade-settings.md) coexistencia y actualización y [TeamsUpgradePolicy: administrar la migración y la coexistencia.](upgrade-to-teams-on-prem-tools.md)

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Actualizar todos los usuarios a Teams a la vez

Siga estos pasos para actualizar todos los usuarios a Teams a la vez.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>Paso 1: Notificar a los usuarios del cambio (opcional)

1. En el Microsoft Teams de administración, seleccione **Configuración de** toda la organización Teams  >  **actualización.**
2. En **Modo de coexistencia,** cambie la opción Notificar a Skype Empresarial usuarios que una actualización a Teams **está disponible,** cambie a **Activar**.

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>Paso 2: Establecer el modo de coexistencia en TeamsOnly para la organización

1. En el Microsoft Teams de administración, seleccione **Configuración de toda la organización.**
2. Seleccione **Teams solo** en la **lista** desplegable Modo de coexistencia.

## <a name="upgrade-users-in-stages"></a>Actualizar usuarios por fases

Siga estos pasos si desea actualizar gradualmente los usuarios a TeamsOnly.

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>Paso 1: Identificar grupos de usuarios para la actualización

A menudo, las organizaciones pueden optar por actualizar sus organizaciones en oleadas de usuarios correctas.  Primero querrá identificar a estos usuarios para que pueda buscarlos fácilmente en el centro Microsoft Teams administración. Como alternativa, es posible que desee usar PowerShell para hacerlo de forma más eficiente. Una vez que haya identificado el conjunto de usuarios para una ola de actualización determinada, continúe con los pasos restantes.

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>Paso 2: Establecer una notificación para los usuarios de la ola de actualización actual (opcional)

Si usa el Microsoft Teams de administración, puede configurar TeamsUpgradePolicy para un máximo de 20 usuarios a la vez:
1. En el Microsoft Teams de administración, seleccione Usuarios **y** busque y seleccione varias casillas para un máximo de 20 usuarios que deben actualizarse. 
2. Seleccione **Editar configuración** en la esquina superior izquierda de la vista de lista. 
3. En el **panel Editar configuración** de la derecha, en Teams **actualizar,** cambie Notificar al **usuario** Skype Empresarial cambiar a **Activar**. Nota: Si el valor del modo de coexistencia es "Usar la configuración de toda la organización", no verá este modificador, por lo que primero tendrá que establecer explícitamente el modo coexistencia para estos usuarios en cualquiera que sea el valor predeterminado para la organización.

Como alternativa, es posible que le resulte más fácil habilitar notificaciones para grupos de usuarios a la vez con PowerShell. 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>Paso 3: Establecer el modo de coexistencia para que los usuarios Teams solo

Cuando esté listo para actualizar los usuarios de la ola actual para usar Teams como su única aplicación, establezca el modo coexistencia para que los usuarios Teams solo.

Si usa el Microsoft Teams de administración, puede configurar TeamsUpgradePolicy para un máximo de 20 usuarios a la vez:
1. En el Microsoft Teams de administración, seleccione **Usuarios** y, a continuación, seleccione la casilla para un máximo de 20 usuarios.
2. Seleccione **Editar configuración** en la esquina superior izquierda de la vista de lista.
3. En el **panel Editar configuración** de la **derecha,** en Teams de actualización, establezca el modo de coexistencia **en Teams solo** en la lista desplegable.

Como alternativa, es posible que le resulte más fácil actualizar grupos de usuarios a la vez con PowerShell. 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>Paso 4: Repetir los pasos 1 a 3 para las sucesivas oleadas de usuarios

A medida que valide la actualización Teams modo solo y esté listo para expandirse, repita los pasos anteriores para aplicar TeamsOnly a más usuarios.  


## <a name="phone-system-and-pstn-connectivity-options"></a>Sistema telefónico y las opciones de conectividad RTC

Sistema telefónico con Teams es compatible después de que el usuario esté en modo TeamsOnly. (Si el usuario está en modo Islas, Sistema telefónico solo es compatible con Skype Empresarial).  

### <a name="pstn-connectivity-options"></a>Opciones de conectividad RTC

Al considerar las opciones de conectividad de red telefónica conmutada (RTC), hay dos escenarios posibles al pasar de Skype Empresarial Online al modo de TeamsOnly:

- Un usuario en Skype Empresarial Online, con un plan de llamadas de Microsoft. Tras la actualización, este usuario seguirá teniendo un plan de Llamadas de Microsoft. Este es el escenario más sencillo que requiere solo un par de pasos. Para obtener más información, vea [Desde Skype Empresarial en línea con planes de llamadas de Microsoft](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).

- Un usuario en Skype Empresarial Online, con funcionalidad de voz local a través Skype Empresarial local o Cloud Connector Edition. La actualización del usuario a Teams debe coordinarse con la migración del usuario a Enrutamiento directo para asegurarse de que el usuario de TeamsOnly tiene funcionalidad RTC.  Para obtener más información, vea [Desde Skype Empresarial Online con voz local.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)