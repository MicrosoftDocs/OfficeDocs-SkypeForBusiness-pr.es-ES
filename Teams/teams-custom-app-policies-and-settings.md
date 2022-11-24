---
title: Administrar la configuración y las directivas de aplicación personalizadas y de instalación de prueba
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
ms.localizationpriority: high
search.appverid: MET150
description: Aprende a administrar las directivas y la configuración para controlar quién en tu organización puede realizar instalaciones de prueba de aplicaciones y cargar aplicaciones personalizadas.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.allowsideloading
- ms.teamsadmincenter.appsetuppolicies.tooltip.allowsideloading
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- seo-marvel-mar2020
ms.openlocfilehash: 818d9b8a64f4a80d8838e368d837a501123976e6
ms.sourcegitcommit: d95a3408e31d3dec37c534c110b09a8847bec724
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2022
ms.locfileid: "69156816"
---
# <a name="manage-custom-and-sideloaded-apps-in-teams-admin-center"></a>Administrar aplicaciones personalizadas y de instalación de prueba en el Centro de administración de Teams

Microsoft Teams permite a los desarrolladores de su organización crear, probar e implementar aplicaciones personalizadas para los usuarios internos de la organización. Estas aplicaciones se denominan aplicaciones personalizadas o aplicaciones de línea de negocio (LOB). Su organización puede encargar la creación de aplicaciones personalizadas para los requisitos específicos de la organización. Los administradores controlan la implementación de y los permisos de las aplicaciones personalizadas mediante diversas configuraciones y directivas.

:::image type="content" source="media/custom-app-orgwide-setting-trimmed.png" alt-text="Recorte de pantalla que muestra cómo permitir aplicaciones personalizadas en la organización en el panel de configuración de toda la organización." lightbox="media/custom-app-orgwide-setting.png":::

Después de permitir el uso de una aplicación personalizada, los usuarios finales pueden encontrarla seleccionando **Creado para su organización** en el panel de navegación izquierdo de la tienda de Teams.

:::image type="content" source="media/built-for-your-org1.png" alt-text="Captura de pantalla de aplicaciones personalizadas en la tienda de Teams en la aplicación de escritorio de Teams." lightbox="media/built-for-your-org2.png":::

Como administrador de Teams, puede usar directivas y configuraciones de aplicaciones personalizadas para controlar quién en su organización puede cargar aplicaciones personalizadas en Microsoft Teams. Los administradores deciden qué usuarios pueden cargar aplicaciones personalizadas y los administradores y propietarios de equipos pueden determinar si ciertos equipos de la organización permiten que se les agreguen aplicaciones personalizadas. Después de editar la directiva de configuración de las aplicaciones personalizadas, los cambios tardan unas horas en surtir efecto. Para administrar estas directivas, debe ser administrador global de Administración o teams.

Los desarrolladores de su organización pueden agregar una aplicación personalizada a Teams si cargan un paquete de aplicación (en un archivo .zip) directamente en un equipo o en el ámbito personal. Este método es diferente de cómo se agregan las aplicaciones a través de la tienda de aplicaciones de Teams. Cargar un paquete de aplicación para agregar una aplicación personalizada, también conocido como instalación de prueba, permite a usuarios específicos de la organización probar una aplicación antes de que esté lista para distribuirse de forma amplia.

<!--- During the creation of an app, the developers create and add an app ID to the manifest file. You can view this external app ID on the Manage apps page after you enable the column `External app ID` from the column settings. You can also view it on the app details page of a custom app. The ID is applicable for custom apps only. --->

## <a name="understand-sideloading-of-custom-apps"></a>Descripción de la instalación de prueba de aplicaciones personalizadas

Al desarrollar aplicaciones personalizadas y antes de distribuirlas a los usuarios finales, los desarrolladores prueban las aplicaciones agregándolas a la Tienda Teams para probarlas. Los desarrolladores pueden realizar pruebas por su cuenta o con un grupo específico de usuarios, pero la aplicación no está disponible para otros usuarios finales de la organización a través de store. Este método se denomina instalación de prueba de aplicaciones y solo se aplica a aplicaciones personalizadas.

Los desarrolladores pueden transferir localmente una aplicación para que esté disponible para los miembros de un equipo específico, normalmente cuando se prueba una aplicación en desarrollo. Cuando se usa una aplicación de esta forma, se limita el uso a los desarrolladores de aplicaciones y no se requiere la aprobación de un administrador, siempre y cuando el administrador permita la instalación de prueba en Teams.

Los desarrolladores pueden compartir una aplicación con instalación de prueba con un equipo específico sin enviarla al catálogo de aplicaciones de Teams. Hace que la aplicación personalizada de instalación de prueba esté disponible para un grupo limitado de usuarios finales, pero no está disponible en la tienda de aplicaciones de su organización para todos los usuarios finales.

Como administrador, se puede denegar la instalación de prueba de aplicaciones para todos los desarrolladores. Si no se permite la instalación de prueba, los desarrolladores podrán probar sus aplicaciones al [crear un inquilino de prueba independiente](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant). Una vez completado el desarrollo de aplicaciones personalizadas, los desarrolladores solicitan a los administradores que distribuyan su aplicación personalizada a los usuarios finales. Para obtener más información, consulte [cómo publicar una aplicación personalizada](/microsoftteams/upload-custom-apps). Como administrador, permite (o bloquea) el uso de una aplicación personalizada para todos los usuarios o para usuarios específicos.

## <a name="app-setup-policy-and-settings-for-custom-apps"></a>Directiva y configuración de configuración de aplicaciones personalizadas

Tres configuraciones determinan si un usuario puede cargar una aplicación personalizada a un equipo. Proporciona a los administradores un control pormenorizada sobre quién puede agregar aplicaciones personalizadas a un equipo y a qué aplicaciones personalizadas de los equipos se pueden agregar. Esta configuración no afecta a la capacidad de bloquear aplicaciones de terceros.

* [Configuración de la directiva de configuración de aplicaciones de usuario para aplicaciones personalizadas](#user-app-setup-policy-settings-for-custom-apps)
* [Configuración de la aplicación personalizada de equipo](#team-custom-app-setting)
* [Configuración de la aplicación personalizada de toda la organización](#org-wide-custom-app-setting)

### <a name="user-app-setup-policy-settings-for-custom-apps"></a>Configuración de la directiva de configuración de aplicaciones de usuario para aplicaciones personalizadas

Como parte de [las directivas de configuración](teams-app-setup-policies.md) de aplicaciones, los administradores pueden usar la opción **Cargar aplicaciones personalizadas** para controlar si un usuario puede cargar aplicaciones personalizadas en Teams.

Si esta configuración está desactivada:

* El usuario no podrá cargar una aplicación personalizada en ningún equipo de su organización ni en el ámbito personal.
* El usuario puede interactuar con aplicaciones personalizadas en función de la configuración de aplicación personalizada de toda la organización.

Si la configuración está activada:

* El usuario puede cargar aplicaciones personalizadas a los equipos que lo permiten y a los equipos de los que son propietarios, en función de la configuración de aplicación personalizada de toda la organización.
* El usuario puede cargar aplicaciones personalizadas en el ámbito personal.
* El usuario puede interactuar con aplicaciones personalizadas en función de la configuración de aplicación personalizada de toda la organización.

Puede editar la configuración en la directiva de configuración de aplicaciones global para incluir las aplicaciones que desee. Si desea personalizar Teams para distintos grupos de usuarios de la organización, puede crear y asignar una o más directivas de configuración de aplicación personalizadas.

#### <a name="set-an-app-setup-policy-settings-for-custom-apps"></a>Establecer una configuración de directiva de configuración de aplicaciones para aplicaciones personalizadas

1. Inicie sesión en el Centro de administración de Teams y acceda a las **directivas****[de configuración de](https://admin.teams.microsoft.com/policies/app-setup)** aplicaciones  >  de Teams.
1. Seleccione **Agregar**.
1. Proporcione un nombre y una descripción para la directiva.
1. Activa o desactiva la opción **Cargar aplicaciones personalizadas** .
1. Elija cualquier otra opción de configuración que desee para la directiva.
1. Seleccione **Guardar**.
1. [Aplique la directiva a los usuarios](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users) que desarrollan aplicaciones personalizadas y tienen permiso para cargarlas.

> [!NOTE]
> Para cambiar esta configuración, permita las aplicaciones personalizadas en la [configuración de aplicaciones de toda la organización](manage-apps.md#manage-org-wide-app-settings).

### <a name="team-custom-app-setting"></a>Configuración de la aplicación personalizada de equipo

Los administradores y los propietarios de equipos pueden controlar si un equipo permite que se le agreguen aplicaciones personalizadas. La configuración **Permitir que los miembros carguen aplicaciones personalizadas**, junto con la configuración de aplicaciones personalizadas de un usuario, determina quién puede agregar aplicaciones personalizadas a un equipo determinado.

Si esta configuración está desactivada:

* Los propietarios de equipos pueden agregar aplicaciones personalizadas, si su configuración de directiva de configuración de aplicaciones para aplicaciones personalizadas lo permite.
* Los miembros del equipo que no sean propietarios del mismo no podrán agregar aplicaciones personalizadas al equipo.

Si la configuración está activada:

* Los propietarios de equipos pueden agregar aplicaciones personalizadas, si su configuración de aplicaciones personalizadas lo permite.
* Los miembros del equipo que no sean propietarios del equipo pueden agregar aplicaciones personalizadas si su configuración de aplicaciones personalizadas lo permite.

#### <a name="configure-the-team-custom-app-setting"></a>Establecer la configuración de aplicación personalizada de equipo

1. En Teams, vaya a un equipo y seleccione **Más opciones...** >  **Administrar equipo**.
1. Seleccione **Configuración** y expanda **Permisos de miembro**.
1. Active o desactive la casilla **Permitir que los miembros carguen aplicaciones personalizadas**.

   :::image type="content" source="media/teams-custom-app-policy-and-settings-team-trim.png" alt-text="Captura de pantalla que muestra la configuración de la aplicación personalizada de equipo." lightbox="media/teams-custom-app-policy-and-settings-team.png":::

### <a name="org-wide-custom-app-setting"></a>Configuración de la aplicación personalizada de toda la organización

La configuración de aplicación personalizada **Permitir interacción con aplicaciones personalizadas** de toda la organización en la página [Administrar aplicaciones](manage-apps.md) se aplica a todos los usuarios de la organización y rige si dichos usuarios pueden cargar aplicaciones personalizadas o interactuar con las mismas. Esta configuración actúa como un conmutador principal de encendido o desactivación para el usuario y el equipo para la configuración relacionada con aplicaciones personalizadas. Está diseñado para que actúe como un conmutador maestro de activación y desactivación durante los eventos de seguridad. La configuración de aplicaciones personalizadas de usuario y equipo se aplica solo después de habilitar la configuración de aplicaciones personalizadas para toda la organización.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Establecer la configuración de aplicaciones personalizadas de toda la organización

1. Inicie sesión en el Centro de administración de Teams y acceda a **las aplicaciones** > **[de Teams Administrar aplicaciones](https://admin.teams.microsoft.com/policies/manage-apps)**.
1. Seleccione **Configuración de aplicaciones para toda la organización**.
1. En **Aplicaciones personalizadas**, active o desactive **Permitir interacción con aplicaciones personalizadas**.

    :::image type="content" source="media/teams-custom-app-policy-and-settings-org-wide.png" alt-text="Captura de pantalla que muestra la configuración de aplicación personalizada de toda la organización.":::

## <a name="how-custom-app-policies-and-settings-work-together"></a>Cómo funcionan conjuntamente las directivas y la configuración de aplicaciones personalizadas

En esta tabla se resume la configuración de las aplicaciones personalizadas, cómo funcionan conjuntamente y su efecto combinado en controlar quién en su organización puede cargar aplicaciones personalizadas en Teams.

Imaginemos que quiere permitir que solo los propietarios de los equipos carguen aplicaciones personalizadas en equipos específicos. Debe establecer lo siguiente:

* Active la opción **Permitir interacción con aplicaciones personalizadas** en el centro de administración de Microsoft Teams.
* Desactive la opción **Permitir que los miembros carguen aplicaciones personalizadas** para cada equipo al que quiera restringir el acceso.
* Cree y asigne una directiva personalizada en la directiva de configuración de aplicaciones en el centro de administración de Microsoft Teams con la opción **Cargar aplicaciones personalizadas** activada y asígnela a los propietarios del equipo.

|Configuración de la aplicación personalizada de toda la organización |Configuración de la aplicación personalizada de equipo |Configuración de la aplicación personalizada del usuario | Efecto  |
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
