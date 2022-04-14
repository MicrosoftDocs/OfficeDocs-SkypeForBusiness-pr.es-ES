---
title: Citas virtuales con Microsoft Teams y la aplicación Bookings
author: lanachin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: ''
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
- Microsoft Cloud for Retail
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- microsoftcloud-retail
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: Obtenga información sobre cómo programar, administrar y llevar a cabo citas virtuales con la aplicación Bookings en Teams.
ms.openlocfilehash: 3a69140bd0a02adb879cc0914d7e5c4703623907
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853211"
---
# <a name="virtual-appointments-with-microsoft-teams-and-the-bookings-app"></a>Citas virtuales con Microsoft Teams y la aplicación Bookings

## <a name="overview"></a>Información general

La [aplicación Bookings](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5) de Microsoft Teams ofrece a las organizaciones una forma sencilla de programar y administrar citas virtuales para el personal y los asistentes. Úselo para programar citas como visitas médicas, consultas financieras, entrevistas, asistencia al cliente, accesorios virtuales y consultas, horarios de oficina de educación y mucho más.

La aplicación Bookings permite administrar fácilmente las demandas de programación complejas de cualquier organización. Los programadores pueden administrar varios calendarios de departamento y de personal, así como las comunicaciones con los asistentes internos y externos desde una sola experiencia.

Las citas virtuales se realizan a través de Microsoft Teams reuniones, que ofrecen sólidas capacidades de videoconferencia. Por ejemplo, un médico puede compartir su pantalla y revisar los resultados de la prueba con un paciente. O bien, un asesor bancario puede solicitar firmas electrónicas en documentos, lo que les permite cerrar transacciones de forma remota.

Cada cita virtual incluye un vínculo de reunión de Teams que se envía a los asistentes por correo electrónico, donde pueden unirse fácilmente desde un explorador web o en Teams en cualquier dispositivo. Los avisos de correo electrónico automatizados ayudan a reducir las no presentaciones y a mejorar la participación de clientes y clientes.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4TQop]

Con Bookings, obtiene una experiencia adaptada a su sector. Estos son algunos ejemplos de cómo puede usarlo en su organización:

|Industria | Ejemplos |
|---------|---------|
|Servicios financieros    |  Citas virtuales para ventas y servicios remotos<br/>Programe y administre citas para gerentes de relaciones bancarias, asesores financieros y ajustadores de reclamaciones, por nombrar algunos, para servir a sus clientes con mayor eficiencia y conveniencia.  |
|Venta al por menor   | Accesorios y consultas virtuales <br/>Programe y administre citas para sus asociados de ventas, expertos en productos y consultores de diseño para llevar a cabo instalaciones virtuales y consultas con los clientes.   |
|Atención sanitaria   |  Citas virtuales para la atención del paciente <br/>Programe y administre citas para que los miembros del equipo de atención médica se reúnan con pacientes u otros proveedores de atención médica para discutir sobre la atención médica.   |

En este artículo se ofrece información general sobre cómo programar, administrar y llevar a cabo citas virtuales con la aplicación Bookings de Teams.

## <a name="before-you-get-started"></a>Antes de empezar

Si es administrador, consulte [Administrar la aplicación de Bookings en Teams](../bookings-app-admin.md) para obtener información sobre los requisitos previos para usar la aplicación Bookings en Teams, cómo controlar el acceso a Bookings en su organización y la configuración recomendada de directivas y administradores.

Recuerde que solo los programadores de su organización deben tener la aplicación de Bookings instalada en Teams. El personal que realiza o participa en citas virtuales no necesita la aplicación. Se unen a citas desde su Teams o Outlook calendario o mediante el vínculo de la reunión en su correo electrónico de confirmación de reserva.

## <a name="set-up-a-new-booking-calendar"></a>Configurar un nuevo calendario de reservas

### <a name="create-the-booking-calendar"></a>Crear el calendario de reservas

En Teams, vaya a **Bookings** >  **Comenzar** y, a continuación, seleccione **Nuevo calendario de reservas**. Complete el formulario y asegúrese de elegir el tipo de negocio relevante para su organización.

:::image type="content" source="../media/bookings-virtual-visits-new-booking-calendar.png" alt-text="Captura de pantalla de la nueva pantalla del calendario de reservas que muestra los tipos de empresa":::

Si es una organización más grande, considere la posibilidad de crear más de un calendario de reservas si desea que los asistentes reciban un correo electrónico de reserva de un departamento específico en lugar de su organización en general.
Para obtener más información, vea [Crear un calendario Bookings](https://support.microsoft.com//office/create-a-bookings-calendar-921cfd26-a24d-4aca-9004-561594112148).

> [!NOTE]
> Si no es la primera vez que usa la aplicación de Bookings o si desea trabajar en un calendario de reservas existente, en Bookings, seleccione la flecha desplegable junto al nombre de su organización y, a continuación, elija **Calendario de reservas existente**. Desde aquí, puedes buscar el que quieras.

### <a name="add-staff"></a>Agregar docentes

En el calendario de reservas, vaya a **Más opciones** (...) > **Configuración** y, a continuación, seleccione **Personal**. Agregue miembros del personal y asigne un rol a cada persona que agregue. Puede agregar hasta 100 miembros del personal a un calendario de reservas.

La aplicación Bookings se integra con Outlook. Después de agregar personal, podrá ver la disponibilidad del calendario de esa persona y programar sus reservas. Para obtener más información, vea [Agregar personal y ver un calendario Bookings](https://support.microsoft.com/office/add-staff-and-view-a-bookings-calendar-6c579f61-8adb-4514-9458-021de2023fa0).  

### <a name="create-appointment-types"></a>Crear tipos de citas

Cree tipos de citas específicos para representar los servicios ofrecidos por su organización y adaptar la experiencia de reserva. A continuación, los programadores pueden usar el tipo de cita para programar una cita.

En el calendario de reservas, vaya a **Más opciones** (...) > **Configuración**, seleccione **Tipos de citas** y, a continuación, seleccione **Agregar tipo de cita**. Escriba un nombrepor&mdash; ejemplo, Apertura de cuenta, Renovación por receta, Consulta de préstamos, Preparación de impuestosy&mdash; cualquier otra información y configuración que desee.

La información que agregue se incluye en la confirmación por correo electrónico que se envía a los asistentes cada vez que se reserva este tipo de cita. Puede establecer avisos por correo electrónico y otras opciones, como si los asistentes pueden [unirse desde un explorador móvil o de escritorio](browser-join.md) sin tener que descargar Teams.

Si es administrador de Bookings, puede vincular hasta cuatro formularios para que los asistentes los rellenen cada vez que se reserve este tipo de cita. Por ejemplo, es posible que necesite que los asistentes completen un formulario de registro antes de que se unan a una cita. Para vincular un formulario, elija **Vincular un formulario**. Escriba la dirección URL del formulario y, después, elija **Vínculo**. (Si es la primera vez que vincula un formulario, se le pedirá que cree un grupo de Microsoft 365 para almacenar formularios. Elija **Crear grupo** para crear el grupo. Solo tiene que hacerlo una vez para el calendario de reservas).

Al trabajar con formularios, tenga en cuenta lo siguiente:

- Para realizar cambios en un formulario que ya está vinculado a un tipo de cita, seleccione el formulario en el tipo de cita o desde dentro del grupo de Microsoft 365 en [https://forms.office.com](https://forms.office.com).
- La carga de archivos en formularios que contienen una [pregunta de carga de archivos](https://support.microsoft.com/office/add-questions-that-allow-for-file-uploads-6a75a658-c02b-450e-b119-d068f3cba4cf) es compatible cuando todos los asistentes son de la misma organización.

Cuando un programador usa el tipo de cita para programar una cita, puede elegir incluir el formulario, quitarlo o agregar cualquier otro formulario vinculado al tipo de cita. Los asistentes deben rellenar el formulario antes de unirse a la cita.

Para obtener más información, vea [Crear un tipo de cita](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887).

## <a name="schedule-an-appointment"></a>Programar una cita 

En el calendario de reservas, seleccione **Nueva reserva**. Seleccione un tipo de cita y, a continuación, rellene la información relevante.

Esto incluye la información de contacto de los asistentes, el miembro del personal que proporcionará el servicio, notas internas que solo el personal puede ver, avisos por correo electrónico y si el asistente puede unirse desde un explorador móvil. Si un formulario está vinculado al tipo de cita, puede elegir incluirlo, quitarlo o agregar cualquier otro formulario vinculado.

La confirmación por correo electrónico enviada al asistente incluye el vínculo de la reunión y un archivo adjunto para que pueda agregar la cita virtual a su calendario. El personal también recibe una confirmación por correo electrónico e invitación a la reunión. Si se incluyó un formulario en la cita, Bookings los administradores y programadores pueden ver si el asistente ha completado el formulario antes de la cita y pueden ver la respuesta del asistente.

Para obtener más información, consulta [Programar una reserva en la aplicación Teams Bookings](https://support.microsoft.com/office/schedule-a-booking-in-the-teams-bookings-app-e275049d-0d0f-4161-8526-461a9f29439f).

## <a name="conduct-an-appointment"></a>Dirigir una cita

En el calendario de Teams o Outlook, vaya a la reserva y, a continuación, seleccione **Unirse** o el vínculo Teams reunión. Compruebe la configuración de audio y vídeo y, después, seleccione **Unirse ahora**. Para obtener más información, consulte [Dirigir una cita Bookings](https://support.microsoft.com/office/conduct-a-bookings-appointment-a86a4007-e26c-4909-9893-f7036e2747cd).

## <a name="monitor-appointments-and-get-real-time-status-updates"></a>Supervisar citas y obtener actualizaciones de estado en tiempo real

La [vista de cola](https://support.microsoft.com/office/queue-view-in-bookings-3eea2840-a1e0-4bcd-8e09-d3cf51c184d6) de Bookings proporciona a sus docentes un panel para supervisar todas las citas virtuales del día, con actualizaciones en tiempo real. Para ver la cola, vaya a la pestaña **Cola** en Bookings.

:::image type="content" source="../media/bookings-virtual-visits-queue.png" alt-text="Captura de pantalla de la vista de cola en la aplicación Bookings de Teams" lightbox="../media/bookings-virtual-visits-queue.png":::

En la cola, los programadores pueden agregar una nueva reserva, ver los detalles relevantes de las citas y ver los estados de las citas durante todo el día. Cuando un paciente se une a la sala de espera, el estado cambia y se muestra y se realiza un seguimiento de su tiempo de espera. La vista se actualiza automáticamente con actualizaciones codificadas por colores para que los cambios se puedan identificar fácilmente.

El personal puede incluso unirse y administrar citas directamente desde la cola.

> [!NOTE]
> Actualmente, la aplicación Bookings admite la adición de hasta 100 empleados por calendario de reserva. Si usó Graph API para configurar y agregar personal a un calendario de reservas, es posible que no se aplique este límite. En este escenario, la pestaña **Cola** no podrá representar contenido para los calendarios que tengan más de 100 empleados. Para una experiencia óptima, le recomendamos que agregue no más de 100 empleados a un calendario de reservas. Estamos trabajando para resolver esta limitación en futuras versiones.

## <a name="additional-capabilities-with-the-bookings-web-app"></a>Funcionalidades adicionales con la aplicación web de Bookings

La aplicación web Bookings le ofrece funcionalidades adicionales. Por ejemplo, puede publicar una página de reserva en línea de autoservicio donde los usuarios pueden programar citas con su personal. Para acceder a la aplicación web de Bookings, vaya a **Más opciones** (...) > **Abrir Bookings aplicación web**.

Para obtener más información, consulta [Microsoft Bookings](/microsoft-365/bookings/bookings-overview).

## <a name="get-insight-into-virtual-appointments-usage"></a>Obtener información sobre el uso de citas virtuales

El [informe uso de visitas virtuales](../teams-analytics-and-reports/virtual-visits-usage-report.md) del centro de administración de Microsoft Teams ofrece a los administradores información general sobre Teams actividad de citas virtuales en su organización. El informe muestra análisis detallados de citas virtuales, incluidas las citas Bookings.

Puede ver métricas clave como el tiempo de espera de la sala de espera y la duración de las citas. Use esta información para obtener información sobre las tendencias de uso para ayudarle a optimizar las citas virtuales y ofrecer mejores resultados empresariales.

## <a name="related-articles"></a>Artículos relacionados

- [Administrar la experiencia de unión para Teams citas virtuales en exploradores móviles](browser-join.md)

- [Teams informe de uso de visitas virtuales](../teams-analytics-and-reports/virtual-visits-usage-report.md)

- [Comenzar con Teams para organizaciones sanitarias](healthcare/teams-in-hc.md)

- [aplicación Bookings en la documentación de ayuda de Teams](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Bookings)
