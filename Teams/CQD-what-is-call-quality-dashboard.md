---
title: ¿Qué es el panel de calidad de llamadas?
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Reporting
- ms.lync.lac.ToolsCallQualityDashboard
- seo-marvel-apr2020
description: Obtenga información sobre el Panel de calidad de llamadas (CQD) y cómo usarlo para ver informes sobre la calidad de las reuniones y las llamadas en Microsoft Teams.
ms.openlocfilehash: 3bc3c9dcd83e4ff95a07fbffb6f07da39d254cde
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2022
ms.locfileid: "66790075"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>¿Qué es el panel de calidad de llamadas?

El Panel de calidad de llamadas (CQD) [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) de Microsoft: muestra la calidad de las llamadas y reuniones, a **nivel de toda la organización**, para Microsoft Teams, Skype Empresarial Online y Skype Empresarial Server 2019. 

  
La última versión del CQD incluye una [fuente de datos casi en tiempo real (NRT](CQD-data-and-reports.md)), lo que significa que los registros de llamadas están disponibles en el CQD dentro de los 30 minutos del final de una llamada.

Siempre que el CQD incluya [datos de información identificable para el usuario final (EUII),](CQD-data-and-reports.md#euii-data) se administra de la misma manera que [la UEII en todo Microsoft 365](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).

El CQD está diseñado para ayudar a los administradores de Teams, Skype Empresarial administradores e ingenieros de red a supervisar la calidad de las llamadas y reuniones a nivel de toda la organización. Usará el CQD para ayudarle a **optimizar su red** para impulsar la calidad del rendimiento. Cuando necesite buscar información de llamadas y reuniones para un **usuario específico**, use los datos del CQD junto con [análisis de llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md) por usuario.

Por ejemplo, con el CQD, puede determinar que la mala calidad de llamada de un usuario (que observó con análisis de llamadas por usuario) se debe a un problema de red que también afecta a muchos otros usuarios. El CQD captura tanto la experiencia de llamada individual como la calidad general de las llamadas realizadas con Teams o Skype Empresarial. Con el CQD, los patrones generales pueden parecer aparentes, por lo que los ingenieros de red pueden realizar evaluaciones informadas de la calidad de las llamadas. El CQD proporciona informes de métricas de calidad de llamada que le proporcionan información sobre la calidad general de las llamadas, las transmisiones de servidor-cliente, las secuencias cliente-cliente y el [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252) de calidad de voz. 
  
![Captura de pantalla del panel de calidad de llamadas.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

En el CQD, le recomendamos que cargue información sobre compilaciones y puntos de conexión, que le permite usar informes de Location-Enhanced para analizar la calidad y la confiabilidad de las llamadas en el edificio de un usuario. Los datos se pueden evaluar para determinar si el problema está aislado para un solo usuario o afecta a un segmento más grande de usuarios. Para activar las vistas específicas del punto de conexión o de compilación en el CQD, un administrador debe [cargar la información de compilación o punto de conexión](CQD-upload-tenant-building-data.md) en la página **Carga de datos del inquilino** del CQD.

![Captura de pantalla de los informes de Location-Enhanced del panel de calidad de llamadas.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

No se pierda nuestro artículo [Administrar la calidad de las llamadas y las reuniones](quality-of-experience-review-guide.md) , que ofrece instrucciones detalladas para el administrador de Teams o el ingeniero de soporte técnico responsable de administrar la calidad del servicio en Teams.


## <a name="use-power-bi-to-analyze-cqd-data"></a>Usar Power BI para analizar datos del CQD

Novedades de enero de 2020: [Descargar plantillas de consulta de Power BI para el CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Plantillas personalizables de Power BI que puede usar para analizar e informar de los datos del CQD.

Lea [Usar Power BI para analizar datos del CQD](CQD-Power-BI-query-templates.md) para obtener más información.



## <a name="related-topics"></a>Temas relacionados

[Mejorar y supervisar la calidad de las llamadas para Teams](monitor-call-quality-qos.md)

[Configurar el panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Cargar datos de inquilinos y compilación](CQD-upload-tenant-building-data.md)

[Datos e informes del CQD](CQD-data-and-reports.md)

[Usar el CQD para administrar la calidad de llamadas y reuniones](quality-of-experience-review-guide.md)

[Dimensiones y medidas disponibles en el CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de transmisiones en el CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analizar datos del CQD](CQD-Power-BI-query-templates.md)


[Solución de problemas de Teams](/MicrosoftTeams/troubleshoot/teams)
