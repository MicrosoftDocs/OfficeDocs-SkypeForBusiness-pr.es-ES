---
title: ¿Qué es el panel de calidad de llamadas??
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, siunies, gageames
ms.topic: article
ms.assetid: 553fa13c-92d2-4d5c-a3d5-41a073cb047c
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Obtenga información sobre el panel de calidad de llamadas y cómo usarlo para ver informes sobre la calidad de las llamadas y reuniones en Microsoft Teams.
ms.openlocfilehash: 9ba1956533887314a9ffa7ad994cbb4c81ffe103
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583489"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>¿Qué es el panel de calidad de llamadas??

Panel de calidad de llamadas de Microsoft (CQD): muestra la calidad de las llamadas y reuniones, a nivel de toda la organización, para Microsoft Teams, Skype Empresarial Online y [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) Skype Empresarial Server 2019.  

  
La última versión del CQD cuenta con una fuente de datos en tiempo [casi real (NRT),](CQD-data-and-reports.md)lo que significa que los registros de llamadas están disponibles en el CQD en un plazo de 30 minutos desde el final de una llamada.

Siempre que el CQD incluya datos de identificación [(EUII)](CQD-data-and-reports.md#euii-data)del usuario final, se administra de la misma manera que [EUII en todo Microsoft 365.](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)

El CQD está diseñado para ayudar a los administradores de Teams, administradores de Skype Empresarial e ingenieros de red a supervisar la calidad de las llamadas y reuniones a nivel de toda la organización. Usará el CQD para ayudarle a **optimizar la red para** mejorar la calidad del rendimiento. Cuando necesite buscar información de llamadas y reuniones de un usuario **específico,** use los datos del CQD junto con el análisis de llamadas [por usuario.](use-call-analytics-to-troubleshoot-poor-call-quality.md)

Por ejemplo, con el CQD, puede determinar que la mala calidad de llamada de un usuario (lo que observó mediante análisis de llamadas por usuario) se debe a un problema de red que también afecta a muchos otros usuarios. El CQD captura tanto la experiencia de llamadas individuales como la calidad general de las llamadas realizadas con Teams o Skype Empresarial. Con el CQD, pueden ser evidentes los patrones generales, por lo que los ingenieros de red pueden realizar evaluaciones informadas de la calidad de la llamada. El CQD proporciona informes de métricas de calidad de llamadas que ofrecen información sobre la calidad general de las llamadas, las transmisiones de cliente-servidor, las transmisiones cliente-cliente y el SLA de calidad de [voz.](https://go.microsoft.com/fwlink/p/?linkid=846252) 
  
![Captura de pantalla del panel de calidad de llamadas.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

En el CQD, se recomienda cargar información de creación y punto de conexión, que le permite usar Location-Enhanced Reports para analizar la calidad y la confiabilidad de las llamadas en el edificio de un usuario. Los datos se pueden evaluar para determinar si el problema está aislado para un solo usuario o afecta a un segmento más grande de usuarios. Para activar la creación o las vistas específicas del [](CQD-upload-tenant-building-data.md) punto de conexión en el CQD, un administrador debe cargar la información de edificio o punto de conexión en la página Carga de datos del inquilino del CQD. 

![Captura de pantalla de los informes de calidad de Location-Enhanced llamadas.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

No se pierda [](quality-of-experience-review-guide.md) nuestro artículo Administrar la calidad de las llamadas y las reuniones, que ofrece instrucciones detalladas para el administrador de Teams o el ingeniero de soporte técnico responsable de administrar la calidad del servicio en Teams.

## <a name="older-version-of-cqd-cqdlynccom"></a>Versión anterior del CQD (CQD.lync.com)

La versión actual del CQD ( https://CQD.Teams.microsoft.com) está reemplazando la versión anterior del CQD ( https://CQD.lync.com) . Aún puede usar CQD.lync.com (disponible en el Centro de administración de Skype Empresarial), pero a partir del 1 de julio de 2020 está usando los datos del CQD. Teams.microsoft.com. Desactivaremos el acceso a CQD.lync.com, por lo que debes moverte al CQD. Teams.microsoft.com si aún no lo ha hecho.

> [!IMPORTANT]
> Desde el 1 de julio de 2020, ya no puede ver ni modificar los datos de creación o consulta desde el CQD antiguo (CQD.lync.com). Si aún no ha migrado estos datos de CQD.lync.com aún los necesita, inicie sesión en una vale de soporte.

## <a name="use-power-bi-to-analyze-cqd-data"></a>Usar Power BI para analizar datos del CQD

Novedades de enero de 2020: Descargar plantillas de consulta [de Power BI para el CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) Plantillas personalizables de Power BI que puede usar para analizar e informar sobre los datos del CQD.

Lea [Usar Power BI para analizar datos del CQD](CQD-Power-BI-query-templates.md) para obtener más información.



## <a name="related-topics"></a>Temas relacionados

[Mejorar y supervisar la calidad de las llamadas en Teams](monitor-call-quality-qos.md)

[Configurar el panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Cargar datos de inquilino y de edificio](CQD-upload-tenant-building-data.md)

[Informes y datos del CQD](CQD-data-and-reports.md)

[Usar el CQD para administrar la calidad de las llamadas y las reuniones](quality-of-experience-review-guide.md)

[Dimensiones y medidas disponibles en el CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de transmisiones en el CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analizar datos del CQD](CQD-Power-BI-query-templates.md)


[Solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)