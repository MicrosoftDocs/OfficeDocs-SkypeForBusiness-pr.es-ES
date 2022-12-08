---
title: Administrar la aplicación Citas virtuales en Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
ms.topic: conceptual
ms.service: msteams
ms.reviewer: ''
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
audience: admin
description: Obtenga información sobre cómo administrar la aplicación de Citas virtuales para los usuarios de su organización.
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a61c8f75ec8825671b5d9fb845b77fab71bf3cfe
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2022
ms.locfileid: "69308051"
---
# <a name="manage-the-virtual-appointments-app-for-your-organization-in-microsoft-teams"></a>Administrar la aplicación de Citas virtuales para su organización en Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

La aplicación Citas virtuales proporciona un centro central para todas las necesidades de citas virtuales en Microsoft Teams. La aplicación permite una experiencia perfecta de un extremo a otro para las negociaciones de empresa a cliente, integrando programaciones desde la [aplicación Bookings](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5), análisis y opciones de administración, todo en un mismo lugar.

Puede programar, ver y administrar citas virtuales, obtener actualizaciones de estado en tiempo real en una vista de cola, enviar recordatorios de citas, ver análisis e informes para obtener información sobre la actividad de las citas virtuales y configurar la configuración del calendario, el personal y la página de reservas.

Con cualquier licencia de Microsoft 365, puede usar las funciones básicas de Citas virtuales para programar y unirse a reuniones de empresa a cliente. Por ejemplo, puede programar citas en el calendario de Bookings y los asistentes externos pueden [unirse a través de un explorador](/microsoft-365/frontline/browser-join) sin tener que descargar Teams. [Teams Premium](teams-add-on-licensing/licensing-enhance-teams.md) (versión preliminar) desbloquea funciones avanzadas de Citas virtuales que su organización puede usar para administrar y personalizar la experiencia. Incluyen una vista en cola de citas programadas y a petición, notificaciones de texto SMS, salas de espera personalizadas y análisis.

## <a name="overview-of-the-virtual-appointments-app"></a>Información general sobre la aplicación Citas virtuales

La aplicación Citas virtuales tiene las siguientes pestañas.

- [Principal](#home)
- [Programación de Bookings](#bookings-schedule)
- [Cola](#queue)
- [Análisis](#analytics)
- [Administrar](#manage)

Esta es una descripción general de lo que hay en cada pestaña.

### <a name="home"></a>Principal

![Icono](media/info.png) de información **Los mosaicos Cola y Análisis forman parte de [Teams Premium](teams-add-on-licensing/licensing-enhance-teams.md) (versión preliminar).**

Obtenga acceso fácil a acciones clave e información. La página principal proporciona una vista rápida de la programación de Bookings, un resumen de la cola de citas, una instantánea del análisis de citas y las opciones de administración.

:::image type="content" source="media/manage-virtual-appointments-app-home.png" alt-text="Captura de pantalla de la página principal en la aplicación Citas virtuales." lightbox="media/manage-virtual-appointments-app-home.png":::

### <a name="bookings-schedule"></a>Programación de Bookings

![Las notificaciones SMS del icono](media/info.png) **de información ahora forman parte de [Teams Premium](teams-add-on-licensing/licensing-enhance-teams.md) (versión preliminar). Los usuarios pueden seguir usando esta característica durante el período de vista previa. Después de la versión preliminar, los usuarios necesitan una licencia de Teams Premium.**

Acceda a su calendario de Bookings para programar citas virtuales como visitas médicas, consultas financieras, entrevistas, accesorios virtuales y consultas, y mucho más. Puede conectar un calendario existente de Bookings o crear uno nuevo. Para obtener más información, consulte [Citas virtuales con Teams y la aplicación Bookings](/microsoft-365/frontline/bookings-virtual-appointments) y [¿Qué es Bookings?](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5).

:::image type="content" source="media/manage-virtual-appointments-app-bookings-schedule.png" alt-text="Captura de pantalla de la página programación de Bookings en la aplicación de Citas virtuales." lightbox="media/manage-virtual-appointments-app-bookings-schedule.png":::

### <a name="queue"></a>Cola

![](media/info.png) Icono de información **La vista de cola programada y las notificaciones SMS ahora forman parte de [Teams Premium](teams-add-on-licensing/licensing-enhance-teams.md) (versión preliminar). Los usuarios pueden seguir usando estas características durante el período de vista previa. Después de la versión preliminar, los usuarios necesitan una licencia de Teams Premium. Para obtener acceso a la cola a petición durante el período de vista previa, los usuarios necesitan una licencia de prueba de Teams Premium.**

Vea y supervise todas las citas virtuales programadas y a petición en el calendario de Bookings que ancle, con actualizaciones en tiempo real.

Desde aquí, los programadores pueden agregar una nueva reserva, ver los detalles relevantes de las citas y ver los estados de las citas durante todo el día. También pueden enviar recordatorios por correo electrónico al personal asignado y a los asistentes, así como enviar notificaciones por SMS a los asistentes para las citas programadas. Los docentes pueden unirse a citas directamente desde la cola.

Para obtener más información, consulta [Supervisar citas y obtener actualizaciones de estado en tiempo real](/microsoft-365/frontline/bookings-virtual-appointments#monitor-appointments-and-get-real-time-status-updates-in-the-queue-view).

:::image type="content" source="media/manage-virtual-appointments-app-queue.png" alt-text="Captura de pantalla de la página Cola en la aplicación Citas virtuales." lightbox="media/manage-virtual-appointments-app-queue.png":::

### <a name="analytics"></a>Análisis

Obtenga información sobre la actividad de uso y las tendencias para ayudar a optimizar Citas virtuales y ofrecer mejores resultados empresariales.

El informe uso de Teams Citas virtuales ofrece a los administradores, responsables de la toma de decisiones y usuarios información general sobre la actividad de las citas virtuales en su organización. El informe proporciona métricas clave como el número total de citas, la duración de las citas, el tiempo de espera de sala de espera y ninguna presentación.

Puede ver la actividad detallada de las citas virtuales programadas y realizadas a través de varios puntos de entrada de programación y explorar en profundidad los datos de citas individuales.

La experiencia de análisis depende del rol del usuario. Los administradores obtienen [análisis organizativos](#organizational-analytics) y los no administradores obtienen [análisis de departamento o individuales](#departmental-and-individual-analytics).

#### <a name="organizational-analytics"></a>Análisis organizativo

![Icono](media/info.png) de información **Esta característica está disponible como parte de [Teams Premium](teams-add-on-licensing/licensing-enhance-teams.md) (versión preliminar). Después del período de vista previa, se requiere una licencia de Teams Premium.**

Los administradores ven un informe a nivel de organización que muestra análisis agregados en todos los departamentos de la organización.

:::image type="content" source="media/manage-virtual-appointments-app-analytics-org.png" alt-text="Captura de pantalla de la página de Analytics en la aplicación Citas virtuales, que muestra el informe de uso de Citas virtuales para administradores." lightbox="media/manage-virtual-appointments-app-analytics-org.png":::

Para obtener más información, consulta [Citas virtuales informe de uso](/microsoft-365/frontline/virtual-appointments-usage-report?bc=%2fmicrosoftteams%2fbreadcrumb%2ftoc.json&toc=%2fmicrosoftteams%2ftoc.json).

#### <a name="departmental-and-individual-analytics"></a>Análisis departamento e individual

![Icono](media/info.png) de información **Para obtener acceso a esta característica durante el período de vista previa, los usuarios necesitan una licencia de prueba [de Teams Premium](teams-add-on-licensing/licensing-enhance-teams.md) .**

Los usuarios que no sean administradores ven un informe a nivel de departamento que proporciona datos para el departamento en cuestión.

:::image type="content" source="media/manage-virtual-appointments-app-analytics-dept.png" alt-text="Captura de pantalla de la página análisis de la aplicación Citas virtuales, que muestra el informe de uso de Citas virtuales para usuarios que no sean administradores." lightbox="media/manage-virtual-appointments-app-analytics-dept.png":::

Si un miembro del personal no está asociado a un departamento, el informe muestra los datos de las citas que realizó.

### <a name="manage"></a>Manage

Administre la configuración del calendario de Bookings. Puede actualizar los detalles de su empresa, personalizar los tipos de citas, agregar personal y asignar roles, y configurar la configuración de la página de reserva.

:::image type="content" source="media/manage-virtual-appointments-app-manage.png" alt-text="Captura de pantalla de la página Administrar en la aplicación Citas virtuales." lightbox="media/manage-virtual-appointments-app-manage.png":::

## <a name="set-up-the-virtual-appointments-app"></a>Configurar la aplicación Citas virtuales

### <a name="enable-or-disable-the-virtual-appointments-app-in-your-organization"></a>Habilitar o deshabilitar la aplicación de Citas virtuales en su organización

La aplicación Citas virtuales está habilitada de forma predeterminada para todos los usuarios de Teams de su organización. Puede desactivar o activar la aplicación en el nivel de organización en la página [Administrar aplicaciones](manage-apps.md) del Centro de administración de Microsoft Teams.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, vaya a **Aplicaciones de Teams** > **Administrar aplicaciones**.
2. En la lista de aplicaciones, busca la aplicación Citas virtuales, selecciónala y cambia el botón de alternancia **Estado** a **Bloqueado** o **Permitido**.

### <a name="enable-or-disable-the-virtual-appointments-app-for-specific-users-in-your-organization"></a>Habilitar o deshabilitar la aplicación Citas virtuales para usuarios específicos de su organización

Para permitir o impedir que usuarios específicos de su organización usen la aplicación, asegúrese de que la aplicación está activada para su organización en la página [Administrar aplicaciones](manage-apps.md) . A continuación, cree una directiva personalizada para los permisos de la aplicación y asígnela a esos usuarios. Para obtener más información, consulte [Administrar configuración y directivas de aplicación personalizadas en Teams](teams-app-permission-policies.md).

### <a name="use-an-app-setup-policy-to-pin-the-virtual-appointments-app-to-teams"></a>Usar una directiva de configuración de aplicaciones para anclar la aplicación de Citas virtuales a Teams

Las directivas de configuración de aplicaciones le permiten personalizar Teams para resaltar las aplicaciones que sean más importantes para los usuarios de su organización. Las aplicaciones que establezca en una directiva se anclan en la barra de aplicaciones (la barra del lado del cliente de escritorio de Teams y en la parte inferior de los clientes móviles de Teams), donde los usuarios pueden acceder a ellas de forma rápida y sencilla.

Para anclar la aplicación Citas virtuales para los usuarios, puede editar la directiva global (predeterminada para toda la organización). O bien, puede crear y asignar una directiva de configuración de aplicaciones personalizada. Para obtener más información, consulte [Administrar las directivas de configuración de aplicaciones en Teams](teams-app-setup-policies.md).

## <a name="terms-of-service"></a>Términos de servicio

Consulte [Términos de servicio](/legal/microsoft-365/virtual-appointments-app-terms-of-service).

## <a name="related-articles"></a>Artículos relacionados

- [Citas virtuales visita guiada](https://guidedtour.microsoft.com/guidedtour/industry-longform/virtual-appointments/1/1)
- [Licencias de Teams Premium](teams-add-on-licensing/licensing-enhance-teams.md)
