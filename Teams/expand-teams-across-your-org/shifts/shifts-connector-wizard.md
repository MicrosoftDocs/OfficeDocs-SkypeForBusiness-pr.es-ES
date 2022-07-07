---
title: Usar el asistente del conector Mayús para conectar Turnos a Blue Yonder Workforce Management
author: lanachin
ms.author: v-lanachin
ms.reviewer: ''
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Obtenga información sobre cómo usar el asistente para conectores Turnos para integrar Turnos en Teams con Workforce Management Blue Yonder.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: de511df118e1c5e6d62e0bed8cd076a7481b3407
ms.sourcegitcommit: 90f03a841f8ca33092dce65c543357c7c2f7b82a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2022
ms.locfileid: "66647805"
---
# <a name="use-the-shifts-connector-wizard-to-connect-shifts-to-blue-yonder-workforce-management"></a>Usar el asistente del conector Mayús para conectar Turnos a Blue Yonder Workforce Management

## <a name="overview"></a>Información general

El asistente del conector Turnos de la Centro de administración de Microsoft 365 le permite integrar la aplicación Turnos en Microsoft Teams con su sistema de administración de la fuerza de trabajo (WFM). Después de configurar una conexión, los trabajadores de primera línea pueden ver y administrar sin problemas sus programaciones en el sistema WFM desde Turnos.

El asistente configura el conector Turnos, crea una conexión a su sistema de WFM y aplica la configuración de sincronización y las asignaciones del equipo que elija. La configuración de sincronización determina la información de programación que se sincroniza entre el sistema de WFM y Turnos. Las asignaciones de equipos definen la relación de sincronización entre las instancias de WFM y los equipos en Teams. Puede asignar a equipos existentes y nuevos equipos.

Puede configurar varias conexiones, cada una con configuraciones de sincronización diferentes. Por ejemplo, si su organización tiene varias ubicaciones con requisitos de programación diferentes, cree una conexión con la configuración de sincronización única para cada ubicación. Tenga en cuenta que una instancia de WFM solo se puede asignar a un equipo en un momento determinado. Si una instancia de WFM ya está asignada a un equipo, no se puede asignar a otro equipo.

Con su sistema de WFM como sistema de registro, sus trabajadores de primera línea pueden ver e intercambiar turnos, administrar su disponibilidad y solicitar permisos en Turnos en sus dispositivos. Los administradores de primera línea pueden seguir usando el sistema de WFM para configurar programaciones.

## <a name="integrate-shifts-with-blue-yonder-workforce-management"></a>Integrar Turnos con Blue Yonder Workforce Management

Actualmente, el asistente es compatible con el [conector Turnos de Microsoft Teams para Blue Yonder](shifts-connectors.md#microsoft-teams-shifts-connector-for-blue-yonder). Este conector le permite integrar Turnos con Blue Yonder Workforce Management (Blue Yonder WFM) para administrar sus programaciones y mantenerlos actualizados. En este artículo, le guiaremos a través de cómo ejecutar el asistente para configurar una conexión a Blue Yonder WFM a través del conector.

> [!NOTE]
> También puede usar PowerShell para integrar Turnos con Blue Yonder WFM. Para obtener más información, consulte [Usar PowerShell para conectar Turnos a Blue Yonder Workforce Management](shifts-connector-blue-yonder-powershell-setup.md).

## <a name="before-you-begin"></a>Antes de empezar

Debe ser administrador global de Microsoft 365 para ejecutar el asistente.

### <a name="prerequisites"></a>Requisitos previos
<a name="prerequisites"> </a>
[!INCLUDE [shifts-connector-prerequisites](../../includes/shifts-connector-prerequisites.md)]

- Los equipos a los que quiere asignar no tienen ninguna programación. Si un equipo tiene una programación existente, [quite la programación del equipo](#remove-schedules-from-teams-you-want-to-map) antes de asignarle una instancia de WFM Azul. En caso contrario, verá turnos duplicados.

## <a name="remove-schedules-from-teams-you-want-to-map"></a>Quitar programaciones de equipos que quiera asignar
<a name="remove_schedules"> </a>

> [!NOTE]
> Complete este paso si está asignando instancias WFM Blue Yonder a equipos existentes que tienen programaciones. Si está asignando equipos que no tienen ninguna programación o si está creando nuevos equipos a los que asignar, puede omitir este paso.

Use PowerShell para quitar programaciones de equipos.

1. En primer lugar, deberá instalar los módulos de PowerShell y configurarlos. Siga los pasos para [configurar su entorno](shifts-connector-powershell-manage.md#set-up-your-environment).
1. Ejecute el siguiente comando:

    ```powershell
    Remove-CsTeamsShiftsScheduleRecord -TeamId <Teams team ID> -DateRangeStartDate <start time> -DateRangeEndDate <end time> -ClearSchedulingGroup:$false -EntityType <the scenario entities that you want to remove, the format is @(scenario1, scenario2, ...)> -DesignatedActorId <Teams team owner ID>
    ```

    Para obtener una lista de escenarios para el `EntityType` parámetro, ejecute [Get-CsTeamsShiftsConnectionConnector](/powershell/module/teams/get-csteamsshiftsconnectionconnector). Los datos de programación se quitarán para el intervalo de fecha y hora que especifique.

Para obtener más información, vea [Remove-CsTeamsShiftsScheduleRecord](/powershell/module/teams/remove-csteamsshiftsschedulerecord).

## <a name="run-the-wizard"></a>Ejecutar el asistente

### <a name="get-started"></a>Introducción

1. En el panel de navegación izquierdo de la [Centro de administración de Microsoft 365](https://admin.microsoft.com/), elija **Configuración** y, después, vaya a la sección **Aplicaciones y correo electrónico**.
1. Seleccione **Conectar el sistema de administración de la fuerza de trabajo**. Aquí, puede obtener más información sobre los conectores de Turnos y la experiencia de los trabajadores de primera línea y del administrador al conectar Turnos a su sistema de WFM.
    :::image type="content" source="../../media/shifts-connector-wizard-get-started.png" alt-text="Captura de pantalla de la página de detalles del asistente del conector Turnos en la Centro de administración de Microsoft 365." lightbox="../../media/shifts-connector-wizard-get-started.png":::
1. Cuando estés listo, selecciona **Introducción**.
1. Selecciona **Siguiente** para crear una conexión de WFM Blue Yonder.

### <a name="enter-connection-details"></a>Escribe los detalles de la conexión
<a name="connection_details"> </a>

1. En la página Detalles de la conexión, asigna un nombre único a la conexión. No puede tener más de 128 caracteres o tener caracteres especiales.
    :::image type="content" source="../../media/shifts-connector-wizard-connection-details.png" alt-text="Captura de pantalla de la página Detalles de la conexión del asistente, que muestra la configuración de conexión." lightbox="../../media/shifts-connector-wizard-connection-details.png":::
1. Escribe el nombre de la cuenta de servicio de Blue Yonder WFM y las direcciones URL de servicio y contraseña.
1. Cuando hayas terminado, selecciona **Siguiente** para probar la conexión con la configuración especificada.

### <a name="choose-sync-settings"></a>Elegir la configuración de sincronización
<a name="sync"> </a>

En la página Configuración de sincronización, elija la información para sincronizar de Blue Yonder WFM a Turnos, la frecuencia de sincronización y si los usuarios de Turnos pueden realizar cambios en los datos.

1. Escriba su cuenta de sistema de Microsoft 365.
    :::image type="content" source="../../media/shifts-connector-wizard-sync-settings.png" alt-text="Captura de pantalla de la página Configuración de sincronización del asistente, que muestra la configuración de sincronización." lightbox="../../media/shifts-connector-wizard-sync-settings.png":::
<a name="email"> </a>
1. En **Destinatarios de notificación por correo electrónico**, elija quién recibe notificaciones por correo electrónico sobre esta conexión. Puede agregar usuarios y grupos individuales. Las notificaciones por correo electrónico contienen información sobre el estado de configuración de la conexión y los problemas o errores que se pueden producir después de configurar la conexión.
1. Elija la configuración de sincronización:
    1. En **Programación y turnos**, elija Blue Yonder WFM los datos que los usuarios de Shifts pueden ver o cambiar y, a continuación, establezca la frecuencia de sincronización.
    2. En **Solicitudes**, elija los tipos de solicitudes que los usuarios de Turnos pueden ver y crear.

    > [!IMPORTANT]
    > Si eligió cualquiera de las siguientes opciones para deshabilitar turnos abiertos, solicitudes de turno abiertas, solicitudes de intercambio o solicitudes de permisos, hay otro paso que debe hacer para ocultar la funcionalidad en Turnos.
    >
    > - Turnos abiertos: **los usuarios de Turnos no verán los datos de Blue Yonder WFM**
    > - Solicitudes de intercambio: **la característica está deshabilitada para todos los usuarios**
    > - Solicitudes de permiso: **la característica está deshabilitada para todos los usuarios**
    >
    > Después de ejecutar el asistente, asegúrese de seguir los pasos de la sección [Deshabilitar turnos abiertos, solicitudes de turnos abiertos, solicitudes de intercambio y solicitudes de permisos](#disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests) más adelante en este artículo.
 
1. Cuando hayas terminado de elegir la configuración, selecciona **Crear conexión**.

### <a name="map-blue-yonder-workforce-management-instances-to-teams"></a>Asignar instancias de Workforce Management azul a los equipos
<a name="sites"> </a>

Elija el blue yonder WFM instancias que desea conectar a Turnos y, a continuación, asigne cada instancia a un equipo en Teams. Puede asignar hasta 100 instancias. Hay dos formas de hacerlo:

- [Asignar instancias manualmente a los equipos](#manually-map-instances-to-teams)
- [Preparar y cargar un archivo CSV que defina las asignaciones](#use-a-csv-file-to-map-instances-to-teams)

#### <a name="manually-map-instances-to-teams"></a>Asignar instancias manualmente a los equipos

Seleccione las instancias que desea asignar.

:::image type="content" source="../../media/shifts-connector-wizard-sites.png" alt-text="Captura de pantalla del asistente, que muestra la lista de instancias de WFM Blue Yonder." lightbox="../../media/shifts-connector-wizard-sites.png":::
<a name="mapping"> </a>
<a name="search_teams"> </a> Después, asigne cada instancia a un equipo en Teams. Puede asignar una instancia a un equipo existente o puede crear un equipo nuevo.
:::image type="content" source="../../media/shifts-connector-wizard-search-team.png" alt-text="Captura de pantalla del panel que muestra la opción buscar equipo y crear una nueva opción de equipo." lightbox="../../media/shifts-connector-wizard-search-team.png":::

##### <a name="to-map-an-instance-to-an-existing-team"></a>Para asignar una instancia a un equipo existente

1. Seleccione el nombre de la instancia.
2. En el panel, busque el equipo y selecciónelo. Tenga en cuenta que los equipos que ya están asignados a una instancia en esta conexión no se muestran en la búsqueda.
3. Elija la zona horaria y la ciudad más cercana.
4. Selecciona **Guardar** y, a continuación, **Siguiente**.

##### <a name="to-map-an-instance-to-a-new-team"></a>Para asignar una instancia a un equipo nuevo

1. Seleccione el nombre de la instancia.
2. En el panel, elija **Crear un nuevo equipo**. Se le lleva a una pestaña nueva en el explorador, donde puede crear un nuevo equipo en la Centro de administración de Microsoft 365.
    1. Escriba un nombre y una descripción opcional para el equipo.
    1. Agregue uno o más propietarios de equipo. Asegúrese de agregar la cuenta del sistema de Microsoft 365 como propietario.
    1. Agregar miembros del equipo.
    1. Agregue una dirección de correo electrónico del equipo y elija una configuración de privacidad.
    1. Revise la configuración y, después, elija **Agregar equipo**. Cuando se cree el equipo, elija **Cerrar**.
3. Volver al asistente, busque y, a continuación, seleccione el nuevo equipo que creó.
4. Elija la zona horaria y la ciudad más cercana.
5. Selecciona **Guardar** y, a continuación, **Siguiente**.

#### <a name="use-a-csv-file-to-map-instances-to-teams"></a>Usar un archivo CSV para asignar instancias a los equipos

1. Seleccione **cambiar al modo masivo**.
1. Seleccione **Descargar un archivo de plantilla** para descargar una plantilla de asignación que pueda usar para definir las asignaciones.

    :::image type="content" source="../../media/shifts-connector-wizard-mapping-file.png" alt-text="Captura de pantalla de la página Cargar archivo de asignación del asistente." lightbox="../../media/shifts-connector-wizard-mapping-file.png":::

1. Use la plantilla para crear el archivo de asignación. Contiene estas columnas, en el siguiente orden, empezando por la primera columna. Un asterisco (*) indica una columna obligatoria.

    |Nombre de columna  |Descripción  |
    |---------|---------|
    |**Id. de instancia de Blue Yonder*** |El Blue Yonder WFM id. de instancia.|
    |**Blue Yonder Instance Name**|El Blue Yonder WFM nombre de instancia.|
    |**Id. de equipo*** |El id. de equipo.|
    |**Nombre del equipo**|El nombre del equipo.|
    |**Zona horaria*** |La zona horaria en formato de base de datos tz. Por ejemplo, Europa/Londres.|

    > [!NOTE]
    > Solo tiene que rellenar las columnas necesarias (Identificador de instancia de Blue Yonder, Id. de equipo, Zona horaria) para asignar instancias a los equipos.

    Este es un ejemplo del aspecto de un archivo de asignación.

    |Id. de instancia de Blue Yonder|Blue Yonder Instance Name|Id. de equipo|Nombre del equipo|Zona horaria|
    |---------|---------|---------|---------|---------|
    |2111|Equipo de Contoso US|3a4d78a-2261|Equipo de EE. UU.|Estados Unidos/Los_Angeles|
    |3212|Equipo de Contoso UK|2d1f6c2e-5272|Equipo del Reino Unido|Europa/Londres|
    |4865||bfa6o89e-1328||Estados Unidos/Toronto|

1. Cuando haya creado el archivo de asignación, seleccione **Examinar** para cargarlo. El asistente valida el archivo. Si encuentra errores, verá una lista de los errores y un mensaje solicitándole que los corrija. En caso contrario, verá un mensaje para continuar con el paso siguiente.  
1. Seleccione **Siguiente**.

### <a name="review-and-finish"></a>Revisar y finalizar

Revisa la configuración. Si necesita realizar cambios en las asignaciones de los equipos, elija **Editar** para hacerlo. Cuando esté listo, seleccione **Finalizar**.

:::image type="content" source="../../media/shifts-connector-wizard-review.png" alt-text="Captura de pantalla de la página Revisar del asistente, que muestra las asignaciones." lightbox="../../media/shifts-connector-wizard-review.png":::

Verá un mensaje para confirmar que hemos recibido su solicitud junto con un id. de operación. Anote el id. de la operación. La necesitarás para comprobar el estado de configuración de la conexión.

:::image type="content" source="../../media/shifts-connector-wizard-operation-id.png" alt-text="Captura de pantalla de la página del asistente, que muestra el mensaje de confirmación y el id. de la operación." lightbox="../../media/shifts-connector-wizard-operation-id.png":::

El asistente inicia el proceso para configurar la conexión y asignar las instancias a los equipos seleccionados. Este proceso puede tardar algún tiempo en completarse. Los destinatarios que elija recibirán notificaciones por correo electrónico sobre el estado de la configuración.

Seleccione **Listo** para salir del asistente.

¡Estás en camino, pero aún no has terminado! Asegúrate de comprobar tu correo electrónico. Recibirá una confirmación de que hemos recibido su solicitud junto con un [vínculo](shifts-connector-powershell-manage.md#check-connection-setup-status) para comprobar el estado de la instalación.

> [!NOTE]
> Si se produce un problema o error en una conexión después de su configuración, recibirá una notificación por correo electrónico. Siga las instrucciones del correo electrónico para solucionar el problema.

## <a name="disable-open-shifts-open-shifts-requests-swap-requests-and-time-off-requests"></a>Deshabilitar turnos abiertos, solicitudes de turnos abiertos, solicitudes de intercambio y solicitudes de permisos

> [!IMPORTANT]
> Siga estos pasos solo si eligió cualquiera de las siguientes opciones para deshabilitar los turnos abiertos, las solicitudes de turno abiertas, las solicitudes de intercambio o las solicitudes de permisos en el asistente. Al completar este paso, se oculta la funcionalidad en Turnos.
>
> - Turnos abiertos: **los usuarios de Turnos no verán los datos de Blue Yonder WFM**
> - Solicitudes de intercambio: **la característica está deshabilitada para todos los usuarios**
> - Solicitudes de permiso: **la característica está deshabilitada para todos los usuarios**
>
> Sin este segundo paso, los usuarios seguirán viendo la funcionalidad en Turnos y recibirán un mensaje de error de "operación no compatible" si intentan usarla.

Para ocultar los turnos abiertos, las solicitudes de permuta y las solicitudes de permisos en turnos, use el [Graph API tipo de recurso de programación](/graph/api/resources/schedule) para establecer los siguientes parámetros ```false``` para cada equipo que haya asignado a una instancia de blue yonder WFM:

- Abrir turnos: ```openShiftsEnabled```
- Solicitudes de intercambio:  ```swapShiftsRequestsEnabled```
- Solicitudes de permisos: ```timeOffRequestsEnabled```

Para ocultar las solicitudes de turnos abiertas en Turnos, vaya a **Configuración** en Turnos y desactive la configuración **Abrir turnos** .

## <a name="if-you-need-to-make-changes-to-a-connection"></a>Si necesita realizar cambios en una conexión
<a name="update_connection"> </a>

Después de configurar una conexión, use PowerShell para realizar cambios en ella. Por ejemplo, puede actualizar la configuración de sincronización, las asignaciones del equipo y deshabilitar la sincronización para una conexión. Para obtener instrucciones detalladas, consulte [Usar PowerShell para administrar la conexión de Turnos a Blue Yonder Workforce Management](shifts-connector-powershell-manage.md).

## <a name="related-articles"></a>Artículos relacionados

- [Conectores de Turnos](shifts-connectors.md)
- [Use PowerShell para administrar la conexión de Turnos a Blue Yonder Workforce Management](shifts-connector-powershell-manage.md)
- [Administrar la aplicación Turnos en Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
