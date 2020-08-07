---
title: ¿Qué es el panel de calidad de llamadas (CQD)?
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
description: Obtenga más información sobre el panel de calidad de llamadas (CQD) y cómo usarlo para ver informes de calidad de llamadas y reuniones en Microsoft Teams.
ms.openlocfilehash: 9ba1956533887314a9ffa7ad994cbb4c81ffe103
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583489"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>¿Qué es el panel de calidad de llamadas (CQD)?

El panel de calidad de llamadas de Microsoft (CQD) muestra la calidad de las [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) llamadas y reuniones, en **el nivel de toda la organización**, de Microsoft Teams, Skype empresarial online y skype empresarial Server 2019. 

  
La última versión del CQD incluye una [fuente de datos casi-real (NRT)](CQD-data-and-reports.md), lo que significa que los registros de llamadas están disponibles en el CQD en un plazo de 30 minutos a partir de la finalización de una llamada.

Dondequiera que el CQD incluya [datos de identificación de usuario final (EUII)](CQD-data-and-reports.md#euii-data), se administra de la misma manera que [EUII en Microsoft 365](https://docs.microsoft.com/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview).

El CQD está diseñado para ayudar a los administradores de equipos, administradores de Skype empresarial e ingenieros de redes a supervisar la calidad de las llamadas y la reunión en el nivel de toda la organización. Deberá usar el CQD para ayudarle a **optimizar su red** y así controlar la calidad de rendimiento. Si necesita buscar información sobre las llamadas y la reunión de un **usuario específico**, use los datos del CQD junto con el [análisis de llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)por usuario.

Por ejemplo, con el CQD, puede determinar que la mala calidad de las llamadas de un usuario (que usted ha observado mediante análisis de llamadas por usuario) se deba a un problema de red que también afecta a muchos otros usuarios. El CQD captura tanto la experiencia de llamada individual como la calidad general de las llamadas hechas con Teams o Skype empresarial. Con el CQD, los patrones generales pueden ser aparentes, por lo que los ingenieros de red pueden realizar evaluaciones informadas de la calidad de las llamadas. El CQD proporciona informes de métricas de calidad de llamadas que proporcionan una perspectiva de la calidad general de las llamadas, las secuencias de clientes de servidor, las secuencias de clientes cliente y los [SLA](https://go.microsoft.com/fwlink/p/?linkid=846252)de calidad de voz. 
  
![Captura de pantalla del panel de calidad de llamadas.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

En el CQD, le recomendamos que cargue la información de compilación y finalización, lo que le permite usar informes con ubicación mejorada para analizar la calidad de las llamadas y la confiabilidad dentro del edificio de un usuario. Los datos se pueden evaluar para determinar si el problema se aísla para un solo usuario o afecta a un segmento de usuarios más grande. Para activar las vistas de creación o específicas de extremos en el CQD, un administrador debe [cargar la información de compilación o de extremo](CQD-upload-tenant-building-data.md) en la página de carga de datos del **inquilino** de CQD.

![Captura de pantalla de la ubicación del panel de calidad de llamadas: informes mejorados.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

No pierdas nuestro artículo de [calidad de llamadas y reuniones de administración](quality-of-experience-review-guide.md) , que ofrece una guía detallada para el administrador o el ingeniero de soporte técnico de equipos responsable de administrar la calidad de los servicios en Teams.

## <a name="older-version-of-cqd-cqdlynccom"></a>Versión anterior del CQD (CQD.lync.com)

La versión actual del CQD ( https://CQD.Teams.microsoft.com) está reemplazando la versión anterior del CQD ( https://CQD.lync.com) . Puede seguir usando CQD.lync.com (disponible en el centro de administración de Skype empresarial) pero, a partir del 1 de julio de 2020, está usando los datos del CQD. Teams.microsoft.com. Desactivaremos el acceso a CQD.lync.com pronto, por lo que debes ir a CQD. Teams.microsoft.com si aún no lo has hecho.

> [!IMPORTANT]
> A partir del 1 de julio de 2020, ya no podrá ver ni modificar los datos de compilación o consulta del CQD anterior (CQD.lync.com). Si todavía no ha migrado los datos de CQD.lync.com y sigue siendo necesario, registre un vale de soporte técnico.

## <a name="use-power-bi-to-analyze-cqd-data"></a>Usar Power BI para analizar los datos del CQD

Novedades de enero de 2020: [Descargue las plantillas de consulta de Power BI para el CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Plantillas de Power BI personalizables que puede usar para analizar y notificar los datos de CQD.

Leer [use Power BI para analizar los datos del CQD](CQD-Power-BI-query-templates.md) y obtener más información.



## <a name="related-topics"></a>Temas relacionados

[Mejorar y supervisar la calidad de las llamadas de los equipos](monitor-call-quality-qos.md)

[Configurar el panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Cargar inquilino y datos de compilación](CQD-upload-tenant-building-data.md)

[Datos e informes del CQD](CQD-data-and-reports.md)

[Usar el CQD para administrar la calidad de las llamadas y reuniones](quality-of-experience-review-guide.md)

[Dimensiones y medidas disponibles en el CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de flujo en el CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analizar los datos del CQD](CQD-Power-BI-query-templates.md)


[Solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)