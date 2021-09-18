---
title: Visitas virtuales con Microsoft Teams y la aplicación Bookings
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
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
ms.reviewer: ''
description: Obtenga información sobre cómo usar la aplicación Bookings en Teams programar, administrar y realizar visitas virtuales.
ms.openlocfilehash: a37a024e31c75bbedbdb36d9aa0d6acfd2af614c
ms.sourcegitcommit: 9364f4fdf3dcd5ab6805360ff913d4e2e7ca9cfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2021
ms.locfileid: "59432462"
---
# <a name="virtual-visits-with-microsoft-teams-and-the-bookings-app"></a>Visitas virtuales con Microsoft Teams y la aplicación Bookings

## <a name="overview"></a>Información general

La [aplicación Bookings en](https://support.microsoft.com/office/what-is-bookings-42d4e852-8e99-4d8f-9b70-d7fc93973cb5) Microsoft Teams proporciona a las organizaciones una forma sencilla de programar y administrar citas virtuales para el personal y los asistentes. Úsese para programar citas virtuales, como visitas sanitarias, consultas financieras, entrevistas, asistencia al cliente, experiencias de compras virtuales, horas de oficinas educativas y mucho más.

La aplicación Bookings facilita la administración de las complejas demandas de programación de cualquier organización. Los programadores pueden administrar varios calendarios de departamento y de personal, así como las comunicaciones con los asistentes internos y externos desde una sola experiencia.

Las visitas virtuales se realizarán a través Microsoft Teams reuniones, lo que ofrece sólidas capacidades de videoconferencia. Por ejemplo, un médico puede compartir su pantalla y revisar los resultados de las pruebas con un paciente. O bien, un asesor bancario puede solicitar firmas electrónicas en los documentos, lo que les permite cerrar transacciones de forma remota.

Cada cita virtual incluye un vínculo Teams reunión que se envía a los asistentes por correo electrónico, donde pueden unirse fácilmente desde un explorador web o Teams en cualquier dispositivo. Los avisos de correo electrónico automatizados ayudan a reducir la falta de presentaciones y a mejorar la participación de clientes y clientes.

Con Bookings, obtiene una experiencia adaptada a su sector. Estos son algunos ejemplos de cómo puede usarlo en su organización:

|Sector | Ejemplos |
|---------|---------|
|Servicios financieros    |  Visitas virtuales para ventas y servicios remotos<br/>Programe y administre citas virtuales para administradores de relaciones bancarias, asesores financieros y ajustadores de reclamaciones, por citar algunos, para servir a sus clientes con mayor eficiencia y comodidad.  |
|Sanidad   |  Visitas virtuales para la atención de pacientes <br/>Programe y administre visitas virtuales para que los miembros del equipo de atención se reúnan con pacientes u otros proveedores de servicios de salud para hablar sobre la atención médica.   |
|Retail   | Experiencias de compra virtuales <br/>Programe y administre citas para sus asociados de ventas, expertos en productos y consultores de diseño para llevar a cabo experiencias de compra virtuales con los clientes.   |

En este artículo se ofrece información general sobre cómo usar la aplicación Bookings en Teams programar, administrar y realizar visitas virtuales.

## <a name="before-you-get-started"></a>Antes de empezar

Si es administrador, consulte Administrar la aplicación [Bookings](../bookings-app-admin.md) en Teams para obtener información sobre los requisitos previos para usar la aplicación Bookings en Teams, cómo controlar el acceso a Bookings en su organización y la configuración de directiva y administrador recomendada.

Recuerde que solo los programadores de su organización necesitan tener la aplicación Bookings instalada en Teams. El personal que dirige o participa en citas virtuales no necesita la aplicación. Se unen a citas desde su Teams o Outlook o mediante el vínculo de reunión en su correo electrónico de confirmación de reserva.

## <a name="set-up-a-new-booking-calendar"></a>Configurar un nuevo calendario de reservas

### <a name="create-the-booking-calendar"></a>Crear el calendario de reserva

En Teams, vaya a Introducción a **Bookings** y, a  >  continuación, **seleccione Nuevo calendario de reservas.** Complete el formulario y asegúrese de elegir el tipo de negocio correspondiente para su organización.

:::image type="content" source="../media/bookings-virtual-visits-new-booking-calendar.png" alt-text="Captura de pantalla de la nueva pantalla del calendario de reservas que muestra los tipos de negocio":::

Si es una organización más grande, considere la posibilidad de crear más de un calendario de reserva si quiere que los asistentes reciban un correo electrónico de reserva de un departamento específico en lugar de su organización general.
Para obtener más información, vea [Crear un calendario de Bookings.](https://support.microsoft.com//office/create-a-bookings-calendar-921cfd26-a24d-4aca-9004-561594112148)

> [!NOTE]
> Si no es la primera vez que se encuentra en la aplicación Bookings o si quiere trabajar en un calendario de reservas existente, en Bookings, seleccione la flecha desplegable junto al nombre de su organización y, a continuación, elija Calendario de reserva **existente.** Desde aquí, puede buscar el que desee.

### <a name="add-staff"></a>Agregar personal

En el calendario de reservas, vaya a **Más opciones** (...) > **Configuración** y, a continuación, seleccione **Personal**. Agregue miembros del personal y asigne un rol a cada persona que agregue.

La aplicación Bookings se integra con Outlook. Después de agregar personal, podrá ver la disponibilidad del calendario de esa persona y programar reservas para ellos. Para obtener más información, vea [Agregar personal y ver un calendario de Bookings.](https://support.microsoft.com/office/add-staff-and-view-a-bookings-calendar-6c579f61-8adb-4514-9458-021de2023fa0)  

### <a name="create-appointment-types"></a>Crear tipos de citas

Cree tipos de citas específicos para representar los servicios ofrecidos por su organización y para adaptar la experiencia de reserva.

En el calendario de reserva, vaya a **Más opciones** (...) > **Tipos de** cita y, a continuación, seleccione Nuevo tipo **de cita.** Escriba un nombre, por ejemplo, Apertura de cuenta, Renovación de la receta, Consulta de préstamo, Preparación de impuestos y cualquier otra información y &mdash; &mdash; configuración que desee.

La información y los vínculos que agregue se incluyen en la confirmación de correo electrónico que se envía a los asistentes cada vez que se reserva este tipo de cita. Incluso puede establecer avisos de correo electrónico y otras opciones, como si los asistentes pueden unirse desde un explorador móvil [sin](mobile-browser-join.md) tener que descargar Teams. Para obtener más información, vea [Crear un tipo de cita.](https://support.microsoft.com/office/create-an-appointment-type-810eac77-6a65-4dc8-964d-c00eadf43887)

## <a name="schedule-a-virtual-visit"></a>Programar una visita virtual

En el calendario de reservas, seleccione **Nueva reserva.** Seleccione un tipo de cita y, a continuación, rellene la información relevante.

Esto incluye la información de contacto de los asistentes, el miembro del personal que va a proporcionar el servicio, notas internas que solo el personal puede ver, avisos por correo electrónico y si el asistente puede unirse desde un explorador móvil. Para obtener más información, vea [Programar una reserva en la Teams Bookings](https://support.microsoft.com/office/schedule-a-booking-in-the-teams-bookings-app-e275049d-0d0f-4161-8526-461a9f29439f).

La confirmación por correo electrónico enviada al asistente incluye el vínculo de la reunión y un archivo adjunto para que puedan agregar la cita virtual a su calendario. El personal también recibe una confirmación por correo electrónico e invitación a la reunión.

## <a name="conduct-a-virtual-visit"></a>Realizar una visita virtual

En el Teams o Outlook, vaya a la reserva y,  a continuación, seleccione Unirse o el vínculo Teams reunión. Compruebe la configuración de audio y vídeo y, a continuación, seleccione **Unirse ahora.** Para obtener más información, vea [Realizar una cita de Bookings.](https://support.microsoft.com/office/conduct-a-bookings-appointment-a86a4007-e26c-4909-9893-f7036e2747cd)

## <a name="additional-capabilities-with-the-bookings-web-app"></a>Funcionalidades adicionales con la aplicación web Bookings

La aplicación web Bookings le ofrece capacidades adicionales. Por ejemplo, puede publicar una página de reserva en línea de autoservicio en la que los usuarios pueden programar citas con su personal. Para acceder a la aplicación web de Bookings, vaya a **Más opciones** (...) > abrir la aplicación web **de Bookings.**

Para obtener más información, vea [Microsoft Bookings](/microsoft-365/bookings/bookings-overview).

## <a name="related-articles"></a>Artículos relacionados

[Administrar la experiencia de combinación para Teams visitas virtuales en exploradores móviles](mobile-browser-join.md)

[Introducción a Teams para organizaciones sanitarias](healthcare/teams-in-hc.md)

[La aplicación Bookings en Teams documentación de ayuda](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b?#PickTab=Bookings)
