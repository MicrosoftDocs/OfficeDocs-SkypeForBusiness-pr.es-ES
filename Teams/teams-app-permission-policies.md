---
title: Administrar directivas de permisos de aplicación en Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: rarang
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
description: Infórmese sobre las directivas de permisos de aplicación en Microsoft Teams y cómo usarlas para controlar qué aplicaciones tienen disponibles los usuarios de su organización.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 73b583493a57141fef3c120fa2eb134cbaa8a500
ms.sourcegitcommit: cfef9dd41cac0df83bd02b35036d8f8f1b472feb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "51697745"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>Administrar directivas de permisos de aplicación en Microsoft Teams

Como administrador, puede usar las directivas de permisos de aplicación para controlar qué aplicaciones están disponibles para los usuarios de Microsoft Teams de su organización. Puede permitir o bloquear todas las aplicaciones publicadas por Microsoft, por terceros o por su organización. Cuando bloquee una aplicación, los usuarios que tienen la directiva no pueden instalarla desde la tienda de aplicaciones de Teams. Debe ser un administrador global o un administrador de servicio de Teams para administrar estas directivas.

Puede administrar directivas de permisos de aplicación en el Centro de administración de Microsoft Teams. Puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas. Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada. Después de editar o asignar una directiva, los cambios pueden tardar unas horas en tener efecto.

![Captura de pantalla de la directiva de permisos de aplicación](media/app-permission-policies.png)

> [!NOTE]
> La configuración de aplicaciones en toda la organización reemplaza a la directiva global y a las directivas personalizadas que cree y asigne a los usuarios.

Si su organización ya usa Teams, la configuración de la aplicación que estableció en **Configuración para todo el espacio empresarial** en el Centro de administración de Microsoft 365 quedará reflejada en la Configuración de aplicaciones para toda la organización en la página [Administrar aplicaciones](manage-apps.md). Si es la primera vez que usa Teams, verá que de forma predeterminada se permiten todas las aplicaciones en la directiva global. Esto incluye las aplicaciones publicadas por Microsoft, por terceros o por su organización.

Pongamos un ejemplo. Digamos que desea bloquear todas las aplicaciones de terceros y permitir aplicaciones específicas de Microsoft para el equipo de RR. HH. de su organización. En primer lugar, tendría que ir a la página [Administrar aplicaciones](manage-apps.md) y asegurarse de que las aplicaciones que quiera permitir para el equipo de RR. HH. estén permitidas a nivel de la organización. Después, debería crear una directiva personalizada denominada Directiva de permisos de aplicación de RR. HH., configurarla para bloquear, permitir las aplicaciones que desee y asignarla a los usuarios del equipo de RR. HH.

> [!NOTE]
> Si implementó Teams en un entorno de Microsoft 365 Government Community Cloud High (GCCH) y department of defense (DoD), vea Administrar la configuración de aplicaciones de toda la organización para [Microsoft 365 Government](#manage-org-wide-app-settings-for-microsoft-365-government) para obtener más información sobre la configuración de aplicaciones de terceros que son exclusivas de GCCH y DoD.

## <a name="create-a-custom-app-permission-policy"></a>Crear una directiva de permisos de aplicación personalizada

Si desea controlar qué aplicaciones están disponibles para distintos grupos de usuarios de la organización, cree y asigne una o más directivas de permisos de aplicación personalizadas. Puede crear y asignar directivas personalizadas en función de si las aplicaciones se publican por Microsoft, terceros o su organización. Debe saber que después de crear una directiva personalizada, no podrá cambiarla si las aplicaciones de terceros están deshabilitadas en la configuración de la aplicación para toda la organización.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **Directivas de permisos**.
2. Haga clic en **Agregar**.<br>
    ![Captura de pantalla de la nueva directiva de permisos de aplicación](media/app-permission-policies-new-policy.png)
3. Escriba un nombre y una descripción para la directiva.
4. En **Aplicaciones de Microsoft**, **Aplicaciones de terceros** y **Aplicaciones personalizadas**, seleccione una de las opciones siguientes:

    - **Permitir todas las aplicaciones**
    - **Permitir aplicaciones específicas y bloquear todas las demás**
    - **Bloquear aplicaciones específicas y permitir todas las demás**
    - **Bloquear todas las aplicaciones**

5. Si seleccionó **Permitir aplicaciones específicas y bloquear las demás**, agregue las aplicaciones que quiera permitir:

    1. Seleccione **Permitir aplicaciones**.
    1. Busque las aplicaciones que quiera permitir y, después, haga clic en **Agregar**. Los resultados de búsqueda se filtran en función de quién haya publicado la aplicación (**Aplicaciones de Microsoft**, **Aplicaciones de terceros** y **Aplicaciones personalizadas**).
    1. Cuando haya elegido la lista de aplicaciones, haga clic en **Permitir**. 

6. De forma similar, si seleccionó **Bloquear aplicaciones específicas y permitir todas las demás**, busque y agregue las aplicaciones que desee bloquear y, después, haga clic en **Bloquear**.
7. Haga clic en **Guardar**.

## <a name="edit-an-app-permission-policy"></a>Editar una directiva de permisos de aplicación

Puede usar el Centro de administración de Microsoft Teams para editar una directiva, incluidas las directivas globales y personalizadas que cree.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **Directivas de permisos**.
2. Haga clic a la izquierda del nombre de la directiva para seleccionarla y, luego, en **Editar**.
3. A partir de aquí, realice los cambios que desee. Puede administrar la configuración en función de quién haya publicado las aplicaciones y agregar y quitar aplicaciones según la configuración de permiso o bloqueo.
4. Haga clic en **Guardar**.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>Asignar una directiva de permisos de aplicación personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a>Administrar la configuración de la aplicación para toda la organización para Microsoft 365 Administración Pública  

En una implementación de Microsoft 365 Government : GCCH y DoD de Teams, es importante conocer lo siguiente sobre la configuración de aplicaciones de terceros, que son únicas para GCCH y DoD.

En GCCH y DoD, todas las aplicaciones de terceros están bloqueadas de forma predeterminada. Además, verá la siguiente nota sobre la administración de aplicaciones de terceros en la página de directivas de permisos de aplicación del Centro de administración de Microsoft Teams.

![Captura de pantalla de la directiva de permisos de aplicación en GCCH y DoD](media/app-permission-policies-gcc.png)

Use la configuración de aplicaciones para toda la organización para controlar si los usuarios pueden instalar aplicaciones de terceros. La configuración de aplicaciones para toda la organización rige el comportamiento de todos los usuarios e invalida cualquier otra directiva de permisos de aplicación asignada a los usuarios. Puede usarla para controlar las aplicaciones malintencionadas o problemáticas.

1. En la página **Directivas de permiso**, seleccione **Configuración de aplicaciones para toda la organización**. Después, podrá configurar las opciones que desee en el panel.

    ![Captura de pantalla de Configuración de aplicaciones para toda la organización](media/app-permission-policies-gcc-org-wide.png)
    
2. En **Aplicaciones de terceros**, desactive o active esta configuración para controlar el acceso a aplicaciones de terceros:

    - **Permitir aplicaciones de terceros**: esto controla si los usuarios pueden usar aplicaciones de terceros. Si desactiva esta configuración, los usuarios no podrán instalar ni usar aplicaciones de terceros. En una implementación de Microsoft 365 Government - GCCH y DoD de Teams, esta configuración está desactivada de forma predeterminada.
    - **Permitir las nuevas aplicaciones de terceros publicadas en la tienda de forma predeterminada**: esto controla si las nuevas aplicaciones de terceros publicadas en la tienda de aplicaciones de Teams están disponibles automáticamente en Teams. Solo puede establecer esta opción si permite aplicaciones de terceros.

3. En **Aplicaciones bloqueadas**, agregue las aplicaciones que quiera bloquear en toda la organización. En una implementación de Microsoft 365 Government : GCCH y DoD de Teams, todas las aplicaciones de terceros se agregan a esta lista de forma predeterminada. Si desea permitir cualquier aplicación de terceros en su organización, quítela de esta lista de aplicaciones bloqueadas. Al bloquear una aplicación en toda la organización, la aplicación se bloquea automáticamente para todos los usuarios, independientemente de si está permitida en las directivas de permisos de la aplicación.
4. Haga clic en **Guardar** para que la configuración de aplicaciones para toda la organización surta efecto.

Como se indicó anteriormente, para permitir aplicaciones de terceros, puede editar y usar la directiva global (predeterminada en toda la organización) o crear y asignar directivas personalizadas.

## <a name="faq"></a>Preguntas más frecuentes

### <a name="working-with-app-permission-policies"></a>Trabajo con directivas de permisos de aplicaciones

#### <a name="what-app-interactions-do-permission-policies-affect"></a>¿A qué tipo de interacciones con aplicaciones afectan las directivas de permisos?
Las directivas de permisos rigen el uso de aplicaciones mediante el control de la instalación, la detección y la interacción de los usuarios finales. Los administradores aún pueden gestionar las aplicaciones en el Centro de administración de Microsoft Teams, independientemente de las directivas de permisos que se les asignen.

#### <a name="can-i-control-line-of-business-lob-apps"></a>¿Puedo controlar las aplicaciones de línea de negocio (LOB)?
Sí, puede usar directivas de permisos de aplicación para controlar la implementación y distribución de aplicaciones personalizadas (LOB). Puede crear una directiva personalizada o editar la directiva global para permitir o bloquear aplicaciones personalizadas según las necesidades de su organización.

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>¿Cómo se relacionan las directivas de permisos de aplicación con las aplicaciones ancladas y las directivas de configuración de aplicaciones?

Puede usar las directivas de configuración de aplicaciones junto con las directivas de permisos de aplicación. Las aplicaciones previamente ancladas se seleccionan desde el conjunto de aplicaciones habilitadas para un usuario. Además, si un usuario tiene una directiva de permisos de aplicación que bloquea una aplicación en su directiva de configuración de la aplicación, esa aplicación no aparecerá en Teams.

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a>¿Puedo usar directivas de permisos de aplicación para restringir la carga de aplicaciones personalizadas?

Sí, puede usar la configuración para toda la organización en la página **Administrar aplicaciones**. También puede usar las directivas de configuración de la aplicación para restringir la carga de aplicaciones personalizadas para su organización.  

Para impedir que determinados usuarios carguen aplicaciones personalizadas, use directivas de aplicación personalizadas. Para obtener más información, consulte [Administrar configuración y directivas de aplicación personalizadas en Teams](teams-custom-app-policies-and-settings.md).

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a>¿El bloqueo de una aplicación se aplica a los clientes móviles de Teams?

Sí, cuando bloquea una aplicación, esa aplicación se bloquea para todos los clientes de Teams.  

### <a name="user-experience"></a>Experiencia de usuario

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a>¿Qué pasa con la experiencia de usuario cuando se bloquea una aplicación?

Los usuarios no pueden interactuar con una aplicación bloqueada ni acceder a funciones como bots, pestañas y extensiones de mensajería. En un contexto compartido, como un chat de grupo o de equipo, los bots sí podrán enviar mensajes a todos los participantes de ese contexto. Teams indica al usuario cuando una aplicación está bloqueada.

Cuando se bloquea una aplicación, los usuarios no pueden realizar ninguna de las siguientes acciones:

- Agregar la aplicación a nivel personal o a un chat o equipo
- Enviar mensajes al bot de la aplicación
- Realizar acciones de botones que envían información de nuevo a la aplicación, como mensajes que requieren acción  
- Ver la pestaña de la aplicación
- Configurar conectores para recibir notificaciones
- Usar la extensión de mensajería de la aplicación

El portal heredado permitía controlar las aplicaciones a nivel de la organización, lo que significa que cuando se bloquea una aplicación, se bloquea para todos los usuarios de la organización. El bloqueo de una aplicación en [Administrar aplicaciones](manage-apps.md) funciona exactamente igual.

Para las directivas de permisos de aplicación asignadas a usuarios específicos, si se permitió y, luego, bloqueó una aplicación con capacidad de bot o conector y si, después, solo se permite la aplicación para algunos usuarios en un contexto compartido, los miembros de un chat grupal o un canal que no tengan permiso para esa aplicación podrán ver el historial de mensajes y los mensajes publicados por el bot o el conector, pero no interactuar con ella.

## <a name="related-topics"></a>Temas relacionados

[Configurar la administración para aplicaciones en Teams](admin-settings.md)

[Asignar directivas a los usuarios en Teams](assign-policies.md)
