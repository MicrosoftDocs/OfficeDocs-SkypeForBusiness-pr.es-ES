---
title: Usar Power BI para analizar datos CQD para Microsoft Teams
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- remotework
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Use Power BI para analizar datos CQD para Microsoft Teams.
ms.openlocfilehash: 5ef98f75854cb4a255bf3f01aeb32de66c059b76
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096526"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Usar Power BI para analizar datos CQD para Microsoft Teams

Nuevo en enero de 2020: Descargar plantillas de consulta [de Power BI para CQD.](https://www.microsoft.com/download/details.aspx?id=102291) Plantillas de Power BI personalizables que puede usar para analizar e informar de los datos de CQD.

Para los informes del Panel de calidad de llamadas (CQD) en Teams, si prefiere usar Power BI para consultar e informar sobre los datos, descargue nuestras plantillas de Power BI de CQD. Al abrir las plantillas en Power BI, se le pedirá que inicie sesión con sus credenciales de administrador de CQD. Puede personalizar estas plantillas de consulta y distribuirlas a cualquier persona de su organización que tenga una licencia de Power BI y permisos de administrador CQD.

Antes de poder usar estos archivos PBIT, deberá instalar Power BI Connector para [Microsoft CQD](CQD-Power-BI-connector.md) con el archivo *MicrosoftCallQuality.pqx* incluido en la [descarga.](https://www.microsoft.com/download/details.aspx?id=102291) 

Asegúrese de que tiene el rol de [acceso CQD adecuado](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) para obtener acceso a los informes de Power BI. 

|  |  |
|---------|---------|
|<strong>(¡Nuevo!)</strong> CQD Teams Operador automático & informe histórico de cola de llamadas.pbit     |  Esta plantilla proporciona los tres informes siguientes:</p><li>Operador automático: muestra análisis de las llamadas que llegan a los Operadores automáticos.</li><li>Cola de llamadas: muestra análisis de las llamadas que llegan a las colas de llamadas.</li><li>Escala de tiempo del agente: muestra una vista de escala de tiempo de los agentes que están activos en las llamadas de cola de llamadas.</li><br>Para obtener más información, lea Operador automático & informe histórico [de cola de llamadas](aa-cq-cqd-historical-reports.md).        |
|Informe del departamento de soporte técnico de CQD.pbit     |Integrando datos de creación y EUII, este informe está diseñado para que pueda explorar en profundidad a un solo usuario para encontrar la causa raíz ascendente de la mala calidad de las llamadas para ese usuario (por ejemplo, el usuario se encuentra en un edificio que experimenta problemas de red).         |
|Ubicación CQD Enhanced Report.pbit     | Volver a imaginar informes de ubicación de SPD CQD. Incluye 9 informes, que proporcionan información sobre calidad de llamadas, WiFi de creación, confiabilidad y tasación de mi llamada (RMC) con detalles adicionales por edificio o por usuario.  Asegúrese de cargar los datos de creación para maximizar la experiencia de creación de informes.        |
|CQD Mobile Device Report.pbit     | Proporciona información específicamente adaptada a los usuarios de dispositivos móviles, como calidad de llamadas, confiabilidad y calificar mi llamada. Ver informes de red móvil, red WiFi e sistema operativo móvil (Android, iOS).        |
|CQD RTC Direct Routing Report.pbit     |Proporciona información específica para las llamadas RTC que pasan por enrutamiento directo. Para obtener más información, lea Usar el informe de enrutamiento directo [RTC CQD](CQD-PSTN-report.md).         |
|Informe de resumen de CQD.pbit     |Mejores visualizaciones, presentación mejorada, mayor densidad de información y fechas de balanceo. Estos informes facilitan el identificador de valores atípicos. Explore la calidad de las llamadas por ubicación con un mapa interactivo fácil de usar. 9 informes nuevos:</p>- Calidad general<br>- Confiabilidad general<br>- RMC (Calificar mi llamada) general<br>- Calidad de conferencia<br>- Calidad P2P<br>- Confiabilidad de conferencias<br>- Confiabilidad P2P<br>- Conferencia RMC<br>- P2P RMC         |
|<strong>(¡Nuevo!)</strong> CQD Teams Utilization Report.pbit     | Muestra cómo los usuarios de su organización usan Teams y cuánto. Asegúrese de cargar los datos de creación para maximizar la experiencia de creación de informes. Para obtener más información, lea [Usar el informe de Power BI de CQD para ver el uso de Microsoft Teams.](CQD-teams-utilization-report.md)        |
|Informe.pbit de comentarios de usuario de CQD (Calificar mi llamada)     | Muestra Calificar los datos de mi llamada de una manera que puede usar fácilmente para ayudar a admitir las llamadas de su organización. Referencia cruzada con literales para identificar las oportunidades de educación de los usuarios finales.        |

> [!TIP]
> Una vez que haya configurado los informes de Power BI para los datos CQD, agrégrelos como una pestaña a un canal. Después de seleccionar **+** en un canal, seleccione **Power BI** y, a continuación, busque el informe. Para obtener más información, lea [Insertar informe con la pestaña Power BI para Teams.](/power-bi/service-embed-report-microsoft-teams) Recuerde que solo las personas con una licencia de Power BI y credenciales de administrador de CQD pueden obtener acceso a estos informes.


## <a name="related-topics"></a>Temas relacionados

[Dimensiones y medidas disponibles en el Panel de calidad de llamadas](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de la secuencia en el Panel de calidad de llamadas](stream-classification-in-call-quality-dashboard.md)

[Configurar el análisis de llamadas de Skype Empresarial](set-up-call-analytics.md)

[Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Análisis de llamadas y Panel de calidad de llamadas](./monitor-call-quality-qos.md)
