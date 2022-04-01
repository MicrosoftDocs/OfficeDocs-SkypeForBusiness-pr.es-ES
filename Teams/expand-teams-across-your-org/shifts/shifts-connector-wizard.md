---
title: Usar el Asistente para conectores de turnos para conectar Turnos a Blue Yonder Workforce Management
author: lanachin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo usar el Asistente para conectores de turnos para integrar Turnos en Teams con Blue Yonder Workforce Management.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4041b0909a3c5e8f1aa256fd2ec662030548343c
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2022
ms.locfileid: "64593697"
---
# <a name="use-the-shifts-connector-wizard-to-connect-shifts-to-blue-yonder-workforce-management"></a>Usar el Asistente para conectores de turnos para conectar Turnos a Blue Yonder Workforce Management

## <a name="overview"></a>Información general

El asistente para conectores turnos de la Centro de administración de Microsoft 365 le permite integrar la aplicación Turnos en Microsoft Teams con su sistema de administración de fuerza de trabajo (WFM). Después de configurar una conexión, los trabajadores de primera línea pueden ver y administrar sin problemas sus programaciones en el sistema WFM desde Turnos.

El asistente configura el conector Turnos, crea una conexión con el sistema WFM y aplica la configuración de sincronización y las asignaciones de equipo que elija. La configuración de sincronización determina la información de programación que se sincroniza entre su sistema WFM y Turnos. Las asignaciones de equipo definen la relación de sincronización entre los sitios y los equipos de WFM en Teams. Puede asignar a equipos existentes y nuevos equipos.

Puede configurar varias conexiones, cada una con diferentes configuraciones de sincronización. Por ejemplo, si su organización tiene varias ubicaciones con requisitos de programación diferentes, cree una conexión con una configuración de sincronización única para cada ubicación. Tenga en cuenta que un sitio WFM solo se puede asignar a un equipo en un momento dado. Si un sitio WFM ya está asignado a un equipo, no se puede asignar a otro equipo.

Con el sistema WFM como sistema de registro, los trabajadores de primera línea pueden ver e intercambiar turnos, administrar su disponibilidad y solicitar permiso en Turnos en sus dispositivos. Los administradores de primera línea pueden seguir usando el sistema WFM para configurar las programaciones.

## <a name="integrate-shifts-with-blue-yonder-workforce-management"></a>Integrar turnos con Blue Yonder Workforce Management

Actualmente, el asistente admite el [conector Microsoft Teams Turnos para Blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder). Este conector le permite integrar Turnos con Blue Yonder Workforce Management (Blue Yonder WFM) para administrar sus programaciones y mantenerlas actualizadas. En este artículo, le explicamos cómo ejecutar el asistente para configurar una conexión a Blue Yonder WFM a través del conector.

> [!NOTE]
> También puede usar PowerShell para integrar Turnos con Blue Yonder WFM. Para obtener más información, vea [Usar PowerShell para conectar Turnos a Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md).

## <a name="before-you-begin"></a>Antes de empezar

Debe ser un administrador Microsoft 365 global para ejecutar el asistente.

### <a name="prerequisites"></a>Requisitos previos
<a name="prerequisites"> </a>
[!INCLUDE [shifts-connector-prerequisites](../../includes/shifts-connector-prerequisites.md)]

- Los equipos que desea asignar no tienen ninguna programación. Si un equipo tiene una programación existente, [quite](#remove-schedules-from-teams-you-want-to-map) la programación del equipo antes de asignarle un sitio wfm de Yonder azul. En caso contrario, verá turnos duplicados.

## <a name="remove-schedules-from-teams-you-want-to-map"></a>Quitar programaciones de los equipos que desea asignar
<a name="remove_schedules"> </a>

> [!NOTE]
> Complete este paso si va a asignar sitios wfm de Yonder azul a equipos existentes que tengan programaciones. Si está asignando a equipos que no tienen ninguna programación o si va a crear nuevos equipos a los que asignar, puede omitir este paso.

Use PowerShell para quitar programaciones de los equipos.

1. En primer lugar, tendrá que instalar los módulos de PowerShell y configurarlo. Siga los pasos para [configurar su entorno](shifts-connector-powershell-manage.md#set-up-your-environment).
1. Ejecute el siguiente comando:

    ```powershell
    Remove-CsTeamsShiftsScheduleRecord -TeamId <Teams team ID> -DateRangeStartDate <start time> -DateRangeEndDate <end time> -ClearSchedulingGroup:$false -EntityType <the scenario entities that you want to remove, the format is @(scenario1, scenario2, ...)> -DesignatedActorId <Teams team owner ID>
    ```

    Para obtener una lista de escenarios para el `EntityType` parámetro, ejecute [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps). Los datos de programación se quitarán para el intervalo de fecha y hora que especifique.

Para obtener más información, [vea Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord?view=teams-ps).

## <a name="run-the-wizard"></a>Ejecutar el asistente

### <a name="get-started"></a>Introducción

1. En el panel de navegación izquierdo de [la Centro de administración de Microsoft 365](https://admin.microsoft.com/), elija **Configurar** y, a continuación, vaya a la **sección Aplicaciones y correo** electrónico.
1. Seleccione **Conectar su sistema de administración de la fuerza laboral**. Aquí puede obtener más información sobre los conectores de Turnos y la experiencia de los trabajadores y administradores de primera línea al conectar Turnos a su sistema WFM.
    :::image type="content" source="../../media/shifts-connector-wizard-get-started.png" alt-text="Captura de pantalla de la página de detalles del Asistente para conectores de turnos en el Centro de administración de Microsoft 365." lightbox="../../media/shifts-connector-wizard-get-started.png":::
1. Cuando esté listo, seleccione **Comenzar**.
1. Seleccione **Siguiente** para crear una conexión WFM de Yonder azul.

### <a name="enter-connection-details"></a>Especificar detalles de conexión
<a name="connection_details"> </a>

1. En la página Detalles de conexión, asigne un nombre único a la conexión. No puede tener más de 128 caracteres ni tener ningún carácter especial.
    :::image type="content" source="../../media/shifts-connector-wizard-connection-details.png" alt-text="Captura de pantalla de la página Detalles de conexión del asistente, que muestra la configuración de conexión." lightbox="../../media/shifts-connector-wizard-connection-details.png":::
1. Escriba el nombre de la cuenta del servicio WFM de Yonder azul y las direcciones URL de contraseña y servicio.
1. Cuando haya terminado, seleccione **Siguiente** para probar la conexión con la configuración que ha escrito.

### <a name="choose-sync-settings"></a>Elegir la configuración de sincronización
<a name="sync"> </a>

En la página Configuración de sincronización, elija la información que desea sincronizar de Blue Yonder WFM a Mayúss, la frecuencia de sincronización y si los usuarios de Turnos pueden realizar cambios en los datos.

1. Escriba su Microsoft 365 del sistema.
    :::image type="content" source="../../media/shifts-connector-wizard-sync-settings.png" alt-text="Captura de pantalla de la página Configuración de sincronización del asistente, que muestra la configuración de sincronización." lightbox="../../media/shifts-connector-wizard-sync-settings.png":::
<a name="email"> </a>
1. En **Destinatarios de notificaciones por correo electrónico**, elija quién recibe notificaciones por correo electrónico sobre esta conexión. Puede agregar usuarios y grupos individuales. Las notificaciones por correo electrónico contienen información sobre el estado de la configuración de la conexión y los problemas o errores que puedan producirse después de configurar la conexión.
1. Elija la configuración de sincronización:
    1. En **Programación y turnos**, elija los datos de WFM de Yonder azul que los usuarios pueden ver o cambiar y, a continuación, establecer la frecuencia de sincronización.
    2. En **Solicitudes**, elija los tipos de solicitudes que los usuarios de Turnos pueden ver y crear.

    > [!IMPORTANT]
    > Si eligió cualquiera de las siguientes opciones para deshabilitar turnos abiertos, abrir solicitudes de turno, solicitudes de intercambio o solicitudes de permiso, hay otro paso que debe hacer para ocultar la capacidad en Turnos.
    >
    > - Abrir turnos: **los usuarios de Turnos no verán los datos de WFM de Yonder azul**
    > - Solicitudes de intercambio: **la característica está deshabilitada para todos los usuarios**
    > - Solicitudes de permiso: **la característica está deshabilitada para todos los usuarios**
    >
    > Después de ejecutar el asistente, asegúrese de seguir los pasos de la sección Deshabilitar turnos abiertos, abrir solicitudes de [turnos,](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) solicitudes de intercambio y solicitudes de permiso más adelante en este artículo.
 
1. Cuando haya terminado de elegir la configuración, seleccione **Crear conexión**.

### <a name="map-blue-yonder-workforce-management-sites-to-teams"></a>Asignar sitios de Administración de la fuerza laboral de Yonder azul a equipos
<a name="sites"> </a>

Elija los sitios de WFM de Yonder azul que desea conectar a Turnos. Puede seleccionar hasta 100 sitios.

:::image type="content" source="../../media/shifts-connector-wizard-sites.png" alt-text="Captura de pantalla del asistente, que muestra una lista de sitios wfm de Yonder azul." lightbox="../../media/shifts-connector-wizard-sites.png":::
<a name="mapping"> </a>
<a name="search_teams"> </a> A continuación, asigne cada sitio DE WFM de Yonder azul que haya seleccionado a un equipo en Teams. Puede asignar un sitio a un equipo existente o puede crear un equipo nuevo.
:::image type="content" source="../../media/shifts-connector-wizard-search-team.png" alt-text="Captura de pantalla del panel que muestra la opción de equipo de búsqueda y crea una nueva opción de equipo." lightbox="../../media/shifts-connector-wizard-search-team.png":::
#### <a name="to-map-a-site-to-an-existing-team"></a>Para asignar un sitio a un equipo existente

1. Seleccione el nombre del sitio.
2. En el panel, busque el equipo y selecciónelo. Tenga en cuenta que los equipos que ya están asignados a un sitio en esta conexión no se muestran en la búsqueda.
3. Elija la zona horaria y la ciudad más cercana.
4. Seleccione **Guardar** y, a continuación, **seleccione Siguiente**.

#### <a name="to-map-a-site-to-a-new-team"></a>Para asignar un sitio a un equipo nuevo

1. Seleccione el nombre del sitio.
2. En el panel, elija **Crear un equipo nuevo**. Se le mostrará una pestaña nueva en el explorador donde puede crear un equipo nuevo en el Centro de administración de Microsoft 365.
    1. Escriba un nombre y una descripción opcional para el equipo.
    1. Agregue uno o varios propietarios de equipos. Asegúrese de agregar la cuenta Microsoft 365 del sistema como propietario.
    1. Agregar miembros del equipo.
    1. Agregue una dirección de correo electrónico de grupo y elija una configuración de privacidad.
    1. Revise la configuración y, a continuación, **elija Agregar equipo**. Cuando se cree el equipo, elija **Cerrar**.
3. Volver al asistente, busque y, a continuación, seleccione el nuevo equipo que creó.
4. Elija la zona horaria y la ciudad más cercana.
5. Seleccione **Guardar** y, a continuación, **seleccione Siguiente**.

### <a name="review-and-finish"></a>Revisar y finalizar

Revise la configuración. Si necesita realizar cambios en las asignaciones de equipo, elija **Editar** para hacerlo. Cuando esté listo, seleccione **Finalizar**.

:::image type="content" source="../../media/shifts-connector-wizard-review.png" alt-text="Captura de pantalla de la página Revisar del asistente, que muestra asignaciones." lightbox="../../media/shifts-connector-wizard-review.png":::

Verá un mensaje para confirmar que hemos recibido la solicitud junto con un id. de operación. Anote el id. de operación. Lo necesitará para comprobar el estado de configuración de la conexión.

:::image type="content" source="../../media/shifts-connector-wizard-operation-id.png" alt-text="Captura de pantalla de la página del asistente, que muestra el mensaje de confirmación y el id. de operación." lightbox="../../media/shifts-connector-wizard-operation-id.png":::

El asistente inicia el proceso para configurar la conexión y asignar los sitios a los equipos seleccionados. Este proceso puede tardar algún tiempo en completarse. Los destinatarios que elija recibirán notificaciones por correo electrónico sobre el estado de configuración.

Seleccione **Listo** para salir del asistente.

Estás en camino, pero aún no has terminado. Asegúrese de comprobar el correo electrónico. Recibirás una confirmación de que hemos recibido tu solicitud junto con un [vínculo](shifts-connector-powershell-manage.md#check-connection-setup-status) a cómo puedes comprobar el estado de configuración.

> [!NOTE]
> Si se produce un problema o un error en una conexión después de configurarlo, se le notificará por correo electrónico. Siga las instrucciones del correo electrónico para solucionar el problema.

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>Deshabilitar turnos abiertos, abrir solicitudes de turnos, solicitudes de intercambio y solicitudes de permiso

> [!IMPORTANT]
> Siga estos pasos solo si eligió cualquiera de las siguientes opciones para deshabilitar turnos abiertos, abrir solicitudes de turno, solicitudes de intercambio o solicitudes de permiso en el asistente. Al completar este paso, se oculta la capacidad en Turnos.
>
> - Abrir turnos: **los usuarios de Turnos no verán los datos de WFM de Yonder azul**
> - Solicitudes de intercambio: **la característica está deshabilitada para todos los usuarios**
> - Solicitudes de permiso: **la característica está deshabilitada para todos los usuarios**
>
> Sin este segundo paso, los usuarios seguirán teniendo la capacidad en Turnos y recibirán un mensaje de error de "operación no compatible" si intentan usarlo.

Para ocultar turnos abiertos, solicitudes de intercambio y solicitudes de permiso en Turnos, use el tipo de recurso programación de Graph API para establecer los siguientes [parámetros para cada](/graph/api/resources/schedule?view=graph-rest-1.0) equipo asignado a ```false``` un sitio WFM de Yonder azul:

- Abrir turnos: ```openShiftsEnabled```
- Solicitudes de intercambio:  ```swapShiftsRequestsEnabled```
- Solicitudes de permiso: ```timeOffRequestsEnabled```

Para ocultar las solicitudes de turnos abiertos en Turnos, vaya a **Configuración** en Turnos y, después, desactive la configuración **Abrir turnos**.

## <a name="if-you-need-to-make-changes-to-a-connection"></a>Si necesita realizar cambios en una conexión
<a name="update_connection"> </a>

Después de configurar una conexión, use PowerShell para realizar cambios en ella. Por ejemplo, puede actualizar la configuración de sincronización, las asignaciones de equipo y deshabilitar la sincronización para una conexión. Para obtener instrucciones paso a paso, vea [Usar PowerShell para administrar la conexión de Turnos a Blue Yonder Workforce Management](shifts-connector-powershell-manage.md).

## <a name="related-articles"></a>Artículos relacionados

- [Conectores de turnos](shifts-connectors.md)
- [Usar PowerShell para administrar la conexión de Turnos a Blue Yonder Workforce Management](shifts-connector-powershell-manage.md)
- [Administrar la aplicación Turnos en Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
