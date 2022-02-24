---
title: Microsoft Teams de uso de visitas virtuales
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
description: Obtenga información sobre cómo usar el informe de uso de visitas virtuales en el centro de administración de Microsoft Teams para obtener información general sobre la actividad visitas virtuales en su organización.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1f00a8e0837ad4603fe38f664f94716aa8016aa9
ms.sourcegitcommit: 5ca04ee10e3f254e1b24506de116591fdfd51d18
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/23/2022
ms.locfileid: "62929425"
---
# <a name="microsoft-teams-virtual-visits-usage-report"></a>Microsoft Teams de uso de visitas virtuales

**Esta es una característica de vista previa**.

El informe de uso de visitas virtuales del centro de Microsoft Teams le ofrece información general sobre Teams de visitas virtuales de su organización. Puede ver la actividad detallada de las citas virtuales programadas a través de la aplicación [Bookings](../expand-teams-across-your-org/bookings-virtual-visits.md) y el conector Microsoft Teams registro de estado electrónico [(EHR](../expand-teams-across-your-org/healthcare/teams-in-hc.md#virtual-visits-and-electronic-healthcare-record-ehr-integration)).

Para ver el informe, debe ser administrador global o administrador Teams usuario.

El informe contiene las siguientes pestañas. La información que verá en el informe depende de si tiene una licencia para la aplicación Bookings, el Teams conector EHR o ambos.

|Pestaña |Descripción  |
|---------|---------|
|**[Visitas virtuales](#virtual-visits)**     |Muestra el número total de visitas virtuales, con un desglose del número de visitas programadas con la aplicación Bookings y Teams reuniones integradas con EHR realizadas desde su sistema EHR.         |
|**[Duración](#duration)**     |Muestra la duración media de las visitas y el tiempo medio de espera en la sala de espera de los participantes.         |
|**[Bookings](#bookings)**     |Muestra el número de visitas programadas a través de la aplicación Bookings.         |
|**[EHR](#ehr)**     |Muestra el número de Teams visitas integradas con EHR realizadas desde su sistema EHR.         |  

Use este informe para obtener información sobre la actividad y las tendencias de las visitas virtuales de su organización. La información puede ayudarle a optimizar las visitas virtuales para ofrecer mejores resultados empresariales.

## <a name="view-the-virtual-visits-usage-report"></a>Ver el informe de uso de visitas virtuales

1. En el panel de navegación izquierdo del centro Microsoft Teams administración, elija **Análisis &** **informesUsar** >  informes. En la pestaña **Ver informes** , en **Informe**, seleccione **Uso de visitas virtuales**.
2. En **Intervalo de** fechas, seleccione un intervalo de fechas de 7 días, 30 días o 90 días. A continuación, elija **Ejecutar informe**.

> [!NOTE]
> De forma predeterminada, el análisis de visitas virtuales está en y el informe está disponible. Al usar este informe, concede a Microsoft permiso para recopilar datos sobre las visitas virtuales de su organización. Para obtener información sobre nuestras directivas de retención de datos, vea Retención[, eliminación](/compliance/assurance/assurance-data-retention-deletion-and-destruction-overview) y eliminación de datos en Microsoft 365.
>
>Si desea desactivar el informe de su organización, puede hacerlo en Configuración en la esquina superior  derecha de la página.


## <a name="interpret-the-report"></a>Interpretar el informe

### <a name="virtual-visits"></a>Visitas virtuales

Los gráficos que verá aquí dependen de si tiene una licencia para la aplicación Bookings, el Teams conector EHR o ambos. Para obtener más información, vea [Administrar la aplicación Bookings](../bookings-app-admin.md) e Integración [en CERNER EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) o [Integración en Épico EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-virtual-visits.png" alt-text="Captura de pantalla de la pestaña Visitas virtuales del informe de uso de visitas virtuales que muestra llamadas numeradas." lightbox="../media/virtual-visits-usage-report-virtual-visits.png":::

|Globo |Descripción  |
|--------|-------------|
|**1**   |Cada informe tiene una fecha para cuando se generó el informe. Los informes normalmente reflejan una latencia de 24 a 48 horas desde el momento de la actividad. |
|**2**   |El eje X es el intervalo de fechas seleccionado para el informe. El eje Y es el número de visitas.<br>Mantenga el puntero sobre el punto en una fecha determinada para ver el número de visitas en esa fecha.|
|**3**   |Puede filtrar lo que ve en el gráfico seleccionando un elemento de la leyenda. Por ejemplo, seleccione **Total de visitas virtuales de Bookings** o **Total de visitas virtuales ehr** para ver solo la información relacionada con cada una de ellas. Al cambiar esta selección no se cambia la información de la tabla. |
|**4**   |La tabla proporciona información detallada sobre cada visita que tuvo lugar durante el intervalo de fechas seleccionado. <ul><li>**Hora de inicio (UTC)** es la fecha y la hora en que un miembro del personal y un participante están en la reunión o cuando se produjo la primera actividad en la reunión.  </li> <li>**Id. de** reunión es el id. único de la reunión.</li> <li>**El tiempo de espera** de la sala de espera es el tiempo entre la primera vez que un participante se une a la sala de espera cuando un miembro del personal admite a ese mismo participante o a otro participante a la reunión.</li><li>**Duración** es la diferencia de tiempo entre la hora de inicio y cuando la última persona abandona la reunión. Si un miembro del personal y un participante no se unen a la reunión, la duración se muestra como 0 (cero).</li> <li>**Estado** muestra el estado de la reunión. <ul><li>**Completado**: si uno o varios miembros del personal y participantes se unen a la reunión y la reunión ha finalizado. O bien, si uno o varios participantes se unen a la reunión y la reunión ha finalizado.</li> <li> **No se muestra**: si un miembro del personal se une a la reunión pero ninguna otra persona se une y la reunión ha finalizado. </li></ul> </li> <li>**El tipo de** reunión indica si la cita virtual se programó a través de la aplicación Bookings o Teams conector EHR.</li> <li>**Los asistentes** son el número total de miembros del personal y participantes de la reunión.</li> <li>**Los SMS enviados** indican si se ha enviado una notificación SMS a los asistentes. </li> </li> </ul> |
|**5**   |Seleccione **Configuración** para abrir el panel de análisis **Visitas virtuales**. Desde aquí, puede desactivar o activar el informe de visitas virtuales de su organización y agregar o quitar columnas en la tabla. Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.|
|**6**   |Puede exportar el informe a un archivo CSV para analizarlo sin conexión. Seleccione **Exportar a Excel** y, a continuación, en la pestaña **Descargas****, elija Descargar** para descargar el informe cuando esté listo.|

### <a name="duration"></a>Duración

:::image type="content" source="../media/virtual-visits-usage-report-duration.png" alt-text="Captura de pantalla de la pestaña Duración del informe de uso de visitas virtuales que muestra llamadas numeradas." lightbox="../media/virtual-visits-usage-report-duration.png":::

|Globo |Descripción  |
|--------|-------------|
|**1**   |Cada informe tiene una fecha para cuando se generó el informe. Los informes normalmente reflejan una latencia de 24 a 48 horas desde el momento de la actividad. |
|**2**   |El eje X es el intervalo de fechas seleccionado para el informe. El eje Y es el número de minutos.<br>Mantenga el puntero sobre el punto de una fecha determinada para ver la duración media de la visita o el tiempo medio de espera de la sala de espera para una fecha determinada.  |
|**3**   |Puede filtrar lo que ve en el gráfico seleccionando un elemento de la leyenda. Por ejemplo, seleccione **Duración media de la visita virtual** o **Tiempo** medio de espera de la sala de espera para ver solo la información relacionada con cada una de ellas. Al cambiar esta selección no se cambia la información de la tabla. |
|**4**   |La tabla proporciona información detallada sobre cada visita que tuvo lugar durante el intervalo de fechas seleccionado. <ul><li>**Hora de inicio (UTC)** es la fecha y la hora en que un miembro del personal y un participante están en la reunión o cuando se produjo la primera actividad en la reunión.  </li> <li>**Id. de** reunión es el id. único de la reunión.</li> <li>**El tiempo de espera** de la sala de espera es el tiempo entre la primera vez que un participante se une a la sala de espera cuando un miembro del personal admite a ese mismo participante o a otro participante a la reunión.</li><li>**Duración** es la diferencia de tiempo entre la hora de inicio y cuando la última persona abandona la reunión. Si un miembro del personal y un participante no se unen a la reunión, la duración se muestra como 0 (cero).</li> <li>**Estado** muestra el estado de la reunión. <ul><li>**Completado**: si uno o varios miembros del personal y participantes se unen a la reunión y la reunión ha finalizado. O bien, si uno o varios participantes se unen a la reunión y la reunión ha finalizado.</li> <li> **No se muestra**: si un miembro del personal se une a la reunión pero ninguna otra persona se une y la reunión ha finalizado. </li></ul> </li> <li>**El tipo de** reunión indica si la cita virtual se programó a través de la aplicación Bookings o Teams conector EHR.</li> <li>**Los asistentes** son el número total de miembros del personal y participantes de la reunión.</li> <li>**Los SMS enviados** indican si se ha enviado una notificación SMS a los asistentes. </li> </li> </ul>|
|**5**   |Seleccione **Configuración** para abrir el panel de análisis **Visitas virtuales**. Desde aquí, puede desactivar o activar el informe de visitas virtuales de su organización y agregar o quitar columnas en la tabla. Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.|
|**6**   |Puede exportar el informe a un archivo CSV para analizarlo sin conexión. Seleccione **Exportar a Excel** y, a continuación, en la pestaña **Descargas****, elija Descargar** para descargar el informe cuando esté listo.|
### <a name="bookings"></a>Bookings

Verá esta pestaña si tiene una licencia que incluye la aplicación Bookings. Para obtener más información, consulte [Administrar la aplicación Bookings](../bookings-app-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-bookings.png" alt-text="Captura de pantalla de la pestaña Bookings del informe de uso de visitas virtuales que muestra llamadas numeradas." lightbox="../media/virtual-visits-usage-report-bookings.png":::

|Globo |Descripción  |
|--------|-------------|
|**1**   |Cada informe tiene una fecha para cuando se generó el informe. Los informes normalmente reflejan una latencia de 24 a 48 horas desde el momento de la actividad. |
|**2**   |El eje X es el intervalo de fechas seleccionado para el informe. El eje Y es el número de visitas de Bookings.<br>Mantenga el puntero sobre el punto en una fecha determinada para ver el número de visitas de Bookings que se produjeron en esa fecha.|
|**3**   |La tabla proporciona información detallada sobre cada visita que tuvo lugar durante el intervalo de fechas seleccionado. <ul><li>**Hora de inicio (UTC)** es la fecha y la hora en que un miembro del personal y un participante están en la reunión o cuando se produjo la primera actividad en la reunión.  </li> <li>**Id. de** reunión es el id. único de la reunión.</li> <li>**El tiempo de espera** de la sala de espera es el tiempo entre la primera vez que un participante se une a la sala de espera cuando un miembro del personal admite a ese mismo participante o a otro participante a la reunión.</li><li>**Duración** es la diferencia de tiempo entre la hora de inicio y cuando la última persona abandona la reunión. Si un miembro del personal y un participante no se unen a la reunión, la duración se muestra como 0 (cero).</li> <li>**Estado** muestra el estado de la reunión. <ul><li>**Completado**: si uno o varios miembros del personal y participantes se unen a la reunión y la reunión ha finalizado. O bien, si uno o varios participantes se unen a la reunión y la reunión ha finalizado.</li> <li> **No se muestra**: si un miembro del personal se une a la reunión pero ninguna otra persona se une y la reunión ha finalizado. </li></ul> </li> <li>**El tipo de** reunión indica si la cita virtual se programó a través de la aplicación Bookings o Teams conector EHR.</li> <li>**Los asistentes** son el número total de miembros del personal y participantes de la reunión.</li> <li>**Los SMS enviados** indican si se ha enviado una notificación SMS a los asistentes. </li> </li> </ul>|
|**4**   |Seleccione **Configuración** para abrir el panel de análisis **Visitas virtuales**. Desde aquí, puede desactivar o activar el informe de visitas virtuales de su organización y agregar o quitar columnas en la tabla. Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.|
|**5**   |Puede exportar el informe a un archivo CSV para analizarlo sin conexión. Seleccione **Exportar a Excel** y, a continuación, en la pestaña **Descargas****, elija Descargar** para descargar el informe cuando esté listo.|
### <a name="ehr"></a>EHR

Verá esta pestaña si tiene una licencia que incluye el Teams EHR. Para obtener más información, consulte [Integración en Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md) o [Integración en Épico EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md).

:::image type="content" source="../media/virtual-visits-usage-report-ehr.png" alt-text="Captura de pantalla de la pestaña EHR del informe de uso de visitas virtuales que muestra llamadas numeradas." lightbox="../media/virtual-visits-usage-report-ehr.png":::

|Globo |Descripción  |
|--------|-------------|
|**1**   |Cada informe tiene una fecha para cuando se generó el informe. Los informes normalmente reflejan una latencia de 24 a 48 horas desde el momento de la actividad. |
|**2**   |El eje X es el intervalo de fechas seleccionado para el informe. El eje Y es el número de visitas EHR.<br>Mantenga el puntero sobre el punto en una fecha determinada para ver el número de visitas ehr en esa fecha.|
|**3**   |La tabla proporciona información detallada sobre cada visita que tuvo lugar durante el intervalo de fechas seleccionado. <ul><li>**Hora de inicio (UTC)** es la fecha y la hora en que un miembro del personal y un participante están en la reunión o cuando se produjo la primera actividad en la reunión.  </li> <li>**Id. de** reunión es el id. único de la reunión.</li> <li>**El tiempo de espera** de la sala de espera es el tiempo entre la primera vez que un participante se une a la sala de espera cuando un miembro del personal admite a ese mismo participante o a otro participante a la reunión.</li><li>**Duración** es la diferencia de tiempo entre la hora de inicio y cuando la última persona abandona la reunión. Si un miembro del personal y un participante no se unen a la reunión, la duración se muestra como 0 (cero).</li> <li>**Estado** muestra el estado de la reunión. <ul><li>**Completado**: si uno o varios miembros del personal y participantes se unen a la reunión y la reunión ha finalizado. O bien, si uno o varios participantes se unen a la reunión y la reunión ha finalizado.</li> <li> **No se muestra**: si un miembro del personal se une a la reunión pero ninguna otra persona se une y la reunión ha finalizado. </li></ul> </li> <li>**El tipo de** reunión indica si la cita virtual se programó a través de la aplicación Bookings o Teams conector EHR.</li> <li>**Los asistentes** son el número total de miembros del personal y participantes de la reunión.</li> <li>**Los SMS enviados** indican si se ha enviado una notificación SMS a los asistentes. </li> </li> </ul>|
|**4**   |Seleccione **Configuración** para abrir el panel de análisis **Visitas virtuales**. Desde aquí, puede desactivar o activar el informe de visitas virtuales de su organización y agregar o quitar columnas en la tabla. Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla.|
|**5**   |Puede exportar el informe a un archivo CSV para analizarlo sin conexión. Seleccione **Exportar a Excel** y, a continuación, en la pestaña **Descargas****, elija Descargar** para descargar el informe cuando esté listo.|

> [!NOTE]
> Si su organización quiere participar en la versión preliminar privada para que los usuarios que no son administradores, como los responsables de la toma de decisiones empresariales, tengan acceso a este informe y lo consulten, puede contactar [con nosotros](mailto:tapmwtanalytics@microsoft.com).

## <a name="related-articles"></a>Artículos relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)
- [Visitas virtuales con Teams y la aplicación Bookings](../expand-teams-across-your-org/bookings-virtual-visits.md)
- [Visitas virtuales con Teams: integración en Épico EHR](../expand-teams-across-your-org/healthcare/ehr-admin.md)
- [Visitas virtuales con Teams: integración en Cerner EHR](../expand-teams-across-your-org/healthcare/ehr-admin-cerner.md)
