---
title: Actualización de Skype para la empresa en línea para los equipos de Microsoft | Implementar
author: arachmanGitHub
ms.author: arachman
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
ms.openlocfilehash: 82577b8e8102baca9ea9681bb94d4a0c73f8b01e
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/07/2019
ms.locfileid: "30465159"
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

# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Actualización de Skype para la empresa en línea a los equipos

Siga las instrucciones de este artículo si totalmente implementado Skype para profesionales en línea y desea actualizar los usuarios de Skype para la empresa a los equipos. Puede actualizar a los usuarios de forma selectiva o en función de la actualización, todo viaje que su organización ha decidido, mediante la asignación de la coexistencia adecuada y el modo de actualización a los usuarios.

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Asignar el modo de actualización y coexistencia

Los usuarios de los equipos que se pueden actualizar asignando el modo de TeamsOnly de TeamsUpgradePolicy, que se puede realizar mediante el centro de administración de Microsoft Teams o un Skype para la sesión remota de Windows Powershell de negocio.

Para obtener más información, vea [establecer la coexistencia y la configuración de actualizaciones](https://aka.ms/SkypeToTeams-SetCoexistence) y [TeamsUpgradePolicy: administración de migración y coexistencia](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Actualizar todos los usuarios a los equipos a la vez

Siga estos pasos para actualizar todos los usuarios a los equipos a la vez.

### <a name="step-1-notify-the-users-of-the-change"></a>Paso 1: Notificar a los usuarios del cambio

1. En el centro de administración de Microsoft Teams, seleccione **configuración de toda la organización** > **actualización de los equipos**.
2. En **modo de coexistencia**, cambie el modificador de **Notificar a Skype para que esté disponible una actualización a los equipos de los usuarios empresariales** a **en**.

### <a name="step-2-set-the-coexistence-mode-for-the-users"></a>Paso 2: Establecer el modo de coexistencia para los usuarios

1. En el centro de administración de Microsoft Teams, seleccione **configuración de toda la organización**.
2. Seleccione el modo de **Sólo los equipos** desde la lista desplegable **modo de coexistencia** .

## <a name="upgrade-users-in-stages"></a>Actualizar los usuarios por fases

Siga estos pasos si desea actualizar gradualmente los usuarios a los equipos.

### <a name="step-1-create-your-user-cohorts-for-the-upgrade"></a>Paso 1: Crear a sus las cohortes de usuario para la actualización

Las cohortes de usuario son grupos de usuarios que se moverán al modo de sólo los equipos al mismo tiempo.

Para crear a sus las cohortes de usuario (Agregar vínculo a la página de selección de usuario)

### <a name="step-2-set-the-user-mode-to-islands"></a>Paso 2: Establecer el modo de usuario a islas

1. En el centro de administración de Microsoft Teams, seleccione **los usuarios**y, a continuación, seleccione un grupo de edad del usuario.
2. Junto a la **actualización de los equipos**, seleccione **Editar**.
3. En el panel de **Actualización de los equipos** , en **modo de coexistencia**, seleccione **Islas** de la lista desplegable.

### <a name="step-3-set-notification-for-the-user-optional"></a>Paso 3: Configurar la notificación para el usuario (opcional)

1. En el centro de administración de Microsoft Teams, seleccione **los usuarios**y seleccione un grupo de edad del usuario.
2. Junto a la **actualización de los equipos**, seleccione **Editar**.
3. En el panel de **Actualización de los equipos** , en **modo de coexistencia**, cambie modificador **Notificar la Skype para usuarios de empresa** a **en**.

### <a name="step-4-set-the-user-mode-to-teams-only"></a>Paso 4: Establecer el modo de usuario en los equipos sólo

Cuando esté listo para actualizar los usuarios para usar los equipos como su única aplicación, establezca el modo de coexistencia para que el usuario sólo los equipos.

1. En el centro de administración de Microsoft Teams, seleccione **los usuarios**y, a continuación, seleccione un grupo de edad del usuario.
2. Junto a la **actualización de los equipos**, seleccione **Editar**.
3. En el panel de **Actualización de los equipos** , en **modo de coexistencia**, seleccione **Sólo los equipos** de la lista desplegable.

## <a name="phone-system-and-teams-upgrade"></a>Sistema telefónico y los equipos de actualización

Si su Skype para la implementación empresarial Online incluye sistema telefónico con planes de llamada y Microsoft es su proveedor de telefónica conmutada (RTC), actualizar a los usuarios a los equipos automáticamente transición RTC entrante a los equipos de llamada.

Si su Skype para la implementación empresarial Online incluye sistema telefónico con la edición de conector en la nube, consulte las [Consideraciones adicionales para el enrutamiento directo de teléfono del sistema](2-envision-make-my-service-decisions-direct-routing.md).