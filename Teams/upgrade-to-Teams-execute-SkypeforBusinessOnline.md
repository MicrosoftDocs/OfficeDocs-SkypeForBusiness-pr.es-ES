---
title: Actualización de Skype para la empresa en línea para los equipos de Microsoft | Implementar
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Consideraciones para actualizar a los equipos de Skype para profesionales en línea
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6748397c354f9238282f9646388993fc0e9f7b88
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902728"
---
![Fases de la actualización viaje, con especial hincapié en la implementación y la fase de implementación] (media/upgrade-banner-deployment.png "Fases de la actualización viaje, con especial hincapié en la implementación y la fase de implementación")

En este artículo forma parte de la fase de implementación y la implementación de su viaje por la actualización. Antes de continuar, confirme que ha realizado las siguientes actividades:

- [Los participantes en el proyecto de alta](upgrade-enlist-stakeholders.md)
- [Define el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)
- [Entiende coexistencia e interoperabilidad de Skype para profesionales y los equipos](https://aka.ms/SkypeToTeams-Coexist)
- [Elegido su viaje por la actualización](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparar el entorno](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Preparar la organización](https://aka.ms/SkypeToTeams-UserReadiness)
- [Realiza una prueba piloto](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Actualización de Skype Empresarial Online a Microsoft Teams

Siga las instrucciones de este artículo si totalmente implementado Skype para profesionales en línea y desea actualizar los usuarios de Skype para la empresa a los equipos. Puede actualizar a los usuarios de forma selectiva o en función de la actualización, todo viaje que su organización ha decidido, mediante la asignación de la coexistencia adecuada y el modo de actualización a los usuarios.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Asignar el modo de actualización y coexistencia

Puede actualizar a los usuarios a modo de TeamsOnly mediante la asignación de la instancia de UpgradeToTeams de TeamsUpgradePolicy, que se puede realizar mediante el centro de administración de Microsoft Teams o un Skype para la sesión remota de Windows Powershell de negocio. Puede hacerlo de forma individual por usuario, o en todo el inquilino si desea actualización el inquilino todo en un solo paso. 

Para obtener más información, vea [establecer la coexistencia y la configuración de actualizaciones](https://aka.ms/SkypeToTeams-SetCoexistence) y [TeamsUpgradePolicy: administración de migración y coexistencia](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Actualizar todos los usuarios a los equipos a la vez

Siga estos pasos para actualizar todos los usuarios a los equipos a la vez.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>Paso 1: Notificar a los usuarios el cambio (opcional)

1. En el centro de administración de Microsoft Teams, seleccione **configuración de toda la organización** > **actualización de los equipos**.
2. En **modo de coexistencia**, cambie el modificador de **Notificar a Skype para que esté disponible una actualización a los equipos de los usuarios empresariales** a **en**.

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>Paso 2: Establecer el modo de coexistencia en TeamsOnly para la organización

1. En el centro de administración de Microsoft Teams, seleccione **configuración de toda la organización**.
2. Seleccione el modo de **Sólo los equipos** desde la lista desplegable **modo de coexistencia** .

## <a name="upgrade-users-in-stages"></a>Actualizar los usuarios por fases

Siga estos pasos si desea actualizar gradualmente los usuarios a TeamsOnly.

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>Paso 1: Identificación de grupos de usuarios para la actualización

A menudo, las organizaciones pueden optar por actualizar sus organizaciones en ondas de éxito de los usuarios.  Desea identificar estos usuarios en primer lugar, por lo que puede buscar fácilmente para ellos en el centro de administración de Microsoft Teams. Como alternativa, es posible que desea usar PowerShell para hacerlo de forma más eficaz. Una vez que haya identificado el conjunto de usuarios para una determinada onda de actualización, continúe con los pasos restantes.

### <a name="step-2-set-notification-for-the-users-in-the-current-ugprade-wave-optional"></a>Paso 2: Configurar la notificación para los usuarios en la onda de actualización actual (opcional)

Si utiliza el centro de administración de Microsoft Teams, puede configurar TeamsUpgradePolicy para un máximo de 20 usuarios a la vez:
1. En el centro de administración de Microsoft Teams, seleccione **los usuarios**y buscar y selección múltiple de la casilla de verificación para los usuarios hasta 20 que debe actualizarse. 
2. Seleccione **Editar la configuración** en la esquina superior izquierda de la vista de lista. 
3. En el panel **Editar configuración** de la derecha, en **los equipos de actualización**, cambiar el modificador de **notificar el Skype para usuarios de empresa** **activado**. Nota: Si el valor del modo de coexistencia es "configuración de toda la organización uso", no verá este modificador, por lo que tendrá que primero establecer explícitamente el modo de coexistencia para estos usuarios a todo lo que es el valor predeterminado para el organigrama.

Como alternativa, es posible que encuentre más fácil habilitar las notificaciones para los grupos de usuarios a la vez mediante PowerShell. 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>Paso 3: Establecer el modo de coexistencia para que los usuarios sólo los equipos

Cuando esté listo para actualizar los usuarios de la onda actual para usar los equipos como su única aplicación, establezca el modo de coexistencia para que los usuarios sólo los equipos.

Si utiliza el centro de administración de Microsoft Teams, puede configurar TeamsUpgradePolicy para un máximo de 20 usuarios a la vez:
1. En el centro de administración de Microsoft Teams, seleccione **los usuarios**y, a continuación, seleccione la casilla de verificación hasta 20 usuarios.
2. Seleccione **Editar la configuración** en la esquina superior izquierda de la vista de lista.
3. En el panel **Editar configuración** de la derecha, en la sección de **actualización de los equipos** , establezca el modo de coexistencia en **Los equipos sólo** en la lista desplegable.

Como alternativa, es posible que encuentre más sencillo actualizar grupos de usuarios a la vez mediante PowerShell. 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>Paso 4: Repita los pasos del 1 al 3 para sucesivas de usuarios

Como validar la actualización al modo de sólo los equipos y esté listo para expandir, repita los pasos anteriores para aplicar TeamsOnly a más usuarios.  


## <a name="phone-system-and-teams-upgrade"></a>Sistema telefónico y los equipos de actualización

Si su Skype para la implementación empresarial Online incluye sistema telefónico con planes de llamada y Microsoft es su proveedor de telefónica conmutada (RTC), actualizar a los usuarios a los equipos automáticamente transición RTC entrante a los equipos de llamada.

Si su Skype para la implementación empresarial Online incluye sistema telefónico con la edición de conector en la nube, consulte las [Consideraciones adicionales para el enrutamiento directo de teléfono del sistema](2-envision-make-my-service-decisions-direct-routing.md).
