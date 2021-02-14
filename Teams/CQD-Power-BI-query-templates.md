---
title: Usar Power BI para analizar datos del CQD para Microsoft Teams
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
description: Use Power BI para analizar datos del CQD para Microsoft Teams.
ms.openlocfilehash: a06a3cb76cd778c132b3e8745b279035e875f16e
ms.sourcegitcommit: f122c078b6458754500f3cc68086d6ccfa62d183
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "49588333"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Usar Power BI para analizar datos del CQD para Microsoft Teams

Novedades de enero de 2020: Descargar plantillas de consulta [de Power BI para el CQD.](https://www.microsoft.com/download/details.aspx?id=102291) Plantillas personalizables de Power BI que puede usar para analizar e informar sobre los datos del CQD.

Si desea usar informes de panel de calidad de llamadas (CQD) en Teams, si prefiere usar Power BI para consultar e informar sobre los datos, descargue nuestras plantillas de Power BI del CQD. Al abrir las plantillas en Power BI, se le pedirá que inicie sesión con sus credenciales de administrador del CQD. Puede personalizar estas plantillas de consulta y distribuirlas a cualquier persona de su organización que tenga una licencia de Power BI y permisos de administrador del CQD.

Antes de poder usar estos archivos PBIT, debe instalar Power BI Connector para [Microsoft CQD](CQD-Power-BI-connector.md) con el archivo *MicrosoftCallQuality.pqx* que se incluye en la [descarga.](https://www.microsoft.com/download/details.aspx?id=102291) 

Asegúrese de que tiene el rol de [acceso del CQD correcto](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) para acceder a los informes de Power BI. 

|  |  |
|---------|---------|
|<strong>(Nuevo!)</strong> CQD Teams Operador automático & Call Queue Historical Report.pbit     |  Esta plantilla proporciona los tres informes siguientes:</p><li>Operador automático: muestra análisis de las llamadas entrantes a los operadores automáticos.</li><li>Cola de llamadas: muestra análisis de las llamadas entrantes en sus colas de llamadas.</li><li>Escala de tiempo del agente: muestra una vista de escala de tiempo de agentes que están activos en las llamadas de la cola de llamadas.</li><br>Para obtener más información, lea el Operador automático & histórico de la cola [de llamadas.](aa-cq-cqd-historical-reports.md)        |
|CQD Helpdesk Report.pbit     |Este informe, que integra los datos de creación y EUII, está diseñado para que pueda explorar en profundidad a un solo usuario y encontrar la causa raíz ascendente de la mala calidad de las llamadas para ese usuario (por ejemplo, el usuario se encuentra en un edificio que está experimentando problemas de red).         |
|Ubicación del CQD Mejorada Report.pbit     | Volver a convertir los informes de ubicación en el CQD SPD. Incluye 9 informes que proporcionan información sobre la calidad de las llamadas, la confiabilidad, la confiabilidad y la velocidad de las llamadas (RMC) con opciones de exploración adicionales mediante la creación o por usuario.  Asegúrese de cargar los datos de creación para maximizar la experiencia de creación de informes.        |
|CQD Mobile Device Report.pbit     | Proporciona información específicamente adaptada a los usuarios de dispositivos móviles, como la calidad de las llamadas, la confiabilidad y la tasa de llamada. Ver informes de redes móviles, redes WiFi e sistemas operativos móviles (Android, iOS).        |
|CQD PSTN Direct Routing Report.pbit     |Proporciona información específica para las llamadas RTC que se dirigen a través del enrutamiento directo. Para obtener más información, lea Usar el informe de enrutamiento directo [DE RTC del CQD.](CQD-PSTN-report.md)         |
|CQD Summary Report.pbit     |Mejores visualizaciones, presentaciones mejoradas, mayor densidad de información y fechas de rolling. Estos informes facilitan la identificación de valores atípicos. Explore en profundidad la calidad de las llamadas por ubicación con un mapa interactivo fácil de usar. 9 nuevos informes:</p>- Calidad general<br>- General de confiabilidad<br>- RMC (Calificar mi llamada) general<br>- Calidad de conferencia<br>- Calidad P2P<br>- Confiabilidad de conferencias<br>- Confiabilidad P2P<br>- Conferencia RMC<br>- P2P RMC         |
|<strong>(Nuevo!)</strong> CQD Teams Utilization Report.pbit     | Muestra cómo los usuarios de su organización usan Teams y cuánto. Asegúrese de cargar los datos de creación para maximizar la experiencia de creación de informes. Para obtener más información, [lea el informe Usar Power BI del CQD para ver el uso de Microsoft Teams.](CQD-teams-utilization-report.md)        |
|Informe.pbit de comentarios del usuario del CQD (Calificar mi llamada)     | Muestra los datos de Calificar mi llamada de una manera que puede usar fácilmente para ayudar a dar soporte a las llamadas para su organización. Referencia cruzada con los verbatims para identificar las oportunidades educativas de los usuarios finales.        |

> [!TIP]
> Una vez que haya configurado los informes de Power BI para los datos del CQD, agrégréslos como una pestaña a un canal. Después de seleccionar **+** en un canal, seleccione **Power BI** y, a continuación, busque el informe. Para obtener más información, [lea Insertar informe con la pestaña Power BI para Teams.](https://docs.microsoft.com/power-bi/service-embed-report-microsoft-teams) Recuerde que solo los usuarios con una licencia de Power BI y credenciales de administrador del CQD pueden acceder a estos informes.


## <a name="related-topics"></a>Temas relacionados

[Dimensiones y medidas disponibles en el Panel de calidad de llamadas](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de la secuencia en el Panel de calidad de llamadas](stream-classification-in-call-quality-dashboard.md)

[Configurar el análisis de llamadas de Skype Empresarial](set-up-call-analytics.md)

[Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Análisis de llamadas y Panel de calidad de llamadas](difference-between-call-analytics-and-call-quality-dashboard.md)
 
