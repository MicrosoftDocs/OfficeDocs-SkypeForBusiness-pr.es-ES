---
title: Usar Power BI para analizar datos del CQD para Microsoft Teams
author: CarolynRowe
ms.author: crowe
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
ms.localizationpriority: medium
description: Use Power BI para analizar datos del CQD para Microsoft Teams.
ms.openlocfilehash: 45dca06abc3ee2a8980c3b963e22fbc8646e15a4
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270705"
---
# <a name="use-power-bi-to-analyze-cqd-data-for-microsoft-teams"></a>Usar Power BI para analizar datos del CQD para Microsoft Teams

Novedades de julio de 2022: La nueva plantilla de calidad de la experiencia (QER) se ha agregado a las [plantillas de consulta de Power BI para su descarga del CQD](https://www.microsoft.com/download/details.aspx?id=102291). El QER es una potente plantilla de informes que supercede las plantillas de consulta de Power BI del CQD original publicadas en 2020. Aunque las plantillas originales seguirán estando disponibles para fines de demostración, ya no son compatibles y recomendamos a los clientes que cambien a la plantilla QER, que seguirá recibiendo actualizaciones. Tenga en cuenta que esto no se aplica al operador automático de teams del CQD & informe de historial de la cola de llamadas.

Para los informes del Panel de calidad de llamadas (CQD) en Teams, si prefiere usar Power BI para consultar e informar de los datos, descargue nuestras plantillas de Power BI del CQD. Al abrir las plantillas en Power BI, se le pedirá que inicie sesión con sus credenciales de administrador del CQD. Puede personalizar estas plantillas de consulta y distribuirlas a cualquier persona de su organización que tenga una licencia de Power BI y permisos de administrador del CQD.

Antes de poder usar estos archivos PBIT, deberá [instalar Power BI Connector para el CQD de Microsoft](CQD-Power-BI-connector.md) con el archivo *MicrosoftCallQuality.pqx* incluido en la [descarga](https://www.microsoft.com/download/details.aspx?id=102291). 

Asegúrese de que tiene el [rol de acceso correcto del CQD](turning-on-and-using-call-quality-dashboard.md#assign-admin-roles-for-access-to-cqd) para obtener acceso a los informes de Power BI. 

|Pbit |Descripción |
|:----------|:---------|
|<strong>(¡Nuevo!)</strong> QER.pbit     |  La plantilla Informe de calidad de la experiencia (QER) permite a los clientes identificar de forma proactiva los problemas que afectan a la experiencia de llamadas y reuniones de Teams antes de que se escalen. También se proporcionan informes para permitir a los administradores responder rápidamente a problemas en escala y ayudar a responder a la pregunta "¿Qué ha ocurrido durante la reunión?".  Esta plantilla proporciona los siguientes informes:</p><li>Búsqueda: permite buscar por DIRECCIÓN URL de la reunión, Id. de conferencia, Subred o UPN.</li><li>Detalles del estado de la reunión: métricas detalladas para una sola reunión.</li><li>Detalles del estado del usuario: métricas detalladas para un solo usuario.</li><li>Estado de los medios: información general de alto nivel de los indicadores clave de salud (KHI) para el estado general de las reuniones y llamadas de inquilinos.</li><li>Configuración de medios: analice los errores de configuración de medios.</li><li>Confiabilidad de medios: analiza los problemas de confiabilidad de los medios.</li><li>Salud de audio/vídeo/uso compartido: revise los KHIs de nivel medio para el estado de audio, vídeo o uso compartido.</li><li>Detalles de estado de audio, vídeo y uso compartido: revise métricas detalladas sobre el estado del audio, el vídeo o el uso compartido.</li><li>VPN: revisa el impacto de la VPN en el estado de las reuniones. (VPN estimada o asignada)</li><li>10 informes principales: identifique áreas problemáticas en su inquilino.</li><li>Dailies – informe diario de los KHIs.</li><li>Uso: uso general de reuniones y llamadas.</li><li>Comentarios de usuario: revise los comentarios de las encuestas de usuario, también conocidos como Calificar mi llamada.</li><li>Transporte: identifique las redes que bloquean UDP.</li><li>Dispositivos: revisa el impacto de los dispositivos.</li><li>Clientes: revise las métricas centradas en el cliente.</li><li>Creación de datos: revise el archivo de datos de compilación en el CQD.</li><li>Estado de RTC y detalles del usuario: dos informes que proporcionan un resumen de alto nivel, así como el estado de los usuarios individuales para las llamadas basadas en RTC.</li><li>Métrica de red: dos informes que muestran detalles de la métrica de red sin procesar para vibración, pérdida de paquetes y latencia.</li> <br/> Esta plantilla supercede las plantillas en desuso como se indica a continuación.|
|Operador automático de Teams de CQD & informe de historial de la cola de llamadas.pbit     |  Esta plantilla proporciona los tres informes siguientes:</p><li>Operador automático: muestra análisis de llamadas que llegan a sus operadores automáticos.</li><li>Cola de llamadas: muestra análisis de llamadas que llegan a las colas de llamadas.</li><li>Línea de tiempo del agente: muestra una vista de escala de tiempo de agentes que están activos en las llamadas de la cola de llamadas.</li><br>Para obtener más información, lea [Operador automático & Informe de historial de la cola de llamadas](aa-cq-cqd-historical-reports.md). |
|Informe de utilización de equipos del CQD.pbit     | Muestra cómo los usuarios de su organización usan Teams y cuánto. Asegúrese de cargar los datos de creación para maximizar la experiencia de creación de informes. Para obtener más información, lea [Usar el informe power BI del CQD para ver el uso de Microsoft Teams](CQD-teams-utilization-report.md). |
|Informe de enrutamiento directo de RTC del CQD.pbit <br/> *(En desuso)*    | Plantilla de ejemplo que proporciona información específica para llamadas RTC que pasan por el enrutamiento directo. Para obtener más información, lea [Usar el informe de enrutamiento directo de RTC del CQD](CQD-PSTN-report.md). |
|Departamento de soporte técnico del CQD Report.pbit <br/> *(En desuso)*     |Integrando datos de construcción y EUII, esta plantilla muestra cómo crear un informe para permitir explorar a un solo usuario para encontrar la causa raíz ascendente de la mala calidad de llamada para ese usuario (por ejemplo, el usuario está en un edificio que está experimentando problemas de red). |
|Informe.pbit mejorado de ubicación del CQD <br/> *(En desuso)*     | En esta plantilla de ejemplo, se vuelven a imaginar los informes de ubicación del SPD del CQD. Incluye 9 informes, que proporcionan información de calidad de llamada, WiFi de edificio, confiabilidad y clasificación de mi llamada (RMC) con pasos adicionales por edificio o por usuario. Asegúrese de cargar los datos de creación para maximizar la experiencia de creación de informes. |
|Informe.pbit del dispositivo móvil del CQD <br/> *(En desuso)*     | Esta plantilla de ejemplo proporciona información específicamente adaptada a los usuarios de dispositivos móviles, como calidad de las llamadas, confiabilidad y clasificación de mi llamada. Ver informes de red móvil, red Wi-Fi e sistema operativo móvil (Android, iOS). |
|Informe de resumen del CQD.pbit <br/> *(En desuso)*    | Una demostración de cómo el CQD combinado con Power BI puede proporcionar mejores visualizaciones, una presentación mejorada, una mayor densidad de información y fechas de lanzamiento. Estos informes facilitan la identificación de valores atípicos. Profundice en la calidad de las llamadas por ubicación con un mapa interactivo fácil de usar. Nueve nuevos informes:</p>- Calidad general<br>- Confiabilidad general<br>- RMC (Calificar mi llamada) en general<br>- Calidad de la conferencia<br>- Calidad P2P<br>- Confiabilidad de conferencias<br>- Confiabilidad P2P<br>- Conferencia RMC<br>- P2P RMC         |
|Informe.pbit comentarios de usuarios del CQD (calificar mi llamada) <br/> *(En desuso)*    | Demostración de un informe de Power BI con los datos de Calificar mi llamada de una manera que pueda usar fácilmente para ayudar a admitir las llamadas para su organización. Referencias cruzadas con verbatims para identificar las oportunidades de educación del usuario final. |

> [!TIP]
> Una vez que haya configurado los informes de Power BI para los datos del CQD, agréguelos como una pestaña a un canal. Después de seleccionar **+** en un canal, seleccione **Power BI** y, a continuación, busque el informe. Para obtener más información, lea [Insertar informe con la pestaña Power BI para Teams](/power-bi/service-embed-report-microsoft-teams). Recuerde que solo los usuarios con una licencia de Power BI y credenciales de administrador del CQD pueden acceder a estos informes.

## <a name="related-topics"></a>Temas relacionados

[Dimensiones y medidas disponibles en el Panel de calidad de llamadas](dimensions-and-measures-available-in-call-quality-dashboard.md)

[Clasificación de la secuencia en el Panel de calidad de llamadas](stream-classification-in-call-quality-dashboard.md)

[Configurar el análisis de llamadas de Skype Empresarial](set-up-call-analytics.md)

[Usar el Análisis de llamadas para solucionar problemas de mala calidad en las llamadas](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[Análisis de llamadas y Panel de calidad de llamadas](./monitor-call-quality-qos.md)
