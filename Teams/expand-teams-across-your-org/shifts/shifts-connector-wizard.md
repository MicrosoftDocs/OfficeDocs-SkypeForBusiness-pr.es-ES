---
title: Usar el asistente del conector Turnos para conectar Turnos a Blue Yonder Workforce Management
author: lanachin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo usar el asistente para conectores Shifts para integrar Turnos en Teams con Blue Yonder Workforce Management.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4041b0909a3c5e8f1aa256fd2ec662030548343c
ms.sourcegitcommit: bf0071417188b33fc23e2a420187da5024d4bd40
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2022
ms.locfileid: "64593697"
---
# <a name="use-the-shifts-connector-wizard-to-connect-shifts-to-blue-yonder-workforce-management"></a>Usar el asistente del conector Turnos para conectar Turnos a Blue Yonder Workforce Management

## <a name="overview"></a>Información general

El asistente del conector Shifts de la Centro de administración de Microsoft 365 le permite integrar la aplicación Turnos en Microsoft Teams con su sistema de administración de la fuerza de trabajo (WFM). Después de configurar una conexión, sus trabajadores de primera línea pueden ver y administrar sin problemas sus programaciones en su sistema WFM desde Shifts.

El asistente configura el conector Shifts, crea una conexión a su sistema WFM y aplica la configuración de sincronización y las asignaciones de equipo que elija. La configuración de sincronización determina la información de programación que se sincroniza entre el sistema WFM y Shifts. Las asignaciones de equipos definen la relación de sincronización entre los sitios de WFM y los equipos en Teams. Puede asignar a equipos existentes y nuevos equipos.

Puede configurar varias conexiones, cada una con configuraciones de sincronización diferentes. Por ejemplo, si su organización tiene varias ubicaciones con requisitos de programación diferentes, cree una conexión con la configuración de sincronización única para cada ubicación. Tenga en cuenta que un sitio de WFM solo se puede asignar a un equipo en cualquier momento. Si un sitio de WFM ya está asignado a un equipo, no se puede asignar a otro equipo.

Con su sistema WFM como sistema de registro, sus trabajadores de primera línea pueden ver e intercambiar turnos, administrar su disponibilidad y solicitar permisos en turnos en sus dispositivos. Los gestores de primera línea pueden seguir usando su sistema WFM para configurar programaciones.

## <a name="integrate-shifts-with-blue-yonder-workforce-management"></a>Integrar Turnos con Blue Yonder Workforce Management

Actualmente, el asistente es compatible con el [conector Microsoft Teams Turnos para Yonder azul](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder). Este conector le permite integrar Turnos con Blue Yonder Workforce Management (Blue Yonder WFM) para administrar sus programaciones y mantenerlos actualizados. En este artículo, le guiaremos por cómo ejecutar el asistente para configurar una conexión a Blue Yonder WFM a través del conector.

> [!NOTE]
> También puede usar PowerShell para integrar Turnos con Blue Yonder WFM. Para obtener más información, consulte [Usar PowerShell para conectar Turnos a Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md).

## <a name="before-you-begin"></a>Antes de empezar

Debe ser un Microsoft 365 administrador global para ejecutar el asistente.

### <a name="prerequisites"></a>Requisitos previos
<a name="prerequisites"> </a>
[!INCLUDE [shifts-connector-prerequisites](../../includes/shifts-connector-prerequisites.md)]

- Los equipos a los que quiere asignar no tienen ninguna programación. Si un equipo tiene una programación existente, [quite la programación del equipo](#remove-schedules-from-teams-you-want-to-map) antes de asignarle un sitio de WFM de Blue Yonder. En caso contrario, verá turnos duplicados.

## <a name="remove-schedules-from-teams-you-want-to-map"></a>Quitar programaciones de equipos que quiera asignar
<a name="remove_schedules"> </a>

> [!NOTE]
> Complete este paso si está asignando sitios de WfM de Blue Yonder a equipos existentes que tienen programaciones. Si está asignando equipos que no tienen ninguna programación o si está creando nuevos equipos a los que asignar, puede omitir este paso.

Use PowerShell para quitar programaciones de equipos.

1. En primer lugar, deberá instalar los módulos de PowerShell y configurarlos. Siga los pasos para [configurar su entorno](shifts-connector-powershell-manage.md#set-up-your-environment).
1. Ejecute el siguiente comando:

    ```powershell
    Remove-CsTeamsShiftsScheduleRecord -TeamId <Teams team ID> -DateRangeStartDate <start time> -DateRangeEndDate <end time> -ClearSchedulingGroup:$false -EntityType <the scenario entities that you want to remove, the format is @(scenario1, scenario2, ...)> -DesignatedActorId <Teams team owner ID>
    ```

    Para obtener una lista de escenarios para el `EntityType` parámetro, ejecute [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector?view=teams-ps). Los datos de programación se quitarán para el intervalo de fecha y hora que especifique.

Para obtener más información, vea [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord?view=teams-ps).

## <a name="run-the-wizard"></a>Ejecutar el asistente

### <a name="get-started"></a>Introducción

1. En el panel de navegación izquierdo de la [Centro de administración de Microsoft 365](https://admin.microsoft.com/), elija **Configuración** y, después, vaya a la sección **Aplicaciones y correo electrónico**.
1. Seleccione **Conectar su sistema de administración de la fuerza laboral**. Aquí puede obtener más información sobre los conectores de Turnos y la experiencia de los trabajadores de primera línea y del administrador al conectar Turnos a su sistema WFM.
    :::image type="content" source="../../media/shifts-connector-wizard-get-started.png" alt-text="Captura de pantalla de la página de detalles del asistente del conector Turnos en la Centro de administración de Microsoft 365." lightbox="../../media/shifts-connector-wizard-get-started.png":::
1. Cuando esté listo, seleccione **Comenzar**.
1. Seleccione **Siguiente** para crear una conexión de WfM de Blue Yonder.

### <a name="enter-connection-details"></a>Escribe los detalles de la conexión
<a name="connection_details"> </a>

1. En la página Detalles de la conexión, asigna un nombre único a la conexión. No puede tener más de 128 caracteres o tener caracteres especiales.
    :::image type="content" source="../../media/shifts-connector-wizard-connection-details.png" alt-text="Captura de pantalla de la página Detalles de la conexión del asistente, que muestra la configuración de conexión." lightbox="../../media/shifts-connector-wizard-connection-details.png":::
1. Escriba su nombre de cuenta de servicio de WfM de Blue Yonder y las direcciones URL de servicio y contraseña.
1. Cuando hayas terminado, selecciona **Siguiente** para probar la conexión con la configuración especificada.

### <a name="choose-sync-settings"></a>Elegir la configuración de sincronización
<a name="sync"> </a>

En la página Configuración de sincronización, elija la información para sincronizar de Blue Yonder WFM a Shifts, la frecuencia de sincronización y si los usuarios de Shifts pueden realizar cambios en los datos.

1. Escriba su cuenta del sistema de Microsoft 365.
    :::image type="content" source="../../media/shifts-connector-wizard-sync-settings.png" alt-text="Captura de pantalla de la página Configuración de sincronización del asistente, que muestra la configuración de sincronización." lightbox="../../media/shifts-connector-wizard-sync-settings.png":::
<a name="email"> </a>
1. En **Destinatarios de notificación por correo electrónico**, elija quién recibe notificaciones por correo electrónico sobre esta conexión. Puede agregar usuarios y grupos individuales. Las notificaciones por correo electrónico contienen información sobre el estado de configuración de la conexión y los problemas o errores que se pueden producir después de configurar la conexión.
1. Elija la configuración de sincronización:
    1. En **Programación y turnos**, elija los datos de WfM de Blue Yonder que los usuarios de Shifts pueden ver o cambiar y, a continuación, establezca la frecuencia de sincronización.
    2. En **Solicitudes**, elija los tipos de solicitudes que los usuarios de Turnos pueden ver y crear.

    > [!IMPORTANT]
    > Si eligió cualquiera de las siguientes opciones para deshabilitar turnos abiertos, solicitudes de turno abiertas, solicitudes de intercambio o solicitudes de permisos, hay otro paso que debe hacer para ocultar la funcionalidad en Turnos.
    >
    > - Turnos abiertos: **Los usuarios de Turnos no verán los datos de WfM de Blue Yonder**
    > - Solicitudes de intercambio: **la característica está deshabilitada para todos los usuarios**
    > - Solicitudes de permiso: **la característica está deshabilitada para todos los usuarios**
    >
    > Después de ejecutar el asistente, asegúrese de seguir los pasos de la sección [Deshabilitar turnos abiertos, solicitudes de turnos abiertos, solicitudes de intercambio y solicitudes de permisos](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) más adelante en este artículo.
 
1. Cuando hayas terminado de elegir la configuración, selecciona **Crear conexión**.

### <a name="map-blue-yonder-workforce-management-sites-to-teams"></a>Asignar sitios de Administración de la fuerza laboral de Blue Yonder a los equipos
<a name="sites"> </a>

Elija los sitios de WfM de Blue Yonder que desea conectar a Turnos. Puede seleccionar hasta 100 sitios.

:::image type="content" source="../../media/shifts-connector-wizard-sites.png" alt-text="Captura de pantalla del asistente, que muestra la lista de sitios de WFM de Blue Yonder." lightbox="../../media/shifts-connector-wizard-sites.png":::
<a name="mapping"> </a>
<a name="search_teams"> </a> Después, asigne cada sitio de WFM de Blue Yonder que seleccionó a un equipo de Teams. Puede asignar un sitio a un equipo existente o puede crear uno nuevo.
:::image type="content" source="../../media/shifts-connector-wizard-search-team.png" alt-text="Captura de pantalla del panel que muestra la opción buscar equipo y crear una nueva opción de equipo." lightbox="../../media/shifts-connector-wizard-search-team.png":::
#### <a name="to-map-a-site-to-an-existing-team"></a>Para asignar un sitio a un equipo existente

1. Seleccione el nombre del sitio.
2. En el panel, busque el equipo y selecciónelo. Tenga en cuenta que los equipos que ya están asignados a un sitio en esta conexión no se muestran en la búsqueda.
3. Elija la zona horaria y la ciudad más cercana.
4. Selecciona **Guardar** y, a continuación, **Siguiente**.

#### <a name="to-map-a-site-to-a-new-team"></a>Para asignar un sitio a un nuevo equipo

1. Seleccione el nombre del sitio.
2. En el panel, elija **Crear un nuevo equipo**. Se le lleva a una pestaña nueva en el explorador, donde puede crear un nuevo equipo en la Centro de administración de Microsoft 365.
    1. Escriba un nombre y una descripción opcional para el equipo.
    1. Agregue uno o más propietarios de equipo. Asegúrate de agregar la cuenta del sistema de Microsoft 365 como propietario.
    1. Agregar miembros del equipo.
    1. Agregue una dirección de correo electrónico del equipo y elija una configuración de privacidad.
    1. Revise la configuración y, después, elija **Agregar equipo**. Cuando se cree el equipo, elija **Cerrar**.
3. Volver al asistente, busque y, a continuación, seleccione el nuevo equipo que creó.
4. Elija la zona horaria y la ciudad más cercana.
5. Selecciona **Guardar** y, a continuación, **Siguiente**.

### <a name="review-and-finish"></a>Revisar y finalizar

Revisa la configuración. Si necesita realizar cambios en las asignaciones de los equipos, elija **Editar** para hacerlo. Cuando esté listo, seleccione **Finalizar**.

:::image type="content" source="../../media/shifts-connector-wizard-review.png" alt-text="Captura de pantalla de la página Revisar del asistente, que muestra las asignaciones." lightbox="../../media/shifts-connector-wizard-review.png":::

Verá un mensaje para confirmar que hemos recibido su solicitud junto con un id. de operación. Anote el id. de la operación. La necesitarás para comprobar el estado de configuración de la conexión.

:::image type="content" source="../../media/shifts-connector-wizard-operation-id.png" alt-text="Captura de pantalla de la página del asistente, que muestra el mensaje de confirmación y el id. de la operación." lightbox="../../media/shifts-connector-wizard-operation-id.png":::

El asistente inicia el proceso para configurar la conexión y asignar los sitios a los equipos seleccionados. Este proceso puede tardar algún tiempo en completarse. Los destinatarios que elija recibirán notificaciones por correo electrónico sobre el estado de la configuración.

Seleccione **Listo** para salir del asistente.

¡Estás en camino, pero aún no has terminado! Asegúrate de comprobar tu correo electrónico. Recibirá una confirmación de que hemos recibido su solicitud junto con un [vínculo](shifts-connector-powershell-manage.md#check-connection-setup-status) para comprobar el estado de la instalación.

> [!NOTE]
> Si se produce un problema o error en una conexión después de su configuración, recibirá una notificación por correo electrónico. Siga las instrucciones del correo electrónico para solucionar el problema.

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>Deshabilitar turnos abiertos, solicitudes de turnos abiertos, solicitudes de intercambio y solicitudes de permisos

> [!IMPORTANT]
> Siga estos pasos solo si eligió cualquiera de las siguientes opciones para deshabilitar los turnos abiertos, las solicitudes de turno abiertas, las solicitudes de intercambio o las solicitudes de permisos en el asistente. Al completar este paso, se oculta la funcionalidad en Turnos.
>
> - Turnos abiertos: **Los usuarios de Turnos no verán los datos de WfM de Blue Yonder**
> - Solicitudes de intercambio: **la característica está deshabilitada para todos los usuarios**
> - Solicitudes de permiso: **la característica está deshabilitada para todos los usuarios**
>
> Sin este segundo paso, los usuarios seguirán viendo la funcionalidad en Turnos y recibirán un mensaje de error de "operación no compatible" si intentan usarla.

Para ocultar turnos abiertos, solicitudes de intercambio y solicitudes de permisos en turnos, use el [Graph API tipo de recurso de programación](/graph/api/resources/schedule?view=graph-rest-1.0) para establecer los siguientes parámetros ```false``` para cada equipo que haya asignado a un sitio WFM de Blue Yonder:

- Abrir turnos: ```openShiftsEnabled```
- Solicitudes de intercambio:  ```swapShiftsRequestsEnabled```
- Solicitudes de permisos: ```timeOffRequestsEnabled```

Para ocultar las solicitudes de turnos abiertas en Turnos, vaya a **Configuración** en Turnos y desactive la configuración **Abrir turnos**.

## <a name="if-you-need-to-make-changes-to-a-connection"></a>Si necesita realizar cambios en una conexión
<a name="update_connection"> </a>

Después de configurar una conexión, use PowerShell para realizar cambios en ella. Por ejemplo, puede actualizar la configuración de sincronización, las asignaciones del equipo y deshabilitar la sincronización para una conexión. Para obtener instrucciones detalladas, consulte [Usar PowerShell para administrar la conexión de Turnos con Blue Yonder Workforce Management](shifts-connector-powershell-manage.md).

## <a name="related-articles"></a>Artículos relacionados

- [Conectores de Turnos](shifts-connectors.md)
- [Usar PowerShell para administrar la conexión de Turnos a Blue Yonder Workforce Management](shifts-connector-powershell-manage.md)
- [Administrar la aplicación Turnos en Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
