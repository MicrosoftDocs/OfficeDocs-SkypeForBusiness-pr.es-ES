---
title: ¿Qué es el Panel de calidad de llamadas (CQD)?
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
description: Obtenga información sobre el Panel de calidad de llamadas (CQD) y cómo usarlo para ver informes sobre la calidad de las reuniones y las llamadas en Microsoft Teams.
ms.openlocfilehash: c78e427ef87f7485932fac207c10add71c8bf269
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094944"
---
# <a name="what-is-call-quality-dashboard-cqd"></a>¿Qué es el Panel de calidad de llamadas (CQD)?

El Panel de calidad de llamadas de Microsoft (CQD): muestra la calidad de las llamadas y reuniones, a nivel de toda la [https://cqd.teams.microsoft.com](https://cqd.teams.microsoft.com) organización, para Microsoft Teams, Skype Empresarial Online y Skype Empresarial Server 2019. 

  
La última versión de CQD incluye una fuente de datos en tiempo [casi real (NRT),](CQD-data-and-reports.md)lo que significa que los registros de llamadas están disponibles en CQD dentro de los 30 minutos adicionales al final de una llamada.

Siempre que CQD incluya datos de identificación del usuario final [(EUII),](CQD-data-and-reports.md#euii-data)se administra de la misma manera que EUII en [Microsoft 365.](/office365/Enterprise/office-365-data-retention-deletion-and-destruction-overview)

CQD está diseñado para ayudar a administradores de Teams, administradores de Skype Empresarial e ingenieros de red a supervisar la calidad de las llamadas y reuniones a nivel de toda la organización. Usará CQD para ayudarle a optimizar **la red para** mejorar la calidad del rendimiento. Cuando necesite buscar información de llamada y reunión para un usuario **específico,** use los datos de CQD junto con el análisis de [llamadas por usuario.](use-call-analytics-to-troubleshoot-poor-call-quality.md)

Por ejemplo, con CQD, puede determinar que la mala calidad de la llamada de un usuario (que observó con análisis de llamadas por usuario) se debe a un problema de red que también afecta a muchos otros usuarios. CQD captura tanto la experiencia de llamada individual como la calidad general de las llamadas realizadas con Teams o Skype Empresarial. Con CQD, los patrones generales pueden ser evidentes, por lo que los ingenieros de red pueden realizar evaluaciones fundamentadas de la calidad de las llamadas. CQD proporciona informes de métricas de calidad de llamadas que le proporcionan información sobre la calidad general de las llamadas, las transmisiones de cliente-servidor, las transmisiones cliente-cliente y el SLA de calidad [de voz.](https://go.microsoft.com/fwlink/p/?linkid=846252) 
  
![Captura de pantalla del panel de calidad de llamadas.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image3.png)

En CQD, le recomendamos que cargue información de creación y punto de conexión, lo que le permite usar Location-Enhanced Informes para analizar la calidad y la confiabilidad de las llamadas dentro del edificio de un usuario. Los datos se pueden evaluar para determinar si el problema está aislado para un solo usuario o afecta a un segmento más grande de usuarios. Para activar la creación o las vistas específicas del [](CQD-upload-tenant-building-data.md) punto de conexión en CQD, un administrador debe cargar información de creación o punto de conexión en la página Carga de datos del inquilino CQD. 

![Captura de pantalla del panel de calidad de Location-Enhanced llamadas.](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image4.png)

No se pierda [](quality-of-experience-review-guide.md) nuestro artículo Administrar la calidad de las llamadas y reuniones, que ofrece instrucciones detalladas para el administrador de Teams o el ingeniero de soporte técnico responsable de administrar la calidad del servicio en Teams.

## <a name="older-version-of-cqd-cqdlynccom"></a>Versión anterior de CQD (CQD.lync.com)

La versión actual de CQD ( reemplaza la https://CQD.Teams.microsoft.com) versión anterior de CQD ( https://CQD.lync.com) . Todavía puede usar CQD.lync.com (disponible en el Centro de administración de Skype Empresarial), pero a partir del 1 de julio de 2020, está usando los datos de CQD. Teams.microsoft.com. Desactivaremos el acceso a CQD.lync.com, por lo que deberías moverte a CQD. Teams.microsoft.com si aún no lo ha hecho.

> [!IMPORTANT]
> A partir del 1 de julio de 2020, ya no puede ver ni modificar los datos de creación o consulta desde el antiguo CQD (CQD.lync.com). Si aún no ha migrado estos datos desde CQD.lync.com y los sigue necesitando, registre un vale de soporte técnico.

## <a name="use-power-bi-to-analyze-cqd-data"></a>Usar Power BI para analizar datos CQD

Nuevo en enero de 2020: Descargar plantillas de consulta [de Power BI para CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) Plantillas de Power BI personalizables que puede usar para analizar e informar de los datos de CQD.

Lea [Usar Power BI para analizar datos CQD](CQD-Power-BI-query-templates.md) para obtener más información.



## <a name="related-topics"></a>Temas relacionados

[Mejorar y supervisar la calidad de las llamadas de Teams](monitor-call-quality-qos.md)

[Configurar el panel de calidad de llamadas (CQD)](turning-on-and-using-call-quality-dashboard.md)

[Cargar datos de inquilino y creación](CQD-upload-tenant-building-data.md)

[Datos e informes de CQD](CQD-data-and-reports.md)

[Usar CQD para administrar la calidad de las llamadas y las reuniones](quality-of-experience-review-guide.md)

[Dimensiones y medidas disponibles en CQD](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de secuencias en CQD](stream-classification-in-call-quality-dashboard.md)

[Usar Power BI para analizar datos CQD](CQD-Power-BI-query-templates.md)


[Solución de problemas de Teams](/MicrosoftTeams/troubleshoot/teams)