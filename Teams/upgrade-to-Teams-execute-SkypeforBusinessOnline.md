---
title: Actualizar de Skype Empresarial Online a Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Obtenga información sobre cómo actualizar su organización a Microsoft Teams desde una implementación de Skype Empresarial Online.
ms.localizationpriority: medium
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
ms.openlocfilehash: 5da45fcc5a9459b909e03f0d4e904b57d9a3f0fa
ms.sourcegitcommit: 9a9168d5c40bbb0cceaf3ffd11eb104c137f26b3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2022
ms.locfileid: "67590217"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Actualización de Skype Empresarial Online a Microsoft Teams

![Diagrama de recorrido de la actualización, en el que se hace hincapié en la implementación y la implementación.](media/upgrade-banner-deployment.png "Fases del recorrido de la actualización, con énfasis en la fase de implementación e implementación")

Este artículo forma parte de la fase de implementación e implementación del recorrido de la actualización. Antes de continuar, confirma que has completado las siguientes actividades:

- [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
- [Ha definido el ámbito del proyecto](./upgrade-define-project-scope.md)
- [Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Elige tu viaje de actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparado para su entorno](./upgrade-prepare-environment.md)
- [Preparado para su organización](./upgrade-prepare-organization.md)
- [Se realizó un piloto](./pilot-essentials.md)

Siga las instrucciones de este artículo si ha implementado completamente Skype Empresarial En línea y desea actualizar los usuarios de Skype Empresarial a Teams. Puede actualizar usuarios selectivamente o todo en función del recorrido de actualización que haya elegido su organización, asignando el modo de coexistencia y actualización adecuado a los usuarios.

> [!IMPORTANT]
> Skype Empresarial Online se retiró el 31 de julio de 2021. Para aprovechar al máximo las ventajas y asegurarse de que su organización dispone del tiempo adecuado para implementar la actualización, le recomendamos que comience ahora su viaje hacia Microsoft Teams. Recuerde que una actualización correcta alinea la preparación técnica y de usuario, así que asegúrese de aprovechar las instrucciones aquí a medida que se desplaza a Microsoft Teams.

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Asignar el modo de coexistencia y actualización

Puede actualizar los usuarios al modo TeamsOnly asignando la instancia UpgradeToTeams de TeamsUpgradePolicy, que se puede realizar mediante el centro de administración de Microsoft Teams o una sesión de Windows PowerShell remota de Skype Empresarial. Puede hacerlo por usuario o por inquilino si desea actualizar todo el inquilino en un solo paso. 

Para obtener más información, consulte [Configuración de la coexistencia y la actualización](./setting-your-coexistence-and-upgrade-settings.md) y [TeamsUpgradePolicy: administración de la migración y coexistencia](upgrade-to-teams-on-prem-tools.md).

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Actualizar todos los usuarios a Teams a la vez

Siga estos pasos para actualizar todos los usuarios a Teams a la vez.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>Paso 1: Notificar a los usuarios el cambio (opcional)

1. En el Centro de administración de Microsoft Teams, seleccione **Configuración de actualización de** **Teams** > .
2. En **Modo de coexistencia**, cambie el botón **Notificar a los usuarios Skype Empresarial que hay disponible una actualización a Teams** a **Activado**.

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>Paso 2: Establecer el modo de coexistencia en TeamsOnly para la organización

1. En el Centro de administración de Microsoft Teams, seleccione **Configuración de actualización de** **Teams** > .
2. Seleccione **Modo solo de Teams** en la lista desplegable **Modo de coexistencia** .

## <a name="upgrade-users-in-stages"></a>Actualizar usuarios por fases

Siga estos pasos si quiere actualizar gradualmente los usuarios a TeamsOnly.

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>Paso 1: Identificar grupos de usuarios para la actualización

A menudo, las organizaciones pueden optar por actualizar sus organizaciones con éxito de usuarios.  En primer lugar, le interesará identificar a estos usuarios para poder buscarlos fácilmente en el Centro de administración de Microsoft Teams. Como alternativa, es posible que desee usar PowerShell para hacer esto de forma más eficaz. Una vez que haya identificado el conjunto de usuarios para una determinada ola de actualización, continúe con los pasos restantes.

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>Paso 2: Establecer notificación para los usuarios en la ola de actualización actual (opcional)

Si usas el Centro de administración de Microsoft Teams, puedes configurar TeamsUpgradePolicy para un máximo de 20 usuarios a la vez:
1. En el Centro de administración de Microsoft Teams, seleccione **Usuarios** y busque y seleccione varias casillas para un máximo de 20 usuarios que deben actualizarse. 
2. Seleccione **Editar configuración** en la esquina superior izquierda de la vista de lista. 
3. En el panel **Editar configuración** de la derecha, en **Actualización de Teams**, cambie **Notificar a los Skype Empresarial usuario** cambie a **Activado**. Nota: Si el valor del modo de coexistencia es "Utilizar la configuración de toda la organización", usted no verá este switch, así que tendrá que establecer explícitamente el modo de coexistencia para estos usuarios a cualquiera que sea el valor predeterminado para la organización.

Como alternativa, es posible que le resulte más fácil habilitar las notificaciones para grupos de usuarios a la vez con PowerShell. Para obtener más información, consulte [Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy).

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>Paso 3: Establecer el modo de coexistencia para los usuarios en Solo teams

Cuando esté listo para actualizar los usuarios de la ola actual para usar Teams como su única aplicación, establezca el modo de coexistencia para los usuarios en Solo Teams.

Si usas el Centro de administración de Microsoft Teams, puedes configurar TeamsUpgradePolicy para un máximo de 20 usuarios a la vez:
1. En el Centro de administración de Microsoft Teams, seleccione **Usuarios** y, a continuación, seleccione la casilla de hasta 20 usuarios.
2. Seleccione **Editar configuración** en la esquina superior izquierda de la vista de lista.
3. En el panel **Editar configuración** de la derecha, en la sección **Actualización de Teams** , establezca el modo de coexistencia en **Solo Teams** en la lista desplegable.

Como alternativa, puede que le resulte más fácil actualizar grupos de usuarios a la vez con PowerShell. Para obtener más información, consulte [Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy).

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>Paso 4: Repita los pasos 1-3 para sucesivas olas de usuarios

Cuando valide la actualización al modo Solo teams y esté listo para expandirse, repita los pasos anteriores para aplicar TeamsOnly a más usuarios.  


## <a name="phone-system-and-pstn-connectivity-options"></a>Sistema telefónico y opciones de conectividad con RTC

El sistema telefónico con Teams se admite después de que el usuario esté en el modo TeamsOnly. (Si el usuario está en modo Islas, Solo se admite Phone System con Skype Empresarial).  

### <a name="pstn-connectivity-options"></a>Opciones de conectividad con RTC

Al considerar las opciones de conectividad de la red telefónica conmutada (RTC), hay dos escenarios posibles al pasar de Skype Empresarial en línea al modo Solo equipos:

- Un usuario de Skype Empresarial Online, con un plan de llamadas de Microsoft. Tras la actualización, este usuario seguirá teniendo un plan de llamadas de Microsoft. Este es el escenario más sencillo que requiere solo un par de pasos. Para obtener más información, consulte [Desde Skype Empresarial en línea con planes de llamadas de Microsoft](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).

- Un usuario de Skype Empresarial Online, con funcionalidad de voz local a través de Skype Empresarial local o Cloud Connector Edition. La actualización del usuario a Teams debe coordinarse con la migración del usuario a Enrutamiento directo para asegurarse de que el usuario de TeamsOnly tiene funcionalidad RTC.  Para obtener más información, vea [Desde Skype Empresarial en línea con voz local](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice).
