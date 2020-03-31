---
title: Usar Power BI para analizar los datos del CQD para Microsoft Teams
ms.author: lolaj
author: LolaJacobsen
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
ms.openlocfilehash: 374f0da0342e5fbd50a7a27b9dde49acf605a23d
ms.sourcegitcommit: f96d66d08a9d6993edbb9554738dc8236d901933
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/30/2020
ms.locfileid: "43053513"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Usar Power BI para analizar los datos del CQD para Microsoft Teams

Novedades de enero de 2020: [Descargue las plantillas de consulta de Power BI para el CQD](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). Plantillas de Power BI personalizables que puede usar para analizar y notificar los datos de CQD.

Para los informes de CQD en Teams, si prefiere usar Power BI para consultar y notificar sus datos, Descargue nuestras plantillas de Power BI para CQD. Al abrir las plantillas en Power BI, se le pedirá que inicie sesión con sus credenciales de administrador del CQD. Puede personalizar estas plantillas de consulta y distribuirlas a cualquier persona de su organización que tenga una licencia de Power BI y permisos de administrador del CQD.

Antes de poder usar estos archivos PBIX, tendrá que [instalar el conector de Power BI para Microsoft CQD](CQD-Power-BI-connector.md) con el archivo *MicrosoftCallQuality. PQx* incluido en la [descarga](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true). 


|  |  |
|---------|---------|
|Informe del Departamento de soporte técnico de CQD. pbix     |Integración de datos de compilación y EUII, este informe está diseñado para que pueda obtener detalles de un solo usuario y encontrar la causa de la baja de la calidad de las llamadas de baja calidad para ese usuario (por ejemplo, el usuario está en un edificio que experimenta problemas de red).         |
|Informe mejorado de ubicación de CQD. pbix     | Reimaginando informes de ubicación SPD de CQD. Incluye 9 informes, con la calidad de las llamadas, la creación de WiFi, la fiabilidad y la clasificación de mi llamada (RMC) información con otros detalles mediante la generación o por el usuario.        |
|Informe de dispositivos móviles CQD. pbix     | Proporciona información adaptada específicamente a usuarios de dispositivos móviles, como la calidad de las llamadas, la confiabilidad y la tarifa de mi llamada. Ver los informes de red móvil, red WiFi y sistema operativo móvil (Android, iOS).        |
|Informe de enrutamiento directo RTC de CQD. pbix     |Proporciona información específica de las llamadas RTC que pasan por el enrutamiento directo. Para obtener más información, lea [con el informe de enrutamiento directo de CQD de CQD](CQD-PSTN-report.md).         |
|Informe de Resumen de CQD. pbix     |Mejores visualizaciones, presentación mejorada, mayor densidad de la información y fechas de rodadura. Estos informes hacen que sea más fácil identificar los valores atípicos. Profundizar la calidad de las llamadas por ubicación con un mapa interactivo fácil de usar. 9 nuevos informes:</p>General de calidad<br>-Fiabilidad general<br>-RMC (calificar mi llamada) general<br>-Calidad de la Conferencia<br>-Calidad de P2P<br>-Fiabilidad de la Conferencia<br>-Fiabilidad P2P<br>-RMC de conferencia<br>-P2P RMC         |
|<strong>(¡ Nuevo!)</strong> Informe de uso de equipos CQD. pbix     | Muestra cómo los usuarios de su organización usan Teams y cuánto. Para obtener más información, lea [usar el informe de Power BI de CQD para ver la utilización de Microsoft Teams](CQD-teams-utilization-report.md).        |
|Comentarios del usuario del CQD (calificar mi llamada) Report. pbix     | Muestra la clasificación de los datos de la llamada de una manera fácil de usar para ayudar a admitir las llamadas de su organización. Referencia cruzada con literales para identificar las oportunidades de educación para el usuario final.        |

> [!TIP]
> Una vez que haya configurado los informes de Power BI para los datos del CQD, agréguelos como una pestaña a un canal. Después de seleccionar **+** un canal, seleccione **Power BI** y, a continuación, busque el informe. Recuerde que solo los usuarios con una licencia de Power BI y credenciales de administrador del CQD pueden acceder a estos informes.


## <a name="related-topics"></a>Temas relacionados

[Dimensiones y medidas disponibles en el Panel de calidad de llamadas](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de la secuencia en el Panel de calidad de llamadas](stream-classification-in-call-quality-dashboard.md)

[Configurar el análisis de llamadas de Skype Empresarial](set-up-call-analytics.md)

[Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Análisis de llamadas y Panel de calidad de llamadas](difference-between-call-analytics-and-call-quality-dashboard.md)
 