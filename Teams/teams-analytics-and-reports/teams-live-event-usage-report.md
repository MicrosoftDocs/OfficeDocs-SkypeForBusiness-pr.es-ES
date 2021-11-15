---
title: Microsoft Teams de uso de eventos en directo
author: HowlinWolf-92
ms.author: v-mahoffman
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
description: Obtenga información sobre cómo usar el Teams de uso de eventos en directo en el Centro de administración de Microsoft Teams para obtener información general sobre Teams actividad de eventos en directo en su organización.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 504c8822146efa7101ca1435cab961a86068ccaf
ms.sourcegitcommit: 4df3d144296b9b8982109be7edaffd636aabdf29
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2021
ms.locfileid: "60959899"
---
# <a name="microsoft-teams-live-event-usage-report"></a>Microsoft Teams de uso de eventos en directo

El Teams de uso de eventos en directo en el centro de administración de Microsoft Teams muestra la información general sobre la actividad de los eventos en directo que se celebre en su organización. Puede ver la información de uso, incluido el estado del evento, la hora de inicio, las vistas y el tipo de producción de cada evento. Puede obtener información sobre las tendencias de uso y ver quién en su organización programa, presenta y produce eventos en directo.

## <a name="view-the-live-event-usage-report"></a>Ver el informe de uso de eventos en directo

1. En el panel de navegación izquierdo del centro Microsoft Teams administración, haga clic **en Análisis & informes de**  >  **uso.** En la **pestaña Ver informes,** **en** Informe, seleccione Teams uso de eventos **en directo.**
2. En **Intervalo de fechas,** seleccione un rango predefinido o establezca un rango personalizado. Puede establecer un rango para mostrar datos hasta un año, seis meses antes y después de la fecha actual.
3. (Opcional) En **Organizador,** puede elegir mostrar solo eventos en directo organizados por un usuario específico.
4. Haga clic **en Ejecutar informe.**  

   :::image type="content" alt-text="Captura de pantalla del Teams de uso de eventos en directo en el Teams de administración con llamadas." source="../media/teams-live-event-usage-report-with-callouts.png" lightbox="../media/teams-live-event-usage-report-with-callouts.png":::

## <a name="interpret-the-report"></a>Interpretar el informe

|Globo |Descripción  |
|--------|-------------|
|**1**   |El Teams de eventos en directo se puede ver para ver las tendencias de los últimos 7 días, 28 días o un intervalo de fechas personalizado que establezca. |
|**2**   |Cada informe tiene una fecha para cuándo se generó. El informe refleja la actividad casi en tiempo real cuando se actualiza la página. |
|**3**   |<ul><li>En el gráfico, el eje X es el intervalo de fechas seleccionado para el informe específico.</li> <li> El eje Y es el recuento total de vistas.</li> </ul>Mantenga el puntero sobre el punto en una fecha determinada para ver el número de vistas en todos los eventos en directo en esa fecha.|
|**4**   |La tabla le proporciona un desglose de cada evento en directo. <ul><li>**Evento** es el nombre para mostrar del evento en directo. Haga clic en el nombre del evento [para obtener más información](#view-event-details) sobre el evento. </li> <li>**Hora de inicio** hace referencia a la fecha y hora de inicio del evento.</li> <li>**Estado del evento** muestra si el evento se ha realizado.  </li><li>**Organizador** es el nombre del organizador del evento.</li> <li>**Los presentadores** son los nombres de los presentadores del evento.</li><li>**Los productores** son los nombres de los productores del evento.</li><li>**Vistas** es el número de vistas únicas después de completar el evento.</li><li>**La** grabación muestra si la configuración de grabación está o no.</li><li>**Tipo de** producción muestra si el evento se produce en Teams o por una aplicación o dispositivo externo.</li></li> </ul>Tenga en cuenta que si una cuenta de usuario ya no existe en Azure AD, el nombre de usuario se muestra como "--" en la tabla. <br><br>Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla. |
|**5**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla.|

## <a name="notes"></a>Notas
Se muestran hasta 100 eventos en directo que coinciden con los criterios de informe actuales. Para ver más eventos en directo, aplique filtros de fecha para reducir el tamaño de la lista. 

Cualquier persona que vea la grabación del evento o el evento a petición no se incluirá en el recuento de vistas. 

## <a name="view-event-details"></a>Ver detalles del evento

La página de detalles del evento en directo le proporciona un resumen de los detalles de un evento en directo y enumera todos los archivos, incluidas transcripciones y grabaciones, asociados con el evento. Haga clic en un nombre de archivo para ver o descargar el archivo.

:::image type="content" alt-text="Captura de pantalla que muestra detalles de un evento en directo." source="../media/teams-live-event-usage-report-event-detail.png" lightbox="../media/teams-live-event-usage-report-event-detail.png":::

Si su organización está habilitada para el eCDN de [Hive](https://www.hivestreaming.com/partners/integration-partners/microsoft/) o [el ECDN de Kollective,](https://kollective.com) puede obtener análisis de asistentes adicionales haciendo clic en el vínculo del informe de partners.

## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)
- [¿Qué son los eventos en directo en Teams?](../teams-live-events/what-are-teams-live-events.md)
