---
title: Informes de mantenimiento y uso
author: altsou
ms.author: altsou
manager: serdars
ms.date: 04/07/2022
ms.reviewer: altsou
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Creación de informes de datos de nodo para el mantenimiento y el uso de informes
f1keywords: ''
ms.openlocfilehash: 9b1f3e1960cbe0089f498045922125b121679646
ms.sourcegitcommit: 64c01699022b47fdfec8dc6e2ca279e57eae3baa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2022
ms.locfileid: "68243801"
---
# <a name="health-and-usage-reports"></a>Informes de mantenimiento y uso

El nodo de informes contiene datos sobre el estado y el uso de los Salas de Microsoft Teams en el portal de administración de Pro. La **información general** presenta las tendencias de estado de los salones para todos los inquilinos. La pestaña **Estado** muestra una lista de salones con sus datos de estado correspondientes. El uso de la sala en función de la información del calendario y los datos de calidad de la llamada está visible en la pestaña **Uso** .

## <a name="navigating-reports"></a>Navegar por los informes

<!--![A screenshot of active tickets bar graph](../media/health-and-usage-002new.png)-->

La sección de información general proporciona representaciones gráficas de aspectos importantes de la administración de salas de reuniones. Los gráficos cambiarán según el intervalo de tiempo seleccionado o el grupo seleccionado. Para cambiar el intervalo de tiempo, haga clic en el menú desplegable.

<!--!![A screenshot of a menu to choose a day](../media/health-and-usage-004.png)-->

Para cambiar el grupo, haga clic en el menú desplegable de selección de grupo en la pancarta.

<!--!![A screenshot of the banner menu auto-generated](../media/health-and-usage-005.png)-->
### <a name="tickets-by-category"></a>Entradas por categoría

La anillo muestra el total de vales recaudados para el intervalo de tiempo seleccionado y el grupo (el valor predeterminado es de siete días, todos los grupos). Las entradas están representadas en sus categorías principales: Audio, Pantalla, Periféricos, Conectividad, Control de versiones y Problemas grabados.

<!--!![A screenshot of pie chart tickets by category](../media/health-and-usage-006.png)-->

Cuando se selecciona, se muestra un control flotante para la vista detallada de entradas de esa categoría.

<!--!![A screenshot of tickets and versioning side by side](../media/health-and-usage-007.png)-->

En el control flotante, es posible filtrar la lista de vales por la subcategoría seleccionando la parte correspondiente de la dona. 

<!--!![A screenshot tickets by subcategory automatically generated](../media/health-and-usage-008.png)-->

Para volver, haga clic en la anillo o haga clic en la ruta de navegación de la parte superior izquierda.

Para ir a un vale específico en esta vista de lista, haga clic en el vínculo en la **columna Vale de soporte** técnico.

<!--### Ticket history

The ticket history graph shows a comparison of incidents assigned to you or Microsoft over the specified time period.

> [!NOTE]
> If a ticket changes owner in a day, whoever owns the assignment for the majority of that day will have the ticket counted towards them. For example, if you assign the ticket to Microsoft early in the day, the ticket counts towards **Assigned to Microsoft** for the day.

<!--![A screen shot of Tickets history by different periods](../media/health-and-usage-009.png)-->

### <a name="health-history"></a>Historial de salud

Este gráfico muestra el estado medio (definición en la sección Salud) para todas las salas del inquilino, así como el estado medio para todos los clientes mtr pro en una base diaria. Puede ver el estado medio durante un máximo de 90 días.

<!--!![A screenshot of rooms health and average health](../media/health-and-usage-010.png)-->

### <a name="most-reliableleast-reliable-rooms"></a>Habitaciones más confiables o menos confiables

Dos tablas muestran los salones más confiables y menos confiables en función de la salud. Para obtener la vista de lista completa, seleccione Estado y, después, ordene la lista por la columna Estado.

### <a name="rooms-history"></a>Historial de salas

Proporciona una vista histórica de los salones inscritos en el servicio y ofrece una visión comparativa de los salones que estaban sanos o no supervisados en el mismo período de tiempo.

## <a name="health"></a>Mantenimiento

Para ir al informe de estado de todas las salas, seleccione Informes y, después, seleccione  **Estado**.

<!--!![A screenshot of a Reports health percentage](../media/health-and-usage-001.png)-->

La puntuación de mantenimiento es una métrica diseñada para salas de superficie que es más probable que cause frustración al usuario final. Una habitación puede estar sana o no saludable durante un día determinado. Se considera poco saludable si un boleto o muchos boletos afectaron a la sala durante más de 20 minutos totales durante las horas de no mantenimiento (5AM -9PM hora local). Por ejemplo, si un ticket se abre a las 5:00, pero se cierra a las 5:15, la sala se considera aún saludable. Sin embargo, si se produjo un segundo boleto de 09:00 a.m. a 9:10 a.m., la sala se consideraría insalubre para el día. Del mismo modo, si un boleto ocurrió de 5:00 a.m. a 5:21 a.m., se considera poco saludable para el día.

> [!NOTE]
> El estado del día se agrega una vez al día a las 12:00 a.m. hora UTC. Para los clientes cercanos a la línea de fecha internacional, la agregación de estado puede ocurrir cerca de la mitad de la jornada laboral.

> [!NOTE]
> Los salones que se están incorporando están ocultos para la lista de salones en la pestaña Estado y no cuentan para el estado medio del inquilino.

Al hacer clic en una sala que aparece en esta vista, se muestran más detalles.

El gráfico de barras muestra el número de entradas cada día. Los boletos abiertos ese día aparecen en azul. Los boletos abiertos antes del día respectivo aparecen en naranja. Al hacer clic en un día en el gráfico, se filtra el gráfico circular y la tabla a los vales relevantes. Para invertir el filtro, navegue con las rutas de navegación o haga clic en el gráfico.

La categorización de las entradas se representa en el gráfico de anillos. Al interactuar con esto se filtran el gráfico de escala de tiempo y la tabla. Para invertir el filtro, navegue con las rutas de navegación o haga clic en el gráfico.

<!--!![A screenshot of a Reports health bar graph](../media/health-and-usage-014.png)-->

La vista de impacto de la reunión muestra las reuniones programadas durante las cuales se ha abierto un vale con una gravedad de "Importante" o "Crítico". El objetivo de esta opinión es proporcionar una aproximación de las reuniones en las que los participantes podrían haber experimentado problemas.

La vista de impacto de la reunión muestra las reuniones programadas durante las cuales se ha abierto un vale con una gravedad de "Importante" o "Crítico". El objetivo de esta opinión es proporcionar una aproximación de las reuniones en las que los participantes podrían haber experimentado problemas.

<!--![A screenshot of a Reports meeting impact](../media/health-and-usage-015.png)-->

La pestaña Configuración muestra los metadatos de la sala, como la información de hardware, la configuración del dispositivo, la información del BIOS, la configuración de las aplicaciones y la ubicación.

## <a name="usage"></a>Uso

Para ver el informe de uso de todas las salas, seleccione **Uso >informes**.

<!--!![A screenshot of all rooms' usage by health](../media/health-and-usage-011.png)-->

Los titulares proporcionan algunas perspectivas:

- Total de salas de su espacio empresarial
- Cuántas reuniones no se han reservado, ya sea sin conexión o en línea
- Porcentaje de utilización de salas en todo el espacio empresarial
- Número total de reuniones reservadas a través de intercambio
- Porcentaje de reuniones reservadas que incluyeron un vínculo de Skype o Teams
- Total de llamadas con participación en la sala
- Puntuación agregada de rendimiento de llamadas de todas las llamadas clasificadas con "Buena" calidad para todas las llamadas. 

Debajo de las métricas de títulos hay una tabla de salas con las métricas correspondientes. Seleccione una sala para ver más detalles de uso. Las métricas de la tabla se describen en la tabla siguiente.

|Columna|Descripción|
|---|---|
|Utilización|Porcentaje de tiempo que la sala se reservó durante el horario laboral en el período seleccionado. Por ejemplo. Período de tiempo establecido en 7 días. Utilización del 80% sobre los medios que la sala se reservó durante 32/40 horas|
|Reservado en línea|De las reuniones reservadas, el porcentaje se ha habilitado con Teams. Por ejemplo. Se han reservado 10 reuniones. De ese número, 8 tenían un vínculo de Teams. Reservado en línea = 80%|
|Reuniones programadas|Número absoluto de reuniones programadas en la sala|
|Total de llamadas|Número absoluto de llamadas con la sala como participante.|
Rendimiento de llamadas|Porcentaje de llamadas con una calificación "Buena". Cada llamada se evalúa y recibe una calificación Buena, Mala y Desconocida. Esta métrica se calcula a partir de Llamadas buenas/Llamadas totales.|

El uso se calcula al final de cada día a medianoche (00:00) hora local del dispositivo de la sala de reuniones. El uso se calcula en función del tiempo total reservado para la reunión de ese día dividido por 8 horas.

## <a name="usage-details-of-a-room"></a>Detalles de uso de una sala

Al hacer clic en una sala de la vista de lista, se muestra un control flotante con información más detallada. En la pestaña Utilización del control flotante hay un gráfico que muestra las horas de uso de los últimos cinco días laborables. Para cada día hay dos barras: azul representa la hora de reunión reservada; púrpura representa la hora programada de las reuniones habilitadas para Teams o Skype. En la parte inferior, se calculan el promedio de reservas de reuniones y la duración de los últimos cinco días laborables.

<!--![A screenshot of utilization by hours per day](../media/health-and-usage-012.png)-->

La tabla **Llamadas** muestra las reuniones en las que la sala ha participado en una llamada de Teams. La Calidad de audio de la sala se evalúa solo para la sala, no para todos los participantes. Para ver la calidad de la llamada para todos los participantes de una llamada específica, seleccione una llamada haciendo clic en la Hora de inicio.

<!--!![A screenshot of room audio quality](../media/health-and-usage-016.png)-->

Para ver los detalles de la transmisión de la sala, haga clic en la Hora de inicio de sesión.
