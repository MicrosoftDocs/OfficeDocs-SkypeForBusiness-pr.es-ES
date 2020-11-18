---
title: Usar Power BI para analizar los datos del CQD para Microsoft Teams
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
description: Use Power BI para analizar los datos del CQD para Microsoft Teams.
ms.openlocfilehash: 4889428096209b9856d75caf11348ac036b4c7b0
ms.sourcegitcommit: b282acc1633c2d62bbff0ea77b6b647775ae6dfe
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/17/2020
ms.locfileid: "49085574"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Usar Power BI para analizar los datos del CQD para Microsoft Teams

Novedades de enero de 2020: [Descargue las plantillas de consulta de Power BI para el CQD](https://www.microsoft.com/download/details.aspx?id=102291). Plantillas de Power BI personalizables que puede usar para analizar y notificar los datos de CQD.

Para los informes del panel de calidad de llamadas (CQD) en Teams, si prefiere usar Power BI para consultar y notificar sus datos, Descargue nuestras plantillas de Power BI para CQD. Al abrir las plantillas en Power BI, se le pedirá que inicie sesión con sus credenciales de administrador del CQD. Puede personalizar estas plantillas de consulta y distribuirlas a cualquier persona de su organización que tenga una licencia de Power BI y permisos de administrador del CQD.

Antes de poder usar estos archivos de PBIT, tendrá que [instalar el conector de Power BI para Microsoft CQD](CQD-Power-BI-connector.md) con el archivo *MicrosoftCallQuality. PQx* incluido en la [descarga](https://www.microsoft.com/download/details.aspx?id=102291). 

Asegúrese de tener el rol de [acceso de CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) adecuado para obtener acceso a los informes de Power BI. 

|  |  |
|---------|---------|
|<strong>(¡ Nuevo!)</strong> Operador automático de equipos del CQD & informe histórico de la cola de llamadas. PBit     |  Esta plantilla proporciona los siguientes tres informes:</p><li>Operador automático: muestra análisis de llamadas entre los operadores automáticos.</li><li>Cola de llamadas: muestra análisis para las llamadas que llegan a las colas de llamadas.</li><li>Escala de tiempo del agente: muestra la vista de la escala de tiempo de los agentes que se activan en llamadas a colas de llamadas.</li><br>Para obtener más información, lea [usar el informe de Power BI de CQD para ver el operador automático & informe histórico de la cola de llamadas](CQD-teams-aa-cq-historical-report.md).        |
|Informe del Departamento de soporte técnico de CQD. PBit     |Integración de datos de compilación y EUII, este informe está diseñado para que pueda obtener detalles de un solo usuario y encontrar la causa de la baja de la calidad de las llamadas de baja calidad para ese usuario (por ejemplo, el usuario está en un edificio que experimenta problemas de red).         |
|Informe mejorado de la ubicación de CQD. PBit     | Reimaginando informes de ubicación SPD de CQD. Incluye 9 informes, con la calidad de las llamadas, la creación de WiFi, la fiabilidad y la clasificación de mi llamada (RMC) información con otros detalles mediante la generación o por el usuario.  Asegúrese de cargar los datos de compilación para maximizar su experiencia de generación de informes.        |
|Informe de dispositivo móvil de CQD. PBit     | Proporciona información adaptada específicamente a usuarios de dispositivos móviles, como la calidad de las llamadas, la confiabilidad y la tarifa de mi llamada. Ver los informes de red móvil, red WiFi y sistema operativo móvil (Android, iOS).        |
|Informe de enrutamiento directo RTC de CQD. PBit     |Proporciona información específica de las llamadas RTC que pasan por el enrutamiento directo. Para obtener más información, lea [con el informe de enrutamiento directo de CQD de CQD](CQD-PSTN-report.md).         |
|Informe de Resumen de CQD. PBit     |Mejores visualizaciones, presentación mejorada, mayor densidad de la información y fechas de rodadura. Estos informes hacen que sea más fácil identificar los valores atípicos. Profundizar la calidad de las llamadas por ubicación con un mapa interactivo fácil de usar. 9 nuevos informes:</p>General de calidad<br>-Fiabilidad general<br>-RMC (calificar mi llamada) general<br>-Calidad de la Conferencia<br>-Calidad de P2P<br>-Fiabilidad de la Conferencia<br>-Fiabilidad P2P<br>-RMC de conferencia<br>-P2P RMC         |
|<strong>(¡ Nuevo!)</strong> Informe de uso de equipos CQD. PBit     | Muestra cómo los usuarios de su organización usan Teams y cuánto. Asegúrese de cargar los datos de compilación para maximizar su experiencia de generación de informes. Para obtener más información, lea [usar el informe de Power BI de CQD para ver la utilización de Microsoft Teams](CQD-teams-utilization-report.md).        |
|Informe de comentarios del usuario del CQD (calificar mi llamada). PBit     | Muestra la clasificación de los datos de la llamada de una manera fácil de usar para ayudar a admitir las llamadas de su organización. Referencia cruzada con literales para identificar las oportunidades de educación para el usuario final.        |

> [!TIP]
> Una vez que haya configurado los informes de Power BI para los datos del CQD, agréguelos como una pestaña a un canal. Después de seleccionar **+** un canal, seleccione **Power BI** y, a continuación, busque el informe. Para obtener más información, lea [Informe de inserción con la pestaña Power BI para Teams](https://docs.microsoft.com/power-bi/service-embed-report-microsoft-teams). Recuerde que solo los usuarios con una licencia de Power BI y credenciales de administrador del CQD pueden acceder a estos informes.


## <a name="related-topics"></a>Temas relacionados

[Dimensiones y medidas disponibles en el Panel de calidad de llamadas](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de la secuencia en el Panel de calidad de llamadas](stream-classification-in-call-quality-dashboard.md)

[Configurar el análisis de llamadas de Skype Empresarial](set-up-call-analytics.md)

[Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Análisis de llamadas y Panel de calidad de llamadas](difference-between-call-analytics-and-call-quality-dashboard.md)
 
