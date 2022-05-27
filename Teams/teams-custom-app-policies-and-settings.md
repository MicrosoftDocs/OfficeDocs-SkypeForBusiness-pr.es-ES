---
title: Administrar las directivas y la configuración personalizadas de las aplicaciones
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.reviewer: akino
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Obtenga información sobre cómo administrar la configuración y las directivas de aplicaciones personalizadas para controlar quién en su organización puede cargar aplicaciones personalizadas en Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: 120f19472a0438c6bb76e98e0c8ef473c012c7b7
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681391"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>Administrar configuración y directivas de aplicación personalizadas en Microsoft Teams

> [!NOTE]
> Para usar App Studio, consulta [Comenzar en la plataforma de Microsoft Teams con C#/.NET y App Studio](/microsoftteams/platform/get-started/get-started-dotnet-app-studio) El último paso aún no funciona, por lo que tendrás que descargar el archivo zip e instalarlo de la manera anterior en [Upload un paquete de aplicación a Microsoft Teams](/microsoftteams/platform/concepts/apps/apps-upload).

Como administrador, puede usar la configuración y las directivas de aplicaciones personalizadas para controlar quién en su organización puede cargar aplicaciones personalizadas en Microsoft Teams. Los administradores deciden qué usuarios pueden cargar aplicaciones personalizadas, y los administradores y los propietarios de equipos pueden determinar si determinados equipos de su organización permiten que se agreguen aplicaciones personalizadas.  Después de editar la directiva de aplicación personalizada, los cambios pueden tardar unas horas en surtir efecto. Debe ser un administrador global o un administrador de servicio de Teams para administrar estas directivas.

## <a name="overview-of-custom-apps"></a>Información general sobre aplicaciones personalizadas

Los usuarios pueden agregar una aplicación personalizada a Teams cargando un paquete de aplicación (en un archivo de .zip) directamente a un equipo o en el contexto personal. Esto es diferente de cómo se agregan las aplicaciones a través de la tienda de aplicaciones de Teams. Agregar una aplicación personalizada cargando un paquete de aplicación, también conocido como instalación de prueba, te permite probar una aplicación mientras se está desarrollando, antes de que esté lista para distribuirse ampliamente. También le permite crear una aplicación solo para uso interno y compartirla con su equipo sin enviarla al catálogo de aplicaciones Teams de la tienda de aplicaciones de Teams.

![Captura de pantalla que muestra la opción cargar una aplicación personalizada en la tienda de aplicaciones.](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>Configuración y directiva de aplicación personalizada

Tres componentes determinan si un usuario puede cargar una aplicación personalizada a un equipo, lo que le ofrece un control pormenorizada sobre quién puede agregar aplicaciones personalizadas a un equipo y a qué aplicaciones personalizadas de teams se pueden agregar:

- [Directiva de aplicación personalizada de usuario](#user-custom-app-policy)
- [Configuración de la aplicación personalizada de equipo](#team-custom-app-setting)
- [Configuración de aplicaciones personalizadas para toda la organización](#org-wide-custom-app-setting)

Esta configuración no afecta a la capacidad de bloquear aplicaciones de terceros.  

### <a name="user-custom-app-policy"></a>Directiva de aplicación personalizada de usuario

Como parte de [las directivas de configuración](teams-app-setup-policies.md) de aplicaciones, los administradores pueden usar una configuración de directiva, **Upload aplicaciones personalizadas**, para controlar si un usuario puede cargar aplicaciones personalizadas a Teams.

Si esta opción está desactivada:

- El usuario no puede cargar una aplicación personalizada a ningún equipo de su organización o en el contexto personal.
- El usuario puede interactuar con aplicaciones personalizadas, según la configuración de aplicaciones personalizadas de toda la organización.

Si esta configuración está activada:

- El usuario puede cargar aplicaciones personalizadas a los equipos que lo permitan y a los equipos de los que sean propietarios, según la configuración de aplicaciones personalizadas de toda la organización.
- El usuario puede cargar aplicaciones personalizadas en el contexto personal.
- El usuario puede interactuar con aplicaciones personalizadas, según la configuración de aplicaciones personalizadas de toda la organización.

Puedes editar la configuración de la directiva global de configuración de aplicaciones para incluir las aplicaciones que quieras. Si desea personalizar Teams para diferentes grupos de usuarios de su organización, cree y asigne una o más directivas de configuración de aplicaciones personalizadas.

#### <a name="set-a-user-custom-app-policy"></a>Establecer una directiva de aplicación personalizada de usuario

1. En el panel de navegación izquierdo del centro de administración de Microsoft Teams, vaya a Directivas de **configuración** de **Teams aplicaciones** > .
2. Haga clic en **Agregar**.
3. Activa o desactiva **Upload aplicaciones personalizadas**.
4. Elija cualquier otra configuración que desee para la directiva.
5. Haga clic en **Guardar**.

### <a name="team-custom-app-setting"></a>Configuración de la aplicación personalizada de equipo

Los administradores y los propietarios de equipos pueden controlar si un equipo permite agregar aplicaciones personalizadas a este. Esta configuración, **Permitir que los miembros carguen aplicaciones personalizadas**, junto con la directiva de aplicación personalizada de un usuario, determina quién puede agregar aplicaciones personalizadas a un equipo determinado.

Si esta opción está desactivada:

- Los propietarios de equipos pueden agregar aplicaciones personalizadas, si su directiva de aplicación personalizada lo permite.
- Los miembros del equipo que no sean propietarios del equipo no pueden agregar aplicaciones personalizadas al equipo.

Si esta configuración está activada:

- Los propietarios de equipos pueden agregar aplicaciones personalizadas, si su directiva de aplicación personalizada lo permite.
- Los miembros del equipo que no sean propietarios del equipo pueden agregar aplicaciones personalizadas, si su directiva de aplicaciones personalizadas lo permite.

#### <a name="configure-the-team-custom-app-setting"></a>Configurar la configuración de la aplicación personalizada del equipo

1. En Teams, vaya al equipo, haga clic en **Más opciones...** >  **Administrar equipo**.
2. Haga clic en **Configuración** y expanda **Permisos de miembro**.
3. Active o desactive la casilla **Permitir que los miembros carguen aplicaciones personalizadas** .

    ![Captura de pantalla que muestra la configuración de la aplicación personalizada del equipo.](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>Configuración de aplicaciones personalizadas para toda la organización

La configuración **Permitir interacción con aplicaciones personalizadas** para toda la organización en la página [Administrar aplicaciones](manage-apps.md) se aplica a todos los usuarios de la organización y rige si pueden cargar o interactuar con aplicaciones personalizadas. Esta configuración actúa como un conmutador maestro de encendido/apagado para la configuración de directivas de aplicación personalizada de usuario y equipo. Está destinado a servir como un interruptor maestro de encendido/apagado durante los eventos de seguridad. Por lo tanto, la configuración de directivas de aplicaciones personalizadas de usuario y equipo no surte efecto a menos que la configuración de la aplicación personalizada de toda la organización esté habilitada incluso si la configuración de directivas de aplicaciones personalizadas del equipo y del usuario están habilitadas.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Configurar la configuración de aplicaciones personalizadas para toda la organización

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **Administrar aplicaciones**.
2. Haga clic en **Configuración de aplicaciones para toda la organización**.
3. En **Aplicaciones personalizadas**, activa o desactiva **Permitir interacción con aplicaciones personalizadas**.

    ![Captura de pantalla que muestra la configuración personalizada de aplicaciones para toda la organización.](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>Cómo funcionan conjuntamente las directivas y la configuración personalizadas de las aplicaciones

Esta tabla resume la configuración y la directiva de aplicaciones personalizadas, cómo funcionan conjuntamente y su efecto combinado en controlar quién en su organización puede cargar aplicaciones personalizadas en Teams.

Por ejemplo, quiere permitir que solo los propietarios del equipo carguen aplicaciones personalizadas en equipos específicos. Establezca lo siguiente:

- Activa la opción **Permitir interacción con aplicaciones personalizadas** en el centro de administración de Microsoft Teams.
- Desactive **Permitir que los miembros carguen aplicaciones personalizadas** para cada equipo al que quiera restringir el acceso.
- Cree y asigne una directiva de configuración de aplicaciones personalizada en el centro de administración de Microsoft Teams con la configuración **de aplicaciones personalizadas Upload** activada y asígnela a los propietarios del equipo.

|Configuración de aplicaciones personalizadas para toda la organización |Configuración de la aplicación personalizada de equipo |Directiva de aplicación personalizada de usuario |Efecto  |
|---------|---------|---------|---------|
| Desactivado    | Desactivado    | Desactivado     |La interacción con todas las aplicaciones personalizadas está bloqueada para su organización. Nadie puede cargar aplicaciones personalizadas excepto un Administración de servicio de Teams o un administrador global. Puede usar PowerShell para quitar la aplicación personalizada.   |
| Desactivado     | Desactivado     | Activado        |La interacción con todas las aplicaciones personalizadas está bloqueada para su organización. Nadie puede cargar aplicaciones personalizadas excepto un Administración de servicio de Teams o un administrador global. Puede usar PowerShell para quitar la aplicación personalizada.         |
| Desactivado    | Activado        | Desactivado        |La interacción con todas las aplicaciones personalizadas está bloqueada para su organización. Nadie puede cargar aplicaciones personalizadas excepto un Administración de servicio de Teams o un administrador global. Puede usar Windows PowerShell para eliminar aplicaciones personalizadas.         |
| Desactivado    | Activado      | Activado       |La interacción con todas las aplicaciones personalizadas está bloqueada para su organización. Nadie puede cargar aplicaciones personalizadas excepto un Administración de servicio de Teams o un administrador global. Puede usar PowerShell para quitar la aplicación personalizada.         |
| Activado    | Desactivado       | Desactivado         |  El usuario no puede cargar aplicaciones personalizadas.      |
| Activado     | Desactivado       | Activado         | Si el usuario es propietario de un equipo, puede cargar aplicaciones personalizadas en el equipo. Si el usuario no es el propietario del equipo, no podrá cargar aplicaciones personalizadas en el equipo. El usuario puede cargar aplicaciones personalizadas en el contexto personal.     |
| Activado     | Activado     | Desactivado         | El usuario no puede cargar aplicaciones personalizadas.       |
| Activado    | Activado        | Activado        | El usuario puede cargar aplicaciones personalizadas al equipo, independientemente de si el usuario es el propietario del equipo. El usuario puede cargar aplicaciones personalizadas en el contexto personal.       |

## <a name="related-topics"></a>Temas relacionados

[Configurar la administración para aplicaciones en Teams](admin-settings.md)

[Asignar directivas a los usuarios en Teams](assign-policies-users-and-groups.md)
