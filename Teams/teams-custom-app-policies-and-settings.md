---
title: Administrar configuración y directivas de aplicación personalizadas en Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/18/2019
ms.reviewer: akino
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Obtenga información sobre cómo administrar las directivas de aplicación personalizadas y la configuración para controlar quién en la organización puede cargar aplicaciones personalizadas de Microsoft Teams.
ms.openlocfilehash: 3cbd517cdfe8066eebff0164457c8e2e3aa37a5d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "32224641"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>Administrar configuración y directivas de aplicación personalizadas en Microsoft Teams

> [!INCLUDE [feature coming soon](includes/new-feature-coming-soon-article.md)]

Como administrador, puede usar directivas de aplicaciones personalizadas y la configuración para controlar quién en la organización puede cargar aplicaciones personalizadas en Microsoft Teams. Administradores de decidir qué usuarios pueden cargar aplicaciones personalizadas y los propietarios de los administradores y del equipo pueden determinar si determinados equipos de la organización permiten aplicaciones personalizadas que se agregarán a ellos.  

## <a name="overview-of-custom-apps"></a>Introducción a las aplicaciones personalizadas

Los usuarios pueden agregar una aplicación personalizada a los equipos mediante la carga de un paquete de aplicación (en un archivo .zip) directamente a un equipo o en el contexto personal. Esto es diferente de cómo se agregan las aplicaciones a través de la tienda de aplicaciones de los equipos. Adición de una aplicación personalizada al cargar un paquete de aplicación, también conocido como sideloading, permite probar una aplicación, como los se está desarrollando, antes de que esté listo para distribuirse a gran escala. También le permite crear una aplicación sólo para uso interno y compartir con su equipo sin enviarlo al catálogo de aplicaciones de los equipos en la tienda de aplicaciones de los equipos.

![carga una aplicación personalizada](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>Configuración y la directiva de aplicación personalizada

Tres componentes determinan si un usuario puede cargar una aplicación personalizada a un equipo, dar a un control detallado quién puede agregar aplicaciones personalizadas a un equipo y que los equipos de aplicaciones personalizadas se pueden agregar a:

- [Directiva de aplicación personalizada de usuario](#user-custom-app-policy)
- [Configuración de aplicación personalizada de equipo](#team-custom-app-setting)
- [Configuración de aplicación personalizada de toda la organización](#org-wide-custom-app-setting)

Estas opciones no afectan a la capacidad de bloquear las aplicaciones de terceros.  

### <a name="user-custom-app-policy"></a>Directiva de aplicación personalizada de usuario

Como parte de [las directivas de aplicación del programa de instalación](teams-app-setup-policies.md), los administradores pueden utilizar una configuración de directiva, **Permitir cargar aplicaciones personalizadas**, para controlar si un usuario puede cargar aplicaciones personalizadas en los equipos.
 
Si esta opción está desactivada:

- El usuario no puede cargar una aplicación personalizada en cualquier equipo de la organización o en el contexto personal.
- El usuario puede interactuar con las aplicaciones personalizadas, dependiendo de la configuración de aplicación personalizada de toda la organización.

Si esta opción está activada:

- El usuario puede cargar sus aplicaciones personalizadas a los equipos que le permiten a los equipos de los que son propietarios, dependiendo de la configuración de aplicación personalizada de toda la organización.
- El usuario puede cargar aplicaciones personalizadas en el contexto de personal. 
- El usuario puede interactuar con las aplicaciones personalizadas, dependiendo de la configuración de aplicación personalizada de toda la organización.

Puede modificar la configuración de la directiva de aplicación global del programa de instalación para incluir las aplicaciones que desee. Si desea personalizar los equipos para distintos grupos de usuarios de la organización, cree y asigne una o varias directivas del programa de instalación de la aplicación personalizada.

#### <a name="set-a-user-custom-app-policy"></a>Establecer una directiva de aplicación personalizada de usuario

1. En la izquierda el centro de administración de Microsoft Teams, vaya a **las aplicaciones de los equipos** > **las directivas de instalación**.
2. Seleccione **nueva directiva**.
3. Activar o desactivar la opción **Permitir la carga de aplicaciones personalizadas**.
4. Elija las demás opciones que desee para la directiva.
5. Haga clic en **Guardar **.

### <a name="team-custom-app-setting"></a>Configuración de aplicación personalizada de equipo

Los propietarios de los administradores y del equipo pueden controlar si permite que un equipo para que las aplicaciones personalizadas que se agregará a él. Esta opción, **los miembros de permitir para cargar aplicaciones personalizadas**, junto con la directiva de aplicación personalizada de un usuario determina quién puede agregar aplicaciones personalizadas a un equipo en particular.
 
Si esta opción está desactivada:

- Los propietarios de equipo pueden agregar aplicaciones personalizadas, si su directiva de aplicación personalizada lo permite.
- Los miembros del equipo que no son propietarios de equipo no pueden agregar aplicaciones personalizadas para el equipo.

Si esta opción está activada:

- Los propietarios de equipo pueden agregar aplicaciones personalizadas, si su directiva de aplicación personalizada lo permite.
- Los miembros del equipo que no son propietarios de equipo pueden agregar aplicaciones personalizadas, si su directiva de aplicación personalizada lo permite.

#### <a name="configure-the-team-custom-app-setting"></a>Configurar la configuración de aplicación personalizada de equipo

1. En los equipos, vaya al equipo, haga clic en **más ˙˙˙ opciones** > **Administrar equipo**.
2. Haga clic en **configuración**y, a continuación, expanda **permisos de miembro**.
3. Active o desactive la casilla de verificación **Permitir (miembros) para cargar aplicaciones personalizadas** .

    ![configuración de aplicación personalizada de equipo](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>Configuración de aplicación personalizada de toda la organización

La configuración de aplicación personalizada de toda la organización, **Permitir la interacción con aplicaciones personalizadas**, se aplica a todas las personas de su organización y controla si se puede cargar o interactuar con aplicaciones personalizadas. Esta configuración invalida la configuración y la directiva de aplicación personalizada de equipo y usuario. Ha diseñado para que sirva como un patrón de modificador activado/desactivado durante los eventos de seguridad.

#### <a name="configure-the-org-wide-custom-app-setting"></a>La configuración de aplicación personalizada de toda la organización

1. En la izquierda el centro de administración de Microsoft Teams, vaya a **las aplicaciones de los equipos** > **las directivas de permisos**.
2. Haga clic en **configuración de la aplicación de toda la organización**.
3. En las **aplicaciones personalizadas**, activar o desactivar la opción **Permitir la interacción con aplicaciones personalizadas**.

    ![Configuración de aplicación personalizada de toda la organización](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>Cómo funciona conjuntamente las directivas de aplicación personalizada y configuración

Esta tabla resume la directiva de aplicación personalizada y configuraciones, cómo funcionan conjuntamente y su efecto combinada sobre cómo controlar personas de su organización pueden cargar aplicaciones personalizadas en los equipos.

Supongamos, por ejemplo, que desea permitir que sólo los propietarios de equipo cargar aplicaciones personalizadas en determinados equipos. Se debe establecer lo siguiente:
- Activar la opción **Permitir la interacción con aplicaciones personalizadas** en el centro de administración de Microsoft Teams.
- Desactivar los **miembros de permitir para cargar aplicaciones personalizadas** para cada equipo al que desea restringir el acceso.
- Crear y asignar una directiva de aplicación personalizada del programa de instalación en el centro de administración de Microsoft Teams con la configuración de **usuario puede cargar sus aplicaciones personalizadas** activada y asignar a los propietarios del equipo.

|Configuración de aplicación personalizada de toda la organización |Configuración de aplicación personalizada de equipo |Directiva de aplicación personalizada de usuario |Efecto  |
|---------|---------|---------|---------|
| Desactivado    | Desactivado    | Desactivado     |Se bloquea la interacción con todas las aplicaciones personalizadas para su organización. Cualquier usuario no se pueden cargar aplicaciones personalizadas. Puede usar PowerShell para quitar la aplicación personalizada.   |
| Desactivado     | Desactivado     | Activado        |Se bloquea la interacción con todas las aplicaciones personalizadas para su organización. Cualquier usuario no se pueden cargar aplicaciones personalizadas. Puede usar PowerShell para quitar la aplicación personalizada.         |
| Desactivado    | Activado        | Desactivado        |Se bloquea la interacción con todas las aplicaciones personalizadas para su organización. Cualquier usuario no se pueden cargar aplicaciones personalizadas. Puede usar Windows PowerShell para eliminar aplicaciones personalizadas.         |
| Desactivado    | Activado      | Activado       |Se bloquea la interacción con todas las aplicaciones personalizadas para su organización. Cualquier usuario no se pueden cargar aplicaciones personalizadas. Puede usar PowerShell para quitar la aplicación personalizada.         |
| Activado    | Desactivado       | Desactivado         |  El usuario no puede cargar aplicaciones personalizadas.      |
| Activado     | Desactivado       | Activado         | Si el usuario es el propietario de un equipo, pueden cargar aplicaciones personalizadas en el equipo. Si el usuario no es propietario de un equipo, no pueden cargar aplicaciones personalizadas para el equipo. El usuario puede cargar sus aplicaciones personalizadas en el contexto personal.     |
| Activado     | Activado     | Desactivado         | El usuario no puede cargar aplicaciones personalizadas.       |
| Activado    | Activado        | Activado        | El usuario puede cargar aplicaciones personalizadas en el equipo, independientemente de si el usuario es el propietario de un equipo. El usuario puede cargar sus aplicaciones personalizadas en el contexto personal.       |

 ## <a name="related-topics"></a>Temas relacionados
- [Configurar la administración para aplicaciones en Teams](admin-settings.md)
- [Administrar directivas de configuración de aplicación en Microsoft Teams](teams-app-setup-policies.md)
- [Administrar directivas de permisos de aplicación en Microsoft Teams](teams-app-permission-policies.md)
