---
title: Uso del informe enrutamiento directo RTC del CQD
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: siunies, fan.fan
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: Use el informe Enrutamiento directo de llamadas (CQD) de Microsoft Teams para supervisar y solucionar problemas de llamadas RTC en Microsoft Teams.
ms.openlocfilehash: e4662d80dbba88c1049c7ef98569dae408ca9ba0
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583107"
---
# <a name="using-the-cqd-pstn-direct-routing-report"></a>Uso del informe enrutamiento directo RTC del CQD

Como novedad en marzo de 2020, hemos agregado un informe de enrutamiento directo de llamadas (CQD) de Microsoft Teams a nuestras plantillas de consulta descargables de Power BI para [el CQD.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/CQD-Power-BI-query-templates.zip?raw=true) 


El informe de enrutamiento directo RTC (CQD PSTN Direct Routing Report.pbit) del CQD le ayuda a comprender los patrones de uso y la calidad de los servicios RTC. Utilice este informe para supervisar el uso del servicio, la información sobre el controlador de borde de sesión (SBC), el servicio de telefonía, los parámetros de red y los detalles de la relación de eficacia de red. Esta información puede ayudarle a identificar problemas, incluido el motivo por el que se descartan llamadas. Por ejemplo, podrá ver cuándo se reduce el volumen o cuántas llamadas se ven afectadas y por qué motivo.


El informe de enrutamiento directo DE RTC del CQD tiene cuatro secciones:

  - [Introducción a RTC](#pstn-overview)

  - [Detalles del servicio](#service-details)

  - [Relación de eficacia de red](#network-effectiveness-ratio)

  - [Parámetros de red](#network-parameters)

## <a name="highlights"></a>Aspectos destacados

1. Analizar por tipo de llamada, SBC, país del autor de la llamada y destinatario de la llamada

   El informe enrutamiento directo RTC del CQD agrega las métricas de confiabilidad y uso de todos los TDC de su inquilino durante los últimos 7, 30 o 180 días (6 meses). Puede analizar datos por tipo de llamada, SBC, país del autor de la llamada y destinatario de la llamada. Si está interesado en un SBC o país en particular, podrá identificar los cambios de las tendencias en el intervalo de tiempo seleccionado.
   :::image type="content" source="media/CQD-PSTN-report8.png" alt-text="Captura de pantalla de los filtros disponibles en el informe enrutamiento directo de RTC del CQD":::
   
2. Realizar un seguimiento de las tendencias

    El análisis de tendencias es esencial al intentar comprender el uso del servicio y la confiabilidad. Las tendencias cada hora ofrecen un vistazo al rendimiento diario, lo que ayuda a identificar incidentes en tiempo real. Las tendencias diarias le permiten ver el estado del servicio desde una perspectiva a largo plazo. Es importante poder cambiar entre estos dos modos con la granularidad de datos adecuada. El informe enrutamiento directo RTC del CQD proporciona información general sobre las tendencias de 6 meses, las tendencias diarias de 7 y 30 días y las tendencias cada hora, para que pueda analizar el rendimiento en cada nivel.
    :::image type="content" source="media/CQD-PSTN-report9.png" alt-text="Captura de pantalla de los gráficos de tendencias en el informe enrutamiento directo de RTC del CQD":::

3. Explorar en profundidad hasta SBC o nivel de usuario

   Hemos mejorado la capacidad de exploración en muchas categorías de datos en el CQD, que le permite comprender rápidamente el uso o la distribución de confiabilidad en el nivel de usuario o SBC. Al explorar en profundidad, puede ver rápidamente los problemas de poinpoint y comprender el impacto real del usuario. Las características del informe de enrutamiento directo RTC del CQD detallan las métricas de detalle del servicio y relación de eficacia de red. Haga clic en el punto de datos que le interesa para explorar en profundidad los detalles de nivel de usuario o SBC.
   :::image type="content" source="media/CQD-PSTN-report10.png" alt-text="Captura de pantalla que muestra la funcionalidad de exploración en profundidad en un punto de datos":::


## <a name="pstn-overview"></a>Introducción a RTC

El informe de enrutamiento directo RTC del CQD proporciona la siguiente información relacionada con el estado general del servicio durante los últimos 180 días.
![Captura de pantalla: Informe CQD de RTC](media/CQD-PSTN-report1.png)

Por ejemplo, si está interesado en el uso general y el estado de todas las llamadas entrantes que pasan a través de SBC abc.bca.adatum.biz con EE. UU. como país interno:

| **Llamar** | **Descripción**                                                                                                                                                 |
| ------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 1            | Puedes usar los filtros de la parte superior para explorar en profundidad y seleccionar ByotIn como tipo de llamada, abc.bca.contoso.com controlador de la sesión y EE. UU. como país interno. |
| 2            | Tendencia de uso de los últimos 180 días. Puede encontrar el informe de detalles de uso en la página Detalles del servicio.                                                                     |
| 3            | Tendencia de retraso después del marcado, latencia, vibración y pérdida de paquetes de los últimos 180 días. Puede encontrar el informe detallado en la página Parámetros de red.                           |
| 4            | Tendencia de llamadas simultáneas y usuarios activos diarios en los últimos 180 días. Este gráfico puede ayudarle a comprender el volumen máximo del servicio.                            |
| 5            | El motivo principal de la finalización de la llamada ha afectado a la calidad del servicio de los últimos 180 días. Encontrará información sobre el estado del servicio en la página relación de eficacia de red (NER).                    |

## <a name="service-details"></a>Detalles del servicio

Esta página proporciona tendencias de uso del servicio por día y un desglose de los comentarios de los usuarios por ubicación geográfica.

  - **Llamadas de intento total:** Llamadas de intento total en ese intervalo de tiempo, incluidas las llamadas con éxito y con errores

  - **Total de llamadas conectadas:** Total de llamadas conectadas en ese intervalo de tiempo

  - **Minutos totales:** Uso total de minutos en ese intervalo de tiempo

  - **Usuarios activos diarios(DAU):** Recuento de usuarios activos diarios que realizaron al menos una llamada conectada en ese día

  - **Llamadas simultáneas:** Máximo de llamadas activas simultáneas en un minuto

  - **Comentarios del usuario:** La puntuación "Calificar mi llamada" proviene del usuario. 3-5 se considera una buena llamada. 1-2 se considera una mala llamada.

![Captura de pantalla: Informe CQD de RTC](media/CQD-PSTN-report2.png)

Por ejemplo:

1.  Si ve que la duración de llamada media se reduce a 0 a las 14/02/2020, primero puede comprobar si el volumen de la llamada tiene un aspecto normal y ver si hay una gran discrepancia entre el total de llamadas que se conectan y el total de llamadas de intento. A continuación, vaya a la página Relación de eficacia de red para invertir en los motivos de los errores de llamada.

2.  Si ve aumento de puntos rojos en el mapa de comentarios de los usuarios, puede ir a la página Relación de eficacia de red y parámetro de red para ver si hay alguna anómalo y podría elevar un vale con el Servicio de asistencia de MS.

## <a name="network-effectiveness-ratio"></a>Relación de eficacia de red

Esta es la misma métrica que aparece en el panel Estado general. Puede comprobar el número NER cada hora con los detalles de las llamadas afectadas para las dos direcciones de llamada (entrantes y salientes) en el gráfico de razones de finalización de llamada y relación de eficacia de red cada hora que se muestra a continuación.

  - **NER-** La capacidad (%) de una red para entregar llamadas midiendo el número de llamadas enviadas frente al número de llamadas que se han entregado a un destinatario.

  - **Código de respuesta SIP:** un código de respuesta entero de tres dígitos muestra el estado de la llamada.

  - **Código de respuesta de Microsoft:** un código de respuesta enviado desde el componente de Microsoft.

  - **Descripción:** la fase del motivo que corresponde al código de respuesta SIP y al código de respuesta de Microsoft.

  - **Número de llamadas afectadas:** el número total de llamadas que se han visto afectadas durante el intervalo de tiempo seleccionado.

> ![Captura de pantalla: Informe CQD de RTC](media/CQD-PSTN-report3.png)
> 
Por ejemplo:

![Captura de pantalla: Informe CQD de RTC](media/CQD-PSTN-report4.png)

Si el NER diario tiene una caída el 05/02/2020, puede hacer clic en la fecha y otros gráficos se acercarán a esa fecha específica.

![Captura de pantalla: Informe CQD de RTC](media/CQD-PSTN-report5.png)

En la tendencia de hora de porcentaje bueno de NER, puede encontrar que la baja ocurre alrededor de las 21:00. A continuación, haga clic de nuevo para ampliar a la hora 21 y compruebe los detalles de la llamada efectiva para ver cuántas llamadas no se realizaron en esa hora y cuáles son los motivos de la finalización de la llamada. Puede empezar con problemas personales en relación con los problemas de SBC o informar al Servicio de atención al cliente si el problema no está relacionado con la SBC.

## <a name="network-parameters"></a>Parámetros de red

Todos los parámetros de red se miden desde la interfaz de enrutamiento directo al controlador de borde de sesión. Para obtener información sobre los valores recomendados, vea Preparar la red de su organización para [Microsoft Teams](prepare-network.md)y mire los valores recomendados del perímetro del cliente hasta Microsoft Edge.

  - **Vibración: es** la medida en milisegundos de la variación del tiempo de retraso en la propagación de red que se calcula entre dos puntos de conexión mediante RTCP (el protocolo de control RTP).

  - **Pérdida de paquetes:** es una medida del paquete que no pudo llegar; se calcula entre dos puntos de conexión.

  - **Latencia:** (también conocido como tiempo de ida y vuelta) es el tiempo que tarda una señal en enviarse más el tiempo que tarda en recibirse la confirmación de dicha señal. Este retraso en el tiempo consiste en los tiempos de propagación entre los dos puntos de una señal.

> ![Captura de pantalla: Informe CQD de RTC](media/CQD-PSTN-report6.png)

Por ejemplo:

Si ve un pico en cualquiera de los cuatro gráficos (latencia, vibración, tasa de pérdida del paquete, retraso después del marcado) para una fecha específica, por ejemplo, latencia el 14/02/2020, haga clic en el punto de fecha. Y el gráfico de tendencia cada hora en la parte inferior se actualizará para mostrar el número cada hora. Puede revisar los sbcs o elevar un vale con el Servicio de asistencia de MS.

![Captura de pantalla: Informe CQD de RTC](media/CQD-PSTN-report7.png)



## <a name="related-topics"></a>Temas relacionados

[Usar Power BI para analizar datos del CQD para Microsoft Teams](CQD-PSTN-report.md)

[Solución de problemas de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)