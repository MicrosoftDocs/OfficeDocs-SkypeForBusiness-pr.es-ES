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
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Aprenda a administrar la configuración y las directivas de la aplicación personalizada para controlar qué usuarios de su organización pueden cargar aplicaciones personalizadas en Microsoft Teams.
ms.openlocfilehash: c1aa7489761fb27f525fbb6eb8f2056ae3dd33c8
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548664"
---
# <a name="manage-custom-app-policies-and-settings-in-microsoft-teams"></a>Administrar configuración y directivas de aplicación personalizadas en Microsoft Teams

> [!INCLUDE [feature coming soon](includes/new-feature-coming-soon-article.md)]

> [!NOTE]
> Para obtener el método de administración de aplicaciones actual en Microsoft Teams, vea [administrar la configuración de Microsoft Teams para su organización](https://docs.microsoft.com/MicrosoftTeams/enable-features-office-365).

Como administrador, puede usar la configuración y las directivas de la aplicación personalizadas para controlar qué usuarios de su organización pueden cargar aplicaciones personalizadas en Microsoft Teams. Los administradores deciden qué usuarios pueden cargar aplicaciones personalizadas, y los administradores y los propietarios del equipo pueden determinar si determinados equipos de su organización permiten agregar aplicaciones personalizadas a ellas.  

## <a name="overview-of-custom-apps"></a>Información general sobre aplicaciones personalizadas

Los usuarios pueden agregar una aplicación personalizada a teams mediante la carga de un paquete de la aplicación (en un archivo. zip) directamente en un equipo o en el contexto personal. Esto es diferente de cómo se agregan las aplicaciones a través de la tienda de aplicaciones de Teams. Agregar una aplicación personalizada mediante la carga de un paquete de la aplicación, también conocido como una aplicación de prueba, le permite probar una aplicación a medida que se desarrolla, antes de que se pueda distribuir ampliamente. También le permite crear una aplicación solo para uso interno y compartirla con su equipo sin enviarla al catálogo de aplicaciones de Teams en la tienda de aplicaciones de Teams.

![Captura de pantalla que muestra la opción cargar una aplicación personalizada en la App Store](media/teams-custom-app-policy-and-settings-upload-app.png)

## <a name="custom-app-policy-and-settings"></a>Configuración y Directiva de aplicación personalizada

Tres componentes determinan si un usuario puede cargar una aplicación personalizada en un equipo, lo que le ofrece un control granular sobre quién puede agregar aplicaciones personalizadas a un equipo y a qué aplicaciones personalizadas de Teams se pueden agregar:

- [Directiva de aplicación personalizada de usuario](#user-custom-app-policy)
- [Configuración de la aplicación personalizada del equipo](#team-custom-app-setting)
- [Configuración de la aplicación personalizada para toda la organización](#org-wide-custom-app-setting)

Esta configuración no afecta a la capacidad de bloquear aplicaciones de terceros.  

### <a name="user-custom-app-policy"></a>Directiva de aplicación personalizada de usuario

Como parte de [las directivas de configuración](teams-app-setup-policies.md)de la aplicación, los administradores pueden usar una configuración de Directiva, **permitir la carga de aplicaciones personalizadas**, controlar si un usuario puede cargar aplicaciones personalizadas en Teams.
 
Si esta opción está desactivada:

- El usuario no puede cargar una aplicación personalizada en ningún equipo de su organización o en el contexto personal.
- El usuario puede interactuar con aplicaciones personalizadas, según la configuración de la aplicación personalizada de toda la organización.

Si esta configuración está activada:

- El usuario puede cargar aplicaciones personalizadas en los equipos que lo permitan y en los equipos para los que sean propietarios, en función de la configuración de la aplicación personalizada de toda la organización.
- El usuario puede cargar aplicaciones personalizadas en el contexto personal. 
- El usuario puede interactuar con aplicaciones personalizadas, según la configuración de la aplicación personalizada de toda la organización.

Puede editar la configuración de la Directiva configuración global de la aplicación para incluir las aplicaciones que quiera. Si desea personalizar Teams para diferentes grupos de usuarios de su organización, cree y asigne una o más directivas personalizadas de configuración de la aplicación.

#### <a name="set-a-user-custom-app-policy"></a>Establecer una directiva de aplicación personalizada de usuario

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a**directivas de configuración**de las **aplicaciones** > de Teams.
2. Seleccione **nueva Directiva**.
3. Activar o desactivar permitir la **carga de aplicaciones personalizadas**.
4. Elija cualquier otra configuración que desee para la Directiva.
5. Haga clic en **Guardar **.

### <a name="team-custom-app-setting"></a>Configuración de la aplicación personalizada del equipo

Los administradores y los propietarios del equipo pueden controlar si un equipo permite que se agreguen a él aplicaciones personalizadas. Esta configuración, **permitir que los miembros carguen aplicaciones personalizadas**, junto con la Directiva de aplicación personalizada de un usuario, determina quién puede agregar aplicaciones personalizadas a un equipo en particular.
 
Si esta opción está desactivada:

- Los propietarios del equipo pueden agregar aplicaciones personalizadas si su Directiva de aplicación personalizada lo permite.
- Los miembros del equipo que no sean propietarios del equipo no pueden agregar aplicaciones personalizadas al equipo.

Si esta configuración está activada:

- Los propietarios del equipo pueden agregar aplicaciones personalizadas si su Directiva de aplicación personalizada lo permite.
- Los miembros del equipo que no sean propietarios del equipo pueden agregar aplicaciones personalizadas, si su Directiva de aplicación personalizada lo permite.

#### <a name="configure-the-team-custom-app-setting"></a>Configurar la configuración de la aplicación personalizada del equipo

1. En Teams, vaya al equipo, haga clic en **más opciones ̇ ̇ ̇** > **Manage Team**.
2. Haga clic en **configuración**y, a continuación, expanda **permisos de miembro**.
3. Active o desactive la casilla **permitir que los miembros carguen aplicaciones personalizadas** .

    ![Captura de pantalla que muestra la configuración de la aplicación personalizada del equipo](media/teams-custom-app-policy-and-settings-team.png)

### <a name="org-wide-custom-app-setting"></a>Configuración de la aplicación personalizada para toda la organización

La configuración de la aplicación personalizada para toda la organización, **permite la interacción con aplicaciones personalizadas**, se aplica a todos los usuarios de su organización y rige si pueden cargar o interactuar con aplicaciones personalizadas. Esta configuración reemplaza la configuración y la Directiva de aplicación personalizada de usuarios y equipos. Está pensado para funcionar como un interruptor de encendido y apagado maestro durante los eventos de seguridad.

#### <a name="configure-the-org-wide-custom-app-setting"></a>Configurar la aplicación personalizada de toda la organización

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a**directivas de permisos**de las **aplicaciones** > de Teams.
2. Haga clic en **configuración de la aplicación en toda la organización**.
3. En **aplicaciones personalizadas**, Active o desactive la **opción permitir la interacción con aplicaciones personalizadas**.

    ![Captura de pantalla que muestra la configuración de la aplicación personalizada para toda la organización](media/teams-custom-app-policy-and-settings-org-wide.png)

## <a name="how-custom-app-policies-and-settings-work-together"></a>Cómo funcionan conjuntamente las directivas y la configuración de la aplicación personalizada

En esta tabla se resumen la configuración y la Directiva de aplicación personalizada, cómo funcionan conjuntamente y su efecto combinado sobre cómo controlar quién en su organización puede cargar aplicaciones personalizadas en Teams.

Supongamos, por ejemplo, que desea permitir que solo los propietarios de equipo carguen aplicaciones personalizadas en determinados equipos. Establecería lo siguiente:
- Active la opción **permitir la interacción con aplicaciones personalizadas** en el centro de administración de Microsoft Teams.
- Desactive la **opción permitir que los miembros carguen aplicaciones personalizadas** para cada equipo al que desee restringir el acceso.
- Crear y asignar una directiva de configuración de aplicación personalizada en el centro de administración de Microsoft Teams con el **usuario puede cargar** la configuración de aplicaciones personalizadas activada y asignarla a los propietarios del equipo.

|Configuración de la aplicación personalizada para toda la organización |Configuración de la aplicación personalizada del equipo |Directiva de aplicación personalizada de usuario |Surti  |
|---------|---------|---------|---------|
| Desactivado    | Desactivado    | Desactivado     |La interacción con todas las aplicaciones personalizadas está bloqueada para su organización. Nadie puede cargar las aplicaciones personalizadas. Puede usar PowerShell para quitar la aplicación personalizada.   |
| Desactivado     | Desactivado     | Activado        |La interacción con todas las aplicaciones personalizadas está bloqueada para su organización. Nadie puede cargar las aplicaciones personalizadas. Puede usar PowerShell para quitar la aplicación personalizada.         |
| Desactivado    | Activado        | Desactivado        |La interacción con todas las aplicaciones personalizadas está bloqueada para su organización. Nadie puede cargar las aplicaciones personalizadas. Puede usar Windows PowerShell para eliminar aplicaciones personalizadas.         |
| Desactivado    | Activado      | Activado       |La interacción con todas las aplicaciones personalizadas está bloqueada para su organización. Nadie puede cargar las aplicaciones personalizadas. Puede usar PowerShell para quitar la aplicación personalizada.         |
| Activado    | Desactivado       | Desactivado         |  El usuario no puede cargar aplicaciones personalizadas.      |
| Activado     | Desactivado       | Activado         | Si el usuario es el propietario de un equipo, puede cargar aplicaciones personalizadas en el equipo. Si el usuario no es un propietario del equipo, no puede cargar aplicaciones personalizadas en el equipo. El usuario puede cargar aplicaciones personalizadas en el contexto personal.     |
| Activado     | Activado     | Desactivado         | El usuario no puede cargar aplicaciones personalizadas.       |
| Activado    | Activado        | Activado        | El usuario puede cargar aplicaciones personalizadas en el equipo, independientemente de si el usuario es el propietario de un equipo. El usuario puede cargar aplicaciones personalizadas en el contexto personal.       |

 ## <a name="related-topics"></a>Temas relacionados
- [Configurar la administración para aplicaciones en Teams](admin-settings.md)
- [Administrar directivas de configuración de aplicación en Microsoft Teams](teams-app-setup-policies.md)
- [Administrar directivas de permisos de aplicación en Microsoft Teams](teams-app-permission-policies.md)
