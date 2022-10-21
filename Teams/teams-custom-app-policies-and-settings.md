---
title: Administrar directivas de aplicación personalizadas
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.subservice: teams-apps
ms.service: msteams
audience: Admin
ms.date: 09/26/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre cómo administrar la configuración y las directivas de aplicaciones personalizadas para poder controlar qué usuarios de la organización pueden cargar aplicaciones personalizadas en Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: 2bbd6d048fdb3e2f0a0d4f9723552127161d25f8
ms.sourcegitcommit: 1161cddd077056a9c1e2da99a84e35be0380b1b1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "68656016"
---
# <a name="manage-custom-apps-and-settings-in-teams-admin-center"></a>Administrar aplicaciones y configuraciones personalizadas en el Centro de administración de Teams

<!--- TBD: Describe custom apps
--->

Como administrador de Teams, puede usar directivas y configuraciones de aplicaciones personalizadas para controlar quién en su organización puede cargar aplicaciones personalizadas en Microsoft Teams. Los administradores deciden qué usuarios pueden cargar aplicaciones personalizadas y los administradores y propietarios de equipos pueden determinar si ciertos equipos de la organización permiten que se les agreguen aplicaciones personalizadas. Al editar la directiva de aplicación personalizada, los cambios pueden tardar unas horas en surtir efecto. Para administrar estas directivas, debe ser administrador global de Administración o teams.

Los desarrolladores de su organización pueden agregar una aplicación personalizada a Teams si cargan un paquete de aplicación (en un archivo .zip) directamente en un equipo o en el ámbito personal. Esto difiere de la forma en que se agregan las aplicaciones a través de la tienda de aplicaciones de Teams. Cargar un paquete de aplicación para agregar una aplicación personalizada, también conocido como instalación de prueba, permite a usuarios específicos de la organización probar una aplicación antes de que esté lista para distribuirse de forma amplia.

Durante la creación de una aplicación, los desarrolladores crean y agregan un identificador de aplicación al archivo de manifiesto. Puede ver esta identificación de aplicación externa en la página Administrar aplicaciones después de habilitar la columna `External app ID` desde la configuración de columna. También puede verlo en la página de detalles de la aplicación de una aplicación personalizada. La identificación solo es aplicable a aplicaciones personalizadas.

## <a name="custom-app-policy-and-settings"></a>Configuración y directiva de aplicaciones personalizadas

Tres configuraciones determinan si un usuario puede cargar una aplicación personalizada a un equipo. Proporciona a los administradores un control pormenorizada sobre quién puede agregar aplicaciones personalizadas a un equipo y a qué aplicaciones personalizadas de los equipos se pueden agregar. Esta configuración no afecta a la capacidad de bloquear aplicaciones de terceros.

* [Directiva de aplicación personalizada de usuario](#user-custom-app-policy)
* [Configuración de la aplicación personalizada de equipo](#team-custom-app-setting)
* [Configuración de la aplicación personalizada de toda la organización](#org-wide-custom-app-setting)

### <a name="user-custom-app-policy"></a>Directiva de aplicación personalizada de usuario

Como parte de [las directivas de configuración](teams-app-setup-policies.md) de aplicaciones, los administradores pueden usar la opción **Cargar aplicaciones personalizadas** para controlar si un usuario puede cargar aplicaciones personalizadas en Teams.

Si esta configuración está desactivada:

* El usuario no podrá cargar una aplicación personalizada en ningún equipo de su organización ni en el ámbito personal.
* El usuario puede interactuar con aplicaciones personalizadas en función de la configuración de aplicación personalizada de toda la organización.

Si la configuración está activada:

* El usuario puede cargar aplicaciones personalizadas a los equipos que lo permiten y a los equipos de los que son propietarios, en función de la configuración de aplicación personalizada de toda la organización.
* El usuario puede cargar aplicaciones personalizadas en el ámbito personal.
* El usuario puede interactuar con aplicaciones personalizadas en función de la configuración de aplicación personalizada de toda la organización.

Puede editar la configuración en la directiva de configuración de aplicaciones global para incluir las aplicaciones que desee. Si desea personalizar Teams para distintos grupos de usuarios de la organización, puede crear y asignar una o más directivas de configuración de aplicación personalizadas.

#### <a name="set-a-user-custom-app-policy"></a>Establecer una directiva de aplicación personalizada de usuario

1. Inicie sesión en el Centro de administración de Teams y acceda a las **directivas****[de configuración de](https://admin.teams.microsoft.com/policies/app-setup)** aplicaciones  >  de Teams.
1. Seleccione **Agregar**.
1. Active o desactive **Cargar aplicaciones personalizadas**.
1. Elija cualquier otra opción de configuración que desee para la directiva.
1. Seleccione **Guardar**.

### <a name="team-custom-app-setting"></a>Configuración de la aplicación personalizada de equipo

Los administradores y los propietarios de equipos pueden controlar si un equipo permite que se le agreguen aplicaciones personalizadas. La configuración **Permitir que los miembros carguen aplicaciones personalizadas** junto con la directiva de aplicación personalizada de un usuario, determina quién puede agregar aplicaciones personalizadas a un equipo determinado.

Si esta configuración está desactivada:

* Los propietarios de equipos pueden agregar aplicaciones personalizadas si su directiva de aplicación personalizada lo permite.
* Los miembros del equipo que no sean propietarios del mismo no podrán agregar aplicaciones personalizadas al equipo.

Si la configuración está activada:

* Los propietarios de equipos pueden agregar aplicaciones personalizadas si su directiva de aplicación personalizada se los permite.
* Los miembros del equipo que no sean propietarios del mismo pueden agregar aplicaciones personalizadas si su directiva de aplicaciones personalizadas se los permite.

#### <a name="configure-the-team-custom-app-setting"></a>Establecer la configuración de aplicación personalizada de equipo

1. En Teams, vaya a un equipo y seleccione **Más opciones...** >  **Administrar equipo**.
1. Seleccione **Configuración** y expanda **Permisos de miembro**.
1. Active o desactive la casilla **Permitir que los miembros carguen aplicaciones personalizadas**.

   :::image type="content" source="media/teams-custom-app-policy-and-settings-team-trim.png" alt-text="Captura de pantalla que muestra la configuración de la aplicación personalizada de equipo." lightbox="media/teams-custom-app-policy-and-settings-team.png":::

### <a name="org-wide-custom-app-setting"></a>Configuración de la aplicación personalizada de toda la organización

La configuración de aplicación personalizada **Permitir interacción con aplicaciones personalizadas** de toda la organización en la página [Administrar aplicaciones](manage-apps.md) se aplica a todos los usuarios de la organización y rige si dichos usuarios pueden cargar aplicaciones personalizadas o interactuar con las mismas. Esta configuración actúa como un conmutador maestro de activación y desactivación para la configuración de directiva de aplicación personalizada tanto de usuario como de equipo. Está diseñado para que actúe como un conmutador maestro de activación y desactivación durante los eventos de seguridad. Por lo tanto, la configuración de directiva de aplicaciones personalizadas de usuario y de equipo no surtirá efecto a menos que se habilite la configuración de aplicación personalizada de toda la organización, aunque la configuración de directiva de aplicaciones personalizadas de usuario y de equipo estén habilitadas.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Establecer la configuración de aplicaciones personalizadas de toda la organización

1. Inicie sesión en el Centro de administración de Teams y acceda a **las aplicaciones** > **[de Teams Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)**.
1. Seleccione **Configuración de aplicaciones para toda la organización**.
1. En **Aplicaciones personalizadas**, active o desactive **Permitir interacción con aplicaciones personalizadas**.

    :::image type="content" source="media/teams-custom-app-policy-and-settings-org-wide.png" alt-text="Captura de pantalla que muestra la configuración de aplicación personalizada de toda la organización.":::

## <a name="how-custom-app-policies-and-settings-work-together"></a>Cómo funcionan conjuntamente las directivas y la configuración de aplicaciones personalizadas

En esta tabla se resumen la configuración y la directiva de aplicaciones personalizadas, cómo funcionan conjuntamente y el efecto combinado que ejercen para controlar qué usuarios de la organización pueden cargar aplicaciones personalizadas en Teams.

Imaginemos que quiere permitir que solo los propietarios de los equipos carguen aplicaciones personalizadas en equipos específicos. Debe establecer lo siguiente:

* Active la opción **Permitir interacción con aplicaciones personalizadas** en el centro de administración de Microsoft Teams.
* Desactive la opción **Permitir que los miembros carguen aplicaciones personalizadas** para cada equipo al que quiera restringir el acceso.
* Cree y asigne una directiva personalizada en la directiva de configuración de aplicaciones en el Centro de administración de Microsoft Teams con la opción **Cargar aplicaciones personalizadas** activada y asígnela a los propietarios del equipo.

|Configuración de la aplicación personalizada de toda la organización |Configuración de la aplicación personalizada de equipo |Directiva de aplicación personalizada de usuario |Efecto  |
|---------|---------|---------|---------|
| Desactivado    | Desactivado    | Desactivado     |La interacción con todas las aplicaciones personalizadas está bloqueada para su organización. Ningún usuario puede cargar aplicaciones personalizadas excepto un Administrador de servicios de Teams o un Administrador global. Puede usar PowerShell para quitar la aplicación personalizada.   |
| Desactivado     | Desactivado     | Activado        |La interacción con todas las aplicaciones personalizadas está bloqueada para su organización. Ningún usuario puede cargar aplicaciones personalizadas excepto un Administrador de servicios de Teams o un Administrador global. Puede usar PowerShell para quitar la aplicación personalizada.         |
| Desactivado    | Activado        | Desactivado        |La interacción con todas las aplicaciones personalizadas está bloqueada para su organización. Ningún usuario puede cargar aplicaciones personalizadas excepto un Administrador de servicios de Teams o un Administrador global. Puede usar PowerShell para eliminar la aplicación personalizada.         |
| Desactivado    | Activado      | Activado       |La interacción con todas las aplicaciones personalizadas está bloqueada para su organización. Ningún usuario puede cargar aplicaciones personalizadas excepto un Administrador de servicios de Teams o un Administrador global. Puede usar PowerShell para quitar la aplicación personalizada.         |
| Activado    | Desactivado       | Desactivado         |  El usuario no puede cargar aplicaciones personalizadas.      |
| Activado     | Desactivado       | Activado         | Si el usuario es un propietario del equipo, puede cargar aplicaciones personalizadas en el equipo. Si el usuario no es un propietario del equipo, no podrá cargar aplicaciones personalizadas en el equipo. El usuario puede cargar aplicaciones personalizadas en el ámbito personal.     |
| Activado     | Activado     | Desactivado         | El usuario no puede cargar aplicaciones personalizadas.       |
| Activado    | Activado        | Activado        | El usuario puede cargar aplicaciones personalizadas en el equipo, independientemente de si el usuario es el propietario del equipo. El usuario puede cargar aplicaciones personalizadas en el ámbito personal.       |

## <a name="related-articles"></a>Artículos relacionados

* [Administración la configuración de las aplicaciones en Teams](admin-settings.md).
* [Asigne directivas a los usuarios en Teams](assign-policies-users-and-groups.md).
