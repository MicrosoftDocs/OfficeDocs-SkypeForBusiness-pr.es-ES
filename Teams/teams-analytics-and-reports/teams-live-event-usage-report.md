---
title: Informe de uso de eventos en directo de Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo usar el informe de uso de eventos en directo de Teams en el Centro de administración de Microsoft Teams para obtener información general sobre la actividad de eventos en directo de Teams en su organización.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 970247bf863942a4f938f96e30533ff550d37e94
ms.sourcegitcommit: 73b13cd8a79ba1724b9fb79c8356a7cacafb7dd3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2022
ms.locfileid: "68964986"
---
# <a name="microsoft-teams-live-event-usage-report"></a>Informe de uso de eventos en directo de Microsoft Teams

El informe de uso de eventos en directo de Teams en el Centro de administración de Microsoft Teams muestra la información general de la actividad de los eventos en directo realizados en su organización. Puede ver la información de uso, incluido el estado del evento, la hora de inicio, las vistas y el tipo de producción para cada evento. Puede obtener información sobre las tendencias de uso y ver quién programa, presenta y produce eventos en directo en su organización.

## <a name="view-the-live-event-usage-report"></a>Ver el informe de uso de eventos en directo

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en **Análisis & informes** > **de uso**. En la pestaña **Ver informes** , en **Informe**, seleccione **Uso de eventos en directo de Teams**.
2. En **Intervalo de fechas**, seleccione un rango predefinido o establezca un intervalo personalizado. Puede establecer un intervalo para mostrar datos hasta un año, seis meses antes y después de la fecha actual.
3. (Opcional) En **Organizador**, puede elegir mostrar solo los eventos en directo organizados por un usuario específico.
4. Haga clic en **Ejecutar informe**.  

   :::image type="content" alt-text="Captura de pantalla del informe de uso de eventos en directo de Teams en el centro de administración de Teams con globos." source="../media/teams-live-event-usage-report-with-callouts.png" lightbox="../media/teams-live-event-usage-report-with-callouts.png":::

## <a name="interpret-the-report"></a>Interpretar el informe

|Globo |Descripción  |
|--------|-------------|
|**1**   |Puede visualizar el informe de eventos en directo de Teams para ver las tendencias de los últimos 7, 28 días o un intervalo de fechas personalizado que establezca. |
|**2**   |Cada informe tiene una fecha en la que se generó. El informe refleja la actividad casi en tiempo real cuando se actualiza la página. |
|**3**   |<ul><li>En el gráfico, el eje X es el intervalo de fechas seleccionado para el informe específico.</li> <li> El eje Y es el recuento total de la vista.</li> </ul>Desplace el puntero sobre el punto de una fecha determinada para ver el número de vistas de todos los eventos en directo en esa fecha.|
|**4**   |La tabla proporciona un desglose de cada evento en directo. <ul><li>**Evento** es el nombre para mostrar del evento en directo. Haga clic en el nombre del evento para [obtener más detalles](#view-event-details) sobre el evento. </li> <li>**Hora de inicio** hace referencia a la fecha y hora de inicio del evento.</li> <li>**Estado del evento** muestra si el evento ha tenido lugar.  </li><li>**Organizador** es el nombre del organizador del evento.</li> <li>**Los moderadores** son los nombres de los moderadores de eventos.</li><li>**Los productores** son los nombres de los productores de eventos.</li><li>**Vistas** es el número de vistas únicas después de completar el evento.</li><li>**La grabación** muestra si la configuración de grabación está activada o desactivada.</li><li>**Tipo de producción** muestra si el evento se produce en Teams o mediante una aplicación o dispositivo externos.</li></li> </ul>Tenga en cuenta que si una cuenta de usuario ya no existe en Azure AD, el nombre de usuario se muestra como "--" en la tabla. <br><br>Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla. |
|**5**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla.|

## <a name="notes"></a>Notas
Se muestran un máximo de 100 eventos en directo que coinciden con los criterios del informe actual. Para ver más eventos en directo, aplique filtros de fecha para reducir el tamaño de la lista.

Los moderadores anónimos no se incluirán en el informe.

Cualquier persona que vea la grabación del evento o el evento a petición no se incluirá en el recuento de vistas. 

## <a name="view-event-details"></a>Ver detalles del evento

La página de detalles del evento en directo le proporciona un resumen de los detalles de un evento en directo y enumera todos los archivos, incluidas las transcripciones y las grabaciones, asociados con el evento. Haga clic en un nombre de archivo para ver o descargar el archivo.

:::image type="content" alt-text="Captura de pantalla que muestra los detalles de un evento en directo." source="../media/teams-live-event-usage-report-event-detail.png" lightbox="../media/teams-live-event-usage-report-event-detail.png":::

Si su organización usa Microsoft eCDN, el análisis avanzado se puede ver y exportar desde el [panel de eCDN](https://admin.ecdn.microsoft.com).  Si su organización está habilitada para eCDN de [Hive](https://www.hivestreaming.com/partners/integration-partners/microsoft/) o [kollective](https://kollective.com) eCDN, puede obtener análisis de asistentes adicionales haciendo clic en el vínculo del informe de asociado.

## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)
- [¿Qué son los eventos en directo en Teams?](../teams-live-events/what-are-teams-live-events.md)
