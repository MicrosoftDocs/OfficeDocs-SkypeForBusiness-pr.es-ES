---
title: Actualizar Skype empresarial online a Microsoft Teams | Implement
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Obtenga información sobre cómo actualizar su organización a Microsoft Teams desde un deployement de Skype empresarial online.
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
ms.openlocfilehash: 29dc02a88efe533f9a43a110c357203b87a890d6
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2020
ms.locfileid: "44523173"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a>Actualización de Skype Empresarial Online a Microsoft Teams

![Actualizar diagrama de viaje, enfatizar implementación e implementación](media/upgrade-banner-deployment.png "Etapas del viaje de actualización, con énfasis en la fase de implementación e implementación")

Este artículo forma parte de la fase de implementación e implementación de su viaje de actualización. Antes de continuar, confirme que ha completado las siguientes actividades:

- [Ha incorporado a las partes interesadas del proyecto](upgrade-enlist-stakeholders.md)
- [Ha definido el ámbito del proyecto](https://aka.ms/SkypetoTeams-Scope)
- [Ha comprendido la coexistencia y la interoperabilidad de Skype Empresarial y Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Eligió la actualización del viaje](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparado su entorno](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [Preparado para su organización](https://aka.ms/SkypeToTeams-UserReadiness)
- [Ha realizado una prueba piloto](https://aka.ms/SkypeToTeams-Pilot)

Siga las instrucciones de este artículo si ha implementado totalmente Skype empresarial online y desea actualizar los usuarios de Skype empresarial a teams. Puede actualizar los usuarios de forma selectiva o todos en función del recorrido de actualización que su organización haya elegido, asignando el modo de coexistencia y actualización adecuado a los usuarios.

> [!IMPORTANT]
> Skype Empresarial Online se retirará el 31 de julio de 2021, momento a partir del cual ya no será posible obtener acceso a este soporte. Para aprovechar al máximo las ventajas y asegurarse de que su organización dispone del tiempo adecuado para implementar la actualización, le recomendamos que comience ahora su viaje hacia Microsoft Teams. Recuerde que una actualización correcta alinea la disposición de los usuarios y técnicos, así que asegúrese de aprovechar las instrucciones de este documento a medida que navega por Microsoft Teams.

## <a name="assign-the-coexistence-and-upgrade-mode"></a>Asignar el modo de coexistencia y actualización

Puede actualizar los usuarios al modo de TeamsOnly asignando la instancia de UpgradeToTeams de TeamsUpgradePolicy, que se puede realizar mediante el centro de administración de Microsoft Teams o una sesión de Windows PowerShell remota de Skype empresarial. Puede hacer esto para cada usuario o a escala de inquilino si quiere actualizar todo el inquilino en un solo paso de tiempo. 

Para obtener más información, vea [configurar la coexistencia y la configuración de actualización](https://aka.ms/SkypeToTeams-SetCoexistence) y [TeamsUpgradePolicy: administración de la migración y la coexistencia](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).

## <a name="upgrade-all-users-to-teams-at-one-time"></a>Actualizar todos los usuarios a teams a la vez

Siga estos pasos para actualizar todos los usuarios a teams a la vez.

### <a name="step-1-notify-the-users-of-the-change-optional"></a>Paso 1: notificar a los usuarios el cambio (opcional)

1. En el centro de administración de Microsoft Teams, seleccione la actualización de la configuración de equipos de la **organización**  >  **Teams upgrade**.
2. En **modo de coexistencia**, cambie la opción **notificar a los usuarios de Skype empresarial que hay disponible una actualización a teams** **.**

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a>Paso 2: establecer el modo de coexistencia en TeamsOnly para la organización

1. En el centro de administración de Microsoft Teams, seleccione **configuración de toda la organización**.
2. Seleccione el modo **solo de Teams** en la lista desplegable **modo de coexistencia** .

## <a name="upgrade-users-in-stages"></a>Actualizar usuarios por etapas

Siga estos pasos si desea actualizar gradualmente los usuarios a TeamsOnly.

### <a name="step-1-identify-groups-of-users-for-upgrade"></a>Paso 1: identificar los grupos de usuarios para la actualización

A menudo, las organizaciones pueden optar por actualizar sus organizaciones con las ondas de éxito de los usuarios.  Es posible que desee identificar estos usuarios en primer lugar para que pueda buscarlos fácilmente en el centro de administración de Microsoft Teams. Como alternativa, es posible que desee usar PowerShell para hacerlo de manera más eficaz. Una vez que haya identificado el conjunto de usuarios para una onda de actualización determinada, continúe con los pasos restantes.

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a>Paso 2: establecer una notificación para los usuarios de la onda de actualización actual (opcional)

Si usa el centro de administración de Microsoft Teams, puede configurar TeamsUpgradePolicy para un máximo de 20 usuarios a la vez:
1. En el centro de administración de Microsoft Teams, seleccione **usuarios**, busque y seleccione la casilla múltiple para un máximo de 20 usuarios que deberían actualizarse. 
2. Seleccione **Editar configuración** en la esquina superior izquierda del ListView. 
3. En el panel **Editar configuración** de la derecha, en la sección **actualizar de Teams**, cambie **notificar al usuario de Skype empresarial** a **activado**. Nota: Si el valor de modo de coexistencia es "usar la configuración de toda la organización", no verá este modificador, por lo que tendrá que establecer explícitamente el modo de coexistencia de estos usuarios en el valor predeterminado de la organización.

Como alternativa, es posible que le resulte más fácil habilitar las notificaciones para grupos de usuarios a la vez mediante PowerShell. 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a>Paso 3: establecer el modo de coexistencia para los usuarios solo para equipos

Cuando esté listo para actualizar los usuarios de la onda actual para que use Teams como única aplicación, establezca el modo de coexistencia para los usuarios solo en Teams.

Si usa el centro de administración de Microsoft Teams, puede configurar TeamsUpgradePolicy para un máximo de 20 usuarios a la vez:
1. En el centro de administración de Microsoft Teams, seleccione **usuarios**y, a continuación, seleccione la casilla de verificación para un máximo de 20 usuarios.
2. Seleccione **Editar configuración** en la esquina superior izquierda del ListView.
3. En el panel **Editar configuración** de la derecha, en la sección **actualización de equipos** , establezca el modo de coexistencia en **Teams solo** en la lista desplegable.

Como alternativa, es posible que le resulte más fácil actualizar grupos de usuarios a la vez mediante PowerShell. 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a>Paso 4: Repita los pasos 1-3 para las ondas sucesivas de los usuarios

Mientras valida la actualización al modo solo para equipos y está listo para expandir, repita los pasos anteriores para aplicar TeamsOnly a más usuarios.  


## <a name="phone-system-and-teams-upgrade"></a>Actualización de equipos y sistemas telefónicos

Si su implementación de Skype empresarial online incluye sistemas telefónicos con planes de llamadas y Microsoft es su proveedor de redes de telefonía pública conmutada (RTC), la actualización de los usuarios a teams migrará automáticamente las llamadas RTC entrantes a teams.

Si su implementación de Skype empresarial online incluye el sistema telefónico con el conector para Cloud Edition, consulte las [consideraciones adicionales para el enrutamiento directo de sistema telefónico](2-envision-make-my-service-decisions-direct-routing.md).
