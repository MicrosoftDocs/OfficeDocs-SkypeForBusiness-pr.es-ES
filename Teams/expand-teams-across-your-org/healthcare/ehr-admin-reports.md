---
title: Informe citas virtuales del conector EHR de Microsoft Teams
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Obtenga información sobre cómo usar el informe Citas virtuales del conector EHR de Teams en el Centro de administración de Microsoft Teams para obtener información general sobre el uso de citas virtuales integrada en EHR en su organización.
ms.openlocfilehash: 0e78b89c934eac101b863bd7b5ba9957939f994b
ms.sourcegitcommit: cf2f2d23e6dcda0c03f22a5800a210a1c88e583f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "65883543"
---
# <a name="microsoft-teams-ehr-connector-virtual-appointments-report"></a>Informe citas virtuales del conector EHR de Microsoft Teams

El informe Citas virtuales del conector de registro médico electrónico (EHR) de Microsoft Teams en el centro de administración de Microsoft Teams le ofrece una forma rápida y sencilla de ver el uso de citas virtuales integrado en EHR de Teams en su organización.

Para ver el informe, debe ser administrador global, administrador de Teams, lector global o lector de informes.

## <a name="view-the-report"></a>Ver el informe

Hay dos formas de acceder al informe y verlo en el Centro de administración de Teams.

- A través de la [tarjeta de uso del conector EHR](#the-ehr-connector-usage-card) en el panel
- Directamente eligiendo [**citas virtuales del conector EHR**](#the-teams-ehr-connector-virtual-appointments-report) en **Análisis & informes** > **de uso**

### <a name="the-ehr-connector-usage-card"></a>Tarjeta de uso del conector EHR

En el panel de navegación izquierdo del Centro de administración de Microsoft Teams, elija **Panel** y, después, vaya a la tarjeta **Citas virtuales del conector EHR** .

Aquí, obtendrá una vista rápida de la actividad de citas virtuales integrada de Teams por mes, incluidas las citas completadas, la asignación restante y si ha superado el límite mensual (en función de la licencia que tenga).

:::image type="content" source="../../media/ehr-connector-report-card.png" alt-text="Captura de pantalla de la tarjeta de uso del conector EHR en el panel del Centro de administración de Teams." lightbox="../../media/ehr-connector-report-card.png":::

Elija **Ver detalles** para ver los detalles del informe. Para comprar más licencias, elija **Comprar más**.

### <a name="the-teams-ehr-connector-virtual-appointments-report"></a>El informe Citas virtuales del conector EHR de Teams

1. En el panel de navegación izquierdo del Centro de administración de Teams, vaya a **Análisis & informes** > **de uso**.
1. En la pestaña **Ver informes** , elija **Citas virtuales del conector EHR** y un intervalo de fechas. A continuación, seleccione **Ejecutar informe**.

    :::image type="content" source="../../media/ehr-connector-report.png" alt-text="Captura de pantalla del informe Citas virtuales del conector EHR de Teams en el Centro de administración de Teams." lightbox="../../media/ehr-connector-report.png":::

#### <a name="interpret-the-report"></a>Interpretar el informe

|Globo |Descripción  |
|--------|-------------|
|**1**   |Cada informe muestra la fecha en la que se generó el informe y el intervalo de fechas que ha elegido.|
|**2**   |La tabla proporciona información detallada sobre cada cita que tuvo lugar durante el intervalo de fechas seleccionado. Tenga en cuenta que no verá las entradas para las citas en las que no se unió un miembro del personal o un paciente. <ul><li>**Hora de inicio (UTC)** es la fecha y hora en la que un miembro del personal y un participante están en la cita.  </li> <li>**Duración** es la diferencia de tiempo entre la hora de inicio y la fecha en que la última persona deja la cita.</li> <li>**Principal** es el nombre del organizador de la reunión. <li>**El correo electrónico de la principal** es la dirección de correo electrónico del organizador de la reunión.</li> <li> **Departamento** es la información del departamento para la cita. Si la información no se muestra correctamente, póngase en contacto con el equipo de soporte técnico de EHR. Para la integración con Epic, asegúrate de que ```&departmentId=%PERFDEPID;;; ; ;;NONE;%``` forma parte del registro de integración del proveedor. </li></li> <li>**Operadores** es el número total de miembros del personal y participantes en la cita.</li> <li>**Dentro del límite** indica si la cita está dentro del límite de asignación. </li> </ul> |
|**3**   |Puede exportar el informe a un archivo CSV para realizar análisis sin conexión. Seleccione **Exportar a Excel** para descargar el informe. |
|**4**   |Seleccione **Filtro** para filtrar la vista de detalles del informe. |
|**5**   |Seleccione **Pantalla completa** para ver el informe en modo de pantalla completa. |
|**6**   |Seleccione **Editar columnas** para agregar o quitar columnas de la tabla |

> [!NOTE]
> Para obtener más análisis sobre las citas virtuales integradas en EHR de Teams, consulte [Informe de uso de visitas virtuales](../../teams-analytics-and-reports/virtual-visits-usage-report.md). Con el informe Uso de visitas virtuales, puede ver métricas clave como el total de citas, el tiempo de espera de sala de espera, la duración de las citas y ninguna presentación. Use esta información para obtener información sobre las tendencias de uso para ayudarle a optimizar las citas virtuales y ofrecer mejores resultados empresariales.

## <a name="related-articles"></a>Artículos relacionados

- [Citas virtuales con Teams: integración en Cerner EHR](ehr-admin-cerner.md)
- [Citas virtuales con Teams: integración en Epic EHR](ehr-admin.md) 
