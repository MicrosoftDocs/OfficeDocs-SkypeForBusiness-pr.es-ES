---
title: Administrar la aplicación Tasks para su organización en Microsoft Teams
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: andfried
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
audience: admin
description: Obtenga información sobre cómo administrar la aplicación Tasks para los usuarios de su organización.
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- microsoftcloud-healthcare
- microsoftcloud-retail
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6412da5bdce345c1d187fd150b3877a63602b40b
ms.sourcegitcommit: 159399f2325af644c20551925c1fa34bf76aad43
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2022
ms.locfileid: "62288358"
---
# <a name="manage-the-tasks-app-for-your-organization-in-microsoft-teams"></a>Administrar la aplicación Tasks para su organización en Microsoft Teams

## <a name="overview-of-tasks"></a>Información general de Tasks

La aplicación Tasks ofrece una experiencia de administración de tareas uniforme en Microsoft Teams. Integra en un solo lugar tareas individuales con la tecnología de [Microsoft To Do](https://todo.microsoft.com/tasks/) y tareas de equipo con la tecnología de Planner. Los usuarios pueden acceder a Tasks como una aplicación en el lado izquierdo de Teams y como una pestaña en un canal dentro de los equipos individuales. Con **Mis tareas y** **Planes compartidos**, los usuarios pueden ver y administrar todas sus tareas individuales y de grupo y priorizar su trabajo. Tasks está disponible en clientes móviles, web y de escritorio de Teams.

> [!NOTE]
> A medida que implementamos la experiencia de Tasks en los clientes de escritorio de Teams, el nombre de la aplicación aparecerá inicialmente como **Planner** para los usuarios. Después, el nombre cambiará temporalmente a **Tasks de Planner y To Do** y, posteriormente, a **Tasks**. En los clientes móviles de Teams, los usuarios siempre verán el nombre de la aplicación como **Tasks**. Una vez que la experiencia de escritorio esté disponible, puede haber un retraso breve en la disponibilidad de la experiencia móvil.

   ![Captura de pantalla de la vista de lista de tareas Teams lista.](media/manage-tasks-app-tasks.png)

Para las organizaciones que desean simplificar la administración de tareas para los trabajadores de primera línea, Tasks también permite dirigir, publicar y seguir las tareas a escala para todos los trabajadores de primera línea. Por ejemplo, los líderes corporativos y regionales pueden crear y publicar listas de tareas dirigidas a ubicaciones relevantes, como tiendas minoristas específicas, y seguir el progreso a través de informes en tiempo real. Los administradores pueden asignar tareas a su personal y actividades directas dentro de sus ubicaciones, mientras que los trabajadores de primera línea tienen una lista prioritaria de tareas asignadas en dispositivos móviles o de escritorio. Para habilitar [la publicación de](#task-publishing) tareas, primero configure una jerarquía de segmentación de equipos para su organización, que define cómo todos los equipos de la jerarquía están relacionados entre sí.

## <a name="what-you-need-to-know-about-tasks"></a>Todo lo que debe saber sobre Tasks

Tasks está disponible como una aplicación y como una pestaña en un canal. La aplicación muestra las tareas individuales de To Do tareas de grupo de Planner. La pestaña muestra solo las tareas de grupo.

Con Tasks, los usuarios obtienen una experiencia móvil, web y de escritorio. Si Tasks está instalada en el cliente de escritorio de Teams, los usuarios también la verán en sus clientes móviles y web de Teams. La excepción son los invitados. Desde el cliente móvil de Teams, los invitados solo pueden obtener acceso a Tasks como una aplicación. En los clientes web y de escritorio de Teams verán las pestañas Tasks.

**Mis tareas** muestra las tareas individuales de un usuario. **Planes compartidos** muestra las tareas en las que trabaja todo el equipo e incluye cualquier lista de tareas que se agregue como pestaña de Tasks a un canal. Observe las siguientes relaciones entre tareas en Tareas, To Do y Planner:

- Las listas de tareas que cree un usuario en la aplicación Tasks también aparecerán en los clientes de To Do para ese usuario. De forma similar, las listas de tareas que un usuario cree en To Do aparecerán en **Mis tareas** de Tasks para ese usuario. Lo mismo ocurre para las tareas individuales.

- Cualquier pestaña de Tasks que se agregue a un canal también aparecerá en los clientes de Planner. Cuando un usuario cree un plan en Planner, el plan no se mostrará en la aplicación Tasks o de Planner a menos que se haya agregado como pestaña a un canal. Al agregar una nueva pestaña de Tasks, el usuario podrá crear una lista o plan nuevos, o elegir uno existente.

## <a name="set-up-tasks"></a>Configurar Tasks

> [!IMPORTANT]
> Las opciones y las directivas configuradas para Planner también se aplicarán a Tasks.

### <a name="enable-or-disable-tasks-in-your-organization"></a>Deshabilitar o habilitar Tasks en la organización

De forma predeterminada, Tasks está habilitado para todos los usuarios de Teams de su organización. Puede desactivar o activar la aplicación en el nivel de organización en la página [Administrar aplicaciones](manage-apps.md) del Centro de administración de Microsoft Teams.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **Administrar aplicaciones**.
2. En la lista de aplicaciones, siga uno de estos pasos:

    - Para desactivar Tareas para su organización, busque la aplicación Tareas, selecciónelo y, a continuación, **seleccione Bloquear**.
    - Para activar Tareas para su organización, busque la aplicación Tareas, selecciónelo y, a continuación, **seleccione Permitir**.

> [!NOTE]
> Si no encuentra la aplicación Tasks, busque los nombres mencionados en la primera nota de este artículo. Es posible que todavía se esté cambiando el nombre de la aplicación.

### <a name="enable-or-disable-tasks-for-specific-users-in-your-organization"></a>Habilitar o deshabilitar Tasks para usuarios específicos de su organización

Para permitir o impedir que usuarios específicos de la organización puedan usar Tasks, asegúrese de que la aplicación esté activada para su organización en la página [Administrar aplicaciones](manage-apps.md) y después cree una directiva de permisos de aplicación personalizada y asígnela a esos usuarios. Para obtener más información, consulte [Administrar configuración y directivas de aplicación personalizadas en Teams](teams-app-permission-policies.md).

### <a name="use-an-app-setup-policy-to-pin-tasks-to-teams"></a>Usar una directiva de configuración de aplicación para anclar Tasks a Teams

Las directivas de configuración de aplicaciones le permiten personalizar Teams para resaltar las aplicaciones que sean más importantes para los usuarios de su organización. Las aplicaciones que establezca en una directiva se anclan Teams la barra de aplicaciones (la barra del lado del cliente de escritorio de Teams y en la parte inferior de los clientes móviles de Teams), donde los usuarios pueden acceder a ellas de forma rápida y sencilla.

Para anclar la aplicación Tasks para sus usuarios, puede editar la directiva global (predeterminada para toda la organización) o crear y asignar una directiva de configuración de aplicación personalizada. Para obtener más información, consulte [Administrar las directivas de configuración de aplicaciones en Teams](teams-app-setup-policies.md).

### <a name="a-users-my-tasks-is-visible-if-the-user-is-licensed-for-exchange-online"></a>Un usuario solo podrá ver Mis tareas si tiene licencia para Exchange Online.

Si no desea que un usuario vea **Mis tareas**, puede ocultarlas. Para ocultar **Mis tareas**, [quite la licencia de Exchange Online usuario](/microsoft-365/admin/manage/remove-licenses-from-users). Debe saber que después de quitar una licencia de Exchange Online, el usuario ya no tendrá acceso a su buzón.  Los datos del buzón se conservarán durante 30 días. Después, se quitarán y no se podrán recuperar a menos que se aplique al buzón una [Conservación local o Suspensión legal](/exchange/security-and-compliance/in-place-and-litigation-holds).

No se recomienda quitar una licencia de Exchange Online para los trabajadores de la información, pero puede haber algunos escenarios en los que puede ocultar Mis  tareas de esta manera, como para los trabajadores de frontline que no dependen del correo electrónico.

## <a name="task-publishing"></a>Publicación de tareas

Con la publicación de tareas, la organización puede publicar listas de tareas dirigidas a ubicaciones específicas (equipos) de su organización para definir y compartir un plan de trabajo que se vaya a completar en esas ubicaciones.

- Los miembros del equipo de publicación, como la dirección regional o corporativa, pueden crear listas de tareas y publicarlas en equipos específicos.<br>
    ![Captura de pantalla de la publicación de tareas.](media/manage-tasks-app-publish.png)
- Los administradores de los equipos de destinatarios pueden revisar las listas de tareas publicadas y asignar tareas individuales a los miembros del equipo.<br>
    ![Captura de pantalla de asignación de una tarea.](media/manage-tasks-app-assign.png)
- Los trabajadores pueden ver sus tareas asignadas de forma sencilla en sus móviles. Pueden adjuntar fotos para mostrar su trabajo cuando corresponda y marcar sus tareas como completadas.
- Quienes publiquen tareas y los administradores podrán ver en los informes a quiénes se han asignado las tareas y su progreso en cada nivel, incluidas la ubicación (equipo), la lista de tareas y la tarea individual.<br>
    ![Captura de pantalla de tareas asignadas en dispositivos móviles.](media/manage-tasks-app-reporting.png)

Los usuarios podrán crear, administrar y publicar listas de tareas en la pestaña **Listas publicadas** de la aplicación Tasks. En esta pestaña solo se muestra a un usuario si su organización [configura una jerarquía basada en equipos](#set-up-your-team-targeting-hierarchy) y si el usuario se encuentra en un equipo incluido en la jerarquía. La jerarquía determina si el usuario puede publicar o recibir listas de tareas y ver los informes de las listas recibidas.

### <a name="example-scenario"></a>Ejemplo ficticio

A continuación le mostramos un ejemplo para ilustrar cómo funciona la publicación de tareas.

Pongamos que la empresa Contoso quiere implementar una nueva promoción para sus tiendas con servicio de alimentación. Quiere ofrecer una experiencia de marca coherente y coordinar el lanzamiento de la promoción de la manera más uniforme posible en sus más de 300 establecimientos.

El equipo de Marketing compartirá los detalles de la promoción y la lista correspondiente de tareas con el Administrador de comunicaciones de minoristas. El Administrador de comunicaciones minoristas, que actúa como portero de las tiendas, revisa la información. A continuación, crean una lista de tareas para la promoción y crean una tarea para cada unidad de trabajo que deben realizar las tiendas afectadas. Cuando se complete la lista de tareas, deben seleccionar las tiendas que deben completar el trabajo. En este caso, la promoción solo se aplica a las tiendas de Estados Unidos que tengan un restaurante en la tienda. En Tareas, filtran la lista de tiendas en función del atributo de restaurante en la tienda, seleccionan las ubicaciones de Estados Unidos que coinciden en la jerarquía y, a continuación, publican la lista de tareas en esas tiendas.

Los administradores de tienda en cada ubicación recibirán una copia de las tareas publicadas y asignarán esas tareas a los miembros de su equipo. Los administradores podrán usar la experiencia Tasks para comprender todo el trabajo necesario en todas las áreas de sus tiendas. También podrán usar los filtros para centrarse en un conjunto específico de trabajos, como un trabajo que vence hoy o el trabajo de un área específica.

Los trabajadores de primera línea en cada ubicación de la tienda tendrán ahora en su dispositivo móvil una lista con prioridades de su trabajo en Tasks. Cuando terminen una tarea, la marcarán como completada. Incluso pueden elegir cargar y adjuntar una foto a la tarea para mostrar su trabajo.

Los administradores intermedios y los gerentes de Contoso podrán ver en los informes la asignación y el progreso de las tareas de cada tienda y de las tiendas en su conjunto. También podrán explorar en profundidad una tarea específica para ver su estado en diferentes tiendas. A medida que se acerque la fecha de lanzamiento, podrán detectar cualquier anomalía y comentarla con sus equipos cuando sea necesario. Esta visibilidad permite a Contoso mejorar la eficiencia del lanzamiento y proporcionar una experiencia más coherente en sus tiendas.

### <a name="set-up-your-team-targeting-hierarchy"></a>Configurar la jerarquía de destinos de equipo

Para habilitar la publicación de tareas en su organización, primero tiene que configurar el esquema basado en equipos en un archivo CSV. El esquema define cómo todos los equipos de la jerarquía están relacionados entre sí y también define los atributos que se pueden usar para filtrar y seleccionar equipos. Después de crear el esquema, cárguelo en Teams para aplicarlo a su organización. Los miembros del equipo de publicación, como el Administrador de comunicaciones de minoristas en el ejemplo anterior, pueden filtrar los equipos por jerarquía, atributos o una combinación de ambos para seleccionar los equipos relevantes que deben recibir las listas de tareas y, después, publicar las listas de tareas en esos equipos.

Para obtener información sobre cómo configurar la jerarquía basada en equipos, consulte [Configurar la jerarquía basada en equipos](set-up-your-team-hierarchy.md).

## <a name="power-automate-and-graph-api"></a>Power Automate y la API de Graph

Tasks es compatible con Power Automate para To Do y Graph API para Planner. Para obtener más información, vea:

- [Introducción a la API de tareas y planes de Planner](/graph/planner-concept-overview)
- [Uso de Microsoft To Do con Power Automate](https://support.office.com/article/using-microsoft-to-do-with-power-automate-526e8f75-217b-46e0-9e06-44780b72c295)