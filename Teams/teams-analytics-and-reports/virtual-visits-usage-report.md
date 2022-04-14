---
title: Microsoft Teams informe de uso de visitas virtuales
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: ''
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo usar el informe de uso de visitas virtuales en el centro de administración de Microsoft Teams para obtener información general sobre la actividad de las citas virtuales en su organización.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 91f1aa8ff25b591305c8d5ca41485f7ceec9faca
ms.sourcegitcommit: 68162a8c9dee9a27af596353baabeda9b8fa64f3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2022
ms.locfileid: "64853221"
---
# <a name="microsoft-teams-virtual-visits-usage-report"></a>Microsoft Teams informe de uso de visitas virtuales

El informe uso de visitas virtuales del centro de administración de Microsoft Teams le ofrece información general sobre Teams actividad de citas virtuales en su organización. Puede ver la actividad detallada de las citas virtuales programadas a través de la [aplicación Bookings](../expand-teams-across-your-org/bookings-virtual-visits.md) y el [conector de registro médico electrónico (EHR) Microsoft Teams](../expand-teams-across-your-org/healthcare/teams-in-hc.md#virtual-appointments-and-electronic-healthcare-record-ehr-integration).

Para ver el informe, debe ser administrador global o administrador de Teams.

El informe contiene las pestañas siguientes. La información que verá en el informe depende de si tiene una licencia para la aplicación de Bookings, el conector EHR Teams o ambos.

|Pestaña |Descripción  |
|---------|---------|
|**[Visitas virtuales](#virtual-visits)**     |Muestra el número total de citas virtuales, con un desglose del número de citas programadas con la aplicación de Bookings y Teams reuniones integradas de EHR realizadas desde su sistema EHR.         |
|**[Duración](#duration)**     |Muestra la duración media de las citas y el tiempo medio de espera de espera de los participantes.         |
|**[Bookings](#bookings)**     |Muestra el número de citas programadas a través de la aplicación Bookings.         |
|**[EHR](#ehr)**     |Muestra el número de citas integradas con EHR Teams realizadas desde su sistema EHR.         |  

Use este informe para obtener información sobre la actividad de las citas virtuales y las tendencias de su organización. La información puede ayudarle a optimizar las citas virtuales para ofrecer mejores resultados empresariales.

## <a name="view-the-virtual-visits-usage-report"></a>Ver el informe de uso de visitas virtuales

1. En el panel de navegación izquierdo del centro de administración de Microsoft Teams, elija **Análisis &** **informesAdministrar** >  informes. En la pestaña **Ver informes** , en **Informe**, seleccione **Uso de visitas virtuales**.
2. En **Intervalo de fechas**, seleccione un intervalo de fechas de 7 días, 30 días o 90 días. Después, elija **Ejecutar informe**.

> [!NOTE]
> De forma predeterminada, el análisis de visitas virtuales está activado y el informe está disponible. Al usar este informe, concede permiso a Microsoft para recopilar datos sobre citas virtuales en su organización. Para obtener información sobre nuestras directivas de retención de datos, vea [Retención, eliminación y destrucción de datos en Microsoft 365](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview).
>
>Si desea desactivar el informe para su organización, puede hacerlo en **Configuración** en la esquina superior derecha de la página. Esta configuración puede tardar entre 0 (cero) y 2 horas en surtir efecto después de cambiarla.

## <a name="interpret-the-report"></a>Interpretar el informe

### <a name="virtual-visits"></a>Visitas virtuales

Los gráficos que verá aquí dependen de si tiene una licencia para la aplicación de Bookings, el conector EHR Teams o ambos. Para obtener más información, consulta [Administrar la aplicación Bookings](../bookings-app-admin.md) e [Integración en Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) o [Integración en Epic EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-virtual-visits.png" alt-text="Captura de pantalla de la pestaña Visitas virtuales del informe uso de visitas virtuales que muestra llamadas numeradas." lightbox="../media/virtual-visits-usage-report-virtual-visits.png":::

|Globo |Descripción  |
|--------|-------------|
|**1**   |Cada informe tiene una fecha en la que se generó el informe. Los informes suelen reflejar una latencia de 24 a 48 horas desde el momento de la actividad. |
|**2**   |El eje X es el intervalo de fechas seleccionado para el informe. El eje Y es el número de citas.<br>Desplace el puntero sobre el punto de una fecha determinada para ver el número de citas en esa fecha.|
|**3**   |Puede filtrar lo que ve en el gráfico seleccionando un elemento de la leyenda. Por ejemplo, selecciona **Total Bookings visitas virtuales** o **Visitas virtuales EHR totales** para ver solo la información relacionada con cada una de ellas. Al cambiar esta selección no se cambia la información de la tabla. |
|**4**   |La tabla proporciona información detallada sobre cada cita que tuvo lugar durante el intervalo de fechas seleccionado. <ul><li>**Hora de inicio (UTC)** es la fecha y hora en la que un miembro del personal y un participante están en la reunión o cuando se produjo la primera actividad en la reunión.  </li> <li>**El Id. de reunión** es el identificador único de la reunión.</li> <li>**Tiempo de espera** en la sala de espera es el tiempo entre la primera vez que un participante se une a la sala de espera y cuando un miembro del personal admite a ese mismo participante o a otro participante en la reunión.</li><li>**Duración** es la diferencia de tiempo entre la hora de inicio y la hora en que la última persona abandona la reunión. Si un miembro del personal y un participante no se unieron a la reunión, la duración se muestra como 0 (cero).</li> <li>**El estado** muestra el estado de la reunión. <ul><li>**Completado**: si uno o más participantes y miembros del personal se unen a la reunión y la reunión ha finalizado. O bien, si uno o más participantes se unen a la reunión y la reunión ha finalizado.</li> <li> **No se muestra**: si un miembro del personal se une a la reunión, pero no se une ninguna otra persona, y la reunión ha finalizado. </li></ul> </li> <li>**El tipo de reunión** indica si la cita virtual se programó a través de la aplicación Bookings o del conector EHR Teams.</li> <li>**Asistentes** es el número total de miembros del personal y participantes en la reunión.</li> <li>**SMS enviado** indica si se envió una notificación SMS a los asistentes. </li> </li> </ul> |
|**5**   |Seleccione **Configuración** para abrir el panel **de análisis de visitas virtuales**. Desde aquí, puede activar o desactivar el informe de visitas virtuales para su organización y agregar o quitar columnas en la tabla. Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.|
|**6**   |Puede exportar el informe a un archivo CSV para realizar análisis sin conexión. Selecciona **Exportar a Excel** y, a continuación, en la pestaña **Descargas**, elige **Descargar** para descargar el informe cuando esté listo.|

### <a name="duration"></a>Duración

:::image type="content" source="../media/virtual-visits-usage-report-duration.png" alt-text="Captura de pantalla de la pestaña Duración del informe uso de visitas virtuales que muestra llamadas numeradas." lightbox="../media/virtual-visits-usage-report-duration.png":::

|Globo |Descripción  |
|--------|-------------|
|**1**   |Cada informe tiene una fecha en la que se generó el informe. Los informes suelen reflejar una latencia de 24 a 48 horas desde el momento de la actividad. |
|**2**   |El eje X es el intervalo de fechas seleccionado para el informe. El eje Y es el número de minutos.<br>Desplace el puntero sobre el punto de una fecha determinada para ver la duración media de las citas o el tiempo medio de espera de espera para una fecha determinada.  |
|**3**   |Puede filtrar lo que ve en el gráfico seleccionando un elemento de la leyenda. Por ejemplo, seleccione **Duración media de la visita virtual** o **Promedio de tiempo de espera de espera** para ver solo la información relacionada con cada una de ellas. Al cambiar esta selección no se cambia la información de la tabla. |
|**4**   |La tabla proporciona información detallada sobre cada cita que tuvo lugar durante el intervalo de fechas seleccionado. <ul><li>**Hora de inicio (UTC)** es la fecha y hora en la que un miembro del personal y un participante están en la reunión o cuando se produjo la primera actividad en la reunión.  </li> <li>**El Id. de reunión** es el identificador único de la reunión.</li> <li>**Tiempo de espera** en la sala de espera es el tiempo entre la primera vez que un participante se une a la sala de espera y cuando un miembro del personal admite a ese mismo participante o a otro participante en la reunión.</li><li>**Duración** es la diferencia de tiempo entre la hora de inicio y la hora en que la última persona abandona la reunión. Si un miembro del personal y un participante no se unieron a la reunión, la duración se muestra como 0 (cero).</li> <li>**El estado** muestra el estado de la reunión. <ul><li>**Completado**: si uno o más participantes y miembros del personal se unen a la reunión y la reunión ha finalizado. O bien, si uno o más participantes se unen a la reunión y la reunión ha finalizado.</li> <li> **No se muestra**: si un miembro del personal se une a la reunión, pero no se une ninguna otra persona, y la reunión ha finalizado. </li></ul> </li> <li>**El tipo de reunión** indica si la cita virtual se programó a través de la aplicación Bookings o del conector EHR Teams.</li> <li>**Asistentes** es el número total de miembros del personal y participantes en la reunión.</li> <li>**SMS enviado** indica si se envió una notificación SMS a los asistentes. </li> </li> </ul>|
|**5**   |Seleccione **Configuración** para abrir el panel **de análisis de visitas virtuales**. Desde aquí, puede activar o desactivar el informe de visitas virtuales para su organización y agregar o quitar columnas en la tabla. Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.|
|**6**   |Puede exportar el informe a un archivo CSV para realizar análisis sin conexión. Selecciona **Exportar a Excel** y, a continuación, en la pestaña **Descargas**, elige **Descargar** para descargar el informe cuando esté listo.|
### <a name="bookings"></a>Bookings

Verá esta pestaña si tiene una licencia que incluye la aplicación Bookings. Para obtener más información, consulta [Administrar la aplicación de Bookings](../bookings-app-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-bookings.png" alt-text="Captura de pantalla de la pestaña Bookings del informe uso de visitas virtuales que muestra llamadas numeradas." lightbox="../media/virtual-visits-usage-report-bookings.png":::

|Globo |Descripción  |
|--------|-------------|
|**1**   |Cada informe tiene una fecha en la que se generó el informe. Los informes suelen reflejar una latencia de 24 a 48 horas desde el momento de la actividad. |
|**2**   |El eje X es el intervalo de fechas seleccionado para el informe. El eje Y es el número de citas Bookings.<br>Desplace el puntero sobre el punto de una fecha determinada para ver el número de Bookings citas que tuvieron lugar en esa fecha.|
|**3**   |La tabla proporciona información detallada sobre cada cita que tuvo lugar durante el intervalo de fechas seleccionado. <ul><li>**Hora de inicio (UTC)** es la fecha y hora en la que un miembro del personal y un participante están en la reunión o cuando se produjo la primera actividad en la reunión.  </li> <li>**El Id. de reunión** es el identificador único de la reunión.</li> <li>**Tiempo de espera** en la sala de espera es el tiempo entre la primera vez que un participante se une a la sala de espera y cuando un miembro del personal admite a ese mismo participante o a otro participante en la reunión.</li><li>**Duración** es la diferencia de tiempo entre la hora de inicio y la hora en que la última persona abandona la reunión. Si un miembro del personal y un participante no se unieron a la reunión, la duración se muestra como 0 (cero).</li> <li>**El estado** muestra el estado de la reunión. <ul><li>**Completado**: si uno o más participantes y miembros del personal se unen a la reunión y la reunión ha finalizado. O bien, si uno o más participantes se unen a la reunión y la reunión ha finalizado.</li> <li> **No se muestra**: si un miembro del personal se une a la reunión, pero no se une ninguna otra persona, y la reunión ha finalizado. </li></ul> </li> <li>**El tipo de reunión** indica si la cita virtual se programó a través de la aplicación Bookings o del conector EHR Teams.</li> <li>**Asistentes** es el número total de miembros del personal y participantes en la reunión.</li> <li>**SMS enviado** indica si se envió una notificación SMS a los asistentes. </li> </li> </ul>|
|**4**   |Seleccione **Configuración** para abrir el panel **de análisis de visitas virtuales**. Desde aquí, puede activar o desactivar el informe de visitas virtuales para su organización y agregar o quitar columnas en la tabla. Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.|
|**5**   |Puede exportar el informe a un archivo CSV para realizar análisis sin conexión. Selecciona **Exportar a Excel** y, a continuación, en la pestaña **Descargas**, elige **Descargar** para descargar el informe cuando esté listo.|
### <a name="ehr"></a>EHR

Verá esta pestaña si tiene una licencia que incluye el conector EHR Teams. Para obtener más información, consulta [Integración en Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) o [Integración en Epic EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-ehr.png" alt-text="Captura de pantalla de la pestaña EHR del informe uso de visitas virtuales que muestra llamadas numeradas." lightbox="../media/virtual-visits-usage-report-ehr.png":::

|Globo |Descripción  |
|--------|-------------|
|**1**   |Cada informe tiene una fecha en la que se generó el informe. Los informes suelen reflejar una latencia de 24 a 48 horas desde el momento de la actividad. |
|**2**   |El eje X es el intervalo de fechas seleccionado para el informe. El eje Y es el número de citas EHR.<br>Desplace el puntero sobre el punto de una fecha determinada para ver el número de citas EHR en esa fecha.|
|**3**   |La tabla proporciona información detallada sobre cada cita que tuvo lugar durante el intervalo de fechas seleccionado. <ul><li>**Hora de inicio (UTC)** es la fecha y hora en la que un miembro del personal y un participante están en la reunión o cuando se produjo la primera actividad en la reunión.  </li> <li>**El Id. de reunión** es el identificador único de la reunión.</li> <li>**Tiempo de espera** en la sala de espera es el tiempo entre la primera vez que un participante se une a la sala de espera y cuando un miembro del personal admite a ese mismo participante o a otro participante en la reunión.</li><li>**Duración** es la diferencia de tiempo entre la hora de inicio y la hora en que la última persona abandona la reunión. Si un miembro del personal y un participante no se unieron a la reunión, la duración se muestra como 0 (cero).</li> <li>**El estado** muestra el estado de la reunión. <ul><li>**Completado**: si uno o más participantes y miembros del personal se unen a la reunión y la reunión ha finalizado. O bien, si uno o más participantes se unen a la reunión y la reunión ha finalizado.</li> <li> **No se muestra**: si un miembro del personal se une a la reunión, pero no se une ninguna otra persona, y la reunión ha finalizado. </li></ul> </li> <li>**El tipo de reunión** indica si la cita virtual se programó a través de la aplicación Bookings o del conector EHR Teams.</li> <li>**Asistentes** es el número total de miembros del personal y participantes en la reunión.</li> <li>**SMS enviado** indica si se envió una notificación SMS a los asistentes. </li> </li> </ul>|
|**4**   |Seleccione **Configuración** para abrir el panel **de análisis de visitas virtuales**. Desde aquí, puede activar o desactivar el informe de visitas virtuales para su organización y agregar o quitar columnas en la tabla. Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.|
|**5**   |Puede exportar el informe a un archivo CSV para realizar análisis sin conexión. Selecciona **Exportar a Excel** y, a continuación, en la pestaña **Descargas**, elige **Descargar** para descargar el informe cuando esté listo.|

> [!NOTE]
> Si su organización desea participar en la vista previa privada para que los usuarios que no sean administradores, como los responsables de la toma de decisiones empresariales, tengan acceso a este informe y lo vean, [póngase en contacto con nosotros](mailto:tapmwtanalytics@microsoft.com).

## <a name="related-articles"></a>Artículos relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)
- [Citas virtuales con Teams y la aplicación Bookings](../expand-teams-across-your-org/bookings-virtual-visits.md)
- [Citas virtuales con Teams - Integración en Epic EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md)
- [Citas virtuales con Teams - Integración en Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md)
