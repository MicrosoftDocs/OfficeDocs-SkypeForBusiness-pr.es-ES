---
title: Visitas virtuales con Microsoft Teams y la Bookings aplicación
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
description: Obtenga información sobre cómo programar, administrar y realizar visitas virtuales con Bookings aplicación en Teams.
ms.openlocfilehash: 0db414765a649192d96122ac69764fa279a8dac5
ms.sourcegitcommit: cbdc80c302e97d18a923ef57bb5d4b6cf7676d00
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2022
ms.locfileid: "64556541"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Consultas virtuales con Microsoft Teams y la aplicación Bookings

## <a name="overview"></a>Información general

La [Bookings en Microsoft Teams](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5) proporciona a las organizaciones una forma sencilla de programar y administrar citas virtuales para el personal y los asistentes. Úsese esta opción para programar citas como visitas sanitarias, consultas financieras, entrevistas, asistencia al cliente, accesorios y consultas virtuales, horas de oficina de educación y mucho más.

La Bookings permite administrar fácilmente las complejas demandas de programación de cualquier organización. Los programadores pueden administrar varios calendarios de departamento y de personal, así como las comunicaciones con los asistentes internos y externos desde una sola experiencia.

Las citas virtuales se celebrarán Microsoft Teams reuniones, que ofrecen funciones de videoconferencia sólidas. Por ejemplo, un médico puede compartir su pantalla y revisar los resultados de las pruebas con un paciente. O bien, un asesor bancario puede solicitar firmas electrónicas en los documentos, lo que les permite cerrar transacciones de forma remota.

Cada cita virtual incluye un vínculo Teams reunión que se envía Teams los asistentes por correo electrónico, donde pueden unirse fácilmente desde un explorador web o Teams en cualquier dispositivo. Los avisos de correo electrónico automatizados ayudan a reducir la falta de presentaciones y a mejorar la participación de clientes y clientes.

Con Bookings, obtiene una experiencia adaptada a su sector. Estos son algunos ejemplos de cómo puede usarlo en su organización:

|Sector | Ejemplos |
|---------|---------|
|Servicios financieros    |  Visitas virtuales para ventas y servicios remotos<br/>Programe y administre citas para administradores de relaciones bancarias, asesores financieros y ajustadores de reclamaciones, por citar solo unos pocos, para servir a sus clientes con mayor eficiencia y comodidad.  |
|Retail   | Accesorios y consultas virtuales <br/>Programe y administre citas para sus asociados de ventas, expertos en productos y consultores de diseño para llevar a cabo accesorios virtuales y consultas con los clientes.   |
|Sanidad   |  Visitas virtuales para la atención de pacientes <br/>Programe y administre citas para que los miembros del equipo de atención se reúnan con pacientes u otros proveedores de servicios de salud para hablar sobre la atención médica.   |

En este artículo se proporciona información general sobre cómo programar, administrar y realizar visitas virtuales con la aplicación Bookings en Teams.

## <a name="before-you-get-started"></a>Antes de empezar

Si es administrador, vea Administrar la aplicación [Bookings en Teams](../bookings-app-admin.md) para obtener información sobre los requisitos previos para usar la aplicación Bookings en Teams, cómo controlar el acceso a Bookings en su organización y la configuración de directiva y administrador recomendada.

Recuerde que solo los programadores de su organización necesitan tener Bookings aplicación instalada en Teams. El personal que dirige o participa en citas virtuales no necesita la aplicación. Se unen a citas desde su calendario Teams o Outlook o mediante el vínculo de la reunión en su correo electrónico de confirmación de reserva.

## <a name="set-up-a-new-booking-calendar"></a>Configurar un nuevo calendario de reservas

### <a name="create-the-booking-calendar"></a>Crear el calendario de reserva

En Teams, vaya **a Bookings** >  **Comenzar** y, a continuación, seleccione **Nuevo calendario de reserva**. Complete el formulario y asegúrese de elegir el tipo de negocio correspondiente para su organización.

:::image type="content" source="../media/bookings-virtual-visits-new-booking-calendar.png" alt-text="Captura de pantalla de la nueva pantalla del calendario de reservas que muestra los tipos de negocio":::

Si es una organización más grande, considere la posibilidad de crear más de un calendario de reserva si quiere que los asistentes reciban un correo electrónico de reserva de un departamento específico en lugar de su organización general.
Para obtener más información, vea [Crear un Bookings calendario](https://support.microsoft.com//office/create-a-bookings-calendar-921cfd26-a24d-4aca-9004-561594112148).

> [!NOTE]
> Si no es la primera vez que se encuentra en la aplicación Bookings o si desea trabajar en un calendario de reservas existente, en Bookings, seleccione la flecha desplegable junto al nombre de su organización y, a continuación, elija Calendario de reserva **existente.** Desde aquí, puede buscar el que desee.

### <a name="add-staff"></a>Agregar personal

En el calendario de reservas, vaya a **Más opciones** (...) > **Configuración** y, a continuación, seleccione **Personal**. Agregue miembros del personal y asigne un rol a cada persona que agregue. Puede agregar hasta 100 miembros del personal a un calendario de reserva.

La Bookings se integra con Outlook. Después de agregar personal, podrá ver la disponibilidad del calendario de esa persona y programar reservas para ellos. Para obtener más información, vea [Agregar personal y ver un Bookings calendario](https://support.microsoft.com/office/add-staff-and-view-a-bookings-calendar-6c579f61-8adb-4514-9458-021de2023fa0).  

### <a name="create-appointment-types"></a>Crear tipos de citas

Cree tipos de citas específicos para representar los servicios ofrecidos por su organización y para adaptar la experiencia de reserva. A continuación, los programadores pueden usar el tipo de cita para programar una visita.

En el calendario de reserva, vaya a Más **opciones (...) >** Configuración, **seleccione** Tipos de cita **y, a** continuación, **seleccione Agregar tipo de cita**. Escriba un nombre&mdash; por ejemplo, Apertura de cuenta, Renovación de la receta, Consulta de préstamo,&mdash; Preparación de impuestos y cualquier otra información y configuración que desee.

La información que agregue se incluye en la confirmación de correo electrónico que se envía a los asistentes cada vez que se reserva este tipo de cita. Puede establecer avisos de correo electrónico y otras opciones, como si los asistentes pueden unirse desde un explorador [móvil sin tener](mobile-browser-join.md) que descargar Teams.

Si es administrador Bookings, puede vincular hasta cuatro formularios para que los asistentes rellenen cada vez que se reserve este tipo de cita. Por ejemplo, puede requerir que los asistentes completen un formulario de registro antes de unirse a una visita. Para vincular un formulario, elija **Vincular un formulario**. Escriba la dirección URL del formulario y, a continuación, elija **Vínculo**. (Si es la primera vez que vincula un formulario, se le pedirá que cree un grupo de Microsoft 365 almacenar formularios. Elija **Crear grupo** para crear el grupo. Solo tiene que hacerlo una vez para el calendario de reserva).

Al trabajar con formularios, tenga en cuenta lo siguiente:

- Para realizar cambios en un formulario que ya está vinculado a un tipo de cita, seleccione el formulario en el tipo de cita o en el grupo de Microsoft 365 en [https://forms.office.com](https://forms.office.com).
- Cargar archivos en formularios que contienen una pregunta [de carga](https://support.microsoft.com/office/add-questions-that-allow-for-file-uploads-6a75a658-c02b-450e-b119-d068f3cba4cf) de archivos es compatible cuando todos los asistentes son de la misma organización.

Cuando un programador usa el tipo de cita para programar una visita, pueden elegir incluir el formulario, quitarlo o agregar cualquier otro formulario que haya vinculado al tipo de cita. Los asistentes deben rellenar el formulario antes de unirse a la visita.

Para obtener más información, vea [Crear un tipo de cita](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887).

## <a name="schedule-a-visit"></a>Programar una visita

En el calendario de reservas, seleccione **Nueva reserva**. Seleccione un tipo de cita y, a continuación, rellene la información relevante.

Esto incluye la información de contacto de los asistentes, el miembro del personal que va a proporcionar el servicio, notas internas que solo el personal puede ver, avisos por correo electrónico y si el asistente puede unirse desde un explorador móvil. Si un formulario está vinculado al tipo de cita, puede incluirlo, quitarlo o agregar cualquier otro formulario vinculado.

La confirmación por correo electrónico enviada al asistente incluye el vínculo de la reunión y un archivo adjunto para que puedan agregar la cita virtual a su calendario. El personal también recibe una confirmación por correo electrónico e invitación a la reunión. Si se incluyó un formulario en la cita, Bookings administradores y programadores pueden ver si el formulario lo completó el asistente antes de la visita y puede ver la respuesta del asistente.

Para obtener más información, vea [Programar una reserva en la Teams Bookings aplicación](https://support.microsoft.com/office/schedule-a-booking-in-the-teams-bookings-app-e275049d-0d0f-4161-8526-461a9f29439f).

## <a name="conduct-a-visit"></a>Realizar una visita

En el Teams o Outlook, vaya a la reserva y, a continuación, seleccione Unirse o  el vínculo Teams reunión. Compruebe la configuración de audio y vídeo y, a continuación, seleccione **Unirse ahora**. Para obtener más información, vea [Realizar una Bookings cita](https://support.microsoft.com/office/conduct-a-bookings-appointment-a86a4007-e26c-4909-9893-f7036e2747cd).

## <a name="monitor-visits-and-get-real-time-status-updates"></a>Supervisar visitas y obtener actualizaciones de estado en tiempo real

La [vista de cola](https://support.microsoft.com/office/queue-view-in-bookings-3eea2840-a1e0-4bcd-8e09-d3cf51c184d6) en Bookings proporciona a su personal un panel para supervisar todas las citas virtuales del día, con actualizaciones en tiempo real. Para ver la cola, vaya a la **pestaña** Cola en Bookings.

:::image type="content" source="../media/bookings-virtual-visits-queue.png" alt-text="Captura de pantalla de la vista de cola en Bookings aplicación en Teams" lightbox="../media/bookings-virtual-visits-queue.png":::

Desde la cola, los programadores pueden agregar una nueva reserva, ver detalles de cita relevantes y ver los estados de cita durante todo el día. Cuando un paciente se une a la sala de espera, el estado cambia y su tiempo de espera se muestra y realiza un seguimiento. La vista se actualiza automáticamente con actualizaciones codificadas por colores para que los cambios se puedan identificar fácilmente.

El personal puede incluso unirse y administrar citas directamente desde la cola.

> [!NOTE]
> Actualmente, la aplicación Bookings permite sumar hasta 100 empleados por calendario de reserva. Si usó Graph API para configurar y agregar personal a un calendario de reserva, es posible que este límite no se aplique. En este escenario, la **pestaña** Cola no podrá representar contenido para calendarios con más de 100 docentes. Para una experiencia óptima, le recomendamos que no agregue más de 100 empleados a un calendario de reservas. Estamos trabajando para resolver esta limitación en futuras versiones.

## <a name="additional-capabilities-with-the-bookings-web-app"></a>Funcionalidades adicionales con la Bookings web

La Bookings web le ofrece capacidades adicionales. Por ejemplo, puede publicar una página de reserva en línea de autoservicio en la que los usuarios pueden programar citas con su personal. Para acceder a la Bookings web, vaya a Más **opciones** (...) > **abrir Bookings aplicación web**.

Para obtener más información, [vea Microsoft Bookings](/microsoft-365/bookings/bookings-overview).

## <a name="get-insight-into-virtual-visits-usage"></a>Obtener información sobre el uso de visitas virtuales

El [informe de uso](../teams-analytics-and-reports/virtual-visits-usage-report.md) de visitas virtuales del centro de administración de Microsoft Teams proporciona a los administradores información general sobre Teams de las visitas virtuales de su organización. El informe muestra análisis detallados para citas virtuales, incluidas Bookings visitas.

Puede ver métricas clave, como el tiempo de espera de la sala de espera y la duración de la visita. Use esta información para obtener información sobre las tendencias de uso para ayudarle a optimizar las visitas virtuales para ofrecer mejores resultados empresariales.

## <a name="related-articles"></a>Artículos relacionados

- [Administrar la experiencia de combinación para Teams visitas virtuales en exploradores móviles](mobile-browser-join.md)

- [Teams de uso de visitas virtuales](../teams-analytics-and-reports/virtual-visits-usage-report.md)

- [Comenzar con Teams para organizaciones sanitarias](healthcare/teams-in-hc.md)

- [Bookings aplicación en Teams documentación de ayuda](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Bookings)
