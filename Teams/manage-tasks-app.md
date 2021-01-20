---
title: Administrar la aplicación Tareas de su organización en Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
audience: admin
description: Obtenga información sobre cómo administrar la aplicación Tareas para los usuarios de su organización.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2cc477b9589aeebb8dcd486e7f85ca04daf6ff4d
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909404"
---
# <a name="manage-the-tasks-app-for-your-organization-in-microsoft-teams"></a>Administrar la aplicación Tareas de su organización en Microsoft Teams

## <a name="overview-of-tasks"></a>Información general sobre las tareas

La aplicación Tareas ofrece una experiencia cohesiva de administración de tareas en Microsoft Teams, integrando tareas individuales con tecnología de [Microsoft To Do](https://todo.microsoft.com/tasks/) y tareas de equipo con tecnología de Planner en un solo lugar. Los usuarios pueden acceder a Tareas como una aplicación en el lado izquierdo de Teams y como una pestaña en un canal dentro de equipos individuales. **Mis tareas y** **planes compartidos en** Tareas permiten a los usuarios ver y administrar todas sus tareas individuales y de equipo, y priorizar su trabajo. Tareas está disponible en clientes móviles, web y de escritorio de Teams. 

> [!NOTE]
> A medida que se despliegue la experiencia de Tareas en los clientes de escritorio de Teams, el nombre de la aplicación aparecerá inicialmente como **Planner** para los usuarios. A continuación, Planner y **To Do** cambiarán temporalmente el nombre a Tareas y, más adelante, se cambiará el nombre a **Tareas.** En los clientes móviles de Teams, los usuarios siempre verán el nombre de la aplicación como **Tareas.** Es posible que haya un retraso breve en la disponibilidad de la experiencia móvil después de que la experiencia de escritorio esté disponible.

   ![Captura de pantalla de la vista de lista de tareas en la lista de Teams](media/manage-tasks-app-tasks.png)

Para las organizaciones que desean simplificar la administración de tareas para los trabajadores frontline workers, Tareas también incluye funciones que le permiten dirigir, publicar y realizar un seguimiento de las tareas a escala en toda la fuerza de trabajo de la línea frontal. Por ejemplo, los líderes corporativos y regionales pueden crear y publicar listas de tareas dirigidas a ubicaciones relevantes, como tiendas minoristas específicas, y realizar un seguimiento del progreso a través de informes en tiempo real. Los administradores pueden asignar tareas a su personal y actividades directas dentro de sus ubicaciones, y los Trabajadores de primera línea tienen una lista con prioridades de sus tareas asignadas en dispositivos móviles o equipos de escritorio. Para habilitar [la publicación](#task-publishing)de tareas, primero debe configurar una jerarquía de segmentación de equipos para su organización, que define cómo se relacionan entre sí todos los equipos de la jerarquía.

## <a name="what-you-need-to-know-about-tasks"></a>Lo que debe saber sobre Tareas

Las tareas están disponibles como aplicación y como pestaña en un canal. Tenga en cuenta que la aplicación incluye tanto tareas individuales de Tareas pendientes como tareas de equipo de Planner, mientras que en la pestaña solo se muestran las tareas de equipo.

Con Tareas, los usuarios obtienen una experiencia móvil, web y de escritorio. Si Tareas está instalada en el cliente de escritorio de Teams, los usuarios también la verán en sus clientes móviles y web de Teams. La excepción son los usuarios invitados. Es importante saber que los invitados solo pueden acceder a Tareas como una aplicación desde el cliente móvil de Teams. Los invitados verán las pestañas Tareas en los clientes web y de escritorio de Teams.

**Mis tareas** muestran las tareas individuales de un usuario. **Los planes compartidos** muestran las tareas en las que está trabajando todo el equipo e incluyen cualquier lista de tareas que se agrega como una pestaña Tareas a un canal. Tenga en cuenta lo siguiente:

- Las listas de tareas que crea un usuario en la aplicación Tareas también aparecerán en los clientes de To Do para ese usuario. De forma similar, las listas de tareas que un usuario crea en To Do aparecerán en Mis **tareas** en Tareas para ese usuario. Lo mismo ocurre con las tareas individuales.

- Cualquier pestaña Tareas que se agrega a un canal también aparecerá en los clientes de Planner. Cuando un usuario crea un plan en Planner, el plan no se muestra en la aplicación Tareas o Planner a menos que se agrega como una pestaña a un canal. Cuando un usuario agrega una nueva pestaña Tareas, puede crear una lista o un plan, o elegir uno existente.

## <a name="set-up-tasks"></a>Configurar tareas

> [!IMPORTANT]
> Las opciones de configuración y directivas que haya configurado para Planner también se aplicarán a Tareas.

### <a name="enable-or-disable-tasks-in-your-organization"></a>Habilitar o deshabilitar tareas en su organización

Las tareas están habilitadas de forma predeterminada para todos los usuarios de Teams en su organización. Puede desactivar o activar la aplicación en el [](manage-apps.md) nivel de la organización en la página Administrar aplicaciones del Centro de administración de Microsoft Teams.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Administrar aplicaciones de Teams.**  >  
2. En la lista de aplicaciones, realice una de las siguientes acciones:

    - Para desactivar tareas para su organización, busque la aplicación Tareas, selecciónelo y, a continuación, haga clic en **Bloquear.**
    - Para activar Tareas para su organización, busque la aplicación Tareas, selecciónelo y, a continuación, haga clic en **Permitir.**

> [!NOTE]
> Si no encuentra la aplicación Tareas, busque los nombres en la primera nota de este artículo. La aplicación podría seguir en proceso de cambiarse de nombre.

### <a name="enable-or-disable-tasks-for-specific-users-in-your-organization"></a>Habilitar o deshabilitar tareas para usuarios específicos de su organización

Para permitir o impedir que determinados usuarios de la organización utilicen [](manage-apps.md) Tareas, asegúrese de que Tareas está activada para su organización en la página Administrar aplicaciones y, a continuación, cree una directiva de permisos de aplicación personalizada y asígnela a esos usuarios. Para obtener más información, consulte [Administrar directivas de permisos de aplicaciones en Teams.](teams-app-permission-policies.md)

### <a name="use-an-app-setup-policy-to-pin-tasks-to-teams"></a>Usar una directiva de configuración de la aplicación para anclar Tareas a Teams

Las directivas de configuración de aplicaciones le permiten personalizar Teams para resaltar las aplicaciones más importantes para los usuarios de su organización. Las aplicaciones que establezca en una directiva se anclan en la barra de aplicaciones situada a un lado del cliente de escritorio de Teams y en la parte inferior de los clientes móviles de Teams, donde los usuarios pueden acceder a ellos de forma rápida y &mdash; &mdash; sencilla.

Para anclar la aplicación Tareas a los usuarios, puede editar la directiva global (predeterminada para toda la organización) o crear y asignar una directiva de configuración de aplicación personalizada. Para obtener más información, consulte [Administrar directivas de configuración de aplicaciones en Teams.](teams-app-setup-policies.md)

### <a name="a-users-my-tasks-is-visible-if-the-user-is-licensed-for-exchange-online"></a>Las tareas de un usuario son visibles si el usuario tiene licencia para Exchange Online

Si no desea que un usuario vea Mis **tareas,** puede ocultarla. Para ello, [quite la licencia de Exchange Online del usuario.](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users) Es importante saber que después de quitar una licencia de Exchange Online, el usuario ya no tiene acceso a su buzón.  Los datos del buzón se mantienen durante 30 días, tras los cuales los datos se quitarán y no se podrán recuperar a menos que el buzón se coloque en retención local o en retención [por juicio.](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds)

No lo recomendamos para los trabajadores de la información, pero puede haber algunos escenarios en los que esto podría aplicarse, como los trabajadores de primera línea que no dependen del correo electrónico.

## <a name="task-publishing"></a>Publicación de tareas

Con la publicación de tareas, su organización puede publicar listas de tareas dirigidas a ubicaciones específicas (equipos) en toda la organización para definir y compartir un plan de trabajo que se va a completar en esas ubicaciones.

- Los miembros del equipo de publicación, como los líderes corporativos o regionales, pueden crear listas de tareas y publicarlas en equipos específicos.<br>
    ![Captura de pantalla de publicación de tareas](media/manage-tasks-app-publish.png)
- Los administradores de los equipos de destinatarios pueden revisar las listas de tareas publicadas y asignar tareas individuales a los miembros del equipo.<br>
    ![Captura de pantalla de la asignación de una tarea](media/manage-tasks-app-assign.png)
- Los Trabajadores de primera línea tienen una experiencia móvil sencilla para ver las tareas que se les asignaron. Pueden adjuntar fotos para mostrar su trabajo cuando sea necesario y marcar sus tareas como completadas.
- Los editores y administradores pueden ver informes para ver el estado de finalización y asignación de las tareas en cada nivel, incluso por ubicación (equipo), lista de tareas y tarea individual.<br>
    ![Captura de pantalla de tareas asignadas en dispositivos móviles](media/manage-tasks-app-reporting.png)

Los usuarios crean, administran y publican listas de tareas en la **pestaña Listas publicadas** de la aplicación Tareas. Esta pestaña solo se muestra [](#set-up-your-team-targeting-hierarchy) para un usuario si su organización configura una jerarquía de destino de equipo y el usuario se encuentra en un equipo que se incluye en la jerarquía. La jerarquía determina si el usuario puede publicar o recibir listas de tareas y ver los informes de las listas recibidas.

### <a name="example-scenario"></a>Escenario de ejemplo

Este es un ejemplo de cómo funciona la publicación de tareas.

Contoso está implementando una nueva promoción para llevar comida y entrega. Para mantener una experiencia de marca coherente, necesitan coordinar la ejecución coherente de la implementación en más de 300 ubicaciones de almacenamiento.

El equipo de Marketing comparte los detalles de la promoción y la lista correspondiente de tareas con el Administrador de comunicaciones comerciales. El Administrador de comunicaciones al por menor, que actúa como entrenador de tiendas, revisa la información, crea una lista de tareas para la promoción y, a continuación, crea una tarea para cada unidad de trabajo que cada uno de los almacenes afectados tiene que realizar. Una vez completada la lista de tareas, necesita seleccionar las tiendas que deben completar el trabajo. En este caso, la promoción solo se aplica a las tiendas de Estados Unidos que tienen un restaurante en la tienda. En Tareas, filtra la lista de la tienda en función del atributo de restaurante en la tienda, selecciona las ubicaciones de Estados Unidos correspondientes en la jerarquía y, a continuación, publica la lista de tareas en esos almacenes.

Los administradores de store en cada ubicación reciben una copia de las tareas publicadas y las asignan a los miembros de su equipo. Los administradores pueden usar la experiencia de tareas para comprender todo el trabajo requerido en su tienda. También pueden usar los filtros disponibles para centrarse en un conjunto específico de trabajo, como el trabajo que vence hoy o el trabajo en un área específica.

Los trabajadores de frontline workers en cada ubicación de la tienda ahora tienen una lista con prioridades de su trabajo en Tareas en su dispositivo móvil. Cuando finalizan una tarea, la marcan como completada. Algunos pueden incluso elegir cargar y adjuntar una foto a la tarea para mostrar su trabajo.

La sede central de Contoso y los administradores intermedios pueden ver los informes para ver el estado de finalización y asignación de las tareas en cada tienda y en todas las tiendas. También pueden explorar en profundidad una tarea específica para ver el estado en diferentes almacenes. A medida que la fecha de lanzamiento se acerca, pueden detectar cualquier anormalidad y consultar a sus equipos según sea necesario. Esta visibilidad permite a Contoso mejorar la eficiencia del lanzamiento y proporcionar una experiencia más coherente en sus tiendas.

### <a name="set-up-your-team-targeting-hierarchy"></a>Configurar la jerarquía de segmentación de equipos

Para habilitar la publicación de tareas en su organización, primero tiene que configurar el esquema de destino de grupo en un . Archivo CSV. El esquema define cómo se relacionan entre sí todos los equipos de la jerarquía y los atributos usados para filtrar y seleccionar equipos. Después de crear el esquema, súbalo a Teams para aplicarlo a su organización. Los miembros del equipo de publicación (como el Administrador de comunicaciones comerciales en el escenario de ejemplo) pueden filtrar los equipos por jerarquía, atributos o una combinación de ambos para seleccionar los equipos pertinentes que recibirán las listas de tareas y, a continuación, publicar las listas de tareas en esos equipos.

Para obtener información sobre cómo configurar la jerarquía de segmentación de equipos, vea Configurar la jerarquía de segmentación [de equipos.](set-up-your-team-hierarchy.md)

## <a name="power-automate-and-graph-api"></a>API power automate y graph

Tareas es compatible con las API de Power Automate for To Do y Graph para Planner. Para obtener más información, consulte:

- [Introducción a las tareas y planes de la API de Planner](https://docs.microsoft.com/graph/planner-concept-overview)
- [Usar Microsoft To Do con Power Automate](https://support.office.com/article/using-microsoft-to-do-with-power-automate-526e8f75-217b-46e0-9e06-44780b72c295)
