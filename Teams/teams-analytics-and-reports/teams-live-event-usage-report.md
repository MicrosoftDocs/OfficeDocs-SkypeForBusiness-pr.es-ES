---
title: Informe de uso de eventos en directo de Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Obtenga información sobre cómo usar el informe de uso de eventos en directo de Teams en el Centro de administración de Microsoft Teams para obtener información general sobre la actividad de eventos en directo de Teams en su organización.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 971e9bc846ad1a7134c1877a1716fc535ae65e4d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809290"
---
# <a name="microsoft-teams-live-event-usage-report"></a>Informe de uso de eventos en directo de Microsoft Teams

El informe de uso de eventos en directo de Teams en el Centro de administración de Microsoft Teams le muestra la información general de la actividad de los eventos en directo que se celebraron en su organización. Puede ver la información de uso, incluido el estado del evento, la hora de inicio, las vistas y el tipo de producción de cada evento. Puede obtener información sobre las tendencias de uso y ver quién en su organización programa, presenta y produce eventos en directo.

## <a name="view-the-live-event-usage-report"></a>Ver el informe de uso de eventos en directo

1. En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, haga clic en **& informes de**  >  **uso.** En la **pestaña Ver informes,** en **Informe,** seleccione Uso de **eventos en directo de Teams.**
2. En **Intervalo de** fechas, seleccione un rango predefinido o establezca un rango personalizado. Puede establecer un intervalo para mostrar datos hasta un año, seis meses antes y después de la fecha actual.
3. (Opcional) En **Organizador,** puede elegir mostrar solo los eventos en directo organizados por un usuario específico.
4. Haga clic **en Ejecutar informe.**  

    ![Captura de pantalla del informe de uso de eventos en directo de Teams en el centro de administración de Teams con llamadas](../media/teams-live-event-usage-report-with-callouts.png "Captura de pantalla del informe de uso de eventos en directo de Teams en el centro de administración de Teams con llamadas")

## <a name="interpret-the-report"></a>Interpretar el informe

|Globo |Descripción  |
|--------|-------------|
|**1**   |Puede visualizar el informe de eventos en directo de Teams para ver las tendencias de los últimos 7 días, 28 días o un intervalo de fechas personalizado que establezca. |
|**2**   |Cada informe tiene la fecha del momento en que se generó. El informe refleja la actividad casi en tiempo real cuando se actualiza la página. |
|**3**   |<ul><li>En el gráfico, el eje X es el intervalo de fechas seleccionado para el informe específico.</li> <li> El eje Y es el recuento total de vistas.</li> </ul>Mantenga el mouse sobre el punto de una fecha determinada para ver el número de vistas de todos los eventos en directo de esa fecha.|
|**4**   |La tabla proporciona un desglose de cada evento en directo. <ul><li>**El** evento es el nombre para mostrar del evento en directo. Haga clic en el nombre del evento [para obtener más información](#view-event-details) sobre el evento. </li> <li>**Hora de** inicio hace referencia a la fecha y hora de inicio del evento.</li> <li>**Estado del** evento muestra si el evento se ha realizado.  </li><li>**El** organizador es el nombre del organizador del evento.</li> <li>**Los presentadores** son los nombres de los presentadores del evento.</li><li>**Los productores** son los nombres de los productores del evento.</li><li>**Vistas** es el número de vistas únicas después de que se haya completado el evento.</li><li>**La** grabación muestra si la configuración de grabación está o no.</li><li>**El tipo** de producción muestra si el evento se produce en Teams o mediante una aplicación o dispositivo externo.</li></li> </ul>Tenga en cuenta que si una cuenta de usuario ya no existe en Azure AD, el nombre de usuario se muestra como "--" en la tabla. <br><br>Para ver la información que quiera en la tabla, asegúrese de agregar las columnas a la tabla. |
|**5**   |Seleccione **Editar columnas** para agregar o quitar columnas en la tabla.|

## <a name="notes"></a>Notas
Se muestran hasta 100 eventos en directo que coinciden con los criterios del informe actual. Para ver más eventos en directo, aplique filtros de fecha para reducir el tamaño de la lista.

## <a name="view-event-details"></a>Ver detalles del evento

La página de detalles del evento en directo le proporciona un resumen de los detalles de un evento en directo y enumera todos los archivos, incluidas las transcripciones y las grabaciones, asociados al evento. Haga clic en un nombre de archivo para ver o descargar el archivo.

![Captura de pantalla que muestra detalles de un evento en directo](../media/teams-live-event-usage-report-event-detail.png)

Si en su [](https://www.hivestreaming.com/partners/integration-partners/microsoft/) organización se habilita el eCDN subárbol o el [eCDN](https://kollective.com) opcional, puede obtener análisis adicionales de los asistentes haciendo clic en el vínculo del informe de asociados.

## <a name="related-topics"></a>Temas relacionados

- [Análisis e informes de Teams](teams-reporting-reference.md)
- [¿Qué son los eventos en directo de Teams?](../teams-live-events/what-are-teams-live-events.md)
