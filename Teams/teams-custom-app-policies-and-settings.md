---
title: Administrar directivas y configuraciones de aplicaciones personalizadas
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: akino
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo administrar las directivas de aplicaciones personalizadas y la configuración para controlar quién en su organización puede cargar aplicaciones personalizadas en Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: 4e9863508d7b10c76ed29bfcb0fec79ca7a33dc5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821010"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>Administrar configuración y directivas de aplicación personalizadas en Microsoft Teams

> [!NOTE]
> Para usar App Studio, vea Introducción en la plataforma de Microsoft Teams con [C#/.NET](https://docs.microsoft.com/microsoftteams/platform/get-started/get-started-dotnet-app-studio) y App Studio El último paso no funciona todavía, por lo que tendrá que descargar el archivo zip e instalarlo a la antigua forma en Cargar un paquete de aplicación en [Microsoft Teams.](https://docs.microsoft.com/microsoftteams/platform/concepts/apps/apps-upload)

Como administrador, puede usar las directivas de aplicación personalizadas y la configuración para controlar quién en su organización puede cargar aplicaciones personalizadas a Microsoft Teams. Los administradores deciden qué usuarios pueden cargar aplicaciones personalizadas, y los administradores y propietarios de equipos pueden determinar si determinados equipos de su organización permiten que se les agregó aplicaciones personalizadas.  Después de editar la directiva de aplicación personalizada, los cambios pueden tardar unas horas en tener efecto. Debe ser un administrador global o un administrador de servicio de Teams para administrar estas directivas.

## <a name="overview-of-custom-apps"></a>Información general sobre aplicaciones personalizadas

Los usuarios pueden agregar una aplicación personalizada a Teams cargando un paquete de aplicación (en un archivo .zip) directamente en un equipo o en el contexto personal. Esto es diferente de cómo se agregan las aplicaciones a través de la tienda de aplicaciones de Teams. Agregar una aplicación personalizada mediante la carga de un paquete de aplicación, también conocido como instalación de prueba, le permite probar una aplicación mientras se está desarrollando, antes de que esté lista para distribuirse ampliamente. También le permite crear una aplicación solo para uso interno y compartirla con su equipo sin enviarla al catálogo de aplicaciones de Teams en la tienda de aplicaciones de Teams.

![Captura de pantalla que muestra la opción cargar una aplicación personalizada en la tienda de aplicaciones](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>Configuración y directiva de aplicación personalizada

Tres componentes determinan si un usuario puede cargar una aplicación personalizada a un equipo, lo que le ofrece control pormenorizado sobre quién puede agregar aplicaciones personalizadas a un equipo y a qué aplicaciones personalizadas de Teams se puede agregar:

- [Directiva de aplicación personalizada de usuario](#user-custom-app-policy)
- [Configuración de la aplicación personalizada de equipo](#team-custom-app-setting)
- [Configuración de aplicaciones personalizadas para toda la organización](#org-wide-custom-app-setting)

Esta configuración no afecta a la capacidad de bloquear aplicaciones de terceros.  

### <a name="user-custom-app-policy"></a>Directiva de aplicación personalizada de usuario

Como parte de las directivas de [configuración de](teams-app-setup-policies.md)aplicaciones, los administradores pueden usar una configuración de **directiva,** Cargar aplicaciones personalizadas, para controlar si un usuario puede cargar aplicaciones personalizadas en Teams.
 
Si esta configuración está desactivada:

- El usuario no puede cargar una aplicación personalizada a ningún equipo de su organización o en el contexto personal.
- El usuario puede interactuar con aplicaciones personalizadas, dependiendo de la configuración de la aplicación personalizada para toda la organización.

Si esta configuración está activada:

- El usuario puede cargar aplicaciones personalizadas a los equipos que las permiten y a los equipos para los que son propietarios, en función de la configuración de la aplicación personalizada para toda la organización.
- El usuario puede cargar aplicaciones personalizadas en el contexto personal. 
- El usuario puede interactuar con aplicaciones personalizadas, dependiendo de la configuración de la aplicación personalizada para toda la organización.

Puede editar la configuración en la directiva global de configuración de aplicaciones para incluir las aplicaciones que desee. Si desea personalizar Teams para distintos grupos de usuarios de su organización, cree y asigne una o más directivas de configuración de aplicaciones personalizadas.

#### <a name="set-a-user-custom-app-policy"></a>Establecer una directiva de aplicación personalizada de usuario

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a directivas **de configuración** de aplicaciones  >  **de** Teams.
2. Haga clic en **Agregar**.
3. Activar o desactivar Cargar **aplicaciones personalizadas.**
4. Elija cualquier otra configuración que quiera para la directiva.
5. Haga clic en **Guardar**.

### <a name="team-custom-app-setting"></a>Configuración de la aplicación personalizada de equipo

Los administradores y los propietarios del equipo pueden controlar si un equipo permite agregar aplicaciones personalizadas a este. Esta configuración, Permitir que los miembros **carguen** aplicaciones personalizadas, junto con la directiva de aplicación personalizada de un usuario determina quién puede agregar aplicaciones personalizadas a un equipo en particular.
 
Si esta configuración está desactivada:

- Los propietarios del equipo pueden agregar aplicaciones personalizadas, si su directiva de aplicación personalizada lo permite.
- Los miembros del equipo que no sean propietarios del equipo no pueden agregar aplicaciones personalizadas al equipo.

Si esta configuración está activada:

- Los propietarios del equipo pueden agregar aplicaciones personalizadas, si su directiva de aplicación personalizada lo permite.
- Los miembros del equipo que no sean propietarios del equipo pueden agregar aplicaciones personalizadas, si su directiva de aplicación personalizada lo permite.

#### <a name="configure-the-team-custom-app-setting"></a>Configurar la configuración de la aplicación personalizada de grupo

1. En Teams, vaya al equipo, haga clic en **Más opciones además de administrar**  >  **equipo.**
2. Haga **clic en Configuración** y, a continuación, expanda Permisos de **miembro.**
3. Active o desactive la casilla **Permitir que los miembros carguen aplicaciones personalizadas.**

    ![Captura de pantalla que muestra la configuración de la aplicación personalizada del equipo](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>Configuración de aplicaciones personalizadas para toda la organización

La **opción Permitir interacción** con aplicaciones personalizadas [](manage-apps.md) para toda la organización en la página Administrar aplicaciones se aplica a todos los usuarios de la organización y rige si pueden cargar o interactuar con aplicaciones personalizadas. Esta configuración actúa como un modificador maestro para la configuración de directivas de aplicaciones personalizadas de usuario y equipo. Está destinado a servir como un maestro en activar o desactivar durante los eventos de seguridad. Por lo tanto, la configuración de directivas de aplicaciones personalizadas para usuarios y equipos no se aplica a menos que la configuración de la aplicación personalizada para toda la organización esté habilitada incluso si la configuración de directivas de aplicación personalizadas de usuario y equipo están habilitadas.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Configurar la configuración de la aplicación personalizada para toda la organización

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Administrar aplicaciones**  >  **de** Teams.
2. Haga clic **en configuración de aplicaciones para toda la organización.**
3. En **Aplicaciones personalizadas,** active o desactive Permitir la **interacción con aplicaciones personalizadas.**

    ![Captura de pantalla que muestra la configuración de la aplicación personalizada para toda la organización](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>Cómo funcionan conjuntamente las directivas y la configuración de aplicaciones personalizadas

Esta tabla resume la configuración y la directiva de aplicaciones personalizadas, cómo funcionan de forma conjunta y su efecto combinado en controlar quién en su organización puede cargar aplicaciones personalizadas a Teams.

Por ejemplo, quiere permitir que solo los propietarios de equipos carguen aplicaciones personalizadas a equipos específicos. Tendría que establecer lo siguiente:
- Active la opción **Permitir interacción con aplicaciones personalizadas** en el Centro de administración de Microsoft Teams.
- Desactive la opción **Permitir que los miembros carguen** aplicaciones personalizadas para cada equipo al que desee restringir el acceso.
- Cree y asigne una directiva de configuración de  aplicaciones personalizada en el Centro de administración de Microsoft Teams con la opción Cargar aplicaciones personalizadas activada y asígnela a los propietarios del equipo.

|Configuración de aplicaciones personalizadas para toda la organización |Configuración de la aplicación personalizada de equipo |Directiva de aplicación personalizada de usuario |Efecto  |
|---------|---------|---------|---------|
| Desactivado    | Desactivado    | Desactivado     |La interacción con todas las aplicaciones personalizadas está bloqueada para la organización. Nadie puede cargar aplicaciones personalizadas excepto un administrador de servicios de Teams o un administrador global. Puede usar PowerShell para quitar la aplicación personalizada.   |
| Desactivado     | Desactivado     | Activado        |La interacción con todas las aplicaciones personalizadas está bloqueada para tu organización. Nadie puede cargar aplicaciones personalizadas excepto un administrador de servicios de Teams o un administrador global. Puede usar PowerShell para quitar la aplicación personalizada.         |
| Desactivado    | Activado        | Desactivado        |La interacción con todas las aplicaciones personalizadas está bloqueada para tu organización. Nadie puede cargar aplicaciones personalizadas excepto un administrador de servicios de Teams o un administrador global. Puede usar Windows PowerShell para eliminar aplicaciones personalizadas.         |
| Desactivado    | Activado      | Activado       |La interacción con todas las aplicaciones personalizadas está bloqueada para la organización. Nadie puede cargar aplicaciones personalizadas excepto un administrador de servicios de Teams o un administrador global. Puede usar PowerShell para quitar la aplicación personalizada.         |
| Activado    | Desactivado       | Desactivado         |  El usuario no puede cargar aplicaciones personalizadas.      |
| Activado     | Desactivado       | Activado         | Si el usuario es propietario de un equipo, puede cargar aplicaciones personalizadas al equipo. Si el usuario no es el propietario de un equipo, no podrá cargar aplicaciones personalizadas en el equipo. El usuario puede cargar aplicaciones personalizadas en el contexto personal.     |
| Activado     | Activado     | Desactivado         | El usuario no puede cargar aplicaciones personalizadas.       |
| Activado    | Activado        | Activado        | El usuario puede cargar aplicaciones personalizadas al equipo, independientemente de si es el propietario del equipo. El usuario puede cargar aplicaciones personalizadas en el contexto personal.       |

## <a name="related-topics"></a>Temas relacionados
 
[Configurar la administración para aplicaciones en Teams](admin-settings.md)

[Asignar directivas a los usuarios en Teams](assign-policies.md)