---
title: Administrar directivas de permisos de aplicación en Microsoft Teams
author: lanachin
ms.author: v-lanac
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
description: Obtenga más información sobre las directivas de permisos de aplicaciones en Microsoft Teams y cómo usarlas para controlar qué aplicaciones están disponibles para los usuarios de su organización.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.apppermspolicies.overview
- ms.teamsadmincenter.appsetuppolicies.addpinnedapp.permissions
- ms.teamsadmincenter.apppermspolicies.orgwideapps.customapps
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 15698c7eeb12187ccc510a42b9a6e2120a7907cc
ms.sourcegitcommit: 2467ece95e100a3a3cc2be3538d8eb7d878b3663
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2020
ms.locfileid: "45043001"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a>Administrar directivas de permisos de aplicación en Microsoft Teams

Como administrador, puede usar las directivas de permisos de aplicación para controlar qué aplicaciones están disponibles para los usuarios de Microsoft Teams de su organización. Puede permitir o bloquear todas las aplicaciones o aplicaciones específicas publicadas por Microsoft, terceros y su organización. Cuando bloquee una aplicación, los usuarios que tienen la directiva no pueden instalarla desde la tienda de aplicaciones de Teams. Debe ser un administrador global o un administrador de servicio de Teams para administrar estas directivas.

Administre las directivas de permisos de aplicaciones en el centro de administración de Microsoft Teams. Puede usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas. Los usuarios de su organización obtendrán automáticamente la directiva global, a menos que cree y asigne una directiva personalizada. Después de modificar o asignar una directiva, los cambios pueden demorar algunas horas en surtir efecto.

![Captura de pantalla de la Directiva de permisos de aplicaciones](media/app-permission-policies.png)

> [!NOTE]
> La configuración de la aplicación en toda la organización reemplaza la directiva global y las directivas personalizadas que cree y asigne a los usuarios.

Si su organización ya está en Teams, la configuración de la aplicación que ha configurado en la **configuración de toda la empresa** en el centro de administración de Microsoft 365 se refleja en la configuración de la aplicación de toda la organización en la página [Administrar aplicaciones](manage-apps.md) . Si es nuevo en Teams y se está preparando, de forma predeterminada, todas las aplicaciones estarán permitidas en la directiva global. Esto incluye las aplicaciones publicadas por Microsoft, terceros y su organización.

Supongamos, por ejemplo, que desea bloquear todas las aplicaciones de terceros y permitir aplicaciones específicas de Microsoft para el equipo de RRHH de su organización. En primer lugar, debería ir a la página [Administrar aplicaciones](manage-apps.md) y asegurarse de que las aplicaciones que desea permitir para el equipo de RRHH estén permitidas en el nivel de organización. Después, cree una directiva personalizada denominada Directiva de permisos de aplicaciones de RRHH, configúrelo para que bloquee y permita las aplicaciones que desee, y asígnela a los usuarios del equipo de RRHH.

> [!NOTE]
> Si implementó Teams en un entorno de nube de Microsoft 365 administración pública (GCC), vea [administrar la configuración de aplicaciones de toda la organización para microsoft 365](#manage-org-wide-app-settings-for-microsoft-365-government) para obtener más información sobre la configuración de aplicaciones de terceros que son exclusivas de GCC.

## <a name="create-a-custom-app-permission-policy"></a>Crear una directiva de permisos de aplicaciones personalizada

Si desea controlar las aplicaciones que están disponibles para los distintos grupos de usuarios de su organización, cree y asigne una o varias directivas de permisos de aplicaciones personalizadas. Puede crear y asignar directivas personalizadas distintas basándose en si las aplicaciones son publicadas por Microsoft, por terceros o por su organización. Es importante saber que después de crear una directiva personalizada, no puede cambiarla si las aplicaciones de terceros se deshabilitan en la configuración de la aplicación en toda la organización.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de permisos de las **aplicaciones de Teams**  >  **Permission policies**.
2. Haga clic en **Agregar**. <br>
    ![Captura de pantalla de nueva Directiva de permisos de aplicaciones](media/app-permission-policies-new-policy.png)
3. Escriba un nombre y una descripción para la directiva.
4. En aplicaciones de **Microsoft**, **aplicaciones de terceros**y **aplicaciones personalizadas**, seleccione una de las siguientes opciones:

    - **Permitir todas las aplicaciones**
    - **Permitir aplicaciones específicas y bloquear a todos los demás**
    - **Bloquear aplicaciones específicas y permitir a todos los demás**
    - **Bloquear todas las aplicaciones**

5. Si seleccionó **permitir aplicaciones específicas y bloquear a otras personas**, agregue las aplicaciones que quiera permitir:

    1. Seleccione **permitir aplicaciones**.
    1. Busque las aplicaciones que desea permitir y, a continuación, haga clic en **Agregar**. Los resultados de la búsqueda se filtran para el publicador de la aplicación (aplicaciones de**Microsoft**, **aplicaciones de terceros**o **aplicaciones personalizadas**).
    1. Cuando haya elegido la lista de aplicaciones, haga clic en **permitir**. 

6. Del mismo modo, si seleccionas **bloquear aplicaciones específicas y permitir a todos los demás**, busca y agrega las aplicaciones que deseas bloquear y luego haz clic en **bloquear**.
7. Haga clic en **Guardar **.

## <a name="edit-an-app-permission-policy"></a>Editar una directiva de permisos de aplicación

Puede usar el centro de administración de Microsoft Teams para editar una directiva, incluida la directiva global y las directivas personalizadas que cree.

1. En el centro de navegación izquierdo del centro de administración de Microsoft Teams, vaya a directivas de permisos de las **aplicaciones de Teams**  >  **Permission policies**.
2. Seleccione la Directiva haciendo clic a la izquierda del nombre de la Directiva y, a continuación, haga clic en **Editar**.
3. Desde aquí, realice los cambios que desee. Puede administrar la configuración basándose en el editor de la aplicación y agregar y quitar aplicaciones en función de la configuración permitir o bloquear.
4. Haga clic en **Guardar **.

## <a name="assign-a-custom-app-permission-policy-to-users"></a>Asignar una directiva de permisos de aplicación personalizada a los usuarios

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="manage-org-wide-app-settings-for-microsoft-365-government"></a>Administrar la configuración de aplicaciones de toda la organización para Microsoft 365 administración pública  

En una implementación de Teams de Microsoft 365 administración pública-GCC, es importante saber lo siguiente sobre la configuración de aplicaciones de terceros, que es exclusiva de GCC.

En GCC, todas las aplicaciones de terceros se bloquean de forma predeterminada. Además, verá la siguiente nota sobre la administración de aplicaciones de terceros en la página de directivas de permisos de aplicaciones en el centro de administración de Microsoft Teams.

![Captura de pantalla de la Directiva de permisos de aplicaciones en GCC](media/app-permission-policies-gcc.png)

Use la configuración de la aplicación en toda la organización para controlar si los usuarios pueden instalar aplicaciones de terceros. La configuración de la aplicación en toda la organización rige el comportamiento de todos los usuarios y anula cualquier otra directiva de permisos de aplicación asignada a los usuarios. Puede usarlos para controlar aplicaciones malintencionadas o problemáticas.

1. En la página **directivas de permisos** , seleccione Configuración de la aplicación en toda la **organización**. Puede establecer la configuración que desee en el panel.

    ![Captura de pantalla de la configuración de aplicación de toda la organización](media/app-permission-policies-gcc-org-wide.png)
    
2. En **aplicaciones de terceros**, desactive o Active esta configuración para controlar el acceso a las aplicaciones de terceros:

    - **Permitir aplicaciones de terceros**: controla si los usuarios pueden usar aplicaciones de terceros. Si desactiva esta configuración, los usuarios no podrán instalar ni usar ninguna aplicación de terceros. En una implementación de Teams de Microsoft 365 Administrator-GCC, esta opción está desactivada de forma predeterminada.
    - **Permitir que todas las aplicaciones de terceros se publiquen en la tienda de forma predeterminada**: controla si las nuevas aplicaciones de terceros publicadas en la tienda de aplicaciones de Teams se encuentran disponibles automáticamente en Teams. Solo puede establecer esta opción si permite aplicaciones de terceros.

3. En **aplicaciones bloqueadas**, agregue las aplicaciones que desea bloquear en toda la organización. En una implementación de Teams de Microsoft 365 Administrator-GCC, todas las aplicaciones de terceros se agregan a esta lista de forma predeterminada. Para cualquier aplicación de terceros que desee permitir en su organización, quite la aplicación de esta lista de aplicaciones bloqueadas. Cuando bloquea una aplicación en toda la organización, la aplicación se bloquea automáticamente para todos los usuarios, independientemente de si está permitida en las directivas de permisos de la aplicación.
4. Haga clic en **Guardar** para que la configuración de la aplicación de toda la organización surta efecto.

Como se mencionó anteriormente, para permitir aplicaciones de terceros, puede editar y usar la directiva global (predeterminada para toda la organización) o crear y asignar directivas personalizadas.

## <a name="faq"></a>Preguntas más frecuentes

### <a name="working-with-app-permission-policies"></a>Trabajar con directivas de permisos de aplicaciones

#### <a name="what-app-interactions-do-permission-policies-affect"></a>¿Qué interacciones de aplicaciones afectan las directivas de permisos?
Las directivas de permisos rigen el uso de la aplicación mediante el control de la instalación, la detección y la interacción de los usuarios finales. Los administradores pueden seguir administrando aplicaciones en el centro de administración de Microsoft Teams independientemente de las directivas de permisos que se les asignen.

#### <a name="can-i-control-line-of-business-lob-apps"></a>¿Puedo controlar las aplicaciones de línea de negocio (LOB)?
Sí, puede usar las directivas de permisos de aplicaciones para controlar el despliegue y la distribución de aplicaciones personalizadas (LOB). Puede crear una directiva personalizada o editar la directiva global para permitir o bloquear aplicaciones personalizadas en función de las necesidades de su organización.

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a>¿Cómo se relacionan las directivas de permisos de aplicaciones con las aplicaciones fijas y las directivas de configuración de aplicaciones?

Puede usar las directivas de configuración de la aplicación junto con directivas de permisos de la aplicación. Las aplicaciones previamente ancladas se seleccionan en el conjunto de aplicaciones habilitadas para un usuario. Además, si un usuario tiene una directiva de permisos de la aplicación que bloquea una aplicación en la Directiva de configuración de la aplicación, esa aplicación no aparecerá en Teams.

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps"></a>¿Puedo usar directivas de permisos de aplicaciones para restringir la carga de aplicaciones personalizadas?

Puede usar la configuración de toda la organización en la página **Administrar aplicaciones** o las directivas de configuración de la aplicación para restringir la carga de aplicaciones personalizadas para su organización.  

Para restringir la carga de aplicaciones personalizadas a usuarios específicos, use directivas de aplicación personalizadas. Para obtener más información, vea [administrar la configuración y las directivas de la aplicación personalizadas en Teams](teams-custom-app-policies-and-settings.md).

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a>¿El bloqueo de una aplicación se aplica a los clientes móviles de Teams?

Sí, cuando bloquea una aplicación, dicha aplicación se bloquea en todos los clientes de Teams.  

### <a name="user-experience"></a>Experiencia de usuario

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a>¿Qué es una experiencia de usuario cuando se bloquea una aplicación?

Los usuarios no pueden interactuar con una aplicación bloqueada ni con sus funciones, como bots, pestañas y extensiones de mensajería. En un contexto compartido, como un chat de grupo o de equipo, los bots pueden enviar mensajes a todos los participantes de ese contexto. Teams indica al usuario Cuándo se bloquea una aplicación.

Por ejemplo, cuando una aplicación está bloqueada, los usuarios no pueden realizar ninguna de las siguientes acciones:

- Agregar la aplicación personalmente o a un chat o un equipo
- Enviar mensajes al bot de la aplicación
- Realizar acciones de botón que envían información a la aplicación, como mensajes accionables  
- Ver la pestaña de la aplicación
- Configurar conectores para recibir notificaciones
- Usar la extensión de mensajería de la aplicación

El portal heredado permitió el control de aplicaciones en el nivel de la organización, lo que significa que cuando una aplicación está bloqueada, está bloqueada para todos los usuarios de la organización. El bloqueo de una aplicación en la página de [Administración de aplicaciones](manage-apps.md) funciona exactamente de la misma manera.

Para directivas de permisos de aplicaciones asignadas a usuarios específicos, si una aplicación con capacidad de bot ó conector se permite y después se bloquea, y si la aplicación solo se permite para algunos usuarios en un contexto compartido, los miembros de un chat o canal de grupo que no tenga permiso para esa aplicación pueden ver el historial de mensajes y los mensajes que el bot o el conector publicaron. , pero no puede interactuar con él.

## <a name="related-topics"></a>Temas relacionados

[Configurar la administración para aplicaciones en Teams](admin-settings.md)

[Asignar directivas a los usuarios de Teams](assign-policies.md)
