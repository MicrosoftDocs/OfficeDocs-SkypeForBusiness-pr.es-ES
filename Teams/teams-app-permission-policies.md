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
description: Obtenga información sobre las directivas de permisos de aplicaciones en Microsoft Teams y cómo usarlas para controlar qué aplicaciones están disponibles para los usuarios de su organización.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: aa11b21405079ab26bf1fa9572eb203560c4e461
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802500"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>Administrar directivas de permisos de aplicación en Microsoft Teams

Como administrador, puede usar las directivas de permisos de aplicación para controlar qué aplicaciones están disponibles para los usuarios de Microsoft Teams de su organización. Puede permitir o bloquear todas las aplicaciones o aplicaciones específicas publicadas por Microsoft, terceros y su organización. Cuando bloquee una aplicación, los usuarios que tienen la directiva no pueden instalarla desde la tienda de aplicaciones de Teams. Debe ser un administrador global o un administrador de servicio de Teams para administrar estas directivas.

Administre las directivas de permisos de aplicaciones en el Centro de administración de Microsoft Teams. Puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas. Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada. Después de editar o asignar una directiva, los cambios pueden tardar unas horas en tener efecto.

![Captura de pantalla de la directiva de permisos de aplicación](media/app-permission-policies.png)

> [!NOTE]
> La configuración de aplicaciones para toda la organización anula la directiva global y las directivas personalizadas que cree y asigne a los usuarios.

Si su organización ya se encuentra en  Teams, la configuración de la aplicación que configuró en la configuración [](manage-apps.md) de toda la cuenta empresarial en el Centro de administración de Microsoft 365 se refleja en la configuración de aplicaciones para toda la organización en la página Administrar aplicaciones. Si es nuevo en Teams y acaba de empezar, de forma predeterminada, todas las aplicaciones están permitidas en la directiva global. Esto incluye las aplicaciones publicadas por Microsoft, terceros y tu organización.

Por ejemplo, quiere bloquear todas las aplicaciones de terceros y permitir aplicaciones específicas de Microsoft para el equipo de RRHH de su organización. En primer lugar, [](manage-apps.md) vaya a la página Administrar aplicaciones y asegúrese de que las aplicaciones que desea permitir para el equipo de RRHH están permitidas en el nivel de organización. A continuación, cree una directiva personalizada denominada Directiva de permisos de aplicaciones de RR. HR, esta debe configurarla para bloquear y permitir las aplicaciones que desee y asignarla a los usuarios del equipo de RRHH.

> [!NOTE]
> Si implementó Teams en un entorno de Microsoft 365 Government Community Cloud (GCC), consulte Administrar la configuración de aplicaciones para toda la organización de [Microsoft 365 Government](#manage-org-wide-app-settings-for-microsoft-365-government) para obtener más información sobre la configuración de aplicaciones de terceros que son exclusivas de GCC.

## <a name="create-a-custom-app-permission-policy"></a>Crear una directiva de permisos de aplicación personalizada

Si quiere controlar las aplicaciones que están disponibles para diferentes grupos de usuarios de su organización, cree y asigne una o más directivas de permisos de aplicación personalizadas. Puede crear y asignar directivas personalizadas independientes en función de si las aplicaciones están publicadas por Microsoft, terceros o su organización. Es importante saber que, después de crear una directiva personalizada, no puede cambiarla si las aplicaciones de terceros están deshabilitadas en la configuración de la aplicación para toda la organización.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a directivas **de permisos de aplicaciones**  >  **de** Teams.
2. Haga clic en **Agregar**. <br>
    ![Captura de pantalla de la nueva directiva de permisos de aplicación](media/app-permission-policies-new-policy.png)
3. Escriba un nombre y una descripción para la directiva.
4. En **Aplicaciones de Microsoft,** **Aplicaciones de terceros** y Aplicaciones personalizadas, seleccione una de las siguientes opciones: 

    - **Permitir todas las aplicaciones**
    - **Permitir aplicaciones específicas y bloquear a todos los demás**
    - **Bloquear aplicaciones específicas y permitir el resto**
    - **Bloquear todas las aplicaciones**

5. Si has seleccionado **Permitir aplicaciones específicas y bloquear a otras** personas, agrega las aplicaciones que quieras permitir:

    1. Seleccione **Permitir aplicaciones.**
    1. Busque las aplicaciones que desee permitir y, a continuación, haga clic en **Agregar.** Los resultados de búsqueda se filtran por el editor de aplicaciones (aplicaciones **de Microsoft,** aplicaciones **de terceros** o **aplicaciones personalizadas).**
    1. Cuando haya elegido la lista de aplicaciones, haga clic en **Permitir.** 

6. De forma similar, si ha seleccionado Bloquear aplicaciones específicas y permite el **resto,** busque y agregue las aplicaciones que desea bloquear y, a continuación, haga clic en **Bloquear.**
7. Haga clic en **Guardar**.

## <a name="edit-an-app-permission-policy"></a>Editar una directiva de permisos de aplicación

Puede usar el Centro de administración de Microsoft Teams para editar una directiva, incluida la directiva global y las directivas personalizadas que cree.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a directivas **de permisos de aplicaciones**  >  **de** Teams.
2. Seleccione la directiva haciendo clic a la izquierda del nombre de la directiva y, a continuación, haga clic en **Editar.**
3. A partir de aquí, realice los cambios que desee. Puede administrar la configuración basada en el editor de la aplicación y agregar y quitar aplicaciones en función de la configuración de permitir o bloquear.
4. Haga clic en **Guardar**.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>Asignar una directiva de permisos de aplicación personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a>Administrar la configuración de aplicaciones para toda la organización para Microsoft 365 Government  

En una implementación de Microsoft 365 Government - GCC de Teams, es importante conocer los siguientes aspectos sobre la configuración de las aplicaciones de terceros, que son exclusivas de GCC.

En GCC, todas las aplicaciones de terceros están bloqueadas de forma predeterminada. Además, verá la siguiente nota sobre la administración de aplicaciones de terceros en la página de directivas de permisos de aplicaciones del Centro de administración de Microsoft Teams.

![Captura de pantalla de la directiva de permisos de aplicaciones en GCC](media/app-permission-policies-gcc.png)

Use la configuración de aplicaciones para toda la organización para controlar si los usuarios pueden instalar aplicaciones de terceros. La configuración de aplicaciones para toda la organización rige el comportamiento de todos los usuarios y reemplaza cualquier otra directiva de permisos de aplicación asignada a los usuarios. Puede usarlos para controlar aplicaciones malintencionadas o problemáticas.

1. En la **página Directivas de** permisos, seleccione Configuración de la aplicación para toda la **organización.** A continuación, puede configurar las opciones que desee en el panel.

    ![Captura de pantalla de la configuración de la aplicación para toda la organización](media/app-permission-policies-gcc-org-wide.png)
    
2. En **Aplicaciones de terceros,** desactiva o activa esta configuración para controlar el acceso a las aplicaciones de terceros:

    - **Permitir aplicaciones de terceros:** esto controla si los usuarios pueden usar aplicaciones de terceros. Si desactiva esta configuración, los usuarios no podrán instalar ni usar aplicaciones de terceros. En una implementación de Microsoft 365 Government - GCC de Teams, esta configuración está desactivada de forma predeterminada.
    - **Permitir que las** nuevas aplicaciones de terceros se publiquen en la tienda de forma predeterminada: esto controla si las nuevas aplicaciones de terceros que se publican en la tienda de aplicaciones de Teams están disponibles automáticamente en Teams. Solo puede establecer esta opción si permite aplicaciones de terceros.

3. En **Aplicaciones bloqueadas,** agrega las aplicaciones que quieres bloquear en toda tu organización. En una implementación de Microsoft 365 Government - GCC de Teams, todas las aplicaciones de terceros se agregan a esta lista de forma predeterminada. Para cualquier aplicación de terceros que quieras permitir en tu organización, quita la aplicación de esta lista de aplicaciones bloqueadas. Al bloquear una aplicación en toda la organización, la aplicación se bloquea automáticamente para todos los usuarios, independientemente de si está permitida en cualquier política de permisos de aplicación
4. Haga **clic en Guardar** para obtener la configuración de la aplicación para toda la organización para hacer efecto.

Como se mencionó anteriormente, para permitir aplicaciones de terceros, puede editar y usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas.

## <a name="faq"></a>Preguntas más frecuentes

### <a name="working-with-app-permission-policies"></a>Trabajar con directivas de permisos de aplicaciones

#### <a name="what-app-interactions-do-permission-policies-affect"></a>¿A qué interacciones de la aplicación afectan las directivas de permisos?
Las directivas de permisos rigen el uso de aplicaciones controlando la instalación, la detección y la interacción de los usuarios finales. Los administradores pueden seguir administrando aplicaciones en el centro de administración de Microsoft Teams independientemente de las directivas de permisos que se les asignen.

#### <a name="can-i-control-line-of-business-lob-apps"></a>¿Puedo controlar las aplicaciones de línea de negocio (LOB)?
Sí, puede usar directivas de permisos de aplicación para controlar la implementación y distribución de aplicaciones personalizadas (LOB). Puede crear una directiva personalizada o editar la directiva global para permitir o bloquear aplicaciones personalizadas según las necesidades de su organización.

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>¿Cómo se relacionan las directivas de permisos de aplicación a las aplicaciones ancladas y las directivas de configuración de aplicaciones?

Puede usar las directivas de configuración de aplicaciones junto con las directivas de permisos de aplicación. Las aplicaciones ancladas previamente se seleccionan del conjunto de aplicaciones habilitadas para un usuario. Además, si un usuario tiene una directiva de permisos de aplicación que bloquea una aplicación en su directiva de configuración de aplicaciones, esa aplicación no aparecerá en Teams.

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a>¿Puedo usar directivas de permisos de aplicación para restringir la carga de aplicaciones personalizadas?

Puede usar la configuración para toda la organización en la **página** Administrar aplicaciones o las directivas de configuración de aplicaciones para restringir la carga de aplicaciones personalizadas para su organización.  

Para impedir que determinados usuarios carguen aplicaciones personalizadas, use directivas de aplicación personalizadas. Para obtener más información, consulte [Administrar directivas y configuraciones de aplicaciones personalizadas en Teams.](teams-custom-app-policies-and-settings.md)

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a>¿Se aplica el bloqueo de una aplicación a los clientes móviles de Teams?

Sí, al bloquear una aplicación, esta se bloquea en todos los clientes de Teams.  

### <a name="user-experience"></a>Experiencia de usuario

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a>¿Qué ocurre cuando se bloquea una aplicación?

Los usuarios no pueden interactuar con una aplicación bloqueada o sus capacidades, como bots, fichas y extensiones de mensajería. En un contexto compartido, como un equipo o un chat grupal, los bots aún pueden enviar mensajes a todos los participantes de ese contexto. Teams indica al usuario cuándo se bloquea una aplicación.

Por ejemplo, cuando se bloquea una aplicación, los usuarios no pueden hacer lo siguiente:

- Agregar la aplicación personalmente o a un chat o equipo
- Enviar mensajes al bot de la aplicación
- Realizar acciones de botón que envían información a la aplicación, como mensajes que se pueden usar para realizar acciones  
- Ver la pestaña de la aplicación
- Configurar conectores para recibir notificaciones
- Usar la extensión de mensajería de la aplicación

El portal heredado permite controlar las aplicaciones en el nivel de la organización, lo que significa que cuando se bloquea una aplicación, se bloquea para todos los usuarios de la organización. Bloquear una aplicación en la [página Administrar aplicaciones](manage-apps.md) funciona exactamente del mismo modo.

Para las directivas de permisos de aplicación asignadas a usuarios específicos, si se permitía y se bloqueara una aplicación con capacidad de bot o conector, y si la aplicación solo se permite para algunos usuarios en un contexto compartido, los miembros de un canal o chat de grupo que no tienen permiso para esa aplicación pueden ver el historial de mensajes y los mensajes publicados por el bot o el conector. , pero no puede interactuar con él.

## <a name="related-topics"></a>Temas relacionados

[Configurar la administración para aplicaciones en Teams](admin-settings.md)

[Asignar directivas a los usuarios en Teams](assign-policies.md)
