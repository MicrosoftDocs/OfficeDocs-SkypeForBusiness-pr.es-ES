---
title: Administrar las directivas y la configuración de aplicaciones personalizadas
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
description: Obtenga información sobre cómo administrar las directivas y la configuración de aplicaciones personalizadas para controlar quién en su organización puede cargar aplicaciones personalizadas en Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: b2225429eee73ecd5c6b33b62d4d1be24da306b9
ms.sourcegitcommit: c7b95254dec4420ba0a697fd49d11b448364c919
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/11/2022
ms.locfileid: "63442546"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>Administrar configuración y directivas de aplicación personalizadas en Microsoft Teams

> [!NOTE]
> Para usar App Studio, vea Introducción a la plataforma [de Microsoft Teams con C#/.NET y App Studio](/microsoftteams/platform/get-started/get-started-dotnet-app-studio) El último paso aún no funciona, por lo que tendrá que descargar el archivo zip e instalarlo de la forma antigua en Upload un paquete de aplicación [para Microsoft Teams](/microsoftteams/platform/concepts/apps/apps-upload).

Como administrador, puede usar las directivas y la configuración de aplicaciones personalizadas para controlar quién de su organización puede cargar aplicaciones personalizadas en Microsoft Teams. Los administradores deciden qué usuarios pueden cargar aplicaciones personalizadas, y los administradores y los propietarios de equipos pueden determinar si determinados equipos de su organización permiten agregarles aplicaciones personalizadas.  Después de editar la directiva de aplicación personalizada, los cambios pueden tardar unas horas en tener efecto. Debe ser un administrador global o un administrador de servicio de Teams para administrar estas directivas.

## <a name="overview-of-custom-apps"></a>Información general sobre las aplicaciones personalizadas

Los usuarios pueden agregar una aplicación personalizada a Teams cargando un paquete de aplicación (en un archivo .zip) directamente a un equipo o en el contexto personal. Esto es diferente de cómo se agregan las aplicaciones a través de Teams de aplicaciones. Agregar una aplicación personalizada cargando un paquete de aplicación, también conocido como sideloading, le permite probar una aplicación a medida que se está desarrollando, antes de que esté lista para distribuirse ampliamente. También le permite crear una aplicación solo para uso interno y compartirla con su equipo sin enviarla al catálogo de aplicaciones de Teams en el Teams de aplicaciones.

![Captura de pantalla que muestra la opción cargar una aplicación personalizada en la tienda de aplicaciones.](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>Configuración y directiva de aplicaciones personalizadas

Tres componentes determinan si un usuario puede cargar una aplicación personalizada a un equipo, lo que le da un control granular sobre quién puede agregar aplicaciones personalizadas a un equipo y a qué equipos se pueden agregar aplicaciones personalizadas:

- [Directiva de aplicación personalizada de usuario](#user-custom-app-policy)
- [Configuración de la aplicación personalizada de equipo](#team-custom-app-setting)
- [Configuración de aplicaciones personalizadas para toda la organización](#org-wide-custom-app-setting)

Esta configuración no afecta a la capacidad de bloquear aplicaciones de terceros.  

### <a name="user-custom-app-policy"></a>Directiva de aplicación personalizada de usuario

Como parte de las directivas [de configuración](teams-app-setup-policies.md) de aplicaciones, los administradores pueden usar una configuración de **directiva, Upload** aplicaciones personalizadas, para controlar si un usuario puede cargar aplicaciones personalizadas en Teams.

Si esta configuración está desactivada:

- El usuario no puede cargar una aplicación personalizada a ningún equipo de su organización o en el contexto personal.
- El usuario puede interactuar con aplicaciones personalizadas, dependiendo de la configuración de la aplicación personalizada de toda la organización.

Si esta configuración está activada:

- El usuario puede cargar aplicaciones personalizadas a los equipos que lo permiten y a los equipos cuyos propietarios sean, según la configuración de la aplicación personalizada de toda la organización.
- El usuario puede cargar aplicaciones personalizadas en el contexto personal.
- El usuario puede interactuar con aplicaciones personalizadas, dependiendo de la configuración de la aplicación personalizada de toda la organización.

Puede editar la configuración de la directiva de configuración global de la aplicación para incluir las aplicaciones que desee. Si desea personalizar los Teams diferentes grupos de usuarios de su organización, cree y asigne una o más directivas de configuración de aplicaciones personalizadas.

#### <a name="set-a-user-custom-app-policy"></a>Establecer una directiva de aplicación personalizada de usuario

1. En el panel de navegación izquierdo del centro Microsoft Teams de administración, vaya a Teams **de aplicacionessetup** > .
2. Haga clic en **Agregar**.
3. Activa o desactiva Upload **aplicaciones personalizadas**.
4. Elija cualquier otra configuración que desee para la directiva.
5. Haga clic en **Guardar**.

### <a name="team-custom-app-setting"></a>Configuración de la aplicación personalizada de equipo

Los administradores y los propietarios de equipos pueden controlar si un equipo permite que se le agregó aplicaciones personalizadas. Esta **configuración permite a** los miembros cargar aplicaciones personalizadas, junto con la directiva de aplicación personalizada de un usuario determina quién puede agregar aplicaciones personalizadas a un equipo en particular.

Si esta configuración está desactivada:

- Los propietarios de equipos pueden agregar aplicaciones personalizadas, si su directiva de aplicación personalizada lo permite.
- Los miembros del equipo que no son propietarios de equipos no pueden agregar aplicaciones personalizadas al equipo.

Si esta configuración está activada:

- Los propietarios de equipos pueden agregar aplicaciones personalizadas, si su directiva de aplicación personalizada lo permite.
- Los miembros del equipo que no son propietarios de equipos pueden agregar aplicaciones personalizadas, si su directiva de aplicación personalizada lo permite.

#### <a name="configure-the-team-custom-app-setting"></a>Configurar la configuración de la aplicación personalizada del equipo

1. En Teams, vaya al equipo, haga clic en **Más opciones** > 
2. Haga **clic Configuración** y, a continuación, expanda **Permisos de miembro**.
3. Active o desactive la casilla Permitir que **los miembros carguen aplicaciones** personalizadas.

    ![Captura de pantalla que muestra la configuración de la aplicación personalizada del equipo.](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>Configuración de aplicaciones personalizadas para toda la organización

La **configuración Permitir interacción** con aplicaciones personalizadas personalizadas para toda la organización [](manage-apps.md) en la página Administrar aplicaciones se aplica a todos los usuarios de su organización y rige si pueden cargar o interactuar con aplicaciones personalizadas. Esta configuración actúa como un modificador principal de encendido y apagado para la configuración de directiva de aplicación personalizada de usuario y equipo. Está pensado para servir como un modificador de encendido y apagado principal durante los eventos de seguridad. Por lo tanto, la configuración de directiva de aplicación personalizada de usuario y equipo no tendrá efecto a menos que la configuración de la aplicación personalizada de toda la organización esté habilitada incluso si la configuración de directiva de aplicación personalizada de usuario y equipo está habilitada.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Configurar la configuración de la aplicación personalizada para toda la organización

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **Administrar aplicaciones**.
2. Haga clic **en Configuración de la aplicación para toda la organización**.
3. En **Aplicaciones personalizadas**, activa o desactiva **Permitir interacción con aplicaciones personalizadas**.

    ![Captura de pantalla que muestra la configuración de la aplicación personalizada para toda la organización.](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>Cómo funcionan conjuntamente las directivas y la configuración de aplicaciones personalizadas

En esta tabla se resumen la configuración y la directiva de aplicaciones personalizadas, cómo funcionan conjuntamente y su efecto combinado al controlar quién de su organización puede cargar aplicaciones personalizadas a Teams.

Por ejemplo, quiere permitir que solo los propietarios de equipos carguen aplicaciones personalizadas en equipos específicos. Establecería lo siguiente:

- Active la configuración **Permitir interacción con aplicaciones** personalizadas en el centro Microsoft Teams administración.
- Desactive permitir que **los miembros carguen aplicaciones personalizadas** para todos los equipos a los que quiera restringir el acceso.
- Cree y asigne una directiva de configuración de aplicaciones personalizada en el centro de administración de Microsoft Teams con la configuración de aplicaciones personalizadas de Upload activada y asígnela **a** los propietarios del equipo.

|Configuración de aplicaciones personalizadas para toda la organización |Configuración de la aplicación personalizada de equipo |Directiva de aplicación personalizada de usuario |Efecto  |
|---------|---------|---------|---------|
| Desactivado    | Desactivado    | Desactivado     |La interacción con todas las aplicaciones personalizadas está bloqueada para su organización. Las aplicaciones personalizadas no se pueden cargar por nadie excepto un administrador Teams servicio o un administrador global. Puede usar PowerShell para quitar la aplicación personalizada.   |
| Desactivado     | Desactivado     | Activado        |La interacción con todas las aplicaciones personalizadas está bloqueada para su organización. Las aplicaciones personalizadas no se pueden cargar por nadie excepto un administrador Teams servicio o un administrador global. Puede usar PowerShell para quitar la aplicación personalizada.         |
| Desactivado    | Activado        | Desactivado        |La interacción con todas las aplicaciones personalizadas está bloqueada para su organización. Las aplicaciones personalizadas no se pueden cargar por nadie excepto un administrador Teams servicio o un administrador global. Puede usar Windows PowerShell para eliminar aplicaciones personalizadas.         |
| Desactivado    | Activado      | Activado       |La interacción con todas las aplicaciones personalizadas está bloqueada para su organización. Las aplicaciones personalizadas no se pueden cargar por nadie excepto un administrador Teams servicio o un administrador global. Puede usar PowerShell para quitar la aplicación personalizada.         |
| Activado    | Desactivado       | Desactivado         |  El usuario no puede cargar aplicaciones personalizadas.      |
| Activado     | Desactivado       | Activado         | Si el usuario es el propietario del equipo, puede cargar aplicaciones personalizadas en el equipo. Si el usuario no es el propietario del equipo, no podrá cargar aplicaciones personalizadas en el equipo. El usuario puede cargar aplicaciones personalizadas en el contexto personal.     |
| Activado     | Activado     | Desactivado         | El usuario no puede cargar aplicaciones personalizadas.       |
| Activado    | Activado        | Activado        | El usuario puede cargar aplicaciones personalizadas en el equipo, independientemente de si el usuario es el propietario del equipo. El usuario puede cargar aplicaciones personalizadas en el contexto personal.       |

## <a name="related-topics"></a>Temas relacionados

[Configurar la administración para aplicaciones en Teams](admin-settings.md)

[Asignar directivas a los usuarios en Teams](assign-policies-users-and-groups.md)
